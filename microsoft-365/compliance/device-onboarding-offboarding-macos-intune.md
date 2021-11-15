---
title: Incorporar y incorporar dispositivos macOS en Microsoft 365 de cumplimiento con Microsoft Intune (versión preliminar)
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Obtenga información sobre cómo incorporar y incorporar dispositivos macOS en Microsoft 365 de cumplimiento con Microsoft Intune (versión preliminar)
ms.openlocfilehash: 82aa3909ac7829f07a797673300cc0061bb4feef
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2021
ms.locfileid: "60962716"
---
# <a name="onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-intune-preview"></a>Incorporar y retirar dispositivos macOS en soluciones de cumplimiento de Microsoft 365 mediante Intune (versión preliminar)

Puedes usar Intune para incorporar dispositivos macOS en Microsoft 365 de cumplimiento normativo.

> [!IMPORTANT]
> Use este procedimiento si ***no tiene*** Microsoft Defender para endpoint (MDE) implementado en sus dispositivos macOS

**Se aplica a:**

- [Prevención de pérdida de datos en punto de conexión en Microsoft 365 (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

## <a name="before-you-begin"></a>Antes de empezar

- Asegúrese de que los [dispositivos macOS están incorporados a Intune](/mem/intune/fundamentals/deployment-guide-platform-macos) y están inscritos en la [aplicación Portal de empresa .](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp) 
- Asegúrese de tener acceso al centro [de Microsoft Endpoint Manager .](https://endpoint.microsoft.com/#home)
- Esto admite macOS versión Catalina 10.15 y versiones posteriores.
- Cree los grupos de usuarios a los que va a asignar las actualizaciones de configuración.
- Instalar el explorador perimetral v95+ en los dispositivos macOS 


## <a name="onboard-macos-devices-into-microsoft-365-compliance-solutions-using-microsoft-intune"></a>Incorporar dispositivos macOS en Microsoft 365 de cumplimiento con Microsoft Intune

La incorporación de un dispositivo macOS a las soluciones de cumplimiento es un proceso de seis fases.

1. [Crear perfiles de configuración del sistema](#create-system-configuration-profiles)
1. [Obtener el paquete de incorporación de dispositivos](#get-the-device-onboarding-package)
1. [Implementar el paquete de incorporación](#deploy-the-onboarding-package)
1. [Habilitar la extensión del sistema](#enable-system-extension)
1. [Obtener el paquete de instalación](#get-the-installation-package)
1. [Implementar el paquete de instalación](#deploy-the-microsoft-dlp-installation-package)

### <a name="create-system-configuration-profiles"></a>Crear perfiles de configuración del sistema

1. Necesitará estos archivos para este procedimiento.

|archivo necesario para |source |
|---------|---------|
|Paquete de incorporación    |descargado desde el paquete de incorporación **del** portal de cumplimiento, nombre de *archivoDeviceComplianceOnboarding.xml* |
|accesibilidad |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
acceso en disco completo     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|Filer de red| [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig)]
|Extensiones del sistema |[sysext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/systext.mobileconfig)
|Preferencia de MDE     |[com.microsoft.wdav.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/com.microsoft.wdav.mobileconfig)|
|Preferencia MAU|[com.microsoft.autoupdate2.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/microsoft_auto_update/com.microsoft.autoupdate2.mobileconfig)|
|Paquete de instalación     |descargado del paquete de instalación del portal **de cumplimiento**, nombre de *\* archivo wdav.pkg*\* |

> [!TIP]
> Puede descargar los archivos *.mobileconfig* individualmente o [en un único archivo combinado](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) que contenga:
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
> - netfilter.mobileconfig
> - extensiones del sistema
>
>Si alguno de estos archivos individuales se actualiza, deberá descargar el archivo combinado de nuevo o el archivo actualizado individualmente.

<!--2. Copy this code and save it in a file named `com.microsoft.autoupdate2.xml`.

```xml
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Production</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```
-->

2. Abra el **centro Microsoft Endpoint Manager**  >  **perfiles**  >  **de configuración de dispositivos**.

1. Elegir: **Crear perfil** 

1. Elija:
    1. **Platform = macOS**
    1. **Tipo de perfil = Plantillas**
    1. **Nombre de plantilla = Personalizado**

1. Elija **Crear**

1. Elija un nombre para el perfil, como *AccessibilityformacOS* en este ejemplo. Elija **Siguiente**.

1. Elija el **archivo accessibility.mobileconfig** que descargó en el paso 1 como archivo de perfil de configuración.

1. Elegir **siguiente**

1. En la **pestaña Asignaciones,** agregue el grupo en el que desea implementar estas configuraciones y elija **Siguiente**.

1. Revise la configuración y elija **Crear** para implementar la configuración.

1. Repita los pasos del 3 al 11 para crear perfiles para:
    1. **archivo fulldisk.mobileconfig**
    1. **com.microsoft.autoupdate2.xml** archivo
    1. Archivo de **preferenciascom.microsoft.wdav.xml** MDE
        1. establecer el motor antivirus `passive mode`  =  `true` o `false` . Se `true` usa si solo se implementa DLP. Use o no asigne un valor si implementa DLP y `false` Microsoft Defender para endpoint (MDE).
    1. **netfilter.mobileconfig**
 
1. Abra   >  **perfiles de configuración de dispositivos,** debe ver los perfiles creados allí.

1. En la página Perfiles de configuración, elija el perfil que acaba de  crear, en este ejemplo *AccessibilityformacOS* y elija Estado del dispositivo para ver una lista de **dispositivos** y el estado de implementación del perfil de configuración.

### <a name="get-the-device-onboarding-package"></a>Obtener el paquete de incorporación de dispositivos

1. En **el Centro de** **cumplimiento, Configuración** Incorporación de  >  **dispositivos y** elija **Incorporación.**
 
1. Para **Seleccionar sistema operativo para iniciar el proceso de incorporación,** elija **macOS**.
 
1. Para **el método Deployment,** elija Administración de dispositivos **móviles/Microsoft Intune**.
 
1. Elija **Descargar paquete de incorporación**. Contiene el código de incorporación en el *DeviceComplianceOnboarding.xml* archivo.

### <a name="deploy-the-onboarding-package"></a>Implementar el paquete de incorporación

1. Abra el **centro Microsoft Endpoint Manager**  >  **perfiles**  >  **de configuración de dispositivos**.

1. Elija: **Crear perfil**. 

1. Elija:
    1. **Platform = macOS**
    1. **Tipo de perfil = Plantillas**
    1. **Nombre de plantilla = Personalizado**

1. Elija **Crear**

1. Elija un nombre para el perfil, como *OnboardingPackage* en este ejemplo. Elija **Siguiente**.

1. Elija el *DeviceComplianceOnboarding.xml* como archivo de perfil de configuración.

1. Elegir **siguiente**

1. En la **pestaña Asignaciones,** agregue el grupo en el que desea implementar estas configuraciones y elija **Siguiente**.

1. Revise la configuración y elija **Crear** para implementar la configuración.

### <a name="enable-system-extension"></a>Habilitar la extensión del sistema

1. En el **centro Microsoft Endpoint Manager seleccione** Crear perfil **en** **Perfiles de configuración**

1. Elija:
    1. **Platform = macOS**
    1. **Tipo de perfil = Plantillas**
    1. **Nombre de plantilla = Extensiones**

1. Elija **Crear**

1. En la **pestaña Conceptos** básicos, asigne un nombre a este nuevo perfil.

1. En la **pestaña Configuración,** expanda **Extensiones del sistema**.

1. En **Identificador de agrupación** e **identificador de equipo,** establezca estos valores

|Identificador de agrupación  |Identificador de equipo  |
|---------|---------|
|**com.microsoft.wdav.epsext**|**UBF8T346G9**|
|**com.microsoft.wdav.netext**|**UBF8T346G9**|


1. En la **pestaña Asignaciones,** agregue el grupo en el que desea implementar estas configuraciones y elija **Siguiente**.

1. Elija **Siguiente para** implementar la configuración.

### <a name="get-the-installation-package"></a>Obtener el paquete de instalación

1. En **el Centro de** **cumplimiento, Configuración** Incorporación de  >  **dispositivos y** elija **Incorporación.**
 
1. Para **Seleccionar sistema operativo para iniciar el proceso de incorporación,** elija **macOS**
 
1. Para **el método Deployment,** **elija Administración de dispositivos móviles/Microsoft Intune**
 
1. Elija **Descargar paquete de instalación**. Esto le dará el *archivo wdav.pkg.*

> [!IMPORTANT]
> Antes de poder implementar *wdav.pkg.* paquete a través de Intune, debe ser reformateado con las Herramientas de ajuste de aplicaciones de Intune para *Mac* en el formato *wdav.pkg.intunemac.*
 

### <a name="deploy-the-microsoft-dlp-installation-package"></a>Implementar el paquete de instalación de Dlp de Microsoft

1. Siga los procedimientos descritos en Cómo agregar aplicaciones de línea de negocio [(LOB)](/mem/intune/apps/lob-apps-macos) de macOS a Microsoft Intune para convertir el archivo *wdav.pkg* en el formato adecuado e implementarlo a través de Intune.

## <a name="offboard-macos-devices-using-intune"></a>Dispositivos macOS fuera de la pantalla con Intune

> [!NOTE]
> Offboarding hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que ha tenido, se conservarán hasta seis meses.

2. En **Microsoft Endpoint Manager,** abra **Perfiles** de configuración  >  **de dispositivos,** debe ver los perfiles creados allí.

1. En la **página Perfiles de configuración,** elija el *perfil wdav.pkg.intunemac.*

1. Elija **Estado del dispositivo** para ver una lista de dispositivos y el estado de implementación del perfil de configuración

1. Propiedades **y** **asignaciones abiertas**

1. Quite el grupo de la asignación. Esto desinstalará el paquete *wdav.pkg.intunemac* y se quitará el dispositivo macOS de las soluciones de cumplimiento.
