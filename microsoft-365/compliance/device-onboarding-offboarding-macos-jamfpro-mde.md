---
title: Incorporar y retirar dispositivos macOS en soluciones de cumplimiento mediante JAMF Pro para clientes de Microsoft Defender para punto de conexión (versión preliminar)
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
description: Obtenga información sobre cómo incorporar y incorporar dispositivos macOS en soluciones de cumplimiento Microsoft 365 con JAMF Pro para clientes de Microsoft Defender para endpoints (versión preliminar)
ms.openlocfilehash: 31ff2803a1180d7a43b462f3a78cc52c894f23a6
ms.sourcegitcommit: 27bf284b3bfe334eb98847798734625bd2ffafb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2021
ms.locfileid: "60792321"
---
# <a name="onboard-and-offboard-macos-devices-into-compliance-solutions-using-jamf-pro-for-microsoft-defender-for-endpoint-customers-preview"></a>Incorporar y retirar dispositivos macOS en soluciones de cumplimiento mediante JAMF Pro para clientes de Microsoft Defender para punto de conexión (versión preliminar)

Puede usar jamf Pro para incorporar dispositivos macOS en Microsoft 365 de cumplimiento.

> [!IMPORTANT]
> Use este procedimiento ***si ha implementado*** Microsoft Defender para endpoint (MDE) en los dispositivos macOS

## <a name="get-registered"></a>Registrarse

Para obtener acceso a esta característica, debe registrar el espacio empresarial con Microsoft. Vea, [registrarse para la compatibilidad Microsoft 365 macOS](https://aka.ms/EndpointDLPIgnite21-Previews).

**Se aplica a:**

- Clientes que tienen MDE implementado en sus dispositivos macOS.
- [Microsoft 365 Prevención de pérdida de datos de extremo (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)


## <a name="before-you-begin"></a>Antes de empezar

- Asegúrese de que los [dispositivos macOS están Azure AD unidos](https://docs.jamf.com/10.30.0/jamf-pro/administrator-guide/Azure_AD_Integration.html)
- Asegúrese de que los [dispositivos macOS se administran a través de JAMF pro](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/) 
- Instalar el explorador perimetral v95+ en los dispositivos macOS 

## <a name="onboard-devices-into-microsoft-365-compliance-solutions-using-jamf-pro"></a>Incorporar dispositivos a Microsoft 365 de cumplimiento con jamf Pro

La incorporación de un dispositivo macOS a las soluciones de cumplimiento es un proceso de varias fases.

### <a name="download-the-configuration-files"></a>Descargar los archivos de configuración

1. Necesitará estos archivos para este procedimiento.

|archivo necesario para |source |
|---------|---------|
|accesibilidad |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
acceso en disco completo     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|Preferencia de MDE |[schema.json](https://github.com/microsoft/mdatp-xplat/blob/master/macos/schema/schema.json)

> [!TIP]
> Puede descargar los archivos *.mobileconfig* individualmente o [en un único archivo combinado](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) que contenga:
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
>
>Si alguno de estos archivos individuales se actualiza, deberá descargar el archivo combinado de nuevo o el archivo actualizado individualmente.

### <a name="update-the-existing-mde-preference-domain-profile-using-the-jamf-pro-console"></a>Actualizar el perfil de dominio de preferencia MDE existente con la consola JAMF PRO

1. Actualice el schema.xml con el **archivo schema.json** que acaba de descargar.

1. En **Propiedades de dominio de preferencia MDE,** elija esta configuración
    - Características 
        - Use System Extensions: `enabled` - required for network extensions on Catalina
        - Usar prevención de pérdida de datos: `enabled`

1. Elija la **pestaña** Ámbito.

1. Elija los grupos en los que desea implementar este perfil de configuración.

1. Seleccione **Guardar**. 

### <a name="update-the-configuration-profile-for-grant-full-disk-access"></a>Actualizar el perfil de configuración para conceder acceso a disco completo

1. Actualice el perfil de acceso a disco completo existente con el **archivo fulldisk.mobileconfig.**

1. Upload el **archivo fulldisk.mobileconfig** a JAMF. Consulte [Deploying Custom Configuration Profiles using JAMF Pro](https://docs.jamf.com/technical-articles/Deploying_Custom_Configuration_Profiles_Using_Jamf_Pro.html).

### <a name="grant-accessibility-access-to-dlp"></a>Conceder acceso de accesibilidad a DLP

1. Use el archivo accessibility.mobileconfig que descargó anteriormente.

1. Upload a JAMF como se describe en Implementar perfiles de configuración [personalizados con Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).

### <a name="check-the-macos-device"></a>Comprobar el dispositivo macOS 

1. Reinicie el dispositivo macOS.

1. Abra **Perfiles de**  >  **preferencias del sistema**.

1. Debería ver:
    - Accessiblity
    - Acceso en disco completo
    - Perfil de extensión kernel
    - MAU
    - Incorporación de MDATP
    - Preferencias de MDE
    - Perfil de administración
    - Filtro de red
    - Notificaciones
    - Perfil de extensión del sistema

## <a name="offboard-macos-devices-using-jamf-pro"></a>Dispositivos macOS fuera de la pantalla con JAMF Pro

> [!IMPORTANT]
> Offboarding hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que ha tenido, se conservarán durante un máximo de 6 meses.

Para salir de un dispositivo macOS, siga estos pasos

 1. En **Propiedades de dominio de preferencia MDE,** quita los valores de esta configuración
    - Características 
        - Usar extensiones del sistema
        - Usar prevención de pérdida de datos

1. Seleccione **Guardar**.
