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
ms.openlocfilehash: 9a57929e42f08db8abda170c889441d3a50ade72
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209252"
---
# <a name="turn-on-microsoft-threat-protection"></a>Habilitar la Protección contra amenazas de Microsoft

**Se aplica a:**
- Protección contra amenazas de Microsoft

La Protección contra amenazas de Microsoft unifica el proceso de respuesta a incidentes de seguridad mediante la integración de las capacidades clave en la Protección contra amenazas avanzada (ATP) de Microsoft Defender, Office 365 ATP, Microsoft Cloud App Security y Azure ATP. Esta experiencia unificada aporta potentes características a las que puede acceder desde el Centro de seguridad de Microsoft 365.

Para obtener la mejor protección y optimizar la protección contra amenazas de Microsoft, se recomienda implementar todos los servicios admitidos aplicables en la red. Para obtener más información, [Consulte acerca de la implementación de servicios compatibles](deploy-supported-services.md).

## <a name="check-license-eligibility-and-required-permissions"></a>Comprobar la elegibilidad de la licencia y los permisos necesarios
Una licencia de seguridad de Microsoft 365 E5, E5 Security, A5 o a5 o una combinación válida de licencias proporciona acceso a los servicios admitidos y le da derecho a usar Microsoft Threat Protection en el centro de seguridad de Microsoft 365 sin costo adicional de licencias.

Para obtener información detallada sobre la licencia, [Lea los requisitos de licencia](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Comprobar el rol
Debe ser **administrador global** o **Administrador de seguridad** en Azure Active Directory para activar la protección contra amenazas de Microsoft. [Ver sus roles en Azure AD](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a>Empiece a usar el servicio

>[!IMPORTANT]
>A partir del 12 de mayo de 2020, Microsoft implementará gradualmente nuevas y optimizadas experiencias sobre [los requisitos de licencia](prerequisites.md#licensing-requirements) y activando la protección contra amenazas de Microsoft. Durante varias semanas durante este período, algunos clientes empezarán a ver los cambios en sus experiencias de portal. La información sobre las nuevas experiencias se marca como **nueva experiencia** en este artículo.

Microsoft Threat Protection agrega datos de los diversos servicios integrados. Procesará y almacenará datos de forma centralizada para identificar nuevos conocimientos y hacer que los flujos de trabajo de respuesta centralizados sean posibles. Lo hace sin afectar a las implementaciones, la configuración o los datos existentes asociados con los servicios integrados.

Antes de activar el servicio, el centro de seguridad de Microsoft 365 ([Security.Microsoft.com](https://security.microsoft.com)) muestra la página de bienvenida de Microsoft Threat Protection al seleccionar **incidentes**, **centro de actividades**o **caza** en el panel de navegación. Estas opciones de navegación no se muestran si no es elegible para usar la protección contra amenazas de Microsoft.

![Imagen de la página de bienvenida de Microsoft Threat Protection que se muestra si no se ha activado la protección contra amenazas de Microsoft en la ](../../media/mtp-welcome.png)
 *Página de bienvenida de Microsoft Threat Protection en el centro de seguridad de Microsoft 365*

Para activar la protección contra amenazas de Microsoft, simplemente complete el proceso desde la página de bienvenida. También puede activar Microsoft Threat Protection accediendo a la **configuración** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) en el panel de navegación y seleccionando **Microsoft Threat Protection**.

>[!NOTE]
>Si no ve la **configuración** en el panel de navegación o no pudo obtener acceso a la página, compruebe los permisos y las licencias.

### <a name="select-data-center-location"></a>Seleccionar la ubicación del centro de datos
Si su organización dispone de ATP de Microsoft Defender, los datos se almacenarán y procesarán en la misma ubicación del centro de datos que seleccionara para [sus datos de ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Si no tiene ATP de Microsoft defender, se le pedirá que elija una nueva ubicación del centro de datos específicamente para la Protección contra amenazas de Microsoft. 
 
Debe proporcionar el consentimiento antes de que los datos se compartan entre los servicios y se agreguen.

**Nueva experiencia:** A partir del 12 de mayo de 2020, los clientes recibirán gradualmente los cambios de esta experiencia. Para los usuarios con la nueva experiencia, el servicio selecciona automáticamente la ubicación óptima del centro de datos para los datos agregados en función de los servicios de seguridad de Microsoft 365 existentes. La ubicación del centro de datos seleccionada se muestra en la pantalla.

### <a name="confirm-that-the-service-is-on"></a>Confirme que el servicio está activado
Una vez que recibe el servicio, este agrega:

- [Administración de incidentes](incidents-overview.md)
- Un centro de actividades para administrar [una investigación y respuestas automáticas](mtp-autoir.md)
- Funcionalidades de [búsqueda avanzada](advanced-hunting-overview.md)

![Imagen del panel de navegación del centro de seguridad de Microsoft 365 con Microsoft Threat Protection características de ](../../media/mtp-on.png)
 *Microsoft 365 Security Center con incidentes de administración de incidentes y otras capacidades de protección contra amenazas de Microsoft*

### <a name="getting-azure-atp-data"></a>Obtener datos de Azure ATP
Para compartir datos de Azure ATP con la Protección contra amenazas de Microsoft, asegúrese de que esté activada la integración entre Microsoft Cloud App Security y Azure ATP. [Infórmese de esta integración](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Deshabilitar la Protección contra amenazas de Microsoft
Para dejar de usar la Protección contra amenazas de Microsoft, vaya a **Configuración** > **** Protección contra amenazas de Microsoft > **** Participar/No participar en el Centro de seguridad de Microsoft 365. Anule la selección de **Activar la Protección contra amenazas de Microsoft** y guarde los cambios.

Se quitarán las características correspondientes del centro de seguridad de Microsoft 365.

## <a name="get-assistance"></a>Cómo recibir asistencia

El personal de soporte técnico de Microsoft puede ayudarle a aprovisionar o desaprovisionar el servicio y los recursos relacionados en su espacio empresarial. Para obtener ayuda, seleccione **¿necesita ayuda?** en el centro de seguridad de Microsoft 365. Al ponerse en contacto con el soporte técnico, mencione Microsoft Threat Protection.

## <a name="related-topics"></a>Temas relacionados

- [Introducción a la Protección contra amenazas de Microsoft](microsoft-threat-protection.md)
- [Requisitos de licencia y otros requisitos previos](prerequisites.md)
- [Implementación de servicios compatibles](deploy-supported-services.md)
- [Introducción al ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Introducción al ATP de Office 365](../office-365-security/office-365-atp.md)
- [Introducción a Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Introducción al ATP de Azure](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Almacenamiento de datos del ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)