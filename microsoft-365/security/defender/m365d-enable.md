---
title: Activar Microsoft 365 Defender en el Centro de seguridad de Microsoft 365
description: Obtenga información sobre cómo habilitar Microsoft 365 Defender y empezar a integrar el incidente de seguridad y la respuesta.
keywords: get started, enable Microsoft 365 Defender, Microsoft 365 Defender, M365, security, data location, required permissions, license eligibility, settings page
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2d69ae70b137c9e5378958721f7f9958e57c0306
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935646"
---
# <a name="turn-on-microsoft-365-defender"></a>Activar Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md) unifica el proceso de respuesta a incidentes integrando funciones clave en Microsoft Defender para Endpoint, Microsoft Defender para Office 365, Microsoft Cloud App Security y Microsoft Defender for Identity. Esta experiencia unificada aporta potentes características a las que puede acceder desde el Centro de seguridad de Microsoft 365.

Microsoft 365 Defender se activa automáticamente cuando los clientes elegibles con los permisos necesarios visitan el Centro de seguridad de Microsoft 365. Lea este artículo para comprender varios requisitos previos y cómo se aprovisiona Microsoft 365 Defender.

## <a name="check-license-eligibility-and-required-permissions"></a>Comprobar la elegibilidad de la licencia y los permisos necesarios

Por lo general, una licencia de un producto de seguridad de Microsoft 365 le da derecho a usar Microsoft 365 Defender en el centro de seguridad de Microsoft 365 sin costo de licencia adicional. Recomendamos obtener una licencia de seguridad de Microsoft 365 E5, E5, A5 o A5 o una combinación válida de licencias que proporciona acceso a todos los servicios compatibles.

Para obtener información detallada sobre las licencias, [lea los requisitos de licencia](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Comprobar el rol

Debe ser un administrador **global o** un administrador **de seguridad** en Azure Active Directory para activar Microsoft 365 Defender. [Ver los roles en Azure AD](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Servicios compatibles

Microsoft 365 Defender agrega datos de los distintos servicios compatibles que ya ha implementado. Procesará y almacenará datos de forma centralizada para identificar nuevos conocimientos y hacer posibles los flujos de trabajo de respuesta centralizados. Lo hace sin afectar a las implementaciones, la configuración o los datos existentes asociados con los servicios integrados.

Para obtener la mejor protección y optimizar Microsoft 365 Defender, se recomienda implementar todos los servicios compatibles aplicables en la red. Para obtener más información, [lea acerca de la implementación de servicios compatibles.](deploy-supported-services.md)

## <a name="onboard-to-the-service"></a>Incorporación al servicio
La incorporación a Microsoft 365 Defender es sencilla. En el menú de navegación, seleccione cualquier elemento de la sección Puntos de conexión, como Incidentes, Búsqueda, Centro de acción o Análisis de amenazas para iniciar el proceso de incorporación. 

### <a name="data-center-location"></a>Ubicación del centro de datos

Microsoft 365 Defender almacenará y procesará datos en la misma ubicación usada por [Microsoft Defender para Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Si no tiene Microsoft Defender para endpoint, se selecciona automáticamente una nueva ubicación del centro de datos en función de la ubicación de los servicios de seguridad de Microsoft 365 activos. La ubicación del centro de datos seleccionada se muestra en la pantalla.

Seleccione **¿Necesita ayuda?** en el Centro de seguridad de Microsoft 365 para ponerse en contacto con el soporte técnico de Microsoft sobre el aprovisionamiento de Microsoft 365 Defender en una ubicación diferente del centro de datos.

> [!NOTE]
> Microsoft Defender para endpoint aprovisiona automáticamente en centros de datos de la Unión Europea (UE) cuando se activa a través de Azure Defender. Microsoft 365 Defender aprovisionará automáticamente en el mismo centro de datos de la UE a los clientes que han aprovisionado Defender para Endpoint de esta manera.

### <a name="confirm-that-the-service-is-on"></a>Confirme que el servicio está activado

Una vez que recibe el servicio, este agrega:

- [Administración de incidentes](incidents-overview.md)
- [Cola de alertas](investigate-alerts.md)
- Un centro de actividades para administrar [una investigación y respuestas automáticas](m365d-autoir.md)
- [Capacidades avanzadas de](advanced-hunting-overview.md) búsqueda
- Análisis de amenazas

![Imagen del panel de navegación del centro de seguridad de Microsoft 365 con Microsoft 365 Defender cuenta con el Centro de seguridad de Microsoft 365 con administración de incidentes y otras funcionalidades de ](../../media/overview-incident.png)
 *Microsoft 365 Defender*

### <a name="getting-microsoft-defender-for-identity-data"></a>Obtener datos de Microsoft Defender para identidades 
Para habilitar la integración con Microsoft Cloud App Security, tendrás que iniciar sesión en Microsoft Cloud App Security al menos una vez.

## <a name="get-assistance"></a>Cómo recibir asistencia

Para obtener respuestas a las preguntas más frecuentes sobre cómo activar Microsoft 365 Defender, [lea las preguntas más frecuentes](m365d-enable-faq.md).

El personal de soporte técnico de Microsoft puede ayudar a aprovisionar o desaprovisionar el servicio y los recursos relacionados en el espacio empresarial. Para obtener ayuda, seleccione **¿Necesita ayuda?** en el Centro de seguridad de Microsoft 365. Al ponerse en contacto con el soporte técnico, mencione Microsoft 365 Defender.

## <a name="related-topics"></a>Temas relacionados

- [Preguntas más frecuentes](m365d-enable-faq.md)
- [Requisitos de licencia y otros requisitos previos](prerequisites.md)
- [Implementación de servicios compatibles](deploy-supported-services.md)
- [Introducción a Microsoft 365 Defender](microsoft-365-defender.md)
- [Introducción a Microsoft Defender para puntos de conexión](../defender-endpoint/microsoft-defender-endpoint.md)
- [Información general de Defender para Office 365](../office-365-security/defender-for-office-365.md)
- [Introducción a Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)
- [Introducción a Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender para el almacenamiento de datos de punto de conexión](../defender-endpoint/data-storage-privacy.md)
