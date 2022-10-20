---
title: Guía de implementación Infraestructura de escritorio virtual antivirus de Microsoft Defender
description: Obtenga información sobre cómo implementar Microsoft Defender Antivirus en un entorno de escritorio virtual para obtener el mejor equilibrio entre la protección y el rendimiento.
keywords: vdi, hyper-v, vm, máquina virtual, Windows Defender, antivirus, av, escritorio virtual, rds, escritorio remoto
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: jesquive
manager: dansimp
ms.subservice: mde
ms.service: microsoft-365-security
ms.collection:
- m365-security
- tier2
- ContentEngagementFY23
search.appverid: met150
ms.openlocfilehash: b3f9ec32541fc77e1ac1191019cb589fb1829e43
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68634374"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Guía de implementación del Antivirus de Microsoft Defender en un entorno de infraestructura de escritorio virtual

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Además de las configuraciones locales o de hardware estándar, puede usar Microsoft Defender Antivirus en un entorno de escritorio remoto (RDS) o de infraestructura de escritorio virtual (VDI) no persistente. Con la capacidad de implementar fácilmente actualizaciones en máquinas virtuales que se ejecutan en VDIs, puede obtener actualizaciones en las máquinas de forma rápida y sencilla. Ya no es necesario crear y sellar imágenes doradas periódicamente, ya que las actualizaciones se expanden en sus bits de componente en el servidor host y, a continuación, se descargan directamente en la máquina virtual cuando está activada.

En esta guía se describe cómo configurar las máquinas virtuales para una protección y un rendimiento óptimos, incluido cómo:

- [Configuración de un recurso compartido de archivos VDI dedicado para las actualizaciones de inteligencia de seguridad](#set-up-a-dedicated-vdi-file-share)
- [Aleatorizar exámenes programados](#randomize-scheduled-scans)
- [Uso de exámenes rápidos](#use-quick-scans)
- [Impedir notificaciones](#prevent-notifications)
- [Deshabilitar que los exámenes se produzcan después de cada actualización](#disable-scans-after-an-update)
- [Examen de máquinas obsoletas o máquinas que han estado sin conexión durante un tiempo](#scan-vms-that-have-been-offline)
- [Aplicar exclusiones](#exclusions)

Para obtener más información sobre Escritorio remoto de Microsoft Services y compatibilidad con VDI, consulte [documentación de Azure Virtual Desktop](/azure/virtual-desktop).

Para las máquinas virtuales basadas en Azure, consulte [Instalación de Endpoint Protection en Microsoft Defender for Cloud](/azure/defender-for-cloud/endpoint-protection-recommendations-technical).

> [!IMPORTANT]
> Aunque la VDI se puede hospedar en Windows Server 2012 o Windows Server 2016, las máquinas virtuales (VM) deben ejecutarse Windows 10, 1607 como mínimo, debido al aumento de las tecnologías y características de protección que no están disponibles en versiones anteriores de Windows.
> Hay mejoras de rendimiento y características en la forma en que Microsoft Defender Antivirus funciona en máquinas virtuales en Windows 10 Insider Preview, compilación 18323 (y versiones posteriores). Identificaremos en esta guía si necesita usar una compilación de Insider Preview; Si no se especifica, la versión mínima necesaria para la mejor protección y rendimiento es Windows 10 1607.

## <a name="set-up-a-dedicated-vdi-file-share"></a>Configuración de un recurso compartido de archivos VDI dedicado

En Windows 10, versión 1903, se introdujo la característica de inteligencia de seguridad compartida, que descarga el desempaquetado de las actualizaciones de inteligencia de seguridad descargadas en una máquina host, lo que ahorra recursos anteriores de CPU, disco y memoria en máquinas individuales. Esta característica ha sido retroportada y ahora funciona en Windows 10 versión 1703 y posteriores. Puede establecer esta característica con un समूह नीति o PowerShell.

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a>Use समूह नीति para habilitar la característica de inteligencia de seguridad compartida:

1. En el equipo de administración de समूह नीति, abra la consola de administración de समूह नीति, haga clic con el botón derecho en el objeto de समूह नीति que desea configurar y, a continuación, seleccione **Editar**.

2. En el **Editor de administración de समूह नीति**, vaya a **Configuración del equipo**.

3. Seleccione **Plantillas administrativas**.

4. Expanda el árbol a **componentes** \> de Windows **Microsoft Defender Antivirus** \> **Security Intelligence Novedades**.

5. Haga doble clic en **Definir ubicación de inteligencia de seguridad para clientes VDI** y, a continuación, establezca la opción **en Habilitado**. Aparece automáticamente un campo.

6. Escriba `\\<sharedlocation\>\wdav-update` (para obtener ayuda con este valor, consulte [Descarga y despampaquete](#download-and-unpackage-the-latest-updates)).

7. Seleccione **Aceptar**.

8. Implemente el GPO en las máquinas virtuales que desea probar.

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a>Uso de PowerShell para habilitar la característica de inteligencia de seguridad compartida

Use el siguiente cmdlet para habilitar la característica. A continuación, deberá insertar la actualización, ya que normalmente insertaría directivas de configuración basadas en PowerShell en las máquinas virtuales:

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

Consulte la sección [Descargar y despaquetes](#download-and-unpackage-the-latest-updates) para ver cuál será.\<shared location\>

## <a name="download-and-unpackage-the-latest-updates"></a>Descarga y despaquetado de las actualizaciones más recientes

Ahora puede empezar a descargar e instalar nuevas actualizaciones. A continuación, hemos creado un script de PowerShell de ejemplo. Este script es la manera más sencilla de descargar nuevas actualizaciones y prepararlas para las máquinas virtuales. A continuación, debe establecer el script para que se ejecute en un momento determinado en la máquina de administración mediante una tarea programada (o, si está familiarizado con el uso de scripts de PowerShell en Azure, Intune o SCCM, también podría usar esos scripts).

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd /d $vdmpath & mpam-fe.exe /x"
```

Puede establecer que una tarea programada se ejecute una vez al día para que cada vez que se descargue y desempaquete el paquete, las máquinas virtuales reciban la nueva actualización.
Se recomienda comenzar con una vez al día, pero debe experimentar con aumentar o reducir la frecuencia para comprender el impacto.

Normalmente, los paquetes de inteligencia de seguridad se publican una vez cada tres o cuatro horas. No se recomienda establecer una frecuencia inferior a cuatro horas porque aumentará la sobrecarga de red en la máquina de administración sin ninguna ventaja.

También puede configurar el único servidor o equipo para capturar las actualizaciones en nombre de las máquinas virtuales a intervalos y colocarlas en el recurso compartido de archivos para su consumo.
Esto es posible cuando los dispositivos tienen los permisos de recurso compartido y NTFS para el acceso de lectura al recurso compartido para que puedan tomar las actualizaciones. Para hacerlo:

 1. Cree un recurso compartido de archivos SMB/CIFS. 
 
 2. Use el ejemplo siguiente para crear un recurso compartido de archivos con los siguientes permisos de recurso compartido.

    ```PowerShell
    PS c:\> Get-SmbShareAccess -Name mdatp$

    Name   ScopeName AccountName AccessControlType AccessRight
    ----   --------- ----------- ----------------- -----------
    mdatp$ *         Everyone    Allow             Read
    ```
   
    > [!NOTE]
    > Se agrega un permiso NTFS para **usuarios autenticados:Read:**. 

    En este ejemplo, el recurso compartido de archivos es:

    `\\fileserver.fqdn\mdatp$\wdav-update`

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a>Establecer una tarea programada para ejecutar el script de PowerShell

1. En la máquina de administración, abra el menú Inicio y escriba **Programador de tareas**. Ábralo y seleccione **Crear tarea...** en el panel lateral.

2. Escriba el nombre como **Desempaquete de inteligencia de seguridad**. Vaya a la pestaña **Desencadenador** . Seleccione **Nuevo...** \> **Todos los días** y seleccione **Aceptar**.

3. Vaya a la pestaña **Acciones** . Seleccione **Nuevo...** Escriba **PowerShell** en el campo **Programa o script** . Escriba `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` en el campo **Agregar argumentos** . Seleccione **Aceptar**.

4. Si lo desea, puede optar por configurar más opciones.

5. Seleccione **Aceptar** para guardar la tarea programada.

Puede iniciar la actualización manualmente haciendo clic con el botón derecho en la tarea y haciendo clic en **Ejecutar**.

### <a name="download-and-unpackage-manually"></a>Descargar y desempaquetar manualmente

Si prefiere hacer todo manualmente, esto es lo que debe hacer para replicar el comportamiento del script:

1. Cree una nueva carpeta en la raíz del sistema llamada `wdav_update` para almacenar las actualizaciones de inteligencia, por ejemplo, cree la carpeta `c:\wdav_update`.

2. Cree una subcarpeta en *wdav_update* con un nombre GUID, como `{00000000-0000-0000-0000-000000000000}`

   Este es un ejemplo: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`

   > [!NOTE]
   > En el script lo establecemos para que los últimos 12 dígitos del GUID sean el año, el mes, el día y la hora en que se descargó el archivo para que se cree una nueva carpeta cada vez. Puede cambiar esto para que el archivo se descargue en la misma carpeta cada vez.

3. Descargue un paquete de inteligencia de seguridad desde [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  en la carpeta GUID. El archivo debe llamarse `mpam-fe.exe`.

4. Abra una ventana del símbolo del sistema de cmd y vaya a la carpeta GUID que ha creado. Use el comando de extracción **/X** para extraer los archivos, por ejemplo `mpam-fe.exe /X`.

   > [!NOTE]
   > Las máquinas virtuales recogerán el paquete actualizado cada vez que se cree una nueva carpeta GUID con un paquete de actualización extraído o siempre que se actualice una carpeta existente con un nuevo paquete extraído.

## <a name="randomize-scheduled-scans"></a>Aleatorizar exámenes programados

Los exámenes programados se ejecutan además [de la protección y el examen en tiempo real](configure-real-time-protection-microsoft-defender-antivirus.md).

La hora de inicio del examen en sí sigue basándose en la directiva de examen programada (**ScheduleDay**, **ScheduleTime** y **ScheduleQuickScanTime**). La aleatoriedad hará que Microsoft Defender Antivirus inicie un examen en cada equipo dentro de un período de cuatro horas a partir del tiempo establecido para el examen programado.

Consulte [Programación de exámenes](scheduled-catch-up-scans-microsoft-defender-antivirus.md) para ver otras opciones de configuración disponibles para los exámenes programados.

## <a name="use-quick-scans"></a>Uso de exámenes rápidos

Puede especificar el tipo de examen que se debe realizar durante un examen programado. Los exámenes rápidos son el enfoque preferido, ya que están diseñados para buscar en todos los lugares donde el malware necesita residir para estar activo. En el procedimiento siguiente se describe cómo configurar exámenes rápidos mediante समूह नीति.

1. En el Editor de समूह नीति, vaya a **Plantillas** \> administrativas **Componentes** \> de Windows **Microsoft Defender Examen antivirus**\>.

2. Seleccione **Especificar el tipo de examen que se va a usar para un examen programado** y, a continuación, edite la configuración de directiva.

3. Establezca la directiva **en Habilitado** y, a continuación, en **Opciones**, seleccione  **Examen rápido**.

4. Seleccione **Aceptar**.

5. Implemente el objeto de directiva de grupo como lo haría normalmente.

## <a name="prevent-notifications"></a>Impedir notificaciones

En ocasiones, Microsoft Defender notificaciones antivirus pueden enviarse o conservarse en varias sesiones. Para minimizar este problema, puede bloquear la interfaz de usuario Microsoft Defender Antivirus. En el procedimiento siguiente se describe cómo suprimir las notificaciones con समूह नीति.

1. En el Editor de समूह नीति, vaya a **Componentes** \> de Windows Microsoft Defender **Interfaz de cliente** **antivirus**\>.

2. Seleccione **Suprimir todas las notificaciones** y, a continuación, edite la configuración de la directiva.

3. Establezca la directiva **en Habilitado** y, a continuación, seleccione **Aceptar**.

4. Implemente el objeto de directiva de grupo como lo haría normalmente.

La supresión de notificaciones impide que las notificaciones de Microsoft Defender Antivirus aparezcan en el Centro de acciones en Windows 10 cuando se realizan exámenes o se realizan acciones de corrección. Sin embargo, el equipo de operaciones de seguridad verá los resultados del examen mientras se detectó y detuvo el ataque; las alertas, como una "alerta de acceso inicial", se desencadenan y aparecen en el [portal de Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender).

> [!TIP]
> Para abrir el Centro de acciones en Windows 10 o Windows 11, realice uno de los pasos siguientes:
> - En el extremo derecho de la barra de tareas, seleccione el icono del Centro de acciones.
> - Presione el botón de tecla del logotipo de Windows + A.
> - En un dispositivo con pantalla táctil, desliza el dedo desde el borde derecho de la pantalla.

## <a name="disable-scans-after-an-update"></a>Deshabilitar exámenes después de una actualización

Deshabilitar un examen después de una actualización impedirá que se produzca un examen después de recibir una actualización. Puede aplicar esta configuración al crear la imagen base si también ha ejecutado un examen rápido. De este modo, puede evitar que la máquina virtual recién actualizada vuelva a realizar un examen (como ya lo ha examinado al crear la imagen base).

> [!IMPORTANT]
> La ejecución de exámenes después de una actualización ayudará a garantizar que las máquinas virtuales estén protegidas con las últimas actualizaciones de Inteligencia de seguridad. Deshabilitar esta opción reducirá el nivel de protección de las máquinas virtuales y solo se debe usar al crear o implementar la imagen base por primera vez.

1. En el Editor de समूह नीति, vaya a **Componentes** \> de Windows **Microsoft Defender Antivirus** \> **Security Intelligence Novedades**.

2. Seleccione **Activar examen después** de la actualización de inteligencia de seguridad y, a continuación, edite la configuración de directiva.

3. Establezca la directiva **en Deshabilitada**.

4. Seleccione **Aceptar**.

5. Implemente el objeto de directiva de grupo como lo haría normalmente.

Esta directiva impide que un examen se ejecute inmediatamente después de una actualización.

## <a name="disable-the-scanonlyifidle-option"></a>Deshabilitar la `ScanOnlyIfIdle` opción

Use el siguiente cmdlet para detener un examen rápido o programado cada vez que el dispositivo esté inactivo si está en modo pasivo.

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled $false
```

También puede deshabilitar la `ScanOnlyIfIdle` opción en Microsoft Defender Antivirus mediante la configuración a través de la directiva de grupo local o de dominio. Esto evita la contención significativa de LA CPU en entornos de alta densidad.

Para obtener más información, vea [Iniciar el examen programado solo cuando el equipo está encendido, pero no en uso](https://admx.help/?Category=SystemCenterEndpointProtection&Policy=Microsoft.Policies.Antimalware::scan_scanonlyifidle).

## <a name="scan-vms-that-have-been-offline"></a>Examen de máquinas virtuales sin conexión

1. En el Editor de समूह नीति, vaya a **Componentes** \> de Windows **Microsoft Defender Antivirus** \> **Scan**.

2. Seleccione **Activar examen rápido de puesta al día** y, a continuación, edite la configuración de directiva.

3. Establezca la directiva **en Habilitado**.

4. Seleccione **Aceptar**.

5. Implemente el objeto समूह नीति como suele hacer.

Esta directiva fuerza un examen si la máquina virtual ha perdido dos o más exámenes programados consecutivos.

## <a name="enable-headless-ui-mode"></a>Habilitación del modo de interfaz de usuario sin cabeza

1. En el Editor de समूह नीति, vaya a **Componentes** \> de Windows Microsoft Defender **Interfaz de cliente** **antivirus**\>.

2. Seleccione **Habilitar modo de interfaz de usuario sin cabeza** y edite la directiva.

3. Establezca la directiva **en Habilitado**.

4. Seleccione **Aceptar**.

5. Implemente el objeto समूह नीति como suele hacer.

Esta directiva oculta toda la interfaz de usuario Microsoft Defender Antivirus a los usuarios finales de la organización.

## <a name="exclusions"></a>Exclusiones

Las exclusiones se pueden agregar, quitar o personalizar para satisfacer sus necesidades.

Para obtener más información, vea [Configurar exclusiones de antivirus de Microsoft Defender en Windows Server](configure-exclusions-microsoft-defender-antivirus.md).

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)

## <a name="additional-resources"></a>Recursos adicionales

- [Blog de tech community: Configuración de Microsoft Defender Antivirus para máquinas VDI no persistentes](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [Foros de TechNet en Servicios de Escritorio remoto y VDI](https://social.technet.microsoft.com/Forums/windowsserver/home?forum=winserverTS)
- [Script de PowerShell SignatureDownloadCustomTask](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)
