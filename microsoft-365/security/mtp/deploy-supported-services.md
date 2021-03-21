---
title: Implementar servicios compatibles con Microsoft 365 Defender
description: Obtenga información sobre los servicios de seguridad de Microsoft que Microsoft 365 Defender puede integrar, sus requisitos de licencia y los procedimientos de implementación
keywords: deploy, licenses, supported services, provisioning, configuration Microsoft Threat Protection, M365, license eligibility, Microsoft Defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud App Security, MCAS, advanced threat protection, E5, A5, EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3dce310dbfd8bd8debe9b6eb3015790073002bee
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928897"
---
# <a name="deploy-supported-services"></a>Implementación de servicios compatibles

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-threat-protection.md) integra varios servicios de seguridad de Microsoft para proporcionar capacidades centralizadas de detección, prevención e investigación contra ataques sofisticados. En este artículo se describen los servicios admitidos, sus requisitos de licencia, las ventajas y limitaciones asociadas con la implementación de uno o varios servicios y vínculos a cómo puede implementarlos completamente individualmente.

## <a name="supported-services"></a>Servicios compatibles
Una licencia de seguridad de Microsoft 365 E5, E5 Security, A5 o A5 o una combinación válida de licencias proporciona acceso a los siguientes servicios compatibles y le da derecho a usar Microsoft 365 Defender en el centro de seguridad de Microsoft 365. [Ver requisitos de licencias](prerequisites.md#licensing-requirements)

| Servicio compatible | Descripción |
| ------ | ------ |
| Microsoft Defender para punto de conexión | Conjunto de aplicaciones de protección de puntos de conexión que se basa en sensores de comportamiento eficaces, análisis en la nube e inteligencia de amenazas |
|Microsoft Defender para Office 365 | Protección avanzada para sus aplicaciones y datos en Office 365, incluido el correo electrónico y otras herramientas de colaboración |
| Microsoft Defender for Identity | Defenderse de amenazas avanzadas, identidades comprometidas e información interna malintencionada mediante señales correlacionadas de Active Directory |
| Microsoft Cloud App Security | Identificar y combatir ciberamenazas en los servicios en la nube de Microsoft y de terceros |

## <a name="deployed-services-and-functionality"></a>Funcionalidad y servicios implementados
Microsoft 365 Defender proporciona una mejor visibilidad, correlación y corrección a medida que implementa servicios más compatibles.

### <a name="benefits-of-full-deployment"></a>Ventajas de la implementación completa
Para obtener las ventajas completas de Microsoft 365 Defender, se recomienda implementar todos los servicios compatibles. Estas son algunas de las ventajas clave de la implementación completa:
- Los incidentes se identifican y correlacionan en función de las alertas y las señales de eventos de todos los sensores disponibles y las capacidades de análisis específicas del servicio
- Los playbooks de investigación y corrección automatizadas (AIR) se aplican en varios tipos de entidad, incluidos dispositivos, buzones y cuentas de usuario
- Se puede consultar un esquema de búsqueda avanzada más completo para los datos de eventos y entidades de dispositivos, buzones y otras entidades

### <a name="limited-deployment-scenarios"></a>Escenarios de implementación limitados
Cada servicio compatible que implemente proporciona un conjunto muy enriquecido de señales sin procesar, así como información correlacionada. Aunque la implementación limitada no hace que la funcionalidad de Microsoft 365 Defender se desactive, su capacidad para proporcionar visibilidad completa en los puntos de conexión, aplicaciones, datos e identidades se ve afectada. Al mismo tiempo, las capacidades de corrección solo se aplican a las entidades que los servicios que ha implementado pueden administrar.

En la tabla siguiente se muestra cómo cada servicio admitido proporciona datos adicionales, oportunidades para obtener información adicional mediante la correlación de los datos y mejores capacidades de corrección y respuesta.

| Servicio | Datos (señales & información correlacionada) | Ámbito de respuesta & corrección |
| ------ | ------ | ------ |
| Microsoft Defender para punto de conexión | - Estados de extremo y eventos sin procesar<br />- Detecciones y alertas de puntos de conexión, incluidos antivirus, EDR, reducción de superficie de ataque<br />- Información sobre archivos y otras entidades observadas en puntos de conexión | Puntos de conexión |
|Microsoft Defender para Office 365 | - Estados de correo y buzón de correo y eventos sin procesar<br />- Detecciones de correo electrónico, datos adjuntos y vínculos | - Buzones<br />- Cuentas de Microsoft 365 |
| Microsoft Defender for Identity | - Señales de Active Directory, incluidos los eventos de autenticación<br />- Detecciones de comportamiento relacionadas con la identidad | Identidades |
| Microsoft Cloud App Security | - Detección de servicios y aplicaciones en la nube no cedida (TECNOLOGÍA de la sombra)<br />- Exposición de datos a aplicaciones en la nube<br />- Actividad de amenazas asociada a aplicaciones en la nube | Aplicaciones en la nube |

## <a name="deploy-the-services"></a>Implementar los servicios
Por lo general, la implementación de cada servicio requiere el aprovisionamiento del espacio empresarial y alguna configuración inicial. Consulte la tabla siguiente para comprender cómo se implementan cada uno de estos servicios.

| Servicio | Instrucciones de aprovisionamiento | Configuración inicial |
| ------ | ------ | ------ |
| Microsoft Defender para punto de conexión | [Guía de implementación de Microsoft Defender para puntos de conexión](/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Ver instrucciones de aprovisionamiento* |
|Microsoft Defender para Office 365 | *Ninguno, aprovisionado con Office 365* | [Configurar las directivas de Microsoft Defender para Office 365](../office-365-security/office-365-atp.md#configure-atp-policies) |
| Microsoft Defender for Identity | [Inicio rápido: crear la instancia de Microsoft Defender for Identity](/azure-advanced-threat-protection/install-atp-step1) | *Ver instrucciones de aprovisionamiento* |
| Microsoft Cloud App Security | *Ninguna* | [Inicio rápido: Introducción a Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security) |

Una vez que haya implementado los servicios compatibles, [active Microsoft 365 Defender](mtp-enable.md).

## <a name="related-topics"></a>Temas relacionados

- [Introducción a Microsoft 365 Defender](microsoft-threat-protection.md)
- [Activar Microsoft 365 Defender](mtp-enable.md)
- [Introducción a Microsoft Defender para puntos de conexión](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Introducción a Microsoft Defender para Office 365](../office-365-security/office-365-atp.md)
- [Introducción a Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)
- [Introducción a Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp)