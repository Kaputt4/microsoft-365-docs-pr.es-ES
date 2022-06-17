---
title: Comparar planes de Microsoft Defender para punto de conexión
description: Compare el plan 1 de Defender para punto de conexión con el plan 2. Obtenga información sobre las diferencias entre los planes y seleccione el plan que se adapte a las necesidades de su organización.
keywords: Defender para punto de conexión, protección contra amenazas avanzada, endpoint protection
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 06/17/2022
ms.prod: m365-security
ms.technology: mdep1
ms.localizationpriority: medium
ms.reviewer: shlomi, efratka
f1.keywords: NOCSH
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: 00db46643d3f2b49003194075c44970a20ba83e9
ms.sourcegitcommit: 7ac54e1952383d5cd5f084c6a9d247eb747d4904
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2022
ms.locfileid: "66139439"
---
# <a name="compare-microsoft-defender-for-endpoint-plans"></a>Comparar planes de Microsoft Defender para punto de conexión

Microsoft Defender para punto de conexión es una plataforma empresarial para la seguridad de puntos de conexión concebida para ayudar a impedir, detectar e investigar las amenazas avanzadas, y responder a ellas. Defender para punto de conexión proporciona protección contra amenazas avanzada que incluye antivirus, antimalware, mitigación de ransomware, etc., junto con la administración centralizada y la generación de informes. Puede elegir entre las siguientes opciones para Microsoft Defender para punto de conexión:

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Administración de vulnerabilidades de Microsoft Defender](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Puede usar este artículo para ayudar a aclarar qué protección proporcionan las distintas características disponibles en El plan 1 de Defender para punto de conexión, El plan 2 de Defender para punto de conexión y el nuevo complemento De administración de vulnerabilidades de Defender.

## <a name="compare-defender-for-endpoint-plans"></a>Comparar planes de Defender para punto de conexión

En la tabla siguiente se resume lo que se incluye en cada plan de Defender para punto de conexión.

| Plan | ¿Qué se incluye? |
|:---|:---|
| [Plan 1 de Defender para punto de conexión](defender-endpoint-plan-1.md) | <ul><li>[Protección de última generación](defender-endpoint-plan-1.md#next-generation-protection) (incluye antimalware y antivirus)</li><li>[Reducción de la superficie expuesta a ataques](defender-endpoint-plan-1.md#attack-surface-reduction)</li><li> [Acciones de contestación manual](defender-endpoint-plan-1.md#manual-response-actions)</li><li>[Administración centralizada](defender-endpoint-plan-1.md#centralized-management)</li><li>[Informes de seguridad](defender-endpoint-plan-1.md#reporting)</li><li>[API](defender-endpoint-plan-1.md#apis)</li><li>[Compatibilidad con dispositivos Windows 10, iOS, sistema operativo Android y macOS](defender-endpoint-plan-1.md#cross-platform-support)</li></ul>|
| [Plan 2 de Defender para punto de conexión](microsoft-defender-endpoint.md) | Todas las funcionalidades del plan 1 de Defender para punto de conexión, además de:<ul><li>[Detección de dispositivo](device-discovery.md)</li><li>[Inventario de dispositivos](machines-view-overview.md)</li><li>[Funcionalidades de administración de vulnerabilidades de Core Defender](../defender-vulnerability-management/defender-vulnerability-management-capabilities.md)</li><li>[Análisis de amenazas](threat-analytics.md)</li><li>[Investigación y respuesta automatizadas](automated-investigations.md)</li><li>[Búsqueda avanzada de amenazas](advanced-hunting-overview.md)</li><li>[EDR](overview-endpoint-detection-response.md)</li><li>[Expertos en amenazas de Microsoft](microsoft-threat-experts.md)</li><li>Compatibilidad con [plataformas Windows](configure-endpoints.md) (cliente y servidor) y [no Windows](configure-endpoints-non-windows.md) (macOS, iOS, Android y Linux)</li></ul> |
| [Complemento de Administración de vulnerabilidades de Defender](../defender-vulnerability-management/defender-vulnerability-management-capabilities.md) | Administración adicional de vulnerabilidades de Defender para Defender para el plan de punto de conexión 2:<ul><li>[Evaluación de líneas base de seguridad](../defender-vulnerability-management/tvm-security-baselines.md)</li><li>[Bloquear aplicaciones vulnerables](../defender-vulnerability-management/tvm-block-vuln-apps.md)</li><li>[Extensiones del explorador](../defender-vulnerability-management/tvm-browser-extensions.md)</li><li>[Evaluación de certificados digitales](../defender-vulnerability-management/tvm-certificate-inventory.md)</li><li>[Análisis de recursos compartidos de red](../defender-vulnerability-management/tvm-network-share-assessment.md)</li><li>Compatibilidad con [plataformas Windows](configure-endpoints.md) (cliente y servidor) y [no Windows](configure-endpoints-non-windows.md) (macOS, iOS, Android y Linux)</li></ul> |

## <a name="mixed-licensing-scenarios"></a>Escenarios de licencias mixtas

Supongamos que su organización usa una combinación de suscripciones de seguridad de puntos de conexión de Microsoft, como Defender para el plan 1 de punto de conexión y El plan 2 de Defender para punto de conexión. **Actualmente, la suscripción de seguridad de punto de conexión de Microsoft más funcional establece la experiencia del inquilino**. En este ejemplo, la experiencia del inquilino sería defender para el plan 2 de punto de conexión para todos los usuarios.

Sin embargo, **puede ponerse en contacto con el soporte técnico y solicitar una invalidación para la experiencia del inquilino**. Es decir, podría solicitar una invalidación para mantener la experiencia del plan 1 de Defender para punto de conexión para todos los usuarios. 

- Para obtener más información sobre las licencias y los términos del producto, consulte [Licencias y términos de producto para suscripciones de Microsoft 365](https://www.microsoft.com/licensing/terms/productoffering/Microsoft365/MCA).
- Para obtener información sobre cómo ponerse en contacto con el soporte técnico, consulte [Póngase en contacto con el soporte técnico de Microsoft Defender para punto de conexión](contact-support.md).

> [!TIP]
> Si su organización es una pequeña o mediana empresa, consulte los artículos siguientes:
> - [¿Qué es Microsoft Defender para Empresas?](../defender-business/mdb-overview.md)
> - [Comparar las características de seguridad de los planes de Microsoft 365 para pequeñas y medianas empresas](../defender-business/compare-mdb-m365-plans.md).

## <a name="start-a-trial"></a>Inicio de una prueba

- Para probar el plan 1 de Defender para punto de conexión, visite [https://aka.ms/mdep1trial](https://aka.ms/mdep1trial).
- Para probar el plan 2 de Defender para punto de conexión, visite [https://aka.ms/MDEp2OpenTrial](https://aka.ms/MDEp2OpenTrial).
- Para probar el complemento Administración de vulnerabilidades de Microsoft Defender, visite [https://aka.ms/AddonPreviewTrial](https://aka.ms/AddonPreviewTrial). 

## <a name="see-also"></a>Vea también

- [Microsoft Defender para Empresas](../defender-business/mdb-overview.md) (endpoint protection para pequeñas y medianas empresas)