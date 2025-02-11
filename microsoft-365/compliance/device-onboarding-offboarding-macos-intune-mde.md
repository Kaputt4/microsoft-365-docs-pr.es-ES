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
- tier1
- purview-compliance
search.appverid:
- MET150
description: Obtenga información sobre cómo incorporar y desconectar dispositivos macOS en soluciones de Microsoft Purview mediante Microsoft Intune para clientes de MDE
ms.openlocfilehash: 7638653c7794270b37c3925f17a64949f1fcae75
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68632280"
---
# <a name="onboard-and-offboard-macos-devices-into-compliance-solutions-using-intune-for-microsoft-defender-for-endpoint-customers"></a>Incorporación y retirada de dispositivos macOS en soluciones de cumplimiento mediante Intune para clientes de Microsoft Defender para punto de conexión

> [!IMPORTANT]
> Use este procedimiento ***si ha*** implementado Microsoft Defender para punto de conexión (MDE) en los dispositivos macOS.

**Se aplica a:**

- Clientes que tienen MDE implementado en sus dispositivos macOS.
- [Prevención de perdida de datos en el punto de conexión (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md)


[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="before-you-begin"></a>Antes de empezar

- Asegúrese de que [los dispositivos macOS están incorporados a Intune](/mem/intune/fundamentals/deployment-guide-platform-macos) e inscritos en la [aplicación Portal de empresa](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp). 
- Asegúrese de que tiene acceso al [Centro de Endpoint Manager de Microsoft](https://endpoint.microsoft.com/#home).
- Esto admite las tres versiones más recientes de macOS publicadas.
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

1. Abra los **perfiles de configuración** de **dispositivos** >  del **centro** >  de Microsoft Endpoint Manager.

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

1. Abra Los **perfiles de configuración de** **dispositivos** > , debería ver los perfiles creados allí.

1. En la página **Perfiles de configuración** , elija el perfil que acaba de crear, en este ejemplo *AccessibilityformacOS* y elija **Estado del dispositivo** para ver una lista de dispositivos y el estado de implementación del perfil de configuración.

### <a name="update-existing-system-configuration-profiles"></a>Actualización de perfiles de configuración del sistema existentes


1. Se debería haber creado e implementado previamente un perfil de configuración de acceso a disco completo para MDE.  Consulte [Implementación basada en Intune para Microsoft Defender para punto de conexión en Mac](/microsoft-365/security/defender-endpoint/mac-install-with-intune#full-disk-access). DLP de punto de conexión requiere un permiso de acceso de disco completo adicional para una nueva aplicación: `com.microsoft.dlp.daemon`. 
    1. Actualice el perfil de configuración de Fullfull Disk Access existente con el archivo fulldisk.mobileconfig. 


1. Busque el perfil de configuración de preferencias MDE existente. Consulte [Establecer preferencias para Microsoft Defender para punto de conexión en macOS](/microsoft-365/security/defender-endpoint/mac-preferences#intune-full-profile)
    1. Agregue una nueva clave al perfil con estos valores:

```xml
<key>features</key> 
<dict> 
    <key>systemExtensions</key> 
    <string>enabled</string> 
    <key>dataLossPrevention</key> 
    <string>enabled</string> 
</dict> 
``` 

Este es un [ejemplo de mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/com.microsoft.wdav.mobileconfig)
 
## <a name="offboard-macos-devices-using-intune"></a>Dispositivos macOS fuera del panel con Intune

> [!IMPORTANT]
> La retirada hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que haya tenido, se conservarán durante un máximo de 6 meses.

1. En **el Centro de Microsoft Endpoint Manager**, abra **Perfiles de configuración** de **dispositivos** > ; debería ver allí los perfiles creados.

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
