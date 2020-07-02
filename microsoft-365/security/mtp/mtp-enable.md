---
title: Habilitar la Protección contra amenazas de Microsoft en el Centro de seguridad de Microsoft 365
description: Obtenga información acerca de cómo habilitar la Protección contra amenazas de Microsoft y empiece a integrar su gestión de incidentes de seguridad y la respuesta a ellos.
keywords: Introducción, habilitación de MTP, protección contra amenazas de Microsoft, M365, seguridad, ubicación de datos, permisos necesarios, requisitos de licencia, página de configuración
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b6ac30f7e32bbec80952ad4f2104032886b11503
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016348"
---
# <a name="turn-on-microsoft-threat-protection"></a>Habilitar la Protección contra amenazas de Microsoft

**Se aplica a:**
- Protección contra amenazas de Microsoft

[Microsoft Threat Protection](microsoft-threat-protection.md) unifica el proceso de respuesta ante incidentes mediante la integración de capacidades clave en la protección contra amenazas avanzada de Microsoft defender (ATP), Office 365 ATP, Microsoft Cloud App Security y Azure ATP. Esta experiencia unificada aporta potentes características a las que puede acceder desde el Centro de seguridad de Microsoft 365.

La protección contra amenazas de Microsoft se activa automáticamente cuando los clientes elegibles con los permisos necesarios visitan el centro de seguridad de Microsoft 365. Lea este artículo para conocer varios requisitos previos y cómo se aprovisiona la protección contra amenazas de Microsoft.

## <a name="check-license-eligibility-and-required-permissions"></a>Comprobar la elegibilidad de la licencia y los permisos necesarios
Una licencia a un producto de seguridad 365 de Microsoft generalmente le da derecho a usar Microsoft Threat Protection en el centro de seguridad de Microsoft 365 sin costo adicional de licencias. Le recomendamos que obtenga una licencia de seguridad de Microsoft 365 E5, E5 Security, A5 o a5 o una combinación válida de licencias que proporcione acceso a todos los servicios admitidos.

Para obtener información detallada sobre la licencia, [Lea los requisitos de licencia](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Comprobar el rol
Debe ser **administrador global** o **Administrador de seguridad** en Azure Active Directory para activar la protección contra amenazas de Microsoft. [Ver sus roles en Azure AD](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Servicios admitidos
Microsoft Threat Protection agrega datos de los diversos servicios compatibles que ya ha implementado. Procesará y almacenará datos de forma centralizada para identificar nuevos conocimientos y hacer que los flujos de trabajo de respuesta centralizados sean posibles. Lo hace sin afectar a las implementaciones, la configuración o los datos existentes asociados con los servicios integrados.

Para obtener la mejor protección y optimizar la protección contra amenazas de Microsoft, se recomienda implementar todos los servicios admitidos aplicables en la red. Para obtener más información, [Consulte acerca de la implementación de servicios compatibles](deploy-supported-services.md).

## <a name="before-starting-the-service"></a>Antes de iniciar el servicio
Antes de activar el servicio, el centro de seguridad 365 de Microsoft ([Security.Microsoft.com](https://security.microsoft.com)) muestra la página de configuración de Microsoft Threat Protection al seleccionar **incidentes**, **centro de actividades**o **caza** en el panel de navegación. Estos elementos de navegación no se muestran si no es elegible para usar la protección contra amenazas de Microsoft.

![Imagen de la página de configuración de Microsoft Threat Protection que se muestra si no se ha activado la protección contra amenazas de Microsoft en la ](../../media/mtp-enable/mtp-settings.png)
 *configuración de protección contra amenazas de Microsoft en el centro de seguridad de Microsoft 365*

## <a name="starting-the-service"></a>Inicio del servicio
Para activar la protección contra amenazas de Microsoft, simplemente seleccione **activar la protección contra amenazas de Microsoft** y aplicar el cambio. También puede tener acceso a esta opción si selecciona **configuración** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) en el panel de navegación y, a continuación, selecciona protección contra **amenazas de Microsoft**.

>[!NOTE]
>Si no ve la **configuración** en el panel de navegación o no pudo obtener acceso a la página, compruebe los permisos y las licencias.

### <a name="data-center-location"></a>Ubicación del centro de datos
Microsoft Threat Protection almacenará y procesará los datos en la [misma ubicación usada por ATP de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Si no tiene Microsoft defender ATP, se selecciona automáticamente una nueva ubicación del centro de datos en función de la ubicación de los servicios de seguridad de Microsoft 365 activos. La ubicación del centro de datos seleccionada se muestra en la pantalla. 

Seleccione **¿necesita ayuda?** en el centro de seguridad de Microsoft 365, póngase en contacto con el soporte técnico de Microsoft sobre el aprovisionamiento de la protección contra amenazas de Microsoft en otra ubicación del centro de datos. 

>[!NOTE]
>Microsoft defender ATP se aprovisiona automáticamente en los centros de datos de la Unión Europea (UE) cuando se activa a través del centro de seguridad de Azure. Microsoft Threat Protection aprovisionará automáticamente en el mismo centro de datos de la UE a los clientes que hayan aprovisionado ATP de Microsoft defender de este modo. 

### <a name="confirm-that-the-service-is-on"></a>Confirme que el servicio está activado
Una vez que recibe el servicio, este agrega:

- [Administración de incidentes](incidents-overview.md)
- Un centro de actividades para administrar [una investigación y respuestas automáticas](mtp-autoir.md)
- Funcionalidades de [búsqueda avanzada](advanced-hunting-overview.md)

![Imagen del panel de navegación del centro de seguridad de Microsoft 365 con Microsoft Threat Protection características de ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Security Center con incidentes de administración de incidentes y otras capacidades de protección contra amenazas de Microsoft*

### <a name="getting-azure-atp-data"></a>Obtener datos de Azure ATP
Para compartir datos de Azure ATP con la Protección contra amenazas de Microsoft, asegúrese de que esté activada la integración entre Microsoft Cloud App Security y Azure ATP. [Infórmese de esta integración](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Deshabilitar la Protección contra amenazas de Microsoft
Para dejar de usar la Protección contra amenazas de Microsoft, vaya a **Configuración** > **** Protección contra amenazas de Microsoft > **** Participar/No participar en el Centro de seguridad de Microsoft 365. Anule la selección **de activar la protección contra amenazas de Microsoft** y aplicar los cambios.

Se quitarán las características correspondientes del centro de seguridad de Microsoft 365.

## <a name="get-assistance"></a>Cómo recibir asistencia

Para obtener respuestas a las preguntas más comunes sobre la activación de la protección contra amenazas de Microsoft, [Lea las preguntas más frecuentes](mtp-enable-faq.md).

El personal de soporte técnico de Microsoft puede ayudarle a aprovisionar o desaprovisionar el servicio y los recursos relacionados en su espacio empresarial. Para obtener ayuda, seleccione **¿necesita ayuda?** en el centro de seguridad de Microsoft 365. Al ponerse en contacto con el soporte técnico, mencione Microsoft Threat Protection.

## <a name="related-topics"></a>Temas relacionados

- [Preguntas más frecuentes](mtp-enable-faq.md)
- [Requisitos de licencia y otros requisitos previos](prerequisites.md)
- [Implementación de servicios compatibles](deploy-supported-services.md)
- [Introducción a la Protección contra amenazas de Microsoft](microsoft-threat-protection.md)
- [Introducción al ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Introducción al ATP de Office 365](../office-365-security/office-365-atp.md)
- [Introducción a Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Introducción al ATP de Azure](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Almacenamiento de datos del ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)