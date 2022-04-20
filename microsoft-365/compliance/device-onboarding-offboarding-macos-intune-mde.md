---
title: Incorporación y eliminación de dispositivos macOS en soluciones de cumplimiento mediante Microsoft Intune para clientes Microsoft Defender para punto de conexión
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
description: Obtenga información sobre cómo incorporar y desconectar dispositivos macOS en soluciones de Microsoft Purview mediante Microsoft Intune para clientes de MDE
ms.openlocfilehash: c6b374ad3c35ba3441e82412d9897132006d0559
ms.sourcegitcommit: e911dd506ea066795e418daf7b84c1e11381a21c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64952850"
---
# <a name="onboard-and-offboard-macos-devices-into-compliance-solutions-using-intune-for-microsoft-defender-for-endpoint-customers"></a>Incorporación y eliminación de dispositivos macOS en soluciones de cumplimiento mediante Intune para clientes Microsoft Defender para punto de conexión

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

> [!IMPORTANT]
> Use este procedimiento ***si ha*** implementado Microsoft Defender para punto de conexión (MDE) en los dispositivos macOS.

**Se aplica a:**

- Clientes que tienen MDE implementado en sus dispositivos macOS.
- [Prevención de perdida de datos en el punto de conexión (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md)


## <a name="before-you-begin"></a>Antes de empezar

- Asegúrese de que [los dispositivos macOS están incorporados a Intune](/mem/intune/fundamentals/deployment-guide-platform-macos) e inscritos en la [aplicación Portal de empresa](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp). 
- Asegúrese de que tiene acceso al [centro de Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)
- Esto es compatible con la versión de macOS Catalina 10.15 y versiones posteriores
- Instalar el explorador v95+ Edge en los dispositivos macOS 

## <a name="onboard-macos-devices-into-microsoft-purview-solutions-using-microsoft-intune"></a>Incorporación de dispositivos macOS a soluciones de Microsoft Purview mediante Microsoft Intune

Siga estos pasos para incorporar un dispositivo macOS a las soluciones de cumplimiento si ya tiene MDE implementado en él.

1. Necesitará estos archivos para este procedimiento.

|archivo necesario para |source |
|---------|---------|
|Accesibilidad |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
acceso completo al disco     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|

> [!TIP]
> Puede descargar los archivos *.mobileconfig* individualmente o en [un único archivo combinado](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) que contenga:
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
> 
>
>Si alguno de estos archivos individuales se actualiza, deberá descargar el archivo combinado de nuevo o el archivo actualizado individualmente.

### <a name="create-system-configuration-profiles"></a>Creación de perfiles de configuración del sistema

1. Abra los perfiles **centerDevicesConfiguration** >  **del centro** >  **de** Microsoft Endpoint Manager.

1. Elija: **Crear perfil**. 

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

1. Abra **DispositivosPerfiles** >  **de configuración**, debería ver los perfiles creados allí.

1. En la página **Perfiles de configuración** , elija el perfil que acaba de crear, en este ejemplo *AccessibilityformacOS* y elija **Estado del dispositivo** para ver una lista de dispositivos y el estado de implementación del perfil de configuración.

### <a name="update-configuration-profiles"></a>Actualizar perfiles de configuración

1. Actualice el perfil de acceso al disco completo existente con el archivo **fulldisk.mobileconfig** .

1. Actualizar el perfil de preferencias de MDE con estos valores
   
```xml
<key>features</key>
<dict>
    <key>systemExtensions</key>
    <string>enabled</string>
    <key>dataLossPrevention</key>
    <string>enabled</string>
</dict>
```

## <a name="offboard-macos-devices-using-intune"></a>Dispositivos macOS fuera del panel con Intune

> [!IMPORTANT]
> La retirada hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que haya tenido, se conservarán durante un máximo de 6 meses.

1. En **Microsoft Endpoint Manager centro**, abra **DispositivosPerfiles** >  de configuración, debería ver allí los perfiles creados.

2. En la página **Perfiles de configuración** , elija el perfil de preferencias de MDE.

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
