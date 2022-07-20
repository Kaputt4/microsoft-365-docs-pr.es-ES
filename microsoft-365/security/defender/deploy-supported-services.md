---
title: Implementación de servicios compatibles con Microsoft 365 Defender
description: Obtenga información sobre los servicios de seguridad de Microsoft que se pueden integrar mediante Microsoft 365 Defender, sus requisitos de licencia y los procedimientos de implementación.
keywords: deploy, licenses, supported services, provisioning, configuration Microsoft 365 Defender, M365, license eligibility, Microsoft Defender para punto de conexión, Microsoft Defender para Office 365, Microsoft Defender for Identity, Microsoft Cloud App Security, MCAS, E5, A5, EMS
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
ms.openlocfilehash: cf2e95a4d129280537f1d7a9d7dcf1b76b492ead
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2022
ms.locfileid: "66893779"
---
# <a name="deploy-supported-services"></a>Implementación de servicios compatibles

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-365-defender.md) integra varios servicios de seguridad de Microsoft para proporcionar funcionalidades centralizadas de detección, prevención e investigación frente a ataques sofisticados. En este artículo se describen los servicios admitidos, sus requisitos de licencia, las ventajas y limitaciones asociadas a la implementación de uno o varios servicios y vínculos a cómo puede implementarlos por completo individualmente.

## <a name="supported-services"></a>Servicios admitidos

Una licencia de seguridad Microsoft 365 E5, E5, A5 o A5 o una combinación válida de licencias proporciona acceso a los siguientes servicios admitidos y le da derecho a usar Microsoft 365 Defender. [Consulte requisitos de licencia](prerequisites.md#licensing-requirements)

| Servicio compatible | Descripción |
| ------ | ------ |
| Microsoft Defender para punto de conexión | Conjunto de aplicaciones de Endpoint Protection basado en potentes sensores de comportamiento, análisis en la nube e inteligencia sobre amenazas |
|Microsoft Defender para Office 365 | Protección avanzada para las aplicaciones y los datos en Office 365, incluidos el correo electrónico y otras herramientas de colaboración |
| Microsoft Defender for Identity | Defenderse de amenazas avanzadas, identidades en peligro y usuarios internos malintencionados mediante señales correlacionadas de Active Directory |
| Microsoft Defender for Cloud Apps | Identificar y combatir las ciberamenazas en los servicios en la nube de Microsoft y de terceros |

## <a name="deployed-services-and-functionality"></a>Servicios y funcionalidad implementados

Microsoft 365 Defender proporciona una mejor visibilidad, correlación y corrección a medida que implementa servicios más admitidos.

### <a name="benefits-of-full-deployment"></a>Ventajas de la implementación completa

Para obtener las ventajas completas de Microsoft 365 Defender, se recomienda implementar todos los servicios admitidos. Estas son algunas de las principales ventajas de la implementación completa:

- Los incidentes se identifican y correlacionan en función de las alertas y señales de evento de todos los sensores disponibles y las funcionalidades de análisis específicas del servicio.
- Los cuadernos de estrategias de investigación y corrección automatizadas (AIR) se aplican a varios tipos de entidad, incluidos dispositivos, buzones y cuentas de usuario.
- Se puede consultar un esquema de búsqueda avanzado más completo para los datos de eventos y entidades de dispositivos, buzones y otras entidades.

### <a name="limited-deployment-scenarios"></a>Escenarios de implementación limitados

Cada servicio compatible que implemente proporciona un conjunto extremadamente completo de señales sin procesar, así como información correlacionada. Aunque la implementación limitada no hace que Microsoft 365 Defender funcionalidad se desactive, su capacidad para proporcionar una visibilidad completa de los puntos de conexión, las aplicaciones, los datos y las identidades se ve afectada. Al mismo tiempo, las funcionalidades de corrección solo se aplican a las entidades que se pueden administrar mediante los servicios que ha implementado.

En la tabla siguiente se muestra cómo cada servicio compatible proporciona datos adicionales, oportunidades de obtener información adicional mediante la correlación de los datos y mejores funcionalidades de corrección y respuesta.

| Servicio | Datos (señales & información correlacionada) | Corrección & ámbito de respuesta |
| ------ | ------ | ------ |
| Microsoft Defender para punto de conexión |<ul><li>Estados de punto de conexión y eventos sin procesar</li><li>Detecciones y alertas de puntos de conexión, incluidos antivirus, EDR y reducción de la superficie expuesta a ataques</li><li>Información sobre archivos y otras entidades observadas en puntos de conexión</li></ul> | Puntos de conexión |
|Microsoft Defender para Office 365 |<ul><li>Estados de correo y buzón y eventos sin procesar</li><li>detecciones de Email, datos adjuntos y vínculos</li></ul> | <ul><li>Buzones</li><li>Cuentas de Microsoft 365</li></ul> |
| Microsoft Defender for Identity |<ul><li>Señales de Active Directory, incluidos los eventos de autenticación</li><li>Detecciones de comportamiento relacionadas con la identidad</li></ul> | Identidades |
| Microsoft Defender for Cloud Apps |<ul><li>Detección de servicios y aplicaciones en la nube no autorizadas (shadow IT)</li><li>Exposición de datos a aplicaciones en la nube</li><li>Actividad de amenazas asociada a aplicaciones en la nube</li></ul> | Aplicaciones en la nube |

## <a name="deploy-the-services"></a>Implementar los servicios

La implementación de cada servicio normalmente requiere el aprovisionamiento del espacio empresarial y alguna configuración inicial. Consulte la tabla siguiente para comprender cómo se implementa cada uno de estos servicios.

| Servicio | Instrucciones de aprovisionamiento | Configuración inicial |
| ------ | ------ | ------ |
| Microsoft Defender para punto de conexión | [Guía de implementación de Microsoft Defender para puntos de conexión](../defender-endpoint/deployment-phases.md) | *Ver instrucciones de aprovisionamiento* |
|Microsoft Defender para Office 365 | *Ninguno, aprovisionado con Office 365* | [Configurar las directivas de Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) |
| Microsoft Defender for Identity | [Inicio rápido: crear la instancia de Microsoft Defender for Identity](/azure-advanced-threat-protection/install-atp-step1) | *Ver instrucciones de aprovisionamiento* |
| Microsoft Defender for Cloud Apps | *Ninguna* | [Inicio rápido: Introducción a Microsof Defender for Cloud Apps](/cloud-app-security/getting-started-with-cloud-app-security) |

Una vez que haya implementado los servicios admitidos, [active Microsoft 365 Defender](m365d-enable.md).

## <a name="related-topics"></a>Temas relacionados

- [introducción a Microsoft 365 Defender](microsoft-365-defender.md)
- [Activar Microsoft 365 Defender](m365d-enable.md)
- [introducción a Microsoft Defender para punto de conexión](../defender-endpoint/microsoft-defender-endpoint.md)
- [introducción a Microsoft Defender para Office 365](../office-365-security/defender-for-office-365.md)
- [Introducción a Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)
- [introducción a Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp)
