---
title: Activar Microsoft 365 Defender
description: Obtenga información sobre cómo habilitar Microsoft 365 Defender y empezar a integrar el incidente de seguridad y la respuesta.
keywords: introducción, habilitación de Microsoft 365 Defender, Microsoft 365 Defender, M365, seguridad, ubicación de datos, permisos necesarios, idoneidad de licencia, página de configuración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-getstarted
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0fa1a47bb5a4a09c22649866bb6c5c6039dc2850
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2022
ms.locfileid: "66895039"
---
# <a name="turn-on-microsoft-365-defender"></a>Activar Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md) unifica el proceso de respuesta a incidentes mediante la integración de funcionalidades clave en Microsoft Defender para punto de conexión, Microsoft Defender para Office 365, Microsoft Defender for Cloud Apps y Microsoft Defender for Identity. Esta experiencia unificada agrega características eficaces a las que puede acceder en el portal de Microsoft 365 Defender.

Microsoft 365 Defender se activa automáticamente cuando los clientes aptos con los permisos necesarios visitan Microsoft 365 Defender portal. Lea este artículo para comprender los distintos requisitos previos y cómo se aprovisiona Microsoft 365 Defender.

## <a name="check-license-eligibility-and-required-permissions"></a>Comprobación de la idoneidad de la licencia y los permisos necesarios

Por lo general, una licencia para un producto de seguridad de Microsoft 365 le da derecho a usar Microsoft 365 Defender sin costo de licencia adicional. Se recomienda obtener una licencia Microsoft 365 E5, E5 Security, A5 o A5 Security o una combinación válida de licencias que proporcione acceso a todos los servicios admitidos.

Para obtener información detallada sobre las licencias, [lee los requisitos de licencia](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Comprobación del rol

Debe ser uno de los siguientes roles para activar Microsoft 365 Defender:

- Administrador global
- Administrador de seguridad
- Operador de seguridad
- Lector global
- Lector de seguridad
- Administrador de cumplimiento
- Administrador de datos de cumplimiento
- Administrador de la aplicación
- Administrador de aplicaciones en la nube

[Visualización de los roles en Azure AD](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Servicios admitidos

Microsoft 365 Defender agrega datos de los distintos servicios compatibles que ya ha implementado. Procesará y almacenará los datos de forma centralizada para identificar nuevas conclusiones y hacer posibles flujos de trabajo de respuesta centralizados. Lo hace sin afectar a las implementaciones, la configuración o los datos existentes asociados a los servicios integrados.

Para obtener la mejor protección y optimizar Microsoft 365 Defender, se recomienda implementar todos los servicios admitidos aplicables en la red. Para obtener más información, [lea sobre la implementación de servicios admitidos](deploy-supported-services.md).

## <a name="onboard-to-the-service"></a>Incorporación al servicio
La incorporación a Microsoft 365 Defender es sencilla. En el menú de navegación, seleccione cualquier elemento, como **Incidentes & alertas**, **Búsqueda**, **Centro de acciones** o **Análisis de amenazas** para iniciar el proceso de incorporación. 

### <a name="data-center-location"></a>Ubicación del centro de datos

Microsoft 365 Defender almacenará y procesará los datos en la [misma ubicación usada por Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Si no tiene Microsoft Defender para punto de conexión, se selecciona automáticamente una nueva ubicación del centro de datos en función de la ubicación de los servicios de seguridad de Microsoft 365 activos. La ubicación del centro de datos seleccionada se muestra en la pantalla.

Seleccione **¿Necesita ayuda?** en el portal de Microsoft 365 Defender para ponerse en contacto con el soporte técnico de Microsoft sobre el aprovisionamiento de Microsoft 365 Defender en otra ubicación del centro de datos.

> [!NOTE]
> En el pasado, Microsoft Defender para punto de conexión aprovisionado automáticamente en centros de datos de la Unión Europea (UE) cuando se activa a través de Microsoft Defender for Cloud. Microsoft 365 Defender aprovisionará automáticamente en el mismo centro de datos de la UE para los clientes que hayan aprovisionado Defender para punto de conexión de esta manera en el pasado.

### <a name="confirm-that-the-service-is-on"></a>Confirme que el servicio está activado

Una vez que recibe el servicio, este agrega:

- [Administración de incidentes](incidents-overview.md)
- [Cola de alertas](investigate-alerts.md)
- Un centro de actividades para administrar [una investigación y respuestas automáticas](m365d-autoir.md)
- [Funcionalidades avanzadas de búsqueda](advanced-hunting-overview.md)
- Análisis de amenazas

:::image type="content" source="../../media/overview-incident.png" alt-text="Panel de navegación del portal de Microsoft 365 Defender con características Microsoft 365 Defender" lightbox="../../media/overview-incident.png":::
*Microsoft 365 Defender portal con administración de incidentes y otras funcionalidades*

### <a name="getting-microsoft-defender-for-identity-data"></a>Obtención de datos Microsoft Defender for Identity 
Para habilitar la integración con Microsoft Defender for Cloud Apps, deberá iniciar sesión en el Microsoft Defender for Cloud Apps al menos una vez.

## <a name="get-assistance"></a>Cómo recibir asistencia

Para obtener respuestas a las preguntas más frecuentes sobre cómo activar Microsoft 365 Defender, [lea las preguntas más frecuentes](m365d-enable-faq.md).

El personal de soporte técnico de Microsoft puede ayudar a aprovisionar o desaprovisionar el servicio y los recursos relacionados en el inquilino. Para obtener ayuda, seleccione **¿Necesita ayuda?** en el portal de Microsoft 365 Defender. Al ponerse en contacto con el soporte técnico, mencione Microsoft 365 Defender.

## <a name="related-topics"></a>Temas relacionados

- [Preguntas más frecuentes](m365d-enable-faq.md)
- [Requisitos de licencia y otros requisitos previos](prerequisites.md)
- [Implementación de servicios compatibles](deploy-supported-services.md)
- [introducción a Microsoft 365 Defender](microsoft-365-defender.md)
- [introducción a Microsoft Defender para punto de conexión](../defender-endpoint/microsoft-defender-endpoint.md)
- [introducción a Defender para Office 365](../office-365-security/defender-for-office-365.md)
- [Introducción a Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)
- [introducción a Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp)
- [almacenamiento de datos de Microsoft Defender para punto de conexión](../defender-endpoint/data-storage-privacy.md)
