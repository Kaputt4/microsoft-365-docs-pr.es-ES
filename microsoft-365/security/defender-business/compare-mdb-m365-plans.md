---
title: Comparación de características de seguridad en planes de Microsoft 365 para pequeñas y medianas empresas
description: ¿Cómo se compara Defender para empresas con Defender para punto de conexión y Microsoft 365 Empresa Premium? Vea lo que se incluye en cada plan para que pueda tomar una decisión más informada para su empresa.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: reference
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-initiative-defender-business
- m365-security-compliance
ms.openlocfilehash: be57910a1f6b2387a1b826e6cff17e418ec3da2b
ms.sourcegitcommit: 5463d4518c269d9c125bb66836a780df292b4854
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66795386"
---
# <a name="compare-security-features-in-microsoft-365-plans-for-small-and-medium-sized-businesses"></a>Comparación de características de seguridad en planes de Microsoft 365 para pequeñas y medianas empresas

Microsoft ofrece una amplia variedad de soluciones y servicios en la nube, incluidos planes para pequeñas y medianas empresas. Por ejemplo, [Microsoft 365 Empresa Premium](../../business/microsoft-365-business-overview.md) incluye funcionalidades de seguridad y administración de dispositivos, junto con características de productividad como las aplicaciones de Office. En este artículo se describen las características de seguridad de Microsoft 365 Empresa Premium, Microsoft Defender para Empresas y [Microsoft Defender para punto de conexión](../defender-endpoint/microsoft-defender-endpoint.md).


**Use este artículo para**:

- [Compare Defender para empresas (independiente) con Microsoft 365 Empresa Premium](#compare-security-features-in-microsoft-defender-for-business-to-microsoft-365-business-premium).
- [Compare Defender para empresas (independiente) con las ofertas empresariales de Defender para punto de conexión](#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2).

> [!TIP]
> Defender for Business está disponible como una solución de seguridad independiente para pequeñas y medianas empresas. También se incluye en Microsoft 365 Empresa Premium. Si ya tiene Microsoft 365 Empresa Básico o Estándar, considere la posibilidad de actualizar a Microsoft 365 Empresa Premium o agregar Defender for Business a su suscripción para obtener más funcionalidades de protección contra amenazas para los dispositivos.

## <a name="compare-security-features-in-microsoft-defender-for-business-to-microsoft-365-business-premium"></a>Compare las características de seguridad de Microsoft Defender para Empresas con Microsoft 365 Empresa Premium

> [!NOTE]
> En este artículo se proporciona información general de alto nivel sobre las características de protección contra amenazas incluidas en Microsoft Defender para Empresas (como un plan independiente) y Microsoft 365 Empresa Premium (que incluye Defender para empresas). No está pensado para ser una descripción del servicio o un documento de contrato de licencia. Para obtener información más detallada, consulte [Guía de licencias de Microsoft 365 para el cumplimiento de & de seguridad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

Defender for Business también está disponible como una suscripción independiente y también se incluye en Microsoft 365 Empresa Premium. En la tabla siguiente se comparan las características y funcionalidades de seguridad de Defender para empresas (independiente) con Microsoft 365 Empresa Premium.

|Característica o funcionalidad|[Microsoft Defender para Empresas](mdb-overview.md)<br/>(independiente)|[Microsoft 365 Empresa Premium](../../business/microsoft-365-business-overview.md)<br/>(incluye Defender para empresas)|
|---|---|---|
|protección Email|Sí <br/>[examen de Email con antivirus de Microsoft Defender](../defender-endpoint/configure-advanced-scan-types-microsoft-defender-antivirus.md)|Sí <ul><li>[Exchange Online Protection](../office-365-security/exchange-online-protection-overview.md)</li><li>[examen de Email con antivirus de Microsoft Defender](../defender-endpoint/configure-advanced-scan-types-microsoft-defender-antivirus.md)</li></ul>|
|Protección contra correo no deseado|Sí<br/>Para dispositivos|Sí <ul><li>Para dispositivos</li><li>Para contenido de correo electrónico de Microsoft 365, como mensajes y datos adjuntos</li></ul>|
|Protección antimalware|Sí<br/>Para dispositivos|Sí<ul><li>Para dispositivos</li><li>Para contenido de correo electrónico de Microsoft 365, como mensajes y datos adjuntos</li></ul>|
|[Protección de última generación](../defender-endpoint/microsoft-defender-antivirus-in-windows-10.md) <br/> (protección antivirus y antimalware para dispositivos incorporados)|Sí |Sí |
|[Reducción de la superficie expuesta a ataques](../defender-endpoint/overview-attack-surface-reduction.md) <br/>(Reglas de ASR en Windows 10 o versiones posteriores y protección del firewall)|Sí|Sí|
|[EDR](../defender-endpoint/overview-endpoint-detection-response.md) <br/>(detección basada en comportamiento y acciones de respuesta manual)|Sí|Sí|
|[Investigación y respuesta automatizadas](../defender-endpoint/automated-investigations.md)|Sí|Sí|
|[Administración de vulnerabilidades y amenazas](../defender-endpoint/tvm-dashboard-insights.md)|Sí|Sí|
|Administración centralizada e informes|Sí|Sí|
|[API](../defender-endpoint/apis-intro.md) <br/>(para la integración con aplicaciones personalizadas o soluciones de informes)|Sí|Sí|

## <a name="compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2"></a>Comparar Microsoft Defender para Empresas con los planes 1 y 2 de Microsoft Defender para punto de conexión

Defender for Business ofrece las funcionalidades de nivel empresarial de Defender para punto de conexión a pequeñas y medianas empresas. En la tabla siguiente se comparan las características y funcionalidades de seguridad de Defender para empresas con las ofertas empresariales, Microsoft Defender para punto de conexión los planes 1 y 2.

|Característica o funcionalidad|[Defender para Empresas](mdb-overview.md)<br/>(independiente)|[Plan 1 de Defender para punto de conexión](../defender-endpoint/defender-endpoint-plan-1.md)<br/>(para clientes empresariales) |[Plan 2 de Defender para punto de conexión](../defender-endpoint/microsoft-defender-endpoint.md)<br/>(para clientes empresariales) |
|---|---|---|---|
|[Administración centralizada](../defender-endpoint/manage-atp-post-migration.md) |Sí <sup>[[1](#fn1)]</sup>|Sí|Sí|
|[Configuración de cliente simplificada](mdb-simplified-configuration.md)|Sí|No|No|
|[Administración de vulnerabilidades y amenazas](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)|Sí|No|Sí|
|[Capacidades de reducción de superficie expuesta a ataques](../defender-endpoint/overview-attack-surface-reduction.md)|Sí|Sí|Sí|
|[Protección de última generación](../defender-endpoint/next-generation-protection.md)|Sí|Sí|Sí|
|[EDR](../defender-endpoint/overview-endpoint-detection-response.md)|Sí <sup>[[2](#fn2)]</sup>|No|Sí|
|[Investigación y respuesta automatizadas](../defender-endpoint/automated-investigations.md)|Sí <sup>[[3](#fn3)]</sup>|No|Sí|
|[Búsqueda de amenazas](../defender-endpoint/advanced-hunting-overview.md) y seis meses de retención de datos |No <sup>[[4](#fn4)]</sup>|No|Sí|
|[Análisis de amenazas](../defender-endpoint/threat-analytics.md)|Sí <sup>[[5](#fn5)]</sup>|No|Sí|
|[Compatibilidad multiplataforma.](../defender-endpoint/minimum-requirements.md) <br/>(Sistema operativo Windows, Mac, iOS y Android)|Sí <sup>[[6](#fn6)]</sup>|Sí|Sí|
|[Expertos en amenazas de Microsoft](../defender-endpoint/microsoft-threat-experts.md)|No|No|Sí|
|API de asociados|Sí|Sí|Sí|
|[integración Microsoft 365 Lighthouse](../../lighthouse/m365-lighthouse-overview.md) <br/>(Para ver los incidentes de seguridad entre los inquilinos del cliente)|Sí |Sí <sup>[[7](#fn7)]</sup>|Sí <sup>[[7](#fn7)]</sup>|

(<a id="fn1">1</a>) Incorporación y administración de dispositivos en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) o mediante Microsoft Intune, administrados en el Centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)).

(<a id="fn2">2</a>) Las funcionalidades de detección y respuesta de puntos de conexión (EDR) en Defender for Business incluyen la detección basada en comportamiento y las siguientes acciones de respuesta manual: 
- Ejecutar examen de antivirus
- Aislar el dispositivo
- Detener y poner en cuarentena un archivo
- Adición de un indicador para bloquear o permitir un archivo

(<a id="fn3">3</a>) En Defender para empresas, la investigación y la respuesta automatizadas están activadas de forma predeterminada, en todo el inquilino. Si desactiva la investigación y la respuesta automatizadas, esto afecta a la protección en tiempo real. Consulte [Revisión de la configuración de las características avanzadas](mdb-configure-security-settings.md#review-settings-for-advanced-features).  

(<a id="fn4">4</a>) No hay ninguna vista de escala de tiempo en Defender para empresas.

(<a id="fn5">5</a>) En Defender para empresas, el análisis de amenazas está optimizado para pequeñas y medianas empresas.

(<a id="fn6">6</a>) Consulte [Incorporación de dispositivos para Microsoft Defender para Empresas](mdb-onboard-devices.md).

(<a id="fn7">7</a>) La capacidad de ver incidentes entre inquilinos mediante Defender para punto de conexión es nueva.

## <a name="next-steps"></a>Siguientes pasos

- [Consulte los requisitos de Microsoft Defender para Empresas](mdb-requirements.md)
- [Obtener Microsoft Defender para Empresas](get-defender-business.md)
- [Aprenda a configurar y configurar Microsoft Defender para Empresas](mdb-setup-configuration.md)
