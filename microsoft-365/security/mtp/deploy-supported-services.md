---
title: Implementación de servicios compatibles con la protección contra amenazas de Microsoft
description: Obtenga información sobre los servicios de seguridad de Microsoft que se pueden integrar con la protección contra amenazas de Microsoft, sus requisitos de licencia y los procedimientos de implementación
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 2b0e033bb80fd73d5b5194bd59ab9c9f14a644b3
ms.sourcegitcommit: cc3b64a91e16ccdaa9c338b9a9056dbe3963ba9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2020
ms.locfileid: "42569051"
---
# <a name="deploy-supported-services"></a>Implementación de servicios compatibles

**Se aplica a:**
- Protección contra amenazas de Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft Threat Protection](microsoft-threat-protection.md) integra varios servicios de seguridad de Microsoft para proporcionar capacidades de detección, prevención e investigación centralizadas frente a ataques sofisticados. En este artículo se describen los servicios compatibles, sus requisitos de licencia, las ventajas y las limitaciones asociadas con la implementación de uno o más servicios, y vínculos a cómo puede implementarlos por completo de forma individual.

## <a name="supported-services"></a>Servicios admitidos
Una [licencia de microsoft 365 E5, E5 o a5 o una combinación válida de licencias](prerequisites.md#licensing-requirements) proporciona acceso a los siguientes servicios admitidos y le da derecho a usar la protección contra amenazas de Microsoft en el centro de seguridad de Microsoft 365.

| Servicio compatible | Description |
| ------ | ------ |
| ATP de Microsoft Defender | Conjunto de aplicaciones de Endpoint Protection creado alrededor de sensores de comportamiento poderosos, análisis de nube e inteligencia de amenazas |
| ATP de Office 365 | Protección avanzada de sus aplicaciones y datos en Office 365, incluido el correo electrónico y otras herramientas de colaboración |
| Azure ATP | Protección contra amenazas avanzadas, identidades en peligro e Insiders malintencionados mediante señales de Active Directory correlacionadas |
| Microsoft Cloud App Security | Identifica y combate ciberamenazas en los servicios en la nube de Microsoft y de terceros |

## <a name="deployed-services-and-functionality"></a>Servicios y funciones implementados
La protección contra amenazas de Microsoft proporciona mejor visibilidad, correlación y corrección a medida que se implementan más servicios admitidos.

### <a name="benefits-of-full-deployment"></a>Ventajas de la implementación completa
Para obtener las ventajas completas de la protección contra amenazas de Microsoft, recomendamos implementar todos los servicios admitidos. Estas son algunas de las ventajas clave de la implementación completa:
- Los incidentes se identifican y correlacionan en función de las alertas y las señales de eventos de todos los sensores disponibles y las capacidades de análisis específicas del servicio.
- Las guías de investigación y corrección automatizada (AIR) se aplican en diversos tipos de entidad, incluidos los dispositivos, los buzones de correo y las cuentas de usuario.
- Se puede consultar un esquema de búsqueda avanzada más completo para obtener datos de eventos y entidades de dispositivos, buzones de correo y otras entidades.

### <a name="limited-deployment-scenarios"></a>Escenarios de implementación limitados
Cada servicio compatible que implemente proporciona un conjunto muy rico de señales sin procesar, así como información correlacionada. Aunque la implementación limitada no causa la desactivación de la funcionalidad de la protección contra amenazas de Microsoft, se ve afectada su capacidad de proporcionar una visibilidad completa en los extremos, las aplicaciones, los datos y las identidades. Al mismo tiempo, las capacidades de corrección solo se aplican a las entidades que se pueden administrar con los servicios que ha implementado.

En la tabla siguiente se muestra cómo cada servicio compatible proporciona datos adicionales, oportunidades para obtener más información mediante la correlación de los datos y mejores capacidades de corrección y respuesta.

| Servicio | Datos (señales & información relacionada) | Ámbito de respuesta & de corrección |
| ------ | ------ | ------ |
| ATP de Microsoft Defender | -Estados de punto de conexión y eventos sin procesar<br />-Detección de puntos de conexión y alertas, incluidos antivirus, EDR y reducción de superficie de ataques<br />-Información sobre los archivos y otras entidades observadas en los puntos de conexión | Extremos |
| ATP de Office 365 | -Estados de correo y de buzón y eventos sin procesar<br />-Detecciones de correo electrónico, datos adjuntos y vínculos | -Buzones de correo<br />-Office 365 cuentas |
| Azure ATP | -Señales de Active Directory, incluidos los eventos de autenticación<br />-Detecciones de comportamiento relacionadas con la identidad | Identidades |
| Microsoft Cloud App Security | -Detección de servicios & de aplicaciones en la nube no autorizados (Sombrear)<br />-Exposición de datos a aplicaciones en la nube<br />-Actividad de amenazas relacionadas con aplicaciones en la nube | Aplicaciones en la nube |

## <a name="deploy-the-services"></a>Implementación de los servicios
La implementación de cada servicio suele requerir un aprovisionamiento para el inquilino y una configuración inicial. Vea la siguiente tabla para comprender cómo se implementa cada uno de estos servicios.

| Servicio | Instrucciones de aprovisionamiento | Configuración inicial |
| ------ | ------ | ------ |
| ATP de Microsoft Defender | [Validar el aprovisionamiento de licencias y la configuración completa para Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/licensing) | *Consulte instrucciones de aprovisionamiento* |
| ATP de Office 365 | *Ninguno, aprovisionado con Office 365* | [Configurar directivas ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Azure ATP | [Inicio rápido: crear una instancia de ATP de Azure](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Consulte instrucciones de aprovisionamiento* |
| Microsoft Cloud App Security | *Ninguna* | [Inicio rápido: Introducción a Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

Una vez que haya implementado los servicios compatibles, [Active la protección contra amenazas de Microsoft](mtp-enable.md).

## <a name="related-topics"></a>Temas relacionados

- [Introducción a la Protección contra amenazas de Microsoft](microsoft-threat-protection.md)
- [Habilitar la Protección contra amenazas de Microsoft](mtp-enable.md)
- [Introducción al ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Introducción al ATP de Office 365](../office-365-security/office-365-atp.md)
- [Introducción a Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Introducción al ATP de Azure](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
