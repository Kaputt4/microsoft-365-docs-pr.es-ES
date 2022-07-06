---
title: Incorporación y descarga de dispositivos macOS en soluciones de Microsoft Purview mediante Microsoft Intune
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Obtenga información sobre cómo incorporar y desconectar dispositivos macOS en soluciones de Microsoft Purview mediante Microsoft Intune
ms.openlocfilehash: e5cc3ff25895f3eb7557566eb8a38722a1aee35f
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66632363"
---
# <a name="onboard-and-offboard-macos-devices-into-microsoft-purview-solutions-using-intune"></a>Incorporar y desactivar dispositivos macOS en soluciones de Microsoft Purview mediante Intune

Puede usar Intune para incorporar dispositivos macOS a las soluciones de Microsoft Purview.

> [!IMPORTANT]
> Use este procedimiento si ***no*** tiene Microsoft Defender para punto de conexión (MDE) implementados en los dispositivos macOS.

**Se aplica a:**

- [Prevención de perdida de datos en el punto de conexión (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md)

## <a name="before-you-begin"></a>Antes de empezar

- Asegúrese de que [los dispositivos macOS están incorporados a Intune](/mem/intune/fundamentals/deployment-guide-platform-macos) y están inscritos en la [aplicación de Portal de empresa](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp). 
- Asegúrese de que tiene acceso al [Centro de Endpoint Manager de Microsoft](https://endpoint.microsoft.com/#home).
- Esto es compatible con la versión de macOS Catalina 10.15 y versiones posteriores.
- Cree los grupos de usuarios a los que va a asignar las actualizaciones de configuración.
- Instalar el explorador v95+ Edge en los dispositivos macOS 


## <a name="onboard-macos-devices-into-microsoft-purview-solutions-using-microsoft-intune"></a>Incorporación de dispositivos macOS a soluciones de Microsoft Purview mediante Microsoft Intune

La incorporación de un dispositivo macOS a las soluciones de cumplimiento es un proceso de seis fases.

1. [Creación de perfiles de configuración del sistema](#create-system-configuration-profiles)
1. [Obtención del paquete de incorporación de dispositivos](#get-the-device-onboarding-package)
1. [Implementación del paquete de incorporación](#deploy-the-onboarding-package)
1. [Habilitación de la extensión del sistema](#enable-system-extension)
1. [Obtención del paquete de instalación](#get-the-installation-package)
1. [Implementación del paquete de instalación](#deploy-the-microsoft-dlp-installation-package)

### <a name="create-system-configuration-profiles"></a>Creación de perfiles de configuración del sistema

1. Necesitará estos archivos para este procedimiento.

|archivo necesario para |source |
|---------|---------|
|Paquete de incorporación    |descargado del **paquete de incorporación** del portal de cumplimiento, nombre de archivo *DeviceComplianceOnboarding.xml* |
|Accesibilidad |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
acceso completo al disco     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|Filer de red| [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig)]
|Extensiones del sistema |[sysext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/sysext.mobileconfig)
|Preferencia de MDE     |[com.microsoft.wdav.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/com.microsoft.wdav.mobileconfig)|
|Preferencias de MAU|[com.microsoft.autoupdate2.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/microsoft_auto_update/com.microsoft.autoupdate2.mobileconfig)|
|Paquete de instalación     |descargado desde el **paquete de instalación** del portal de cumplimiento, nombre *\*de archivo wdav.pkg*\* |

> [!TIP]
> Puede descargar los archivos *.mobileconfig* individualmente o en [un único archivo combinado](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) que contenga:
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

2. Abra los **perfiles de configuración** de **dispositivos** >  del **centro** >  de Microsoft Endpoint Manager.

1. Elegir: **Crear perfil** 

1. Elegir:
    1. **Plataforma = macOS**
    1. **Tipo de perfil = Plantillas**
    1. **Nombre de plantilla = Personalizado**

1. Elija **Crear**

1. Elija un nombre para el perfil, como *AccessibilityformacOS* en este ejemplo. Elija **Siguiente**.

1. Elija el archivo **accessibility.mobileconfig** que descargó en el paso 1 como archivo de perfil de configuración.

1. Elija **Siguiente**

1. En la pestaña **Asignaciones** , agregue el grupo en el que desea implementar estas configuraciones y elija **Siguiente**.

1. Revise la configuración y elija **Crear** para implementar la configuración.

1. Repita los pasos del 3 al 11 para crear perfiles para:
    1. **archivo fulldisk.mobileconfig**
    1. **archivocom.microsoft.autoupdate2.xml**
    1. Archivo **decom.microsoft.wdav.xml** de preferencias de MDE
        1. establezca el motor antivirus `passive mode` = `true` o .`false` Use `true`si solo implementa DLP. Use `false` o no asigne un valor si implementa DLP y Microsoft Defender para punto de conexión (MDE).
    1. **netfilter.mobileconfig**
 
1. Abra Los **perfiles de configuración de** **dispositivos** > , debería ver los perfiles creados allí.

1. En la página **Perfiles de configuración** , elija el perfil que acaba de crear, en este ejemplo *AccessibilityformacOS* y elija **Estado del dispositivo** para ver una lista de dispositivos y el estado de implementación del perfil de configuración.

### <a name="get-the-device-onboarding-package"></a>Obtención del paquete de incorporación de dispositivos

1. En **el Centro de cumplimiento** , abra **Configuración** > **Incorporación de** dispositivos y elija **Incorporación**.
 
1. En **Seleccionar sistema operativo para iniciar el proceso de incorporación** , elija **macOS**.
 
1. En **Método de implementación**, elija **Mobile Administración de dispositivos/Microsoft Intune**.
 
1. Elija **Descargar paquete de incorporación**. Contiene el código de incorporación en el archivo *DeviceComplianceOnboarding.xml* .

### <a name="deploy-the-onboarding-package"></a>Implementación del paquete de incorporación

1. Abra los **perfiles de configuración** de **dispositivos** >  del **centro** >  de Microsoft Endpoint Manager.

1. Elija: **Crear perfil**. 

1. Elegir:
    1. **Plataforma = macOS**
    1. **Tipo de perfil = Plantillas**
    1. **Nombre de plantilla = Personalizado**

1. Elija **Crear**

1. Elija un nombre para el perfil, como *OnboardingPackage* en este ejemplo. Elija **Siguiente**.

1. Elija el archivo *DeviceComplianceOnboarding.xml* como archivo de perfil de configuración.

1. Elija **Siguiente**

1. En la pestaña **Asignaciones** , agregue el grupo en el que desea implementar estas configuraciones y elija **Siguiente**.

1. Revise la configuración y elija **Crear** para implementar la configuración.

### <a name="enable-system-extension"></a>Habilitación de la extensión del sistema

1. En el **centro de Microsoft Endpoint Manager**, seleccione **Crear perfil** en **Perfiles de configuración**.

1. Elegir:
    1. **Plataforma = macOS**
    1. **Tipo de perfil = Plantillas**
    1. **Nombre de plantilla = Extensiones**

1. Elija **Crear**

1. En la pestaña **Aspectos básicos** , asigne un nombre a este nuevo perfil.

1. En la pestaña **Configuración,** expanda **Extensiones del sistema**.

1. En **Identificador de agrupación** e **Identificador de equipo**, establezca estos valores.

|Identificador de agrupación  |Identificador de equipo  |
|---------|---------|
|**com.microsoft.wdav.epsext**|**UBF8T346G9**|
|**com.microsoft.wdav.netext**|**UBF8T346G9**|


1. En la pestaña **Asignaciones** , agregue el grupo en el que desea implementar estas configuraciones y elija **Siguiente**.

1. Elija **Siguiente** para implementar la configuración.

### <a name="get-the-installation-package"></a>Obtención del paquete de instalación

1. En **el Centro de cumplimiento** , abra **Configuración** > **Incorporación de** dispositivos y elija **Incorporación**.
 
1. En **Seleccionar sistema operativo para iniciar el proceso de incorporación**, elija **macOS**.
 
1. En **Método de implementación**, elija **Mobile Administración de dispositivos/Microsoft Intune**
 
1. Elija **Descargar paquete de instalación**. Esto le proporcionará el archivo *wdav.pkg* .

> [!IMPORTANT]
> Antes de implementar *wdav.pkg.* el paquete a través de Intune, se debe volver a formatear mediante el *Intune Herramientas de ajuste de aplicaciones para Mac* en el formato *wdav.pkg.intunemac*.
 

### <a name="deploy-the-microsoft-dlp-installation-package"></a>Implementación del paquete de instalación de Microsoft DLP

1. Siga los procedimientos descritos en [Adición de aplicaciones de línea de negocio (LOB) de macOS a Microsoft Intune](/mem/intune/apps/lob-apps-macos) para convertir el archivo *wdav.pkg* en el formato adecuado e implementarlo a través de Intune.

## <a name="offboard-macos-devices-using-intune"></a>Dispositivos macOS fuera del panel con Intune

> [!NOTE]
> La retirada hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que haya tenido, se conservarán durante un máximo de seis meses.

2. En **el Centro de Microsoft Endpoint Manager**, abra **Perfiles de configuración** de **dispositivos** > ; debería ver allí los perfiles creados.

1. En la página **Perfiles de configuración** , elija el perfil *wdav.pkg.intunemac* .

1. Elija **Estado del dispositivo** para ver una lista de dispositivos y el estado de implementación del perfil de configuración.

1. Abrir **propiedades** y **asignaciones**

1. Quite el grupo de la asignación. De este modo, se desinstalará el paquete *wdav.pkg.intunemac* y se quitará el dispositivo macOS de las soluciones de cumplimiento.
