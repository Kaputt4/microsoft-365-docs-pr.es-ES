---
title: Antivirus de Microsoft Defender Infraestructura de escritorio virtual de implementación
description: Obtenga información sobre cómo implementar Antivirus de Microsoft Defender en un entorno de escritorio virtual para obtener el mejor equilibrio entre la protección y el rendimiento.
keywords: vdi, hyper-v, vm, máquina virtual, Windows Defender, antivirus, av, escritorio virtual, rds, escritorio remoto
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4ecd14e055646804d81e22da7c192988cf1e6f6f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275257"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Guía de implementación del Antivirus de Microsoft Defender en un entorno de infraestructura de escritorio virtual

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Además de las configuraciones de hardware o locales estándar, también puede usar Antivirus de Microsoft Defender en un entorno de escritorio remoto (RDS) o de infraestructura de escritorio virtual (VDI).

Consulte [Windows documentación de Escritorio virtual para](/azure/virtual-desktop) obtener más información sobre Escritorio remoto de Microsoft servicios y compatibilidad con VDI.

Para las máquinas virtuales basadas en Azure, [consulte Install Endpoint Protection in Azure Defender](/azure/security-center/security-center-install-endpoint-protection).

Con la capacidad de implementar fácilmente actualizaciones en máquinas virtuales que se ejecutan en VDI, hemos acortado esta guía para centrarse en cómo puede obtener actualizaciones en sus máquinas de forma rápida y sencilla. Ya no es necesario crear y sellar imágenes doradas periódicamente, ya que las actualizaciones se expanden en sus bits de componente en el servidor host y, a continuación, se descargan directamente en la máquina virtual cuando está activada.

En esta guía se describe cómo configurar las máquinas virtuales para obtener una protección y un rendimiento óptimos, incluido cómo:

- [Configurar un recurso compartido de archivos VDI dedicado para actualizaciones de inteligencia de seguridad](#set-up-a-dedicated-vdi-file-share)
- [Aleatorizar exámenes programados](#randomize-scheduled-scans)
- [Usar exámenes rápidos](#use-quick-scans)
- [Impedir notificaciones](#prevent-notifications)
- [Deshabilitar los exámenes para que no se produzcan después de cada actualización](#disable-scans-after-an-update)
- [Examinar máquinas o máquinas no actualizadas que han estado sin conexión durante un tiempo](#scan-vms-that-have-been-offline)
- [Aplicar exclusiones](#exclusions)

También puede descargar el documento técnico Antivirus de Microsoft Defender en [Infraestructura de escritorio virtual](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf), que analiza la nueva característica de actualización de inteligencia de seguridad compartida, junto con las pruebas de rendimiento y las instrucciones sobre cómo probar el rendimiento del antivirus en su propio VDI.

> [!IMPORTANT]
> Aunque la VDI se puede hospedar en Windows Server 2012 o Windows Server 2016, las máquinas virtuales (VM) deben ejecutar Windows 10, 1607 como mínimo, debido al aumento de las tecnologías y características de protección que no están disponibles en versiones anteriores de Windows.<br/>Hay mejoras de rendimiento y características en la forma en que Microsoft Defender AV funciona en máquinas virtuales en Windows 10 Insider Preview, compilación 18323 (y versiones posteriores). Identificaremos en esta guía si necesita usar una compilación de Insider Preview; si no se especifica, la versión mínima necesaria para la mejor protección y rendimiento es Windows 10 1607.

## <a name="set-up-a-dedicated-vdi-file-share"></a>Configurar un recurso compartido de archivos VDI dedicado

En Windows 10, versión 1903, presentamos la característica de inteligencia de seguridad compartida, que descarga el desempaquetar las actualizaciones de inteligencia de seguridad descargadas en un equipo host, lo que ahorra recursos anteriores de CPU, disco y memoria en máquinas individuales. Esta característica se ha backported y ahora funciona Windows 10 versión 1703 y versiones posteriores. Puede establecer esta característica con una directiva de grupo o PowerShell.

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a>Use la directiva de grupo para habilitar la característica de inteligencia de seguridad compartida:

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de grupo, haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, haga clic en **Editar**.

2. En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**

3. Haga clic **en Plantillas administrativas**.

4. Expanda el árbol para Windows **componentes Antivirus de Microsoft Defender** actualizaciones  >    >  **de inteligencia de seguridad**.

5. Haga doble clic en **Definir ubicación de inteligencia de seguridad para clientes VDI** y, a continuación, establezca la opción en **Habilitado**. Aparece automáticamente un campo.

6. Escriba `\\<sharedlocation\>\wdav-update` (para obtener ayuda con este valor, vea [Descargar y desempaquete](#download-and-unpackage-the-latest-updates)).

7. Haga clic en **Aceptar**.

8. Implemente el GPO en las máquinas virtuales que desea probar.

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a>Usar PowerShell para habilitar la característica de inteligencia de seguridad compartida

Use el siguiente cmdlet para habilitar la característica. Tendrá que insertar esto como normalmente insertaría directivas de configuración basadas en PowerShell en las máquinas virtuales:

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

Consulta la sección Descargar y desempaquete para saber cuál [](#download-and-unpackage-the-latest-updates) \<shared location\> será.

## <a name="download-and-unpackage-the-latest-updates"></a>Descargar y desempaquete las actualizaciones más recientes

Ahora puedes empezar a descargar e instalar nuevas actualizaciones. Hemos creado un script de PowerShell de ejemplo para usted a continuación. Este script es la forma más sencilla de descargar nuevas actualizaciones y prepararlas para las máquinas virtuales. A continuación, debe establecer el script para que se ejecute en un momento determinado en el equipo de administración mediante una tarea programada (o, si está familiarizado con el uso de scripts de PowerShell en Azure, Intune o SCCM, también podría usar esos scripts).

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

Puede establecer una tarea programada para que se ejecute una vez al día de modo que siempre que se descargue y desempaquete el paquete, las máquinas virtuales recibirán la nueva actualización. Se recomienda empezar por una vez al día, pero debe experimentar con aumentar o disminuir la frecuencia para comprender el impacto. 

Los paquetes de inteligencia de seguridad suelen publicarse una vez cada tres o cuatro horas. No se recomienda establecer una frecuencia inferior a cuatro horas porque aumentará la sobrecarga de red en el equipo de administración sin ningún beneficio.

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a>Establecer una tarea programada para ejecutar el script de PowerShell

1. En el equipo de administración, abra el menú Inicio y escriba **Programador de tareas**. Ábralo y seleccione **Crear tarea...** en el panel lateral.

2. Escriba el nombre como **Desempaquete de inteligencia de seguridad**. Vaya a la **pestaña Desencadenador.** Seleccione **Nuevo...** > **Diario** y seleccione **Aceptar**.

3. Vaya a la **pestaña** Acciones. Seleccione **Nuevo...** Escriba **PowerShell** en el **campo Programa/Script.** Escriba `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` en el campo Agregar **argumentos.** Seleccione **Aceptar**.

4. Puede elegir configurar opciones adicionales si lo desea.

5. Seleccione **Aceptar** para guardar la tarea programada.
 
Puede iniciar la actualización manualmente haciendo clic con el botón secundario en la tarea y haciendo clic en **Ejecutar**.

### <a name="download-and-unpackage-manually"></a>Descargar y desempaquete manualmente

Si prefiere hacer todo manualmente, esto es lo que debe hacer para replicar el comportamiento del script:

1. Cree una nueva carpeta en la raíz del sistema llamada para almacenar actualizaciones de `wdav_update` inteligencia, por ejemplo, cree la carpeta `c:\wdav_update` .

2. Crear una subcarpeta en *wdav_update* con un nombre GUID, como, por ejemplo, `{00000000-0000-0000-0000-000000000000}`

Este es un ejemplo: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`

   > [!NOTE]
   > En el script lo establecemos para que los últimos 12 dígitos del GUID sean el año, mes, día y hora en que se descargó el archivo para que se cree una nueva carpeta cada vez. Puede cambiar esto para que el archivo se descargue en la misma carpeta cada vez.

3. Descargue un paquete de inteligencia de seguridad [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  desde en la carpeta GUID. El archivo debe tener el nombre `mpam-fe.exe` .

4. Abra una ventana del símbolo del sistema cmd y vaya a la carpeta GUID que creó. Use el **comando de extracción /X** para extraer los archivos, por ejemplo `mpam-fe.exe /X` .

   > [!NOTE]
   > Las máquinas virtuales recogerán el paquete actualizado siempre que se cree una nueva carpeta GUID con un paquete de actualización extraído o siempre que se actualice una carpeta existente con un nuevo paquete extraído.

## <a name="randomize-scheduled-scans"></a>Aleatorizar exámenes programados

Los exámenes programados se ejecutan además de la protección y [el examen en tiempo real.](configure-real-time-protection-microsoft-defender-antivirus.md)

La hora de inicio del examen en sí se sigue basando en la directiva de examen programada (**ScheduleDay**, **ScheduleTime** y **ScheduleQuickScanTime**). La aleatorización hará Antivirus de Microsoft Defender iniciar un examen en cada equipo dentro de una ventana de 4 horas desde el tiempo establecido para el examen programado.

Consulte [Programar exámenes para](scheduled-catch-up-scans-microsoft-defender-antivirus.md) obtener otras opciones de configuración disponibles para exámenes programados.

## <a name="use-quick-scans"></a>Usar exámenes rápidos

Puede especificar el tipo de examen que se debe realizar durante un examen programado. Los exámenes rápidos son el enfoque preferido, ya que están diseñados para buscar en todos los lugares donde el malware debe residir para estar activo. El siguiente procedimiento describe cómo configurar exámenes rápidos mediante la directiva de grupo.

1. En el Editor de directivas de grupo, vaya a **Plantillas administrativas** Windows  >  **componentes**  >  **Antivirus de Microsoft Defender**  >  **Examinar**.

2. Seleccione **Especificar el tipo de examen que se usará para un examen programado** y, a continuación, edite la configuración de directiva.

3. Establezca la directiva en **Habilitado** y, a continuación, en **Opciones,** seleccione  **Examen rápido**.

4. Seleccione **Aceptar**. 

5. Implemente el objeto de directiva de grupo como lo haría normalmente.

## <a name="prevent-notifications"></a>Impedir notificaciones

A veces, Antivirus de Microsoft Defender notificaciones se pueden enviar o conservar en varias sesiones. Para minimizar este problema, puede bloquear la interfaz Antivirus de Microsoft Defender usuario. En el siguiente procedimiento se describe cómo suprimir las notificaciones con la directiva de grupo.

1. En el Editor de directivas de grupo, vaya **a Windows componentes Antivirus de Microsoft Defender** interfaz de  >    >  **cliente**.

2. Seleccione **Suprimir todas las notificaciones** y, a continuación, edite la configuración de directiva. 

3. Establezca la directiva en **Habilitado** y, a continuación, seleccione **Aceptar**.

4. Implemente el objeto de directiva de grupo como lo haría normalmente.

La supresión de notificaciones impide que las notificaciones Antivirus de Microsoft Defender se muestren en el Centro de acciones en Windows 10 cuando se realizan exámenes o se realizan acciones de corrección. Sin embargo, el equipo de operaciones de seguridad verá los resultados del examen en el Centro de seguridad de Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

> [!TIP]
> Para abrir el Centro de acciones en Windows 10, siga uno de los pasos siguientes:
> - En el extremo derecho de la barra de tareas, seleccione el icono centro de acciones.
> - Presione el Windows tecla de logotipo + A.
> - En un dispositivo con pantalla táctil, desliza el dedo desde el borde derecho de la pantalla.

## <a name="disable-scans-after-an-update"></a>Deshabilitar exámenes después de una actualización

Deshabilitar un examen después de una actualización impedirá que se produzca un examen después de recibir una actualización. Puedes aplicar esta configuración al crear la imagen base si también has ejecutado un examen rápido. De este modo, puede impedir que la máquina virtual recién actualizada vuelva a realizar un examen (como ya la ha examinado al crear la imagen base).

> [!IMPORTANT]
> La ejecución de exámenes después de una actualización ayudará a garantizar que las máquinas virtuales estén protegidas con las últimas actualizaciones de inteligencia de seguridad. Deshabilitar esta opción reducirá el nivel de protección de las máquinas virtuales y solo se debe usar al crear o implementar la imagen base por primera vez.

1. En el Editor de directivas de grupo, vaya **a Windows componentes Antivirus de Microsoft Defender** actualizaciones de inteligencia de  >    >  **seguridad**.

2. Seleccione **Activar el examen después de la actualización de inteligencia de seguridad** y, a continuación, edite la configuración de directiva.

3. Establezca la directiva en **Deshabilitado**.

4. Seleccione **Aceptar**.

5. Implemente el objeto de directiva de grupo como lo haría normalmente.

Esta directiva impide que un examen se ejecute inmediatamente después de una actualización.

## <a name="scan-vms-that-have-been-offline"></a>Examinar máquinas virtuales sin conexión

1. En el Editor de directivas de grupo, vaya a Windows **componentes Antivirus de Microsoft Defender**  >    >  **Scan**.

2. Seleccione **Activar el examen rápido de puesta al día** y, a continuación, edite la configuración de directiva.

3. Establezca la directiva en **Enabled**.

4. Seleccione **Aceptar**.

5. Implemente el objeto de directiva de grupo como suele hacer.

Esta directiva fuerza un examen si la máquina virtual ha perdido dos o más exámenes programados consecutivos.

## <a name="enable-headless-ui-mode"></a>Habilitar el modo de interfaz de usuario sin cabeza

1. En el Editor de directivas de grupo, vaya **a Windows componentes Antivirus de Microsoft Defender** interfaz de  >    >  **cliente**.

2. Selecciona **Habilitar el modo de interfaz de usuario sin** cabeza y edita la directiva.

3. Establezca la directiva en **Enabled**.

4. Haga clic en **Aceptar**.

5. Implemente el objeto de directiva de grupo como suele hacer.
 
Esta directiva oculta toda la interfaz Antivirus de Microsoft Defender usuario de los usuarios finales de la organización.

## <a name="exclusions"></a>Exclusiones

Las exclusiones se pueden agregar, quitar o personalizar para que se adapten a sus necesidades.

Para obtener más información, [vea Configure Antivirus de Microsoft Defender exclusiones en Windows Server](configure-exclusions-microsoft-defender-antivirus.md).

## <a name="additional-resources"></a>Recursos adicionales

- [Blog Community tech: Configuración de Antivirus de Microsoft Defender para máquinas VDI no persistentes](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [Foros de TechNet en Servicios de Escritorio remoto y VDI](https://social.technet.microsoft.com/Forums/windowsserver/en-US/home?forum=winserverTS)
- [Script de PowerShell SignatureDownloadCustomTask](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)