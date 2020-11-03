---
title: Implementación de servicios compatibles con Microsoft 365 defender
description: Obtenga información sobre los servicios de seguridad de Microsoft que se pueden integrar con Microsoft 365 defender, sus requisitos de licencia y los procedimientos de implementación.
keywords: implementación, licencias, servicios admitidos, aprovisionamiento, configuración de la protección contra amenazas de Microsoft, M365, elegibilidad de licencias, ATP de Microsoft defender, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud App Security, MCAS, protección contra amenazas avanzada, E5, A5, EMS
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 4a1bed4d6c6688c266b9df8ce36e4b25a0632d68
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843929"
---
# <a name="deploy-supported-services"></a>Implementación de servicios compatibles

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 defender](microsoft-threat-protection.md) integra varios servicios de seguridad de Microsoft para proporcionar capacidades de detección, prevención e investigación centralizadas frente a ataques sofisticados. En este artículo se describen los servicios compatibles, sus requisitos de licencia, las ventajas y las limitaciones asociadas con la implementación de uno o más servicios, y vínculos a cómo puede implementarlos por completo de forma individual.

## <a name="supported-services"></a>Servicios admitidos
Una licencia de seguridad de Microsoft 365 E5, E5 Security, A5 o a5 o una combinación válida de licencias proporciona acceso a los siguientes servicios admitidos y le da derecho a usar Microsoft 365 defender en el centro de seguridad de Microsoft 365. [Ver requisitos de licencia](prerequisites.md#licensing-requirements)

| Servicio compatible | Description |
| ------ | ------ |
| Microsoft Defender para punto de conexión | Conjunto de aplicaciones de Endpoint Protection creado alrededor de sensores de comportamiento poderosos, análisis de nube e inteligencia de amenazas |
|Microsoft defender para Office 365 | Protección avanzada de sus aplicaciones y datos en Office 365, incluido el correo electrónico y otras herramientas de colaboración |
| Microsoft Defender for Identity | Protección contra amenazas avanzadas, identidades en peligro e Insiders malintencionados mediante señales de Active Directory correlacionadas |
| Microsoft Cloud App Security | Identificar y combatir ciberamenazas en los servicios en la nube de Microsoft y de terceros |

## <a name="deployed-services-and-functionality"></a>Servicios y funciones implementados
Microsoft 365 defender proporciona mejor visibilidad, correlación y corrección a medida que se implementan más servicios admitidos.

### <a name="benefits-of-full-deployment"></a>Ventajas de la implementación completa
Para obtener las ventajas completas de Microsoft 365 defender, recomendamos implementar todos los servicios admitidos. Estas son algunas de las ventajas clave de la implementación completa:
- Los incidentes se identifican y correlacionan en función de las alertas y las señales de eventos de todos los sensores disponibles y las capacidades de análisis específicas del servicio.
- Las guías de investigación y corrección automatizada (AIR) se aplican en diversos tipos de entidad, incluidos los dispositivos, los buzones de correo y las cuentas de usuario.
- Se puede consultar un esquema de búsqueda avanzada más completo para obtener datos de eventos y entidades de dispositivos, buzones de correo y otras entidades.

### <a name="limited-deployment-scenarios"></a>Escenarios de implementación limitados
Cada servicio compatible que implemente proporciona un conjunto muy rico de señales sin procesar, así como información correlacionada. Aunque la implementación limitada no produce la desactivación de la funcionalidad de Microsoft 365 defender, se ve afectada su capacidad para proporcionar una visibilidad completa en los extremos, las aplicaciones, los datos y las identidades. Al mismo tiempo, las capacidades de corrección solo se aplican a las entidades que se pueden administrar con los servicios que ha implementado.

En la tabla siguiente se muestra cómo cada servicio compatible proporciona datos adicionales, oportunidades para obtener más información mediante la correlación de los datos y mejores capacidades de corrección y respuesta.

| Servicio | Datos (señales & información relacionada) | Ámbito de respuesta & de corrección |
| ------ | ------ | ------ |
| Microsoft Defender para punto de conexión | -Estados de punto de conexión y eventos sin procesar<br />-Detección de puntos de conexión y alertas, incluidos antivirus, EDR y reducción de superficie de ataques<br />-Información sobre los archivos y otras entidades observadas en los puntos de conexión | Puntos de conexión |
|Microsoft defender para Office 365 | -Estados de correo y de buzón y eventos sin procesar<br />-Detecciones de correo electrónico, datos adjuntos y vínculos | -Buzones de correo<br />-Cuentas de 365 de Microsoft |
| Microsoft Defender for Identity | -Señales de Active Directory, incluidos los eventos de autenticación<br />-Detecciones de comportamiento relacionadas con la identidad | Identidades |
| Microsoft Cloud App Security | -Detección de servicios y aplicaciones en la nube no autorizados (Sombrear)<br />-Exposición de datos a aplicaciones en la nube<br />-Actividad de amenaza asociada con las aplicaciones en la nube | Aplicaciones en la nube |

## <a name="deploy-the-services"></a>Implementación de los servicios
La implementación de cada servicio suele requerir un aprovisionamiento para el inquilino y una configuración inicial. Vea la siguiente tabla para comprender cómo se implementa cada uno de estos servicios.

| Servicio | Instrucciones de aprovisionamiento | Configuración inicial |
| ------ | ------ | ------ |
| Microsoft Defender para punto de conexión | [Guía de implementación de Microsoft defender para extremo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Consulte instrucciones de aprovisionamiento* |
|Microsoft defender para Office 365 | *Ninguno, aprovisionado con Office 365* | [Configurar las directivas de Microsoft defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Microsoft Defender for Identity | [Inicio rápido: crear su Microsoft defender para una instancia de identidad](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Consulte instrucciones de aprovisionamiento* |
| Microsoft Cloud App Security | *Ninguna* | [Inicio rápido: Introducción a Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

Una vez que haya implementado los servicios compatibles, [Active Microsoft 365 defender](mtp-enable.md).

## <a name="related-topics"></a>Temas relacionados

- [Información general de Microsoft 365 defender](microsoft-threat-protection.md)
- [Activar Microsoft 365 defender](mtp-enable.md)
- [Información general de Microsoft defender para Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Información general de Microsoft defender para Office 365](../office-365-security/office-365-atp.md)
- [Introducción a Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Información general de Microsoft defender para identidad](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
