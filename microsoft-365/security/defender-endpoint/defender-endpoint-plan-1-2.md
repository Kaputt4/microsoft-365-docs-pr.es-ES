---
title: Comparar planes de seguridad de puntos de conexión de Microsoft
description: Compare los planes de seguridad de puntos de conexión de Microsoft, como Defender para el plan de punto de conexión 1, con Defender para el plan de punto de conexión 2. Obtenga información sobre las diferencias entre los planes y seleccione el plan que se adapte a las necesidades de su organización.
keywords: Defender for Endpoint, advanced threat protection, endpoint protection, endpoint security, device security, cybersecurity
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 09/26/2022
ms.service: microsoft-365-security
ms.subservice: mde
ms.localizationpriority: medium
ms.reviewer: shlomi, efratka
f1.keywords: NOCSH
ms.collection:
- m365-security
- tier1
ms.openlocfilehash: 2d627357f4242d74fbec8a7d6a15925f60a32f63
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68180217"
---
# <a name="compare-microsoft-endpoint-security-plans"></a>Comparar planes de seguridad de puntos de conexión de Microsoft

Los planes de seguridad de los puntos de conexión de Microsoft, como Microsoft Defender para punto de conexión y Microsoft 365 Defender, se diseñaron para ayudar a las organizaciones empresariales a prevenir, detectar, investigar y responder a amenazas avanzadas. Microsoft Defender para Empresas y Microsoft 365 Empresa Premium proporcionan funcionalidades similares, optimizadas para pequeñas y medianas empresas. Estos planes proporcionan protección contra amenazas avanzada con protección antivirus y antimalware, mitigación de ransomware, etc., junto con la administración centralizada y la generación de informes. 

Este artículo ayuda a aclarar lo que se incluye en los siguientes planes: 

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [complemento Administración de vulnerabilidades de Microsoft Defender](../defender-vulnerability-management/index.yml)
- [Microsoft Defender para Empresas](../defender-business/mdb-overview.md) 

> [!IMPORTANT]
> En este artículo se proporciona un resumen de las funcionalidades de protección contra amenazas en los planes de seguridad de puntos de conexión de Microsoft; sin embargo, no está pensado para ser una descripción del servicio o un documento de contrato de licencia. Para obtener información más detallada, consulte los siguientes recursos:
> - [Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)
> - [Microsoft 365 Educación](/office365/servicedescriptions/office-365-platform-service-description/microsoft-365-education)

## <a name="compare-microsoft-endpoint-security-plans"></a>Comparar planes de seguridad de puntos de conexión de Microsoft

En la tabla siguiente se resume lo que se incluye en los planes de seguridad de puntos de conexión de Microsoft.

| Plan | ¿Qué se incluye? |
|:---|:---|
| [Plan 1 de Defender para punto de conexión](defender-endpoint-plan-1.md)  | <ul><li>[Protección de última generación](defender-endpoint-plan-1.md#next-generation-protection) (incluye antimalware y antivirus)</li><li>[Reducción de la superficie expuesta a ataques](defender-endpoint-plan-1.md#attack-surface-reduction)</li><li> [Acciones de contestación manual](defender-endpoint-plan-1.md#manual-response-actions)</li><li>[Administración centralizada](defender-endpoint-plan-1.md#centralized-management)</li><li>[Informes de seguridad](defender-endpoint-plan-1.md#reporting)</li><li>[API](defender-endpoint-plan-1.md#apis)</li><li>[Compatibilidad con dispositivos Windows 10, iOS, Android OS y macOS](defender-endpoint-plan-1.md#cross-platform-support)</li></ul>|
| [Plan 2 de Defender para punto de conexión](microsoft-defender-endpoint.md)  | Todas las funcionalidades del plan 1 de Defender para punto de conexión, además de:<ul><li>[Detección de dispositivo](device-discovery.md)</li><li>[Inventario de dispositivos](machines-view-overview.md)</li><li>[Funcionalidades de administración de vulnerabilidades de Core Defender](../defender-vulnerability-management/defender-vulnerability-management-capabilities.md)</li><li>[Análisis de amenazas](threat-analytics.md)</li><li>[Investigación y respuesta automatizadas](automated-investigations.md)</li><li>[Búsqueda avanzada de amenazas](advanced-hunting-overview.md)</li><li>[EDR](overview-endpoint-detection-response.md)</li><li>[Expertos en amenazas de Microsoft](microsoft-threat-experts.md)</li><li>Compatibilidad con [Windows](configure-endpoints.md) (cliente y servidor) y [plataformas que no son de Windows](configure-endpoints-non-windows.md) (macOS, iOS, Android y Linux)</li></ul> |
| [Complemento de Administración de vulnerabilidades de Defender](../defender-vulnerability-management/defender-vulnerability-management-capabilities.md) | Más funcionalidades de Administración de vulnerabilidades de Defender para Defender para el plan de punto de conexión 2:<ul><li>[Evaluación de líneas base de seguridad](../defender-vulnerability-management/tvm-security-baselines.md)</li><li>[Bloquear aplicaciones vulnerables](../defender-vulnerability-management/tvm-block-vuln-apps.md)</li><li>[Extensiones del explorador](../defender-vulnerability-management/tvm-browser-extensions.md)</li><li>[Evaluación de certificados digitales](../defender-vulnerability-management/tvm-certificate-inventory.md)</li><li>[Análisis de recursos compartidos de red](../defender-vulnerability-management/tvm-network-share-assessment.md)</li><li>Compatibilidad con [Windows](configure-endpoints.md) (cliente y servidor) y [plataformas que no son de Windows](configure-endpoints-non-windows.md) (macOS, iOS, Android y Linux)</li></ul> |
| [Defender para empresas](../defender-business/mdb-overview.md) <sup>[[1](#fn1)]</sup>  | [Los servicios optimizados para pequeñas y medianas empresas](../defender-business/compare-mdb-m365-plans.md) incluyen: <ul><li>protección Email</li><li>Protección contra correo no deseado</li><li>Protección antimalware</li><li>Protección de última generación</li><li>Reducción de la superficie expuesta a ataques</li><li>Detección y respuesta de puntos de conexión</li><li>Investigación y respuesta de amenazas </li><li>Administración de amenazas y vulnerabilidades</li><li>Informes centralizados</li><li>API (para la integración con aplicaciones personalizadas o soluciones de informes)</li><li>[Integración con Microsoft 365 Lighthouse](../defender-business/mdb-lighthouse-integration.md)</li></ul> |

(<a id="fn1">1</a>) Microsoft Defender para Empresas está disponible como una suscripción independiente para pequeñas y medianas empresas. También se incluye como parte de [Microsoft 365 Empresa Premium](/microsoft-365/business-premium). Estos planes incluyen funcionalidades de seguridad avanzadas con una experiencia de configuración y configuración simplificada. Consulte [Comparación de Microsoft Defender para Empresas con Microsoft 365 Empresa Premium](/microsoft-365/security/defender-business/compare-mdb-m365-plans#compare-microsoft-defender-for-business-to-microsoft-365-business-premium).

> [!TIP]
> Para obtener información más detallada, consulte los siguientes recursos:
> - [Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)
> - [Microsoft 365 Educación](/office365/servicedescriptions/office-365-platform-service-description/microsoft-365-education)

## <a name="options-for-onboarding-servers"></a>Opciones para la incorporación de servidores

Los planes 1 y 2 de Defender para punto de conexión (independiente), Defender para la empresa (independiente) y Microsoft 365 Empresa Premium no incluyen licencias de servidor. Para incorporar servidores, elija entre las siguientes opciones:

- **Microsoft Defender para el plan 1 o el plan 2** de servidores como parte de la oferta de [Defender for Cloud](/azure/defender-for-cloud/defender-for-cloud-introduction). Para obtener más información. consulte [Información general de Microsoft Defender para servidores](/azure/defender-for-cloud/defender-for-servers-introduction).
- **Microsoft Defender para Empresas servidores (versión preliminar)** para pequeñas y medianas empresas. Consulta [Cómo obtener servidores de Microsoft Defender para Empresas (versión preliminar).](../defender-business/get-defender-business-servers.md)

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

- Para probar Defender para punto de conexión, vaya a la [página de registro de prueba de Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?LinkID=2168109).
- Para probar el complemento de Administración de vulnerabilidades de Microsoft Defender para Defender para punto de conexión 2, visite [https://aka.ms/AddonPreviewTrial](https://aka.ms/AddonPreviewTrial). 

## <a name="see-also"></a>Vea también

- [Introducción a Microsoft Security (ofertas de prueba)](https://www.microsoft.com/security/business/get-started/start-free-trial)
- [Microsoft Defender para punto de conexión](microsoft-defender-endpoint.md)
- [Microsoft Defender para Empresas](../defender-business/mdb-overview.md) (endpoint protection para pequeñas y medianas empresas)
- [Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)
