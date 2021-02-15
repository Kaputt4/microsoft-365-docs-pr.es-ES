---
title: Implementar servicios compatibles con Microsoft 365 Defender
description: Obtenga información sobre los servicios de seguridad de Microsoft que Microsoft 365 Defender puede integrar, sus requisitos de licencia y los procedimientos de implementación
keywords: implementar, licencias, servicios admitidos, aprovisionamiento, configuración de Protección contra amenazas de Microsoft, M365, elegibilidad de licencia, ATP de Microsoft Defender, MDATP, ATP de Office 365, Azure ATP, Microsoft Cloud App Security, MCAS, protección contra amenazas avanzada, E5, A5, EMS
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
ms.openlocfilehash: 5af58a1c6850619ca08960997a30fe4a81158446
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928967"
---
# <a name="deploy-supported-services"></a>Implementación de servicios compatibles

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender integra](microsoft-threat-protection.md) varios servicios de seguridad de Microsoft para proporcionar capacidades centralizadas de detección, prevención e investigación contra ataques sofisticados. En este artículo se describen los servicios admitidos, sus requisitos de licencia, las ventajas y limitaciones asociadas con la implementación de uno o más servicios y vínculos a cómo puede implementarlos por completo de forma individual.

## <a name="supported-services"></a>Servicios admitidos
Una licencia de Seguridad de Microsoft 365 E5, Seguridad E5, A5 o A5 o una combinación válida de licencias proporciona acceso a los siguientes servicios admitidos y le da derecho a usar Microsoft 365 Defender en el Centro de seguridad de Microsoft 365. [Ver requisitos de licencia](prerequisites.md#licensing-requirements)

| Servicio compatible | Description |
| ------ | ------ |
| Microsoft Defender para punto de conexión | Conjunto de aplicaciones de Endpoint Protection creado en torno a potentes sensores de comportamiento, análisis en la nube e inteligencia de amenazas |
|Microsoft Defender para Office 365 | Protección avanzada para sus aplicaciones y datos en Office 365, incluido el correo electrónico y otras herramientas de colaboración |
| Microsoft Defender for Identity | Defenderse contra amenazas avanzadas, identidades comprometidas e información interna malintencionada mediante señales correlacionadas de Active Directory |
| Microsoft Cloud App Security | Identificar y combatir ciberamenazas en los servicios en la nube de Microsoft y de terceros |

## <a name="deployed-services-and-functionality"></a>Funcionalidad y servicios implementados
Microsoft 365 Defender proporciona una mejor visibilidad, correlación y corrección a medida que implementa servicios más compatibles.

### <a name="benefits-of-full-deployment"></a>Ventajas de la implementación completa
Para obtener todas las ventajas de Microsoft 365 Defender, se recomienda implementar todos los servicios compatibles. Estas son algunas de las ventajas clave de la implementación completa:
- Los incidentes se identifican y correlacionan en función de las alertas y señales de eventos de todos los sensores disponibles y de las capacidades de análisis específicas del servicio.
- Las guías de reproducción automatizadas de investigación y corrección (AIR) se aplican en varios tipos de entidad, incluidos dispositivos, buzones de correo y cuentas de usuario.
- Se puede consultar un esquema de búsqueda avanzada más completo para obtener datos de eventos y entidades de dispositivos, buzones y otras entidades.

### <a name="limited-deployment-scenarios"></a>Escenarios de implementación limitados
Cada servicio compatible que implemente proporciona un conjunto muy completo de señales sin procesar, así como información correlacionada. Aunque la implementación limitada no hace que la funcionalidad de Microsoft 365 Defender se desactive, su capacidad para proporcionar visibilidad completa en los puntos de conexión, las aplicaciones, los datos y las identidades se ve afectada. Al mismo tiempo, las capacidades de corrección solo se aplican a las entidades que pueden ser administradas por los servicios que ha implementado.

En la tabla siguiente se muestra cómo cada servicio compatible proporciona datos adicionales, oportunidades para obtener información adicional mediante la correlación de los datos y mejores capacidades de corrección y respuesta.

| Servicio | Datos (señales & información correlacionada) | Ámbito de respuesta & corrección |
| ------ | ------ | ------ |
| Microsoft Defender para punto de conexión | - Estados de extremo y eventos sin procesar<br />- Detecciones y alertas de puntos de conexión, como antivirus, EDR, reducción de superficie de ataque<br />- Información sobre archivos y otras entidades observadas en los puntos de conexión | Puntos de conexión |
|Microsoft Defender para Office 365 | - Estados de correo y buzón de correo y eventos sin procesar<br />- Detecciones de correo electrónico, datos adjuntos y vínculos | - Buzones<br />- Cuentas de Microsoft 365 |
| Microsoft Defender for Identity | - Señales de Active Directory, incluidos los eventos de autenticación<br />- Detecciones de comportamiento relacionadas con la identidad | Identidades |
| Microsoft Cloud App Security | - Detección de servicios y aplicaciones en la nube no disponibles (SHADOW IT)<br />- Exposición de datos a aplicaciones en la nube<br />- Actividad de amenazas asociada a aplicaciones en la nube | Aplicaciones en la nube |

## <a name="deploy-the-services"></a>Implementar los servicios
La implementación de cada servicio normalmente requiere el aprovisionamiento al inquilino y alguna configuración inicial. Consulte la tabla siguiente para comprender cómo se implementa cada uno de estos servicios.

| Servicio | Instrucciones de aprovisionamiento | Configuración inicial |
| ------ | ------ | ------ |
| Microsoft Defender para punto de conexión | [Guía de implementación de Microsoft Defender para puntos de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Ver instrucciones de aprovisionamiento* |
|Microsoft Defender para Office 365 | *Ninguno, aprovisionado con Office 365* | [Configurar las directivas de Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Microsoft Defender for Identity | [Inicio rápido: crear la instancia de Microsoft Defender para Identidad](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Ver instrucciones de aprovisionamiento* |
| Microsoft Cloud App Security | *Ninguna* | [Inicio rápido: Introducción a Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

Una vez que haya implementado los servicios compatibles, [active Microsoft 365 Defender.](mtp-enable.md)

## <a name="related-topics"></a>Temas relacionados

- [Introducción a Microsoft 365 Defender](microsoft-threat-protection.md)
- [Activar Microsoft 365 Defender](mtp-enable.md)
- [Introducción a Microsoft Defender para puntos de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Introducción a Microsoft Defender para Office 365](../office-365-security/office-365-atp.md)
- [Introducción a Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Introducción a Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
