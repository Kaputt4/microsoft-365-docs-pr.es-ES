---
title: Incorporación y eliminación de dispositivos macOS en soluciones de cumplimiento mediante jamf Pro para clientes Microsoft Defender para punto de conexión
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
description: Aprenda a incorporar y desconectar dispositivos macOS en soluciones de Microsoft Purview mediante JAMF Pro para clientes Microsoft Defender para punto de conexión
ms.openlocfilehash: ba2ff7723e54451ace46823fafb5323dcb35069e
ms.sourcegitcommit: e911dd506ea066795e418daf7b84c1e11381a21c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64953391"
---
# <a name="onboard-and-offboard-macos-devices-into-compliance-solutions-using-jamf-pro-for-microsoft-defender-for-endpoint-customers"></a>Incorporación y eliminación de dispositivos macOS en soluciones de cumplimiento mediante jamf Pro para clientes Microsoft Defender para punto de conexión

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Puede usar JAMF Pro para incorporar dispositivos macOS a soluciones de Microsoft Purview.

> [!IMPORTANT]
> Use este procedimiento ***si ha*** implementado Microsoft Defender para punto de conexión (MDE) en los dispositivos macOS.

**Se aplica a:**

- Clientes que tienen MDE implementado en sus dispositivos macOS.
- [Prevención de perdida de datos en el punto de conexión (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md)


## <a name="before-you-begin"></a>Antes de empezar

- Asegúrese de que [los dispositivos macOS se administran a través de JAMF Pro](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/) y que están asociados a una identidad (UPN Azure AD unida) a través de JAMF Conectar o Intune.
- Instalar el explorador v95+ Edge en los dispositivos macOS

## <a name="onboard-devices-into-microsoft-purview-solutions-using-jamf-pro"></a>Incorporación de dispositivos a soluciones de Microsoft Purview mediante JAMF Pro

La incorporación de un dispositivo macOS a las soluciones de cumplimiento es un proceso de varias fases.

### <a name="download-the-configuration-files"></a>Descarga de los archivos de configuración

1. Necesitará estos archivos para este procedimiento.

|archivo necesario para |source |
|---------|---------|
|Accesibilidad |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
acceso completo al disco     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|Preferencia de MDE |[schema.json](https://github.com/microsoft/mdatp-xplat/blob/master/macos/schema/schema.json)

> [!TIP]
> Puede descargar los archivos *.mobileconfig* individualmente o en [un único archivo combinado](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) que contenga:
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
>
>Si alguno de estos archivos individuales se actualiza, deberá descargar el archivo combinado de nuevo o el archivo actualizado individualmente.

### <a name="update-the-existing-mde-preference-domain-profile-using-the-jamf-pro-console"></a>Actualización del perfil de dominio de preferencia de MDE existente mediante la consola de JAMF PRO

1. Actualice el perfil de schema.xml con el archivo **schema.json** que acaba de descargar.

1. En **Propiedades de dominio de preferencia de MDE** , elija esta configuración.
    - Características 
        - Uso de extensiones del sistema: `enabled` necesario para las extensiones de red en Catalina
        - Usar la prevención de pérdida de datos: `enabled`

1. Elija la pestaña **Ámbito** .

1. Elija los grupos en los que implementar este perfil de configuración.

1. Seleccione **Guardar**. 

### <a name="update-the-configuration-profile-for-grant-full-disk-access"></a>Actualización del perfil de configuración para conceder acceso completo al disco

1. Actualice el perfil de acceso al disco completo existente con el archivo **fulldisk.mobileconfig** .

1. Upload el archivo **fulldisk.mobileconfig** a JAMF. Consulte [Implementación de perfiles de configuración personalizados mediante jamf Pro](https://docs.jamf.com/technical-articles/Deploying_Custom_Configuration_Profiles_Using_Jamf_Pro.html).

### <a name="grant-accessibility-access-to-dlp"></a>Concesión de acceso de accesibilidad a DLP

1. Use el archivo accessibility.mobileconfig que descargó anteriormente.

1. Upload a JAMF como se describe en [Implementación de perfiles de configuración personalizados mediante Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).

### <a name="check-the-macos-device"></a>Comprobación del dispositivo macOS 

1. Reinicie el dispositivo macOS.

1. Abra **Preferencias** >  del **sistemaPerfiles**.

1. Debería ver lo siguiente:
    - Accesibilidad
    - Acceso completo al disco
    - Perfil de extensión del kernel
    - MAU
    - Incorporación de MDATP
    - Preferencias de MDE
    - Perfil de administración
    - Filtro de red
    - Notificaciones
    - Perfil de extensión del sistema

## <a name="offboard-macos-devices-using-jamf-pro"></a>Dispositivos macOS fuera del panel con JAMF Pro

> [!IMPORTANT]
> La retirada hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que haya tenido, se conservarán durante un máximo de 6 meses.

Para desconectar un dispositivo macOS, siga estos pasos.

 1. En **Propiedades de dominio de preferencia de MDE** , quite los valores de esta configuración.
    - Características 
        - Uso de extensiones del sistema
        - Uso de la prevención de pérdida de datos

1. Seleccione **Guardar**.
