---
title: Incorporación y descarga de dispositivos macOS en soluciones de cumplimiento con Microsoft Intune para clientes de Microsoft Defender para endpoints (versión preliminar)
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
description: Obtenga información sobre cómo incorporar y incorporar dispositivos macOS en soluciones de cumplimiento Microsoft 365 con Microsoft Intune para clientes de MDE (versión preliminar)
ms.openlocfilehash: 6cc4362e924f291c6a8396bff342c6f628e33be3
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526560"
---
# <a name="onboard-and-offboard-macos-devices-into-compliance-solutions-using-intune-for-microsoft-defender-for-endpoint-customers-preview"></a>Incorporar y retirar dispositivos macOS en soluciones de cumplimiento mediante Intune para clientes de Microsoft Defender para punto de conexión (versión preliminar)

> [!IMPORTANT]
> Use este procedimiento ***si ha implementado*** Microsoft Defender para endpoint (MDE) en los dispositivos macOS

**Se aplica a:**

- Clientes que tienen MDE implementado en sus dispositivos macOS.
- [Prevención de pérdida de datos en punto de conexión en Microsoft 365 (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)


## <a name="before-you-begin"></a>Antes de empezar

- Asegúrate de que los [dispositivos macOS se incorporen a Intune](/mem/intune/fundamentals/deployment-guide-platform-macos) y se inscribieron en la [Portal de empresa aplicación](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp). 
- Asegúrese de que tiene acceso al centro [de Microsoft Endpoint Manager de datos](https://endpoint.microsoft.com/#home)
- Esto admite macOS versión Catalina 10.15 y versiones posteriores
- Instalar el explorador perimetral v95+ en los dispositivos macOS 

## <a name="onboard-macos-devices-into-microsoft-365-compliance-solutions-using-microsoft-intune"></a>Incorporar dispositivos macOS en Microsoft 365 de cumplimiento normativo mediante Microsoft Intune

Usa estos pasos para incorporar un dispositivo macOS en las soluciones de cumplimiento si ya tiene MDE implementado en él.

1. Necesitará estos archivos para este procedimiento.

|archivo necesario para |source |
|---------|---------|
|accesibilidad |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
acceso en disco completo     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|

> [!TIP]
> Puede descargar los archivos *.mobileconfig* individualmente o [en un único archivo combinado](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) que contenga:
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
> 
>
>Si alguno de estos archivos individuales se actualiza, deberá descargar el archivo combinado de nuevo o el archivo actualizado individualmente.

### <a name="create-system-configuration-profiles"></a>Crear perfiles de configuración del sistema

1. Abra los **Microsoft Endpoint Manager** **centerDevicesConfiguration** >  > .

1. Elija: **Crear perfil**. 

1. Elija:
    1. **Platform = macOS**
    1. **Tipo de perfil = Plantillas**
    1. **Nombre de plantilla = Personalizado**

1. Elija **Crear**

1. Elija un nombre para el perfil, como *AccessibilityformacOS* en este ejemplo. Elija **Siguiente**.

1. Elija el **archivo accessibility.mobileconfig** que descargó en el paso 1 como archivo de perfil de configuración.

1. Elija **Siguiente**

1. En la **pestaña Asignaciones** , agregue el grupo en el que desea implementar estas configuraciones y elija **Siguiente**.

1. Revise la configuración y elija **Crear** para implementar la configuración.

1. Abra **los perfiles devicesConfiguration** > , debe ver los perfiles creados allí.

1. En la página Perfiles de configuración, elija el perfil que acaba de crear, en este ejemplo *AccessibilityformacOS* y  elija Estado del dispositivo para ver una lista de **dispositivos** y el estado de implementación del perfil de configuración.

### <a name="update-configuration-profiles"></a>Actualizar perfiles de configuración

1. Actualice el perfil de acceso a disco completo existente con el **archivo fulldisk.mobileconfig** .

1. Actualizar el perfil de preferencias de MDE existing con estos valores
   
```xml
<key>features</key>
<dict>
    <key>systemExtensions</key>
    <string>enabled</string>
    <key>dataLossPrevention</key>
    <string>enabled</string>
</dict>
```

## <a name="offboard-macos-devices-using-intune"></a>Dispositivos macOS fuera de la pantalla con Intune

> [!IMPORTANT]
> Offboarding hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que ha tenido, se conservarán durante un máximo de 6 meses.

1. En **Microsoft Endpoint Manager,** abra **los perfiles DevicesConfiguration** > , debería ver los perfiles creados allí.

2. En la **página Perfiles de configuración** , elija el perfil de preferencias MDE.

1. Quite esta configuración:
   
```xml
<key>features</key>
<dict>
    <key>systemExtensions</key>
    <string>enabled</string>
    <key>dataLossPrevention</key>
    <string>enabled</string>
</dict>
```
3. **Guardar**.