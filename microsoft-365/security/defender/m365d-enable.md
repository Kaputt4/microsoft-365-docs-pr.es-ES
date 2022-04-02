---
title: Activar Microsoft 365 Defender
description: Obtenga información sobre cómo habilitar Microsoft 365 Defender y empezar a integrar el incidente de seguridad y la respuesta.
keywords: get started, enable Microsoft 365 Defender, Microsoft 365 Defender, M365, security, data location, required permissions, license eligibility, settings page
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2a99dbaf50b582df4203fc9c8e1d04e0a3f6d807
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2022
ms.locfileid: "64498664"
---
# <a name="turn-on-microsoft-365-defender"></a>Activar Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md) unifica el proceso de respuesta a incidentes integrando funciones clave en Microsoft Defender para endpoint, Microsoft Defender para Office 365, Microsoft Defender para aplicaciones en la nube y Microsoft Defender para identidad. Esta experiencia unificada agrega características eficaces a las que puede tener acceso en el portal Microsoft 365 Defender web.

Microsoft 365 Defender se activa automáticamente cuando los clientes elegibles con los permisos necesarios visitan Microsoft 365 Defender portal. Lea este artículo para comprender varios requisitos previos y cómo Microsoft 365 Defender se aprovisiona.

## <a name="check-license-eligibility-and-required-permissions"></a>Comprobar la elegibilidad de la licencia y los permisos necesarios

Una licencia de un Microsoft 365 de seguridad por lo general le da derecho a usar Microsoft 365 Defender sin costo de licencia adicional. Se recomienda obtener una Microsoft 365 E5, una licencia de seguridad de E5, A5 o A5 o una combinación válida de licencias que proporciona acceso a todos los servicios compatibles.

Para obtener información detallada sobre las licencias, [lee los requisitos de licencia](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Comprobar el rol

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

[Ver los roles en Azure AD](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Servicios compatibles

Microsoft 365 Defender agrega datos de los distintos servicios compatibles que ya ha implementado. Procesará y almacenará los datos de forma centralizada para identificar nuevas conclusiones y hacer posibles flujos de trabajo de respuesta centralizados. Lo hace sin afectar a las implementaciones, la configuración o los datos existentes asociados a los servicios integrados.

Para obtener la mejor protección y optimizar Microsoft 365 Defender, se recomienda implementar todos los servicios compatibles aplicables en la red. Para obtener más información, [lea acerca de la implementación de servicios compatibles](deploy-supported-services.md).

## <a name="onboard-to-the-service"></a>Incorporación al servicio
La incorporación a Microsoft 365 Defender es sencilla. En el menú de navegación, seleccione cualquier elemento, como incidentes **& alertas****, búsqueda****, centro** de acción o análisis de amenazas  para iniciar el proceso de incorporación. 

### <a name="data-center-location"></a>Ubicación del centro de datos

Microsoft 365 Defender almacenará y procesará datos en la [misma ubicación usada por Microsoft Defender para Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Si no tiene Microsoft Defender para endpoint, se selecciona automáticamente una nueva ubicación del centro de datos en función de la ubicación de los servicios de seguridad Microsoft 365 seguridad. La ubicación del centro de datos seleccionada se muestra en la pantalla.

Seleccione **¿Necesita ayuda?** en el portal de Microsoft 365 Defender para ponerse en contacto con el soporte técnico de Microsoft sobre el Microsoft 365 Defender en una ubicación diferente del centro de datos.

> [!NOTE]
> En el pasado, Microsoft Defender para Endpoint se aprovisionaba automáticamente en centros de datos de la Unión Europea (UE) cuando se activaba a través de Microsoft Defender para la nube. Microsoft 365 Defender aprovisionará automáticamente en el mismo centro de datos de la UE para los clientes que han aprovisionado Defender for Endpoint de esta manera en el pasado.

### <a name="confirm-that-the-service-is-on"></a>Confirme que el servicio está activado

Una vez que recibe el servicio, este agrega:

- [Administración de incidentes](incidents-overview.md)
- [Cola de alertas](investigate-alerts.md)
- Un centro de actividades para administrar [una investigación y respuestas automáticas](m365d-autoir.md)
- [Capacidades avanzadas de](advanced-hunting-overview.md) búsqueda
- Análisis de amenazas

:::image type="content" source="../../media/overview-incident.png" alt-text="El panel de navegación del portal Microsoft 365 Defender con Microsoft 365 Defender características" lightbox="../../media/overview-incident.png":::
*Microsoft 365 Defender portal con administración de incidentes y otras funcionalidades*

### <a name="getting-microsoft-defender-for-identity-data"></a>Obtener datos de Microsoft Defender para identidades 
Para habilitar la integración con Microsoft Defender para aplicaciones en la nube, tendrás que iniciar sesión en Microsoft Defender para Aplicaciones en la nube al menos una vez.

## <a name="get-assistance"></a>Cómo recibir asistencia

Para obtener respuestas a las preguntas más frecuentes sobre cómo activar Microsoft 365 Defender, [lea las preguntas más frecuentes](m365d-enable-faq.md).

El personal de soporte técnico de Microsoft puede ayudar a aprovisionar o desaprovisionar el servicio y los recursos relacionados en el espacio empresarial. Para obtener ayuda, seleccione **¿Necesita ayuda?** en Microsoft 365 Defender portal. Al ponerse en contacto con el soporte técnico, Microsoft 365 Defender.

## <a name="related-topics"></a>Temas relacionados

- [Preguntas más frecuentes](m365d-enable-faq.md)
- [Requisitos de licencia y otros requisitos previos](prerequisites.md)
- [Implementación de servicios compatibles](deploy-supported-services.md)
- [Microsoft 365 Defender información general](microsoft-365-defender.md)
- [Introducción a Microsoft Defender para puntos de conexión](../defender-endpoint/microsoft-defender-endpoint.md)
- [Información general Office 365 defender para Office 365 información general](../office-365-security/defender-for-office-365.md)
- [Introducción a Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)
- [Introducción a Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender para el almacenamiento de datos de punto de conexión](../defender-endpoint/data-storage-privacy.md)
