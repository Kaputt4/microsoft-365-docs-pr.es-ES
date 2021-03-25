---
title: Incorporación de dispositivos Windows 10 a ATP de Microsoft Defender a través de la directiva de grupo
description: Usa la directiva de grupo para implementar el paquete de configuración en dispositivos Windows 10 para que se incorpore al servicio.
keywords: configurar dispositivos mediante directiva de grupo, administración de dispositivos, configurar dispositivos de Windows ATP, incorporar Microsoft Defender para dispositivos de punto de conexión, directiva de grupo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: fc4b17ef96e85d3bacd4e83c2de3f4bb7fbfa5c3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166178"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>Incorporación de dispositivos Windows 10 con la directiva de grupo 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- Directiva de grupo
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)


> [!NOTE]
> Para usar las actualizaciones de directiva de grupo (GP) para implementar el paquete, debes estar en Windows Server 2008 R2 o posterior.
> 
> Para Windows Server 2019, es posible que deba reemplazar NT AUTHORITY\Well-Known-System-Account por NT AUTHORITY\SYSTEM del archivo XML que crea la preferencia de directiva de grupo.

## <a name="onboard-devices-using-group-policy"></a>Incorporación de dispositivos mediante directiva de grupo

[![Imagen del PDF que muestra las distintas rutas de implementación](images/onboard-gp.png)](images/onboard-gp.png#lightbox)

Consulte el [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  o  [Visio para](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) ver las distintas rutas de acceso en la implementación de Defender para endpoint. 



1. Abra el archivo .zip del paquete de configuración de GP (*WindowsDefenderATPOnboardingPackage.zip*) que descargó del Asistente para incorporación de servicios. También puede obtener el paquete del Centro de seguridad [de Microsoft Defender:](https://securitycenter.windows.com/)
 
    1. En el panel de navegación, seleccione **Configuración**  >  **incorporación**.

    1. Selecciona Windows 10 como sistema operativo.
    
    1. En el **campo Método de** implementación, seleccione Directiva de **grupo**.
    
    1. Haga **clic en Descargar paquete** y guarde el archivo .zip.

2. Extrae el contenido del archivo .zip en una ubicación compartida de solo lectura a la que pueda tener acceso el dispositivo. Debe tener una carpeta denominada *OptionalParamsPolicy* y el archivo *WindowsDefenderATPOnboardingScript.cmd*.

3. Abra la [Consola de administración de directivas de](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) grupo (GPMC), haga clic con el botón secundario en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.

4. En el **Editor de administración de directivas de** grupo, vaya a Configuración **del** equipo , luego Preferencias **y,** a continuación, **Configuración del panel de control.**

5. Haga clic con el botón secundario en **Tareas programadas**, elija **Nuevo** y, a continuación, haga clic en Tarea inmediata **(al menos Windows 7).**

6. En la **ventana Tarea** que se abre, vaya a la **pestaña General.** En **Opciones de seguridad,** **haga clic en Cambiar usuario o grupo** y escriba SISTEMA y, a continuación, haga clic en Comprobar nombres **y, a** continuación, en **Aceptar**. NT AUTHORITY\SYSTEM aparece como la cuenta de usuario en la que se ejecutará la tarea.

7. Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla Ejecutar con **privilegios** más altos.

8. Vaya a la **pestaña Acciones** y haga clic **en Nuevo...** Asegúrese de **que Iniciar un programa** está seleccionado en el **campo** Acción. Escriba el nombre de archivo y la ubicación del archivo *compartido WindowsDefenderATPOnboardingScript.cmd.*

9. Haga **clic en Aceptar** y cierre las ventanas GPMC abiertas.

>[!TIP]
> Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que el dispositivo está correctamente incorporado al servicio. Para obtener más información, consulta [Ejecutar una prueba de detección en un dispositivo defender para endpoint](run-detection-test.md)recién incorporado.

## <a name="additional-defender-for-endpoint-configuration-settings"></a>Opciones adicionales de configuración de Defender para puntos de conexión
Para cada dispositivo, puedes especificar si se pueden recopilar muestras del dispositivo cuando se realiza una solicitud a través del Centro de seguridad de Microsoft Defender para enviar un archivo para un análisis profundo.

Puede usar la directiva de grupo (GP) para configurar opciones, como las opciones para el uso compartido de muestras usado en la característica de análisis profundo.

### <a name="configure-sample-collection-settings"></a>Configuración de la colección de ejemplo
1.  En el dispositivo de administración de GP, copie los siguientes archivos del paquete de configuración:

    - Copiar _AtpConfiguration.admx_ en _C: \\ \\ PolicyDefinitions de Windows_

    - Copiar _AtpConfiguration.adml_ en _C: \\ \\ PolicyDefinitions de Windows \\ en-US_

    Si usa un Almacén central para plantillas administrativas de directiva [de](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)grupo, copie los siguientes archivos del paquete de configuración:
    
    - Copiar _AtpConfiguration.admx_ en _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ Policies \\ PolicyDefinitions_

    - Copiar _AtpConfiguration.adml_ en _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ Policies \\ PolicyDefinitions \\ en-US_

2.  Abra la [Consola de administración de directivas de grupo,](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)haga clic con el botón secundario en el GPO que desea configurar y haga clic en **Editar**.

3.  En el **Editor de administración de directivas de** grupo, vaya a Configuración del **equipo**.

4.  Haga **clic en Directivas** y, a **continuación, en Plantillas administrativas.**

5.  Haga clic **en Componentes de Windows** **y, a continuación, Windows Defender ATP**.

6.  Elige habilitar o deshabilitar el uso compartido de muestras desde tus dispositivos.

>[!NOTE]
> Si no establece un valor, el valor predeterminado es habilitar la colección de muestras.


## <a name="other-recommended-configuration-settings"></a>Otras opciones de configuración recomendadas

### <a name="update-endpoint-protection-configuration"></a>Actualizar la configuración de protección de puntos de conexión

Después de configurar el script de incorporación, siga editando la misma directiva de grupo para agregar configuraciones de protección de extremos. Realice ediciones de directivas de grupo desde un sistema que ejecute Windows 10 o Server 2019 para asegurarse de que tiene todas las funcionalidades necesarias de Antivirus de Microsoft Defender. Es posible que deba cerrar y volver a abrir el objeto de directiva de grupo para registrar las opciones de configuración de Defender ATP.

Todas las directivas se encuentran en `Computer Configuration\Policies\Administrative Templates` .

**Ubicación de la directiva:** \Componentes de Windows\Windows Defender ATP

Policy | Configuración 
:---|:---
Enable\Disable Sample (colección)|   Habilitado: "Habilitar la colección de muestras en máquinas" activada

<br/>

**Ubicación de la directiva:**  \Componentes de Windows\Windows Defender Antivirus

Policy | Configuración 
:---|:---
Configurar la detección para aplicaciones potencialmente no deseadas | Enabled, Block

<br/>

**Ubicación de la directiva:** \Componentes de Windows\Windows Defender Antivirus\MAPS

Policy | Configuración 
:---|:---
Unirse a Microsoft MAPS | Mapas avanzados habilitados
Enviar ejemplos de archivos cuando sea necesario realizar análisis adicionales | Habilitado, Enviar muestras seguras

<br/>

**Ubicación de la directiva:** \Componentes de Windows\Windows Defender Antivirus\Protección en tiempo real

Policy | Configuración 
:---|:---
Desactivar la protección en tiempo real|Deshabilitado
Activar la supervisión del comportamiento|Habilitado
Examinar todos los archivos y datos adjuntos descargados|Habilitado
Supervisar la actividad de archivos y programas en el equipo|Habilitado

<br/>

**Ubicación de la directiva:**  \Componentes de Windows\Windows Defender Antivirus\Scan

Estas opciones configuran exámenes periódicos del extremo. Se recomienda realizar un examen rápido semanal, lo que permite el rendimiento.

Policy | Configuración 
:---|:---
Compruebe la inteligencia de seguridad de virus y spyware más reciente antes de ejecutar un examen programado |Habilitado


<br/>

**Ubicación de la directiva:** \Componentes de Windows\Windows Defender Antivirus\Windows Defender Protección contra vulnerabilidades de seguridad\Reducción de superficie de ataque

Obtener la lista actual de GUID de reducción de superficie de ataque de [Personalizar reglas de reducción de superficie de ataque](customize-attack-surface-reduction.md)

1. Abre la **directiva Configurar reducción de superficie de ataque.**

1. Seleccione **Habilitado**.

1. Seleccione el **botón Mostrar.**

1. Agregue cada GUID en el **campo Nombre de** valor con un valor de 2.

   Esto configurará cada uno solo para auditoría.

   ![Imagen de configuración de reducción de superficie de ataque](images/asr-guid.png)



Policy | Configuración 
:---|:---
Configurar acceso controlado a carpetas| Habilitado, modo auditoría



## <a name="offboard-devices-using-group-policy"></a>Dispositivos offboard con directiva de grupo
Por motivos de seguridad, el paquete usado para dispositivos offboard expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo. Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y de incorporación no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario esto provocará colisiones impredecibles.

1. Obtener el paquete de offboarding del Centro de [seguridad de Microsoft Defender:](https://securitycenter.windows.com/)

    1. En el panel de navegación, seleccione **Configuración**  >  **de offboarding**.

    1. Selecciona Windows 10 como sistema operativo.
    
    1. En el **campo Método de** implementación, seleccione Directiva de **grupo**.

    1. Haga **clic en Descargar paquete** y guarde el archivo .zip.

2. Extrae el contenido del archivo .zip en una ubicación compartida de solo lectura a la que pueda tener acceso el dispositivo. Debe tener un archivo denominado *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

3. Abra la [Consola de administración de directivas de](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) grupo (GPMC), haga clic con el botón secundario en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.

4. En el **Editor de administración de directivas de** grupo, vaya a Configuración del **equipo, preferencias** **y,** a continuación, **configuración del panel de control.**

5. Haga clic con el botón secundario **en Tareas programadas**, **elija Nuevo** y, a continuación, haga clic en **Tarea inmediata**.

6. En la **ventana Tarea** que se abre, vaya a la **pestaña General.** Elija la cuenta de usuario del SISTEMA local (BUILTIN\SYSTEM) en **Opciones de seguridad**.

7. Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla Ejecutar con **privilegios** más altos.

8. Vaya a la **pestaña Acciones** y haga clic **en Nuevo...**. Asegúrese de **que Iniciar un programa** está seleccionado en el **campo** Acción. Escriba el nombre de archivo y la ubicación del archivo  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* compartido.

9. Haga **clic en Aceptar** y cierre las ventanas GPMC abiertas.

> [!IMPORTANT]
> Offboarding hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que ha tenido, se conservarán durante un máximo de 6 meses.


## <a name="monitor-device-configuration"></a>Supervisar la configuración del dispositivo
Con la directiva de grupo no hay una opción para supervisar la implementación de directivas en los dispositivos. La supervisión se puede realizar directamente en el portal o mediante las distintas herramientas de implementación.

## <a name="monitor-devices-using-the-portal"></a>Supervisar dispositivos con el portal
1. Vaya al [Centro de seguridad de Microsoft Defender](https://securitycenter.windows.com/).
2. Haga clic **en Lista dispositivos**.
3. Compruebe que aparecen dispositivos.

> [!NOTE]
> Los dispositivos pueden tardar varios días en aparecer en la **lista Dispositivos.** Esto incluye el tiempo que tardan las directivas en distribuirse en el dispositivo, el tiempo que tarda antes de que el usuario inicie sesión y el tiempo que tarda el punto de conexión en iniciar la presentación de informes.


## <a name="related-topics"></a>Temas relacionados
- [Incorporación de dispositivos Windows 10 con Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles](configure-endpoints-mdm.md)
- [Incorporar dispositivos Windows 10 mediante un script local](configure-endpoints-script.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](configure-endpoints-vdi.md)
- [Ejecutar una prueba de detección en un Microsoft Defender recién incorporado para dispositivos de punto de conexión](run-detection-test.md)
- [Solucionar problemas de incorporación de puntos de conexión de Microsoft Defender](troubleshoot-onboarding.md)
