---
title: Comparación de características de seguridad en planes de Microsoft 365 para pequeñas y medianas empresas
description: Comprenda las diferencias entre Defender para empresas y Defender para punto de conexión. Conocer lo que se incluye en cada plan puede ayudarle a tomar una decisión informada para su empresa.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: reference
ms.date: 04/12/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-initiative-defender-business
- m365-security-compliance
ms.openlocfilehash: b1dbe79aadea39bfc737ae9f5457715b669cc79b
ms.sourcegitcommit: e3bc6563037bd2cce2abf108b3d1bcc2ccf538f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2022
ms.locfileid: "64861826"
---
# <a name="compare-microsoft-defender-for-business-to-microsoft-365-business-premium"></a>Comparar Microsoft Defender para Empresas con Microsoft 365 Empresa Premium

> [!IMPORTANT]
> Microsoft Defender para Empresas se está implementando para [Microsoft 365 Empresa Premium](../../business-premium/index.md) clientes, a partir del 1 de marzo de 2022. Defender for Business como una suscripción independiente está en versión preliminar y se implementará gradualmente para los clientes y asociados de TI que [se registren aquí](https://aka.ms/mdb-preview) para solicitarla. La versión preliminar incluye un [conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y vamos a agregar funcionalidades con regularidad.
>
> Parte de la información de este artículo se refiere a los productos o servicios preliminares que se pueden modificar sustancialmente antes de que se publiquen comercialmente. Microsoft no ofrece ninguna garantía, expresa o implícita, de la información que se proporciona aquí.

Microsoft ofrece una amplia variedad de soluciones y servicios en la nube, incluidos varios planes diferentes para pequeñas y medianas empresas. Por ejemplo, [Microsoft 365 Empresa Premium](../../business/microsoft-365-business-overview.md) incluye funcionalidades de administración de dispositivos y seguridad, junto con características de productividad, como Office aplicaciones. Este artículo está diseñado para ayudar a aclarar qué características de seguridad, como la protección de dispositivos, se incluyen en Microsoft 365 Empresa Premium, Microsoft Defender para Empresas y Microsoft Defender para punto de conexión.

Microsoft Defender para Empresas está disponible como oferta independiente o como parte de Microsoft 365 Empresa Premium (a partir del 1 de marzo de 2022).

>
> **¿Tiene un minuto?**
> Realice nuestra <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">breve encuesta sobre seguridad</a>. Nos encantaría conocer su opinión.
>

**Use este artículo para**:

- [Comparar Microsoft Defender para Empresas (independiente) con Microsoft 365 Empresa Premium](#compare-security-features-in-microsoft-defender-for-business-to-microsoft-365-business-premium)
- [Comparación de Defender para empresas (independiente) con Microsoft Defender para punto de conexión ofertas empresariales](#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2)

**No es necesario tener una suscripción Microsoft 365 para comprar y usar Microsoft Defender para Empresas.** Microsoft Defender para Empresas se incluye en Microsoft 365 Empresa Premium y está disponible como una solución de seguridad independiente para pequeñas y medianas empresas. Si ya tiene Microsoft 365 Empresa Básico o Estándar, considere la posibilidad de agregar actualizaciones a Microsoft 365 Empresa Premium o agregar Microsoft Defender para Empresas para obtener más funcionalidades de protección contra amenazas.

## <a name="compare-security-features-in-microsoft-defender-for-business-to-microsoft-365-business-premium"></a>Compare las características de seguridad de Microsoft Defender para Empresas con Microsoft 365 Empresa Premium

> [!NOTE]
> Este artículo está diseñado para proporcionar información general de alto nivel sobre las características de protección contra amenazas incluidas en Microsoft Defender para Empresas (como un plan independiente) y Microsoft 365 Empresa Premium (que incluye Defender para empresas). Este artículo no está pensado para servir como descripción del servicio o documento de contrato de licencia. Para obtener más información, consulte [Microsoft 365 guía de licencias para la seguridad & cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

**A partir del 1 de marzo de 2022, Defender for Business comenzará a implementarse como parte de Microsoft 365 Empresa Premium. Defender for Business como oferta independiente sigue en versión preliminar.**

En la tabla siguiente se comparan las características y funcionalidades de seguridad de Defender para empresas (independiente) con Microsoft 365 Empresa Premium.

|Característica o funcionalidad|[Microsoft Defender para Empresas](mdb-overview.md)<br/>(independiente; actualmente en versión preliminar)|[Microsoft 365 Empresa Premium](../../business/microsoft-365-business-overview.md)<br/>(incluye Defender para empresas)|
|---|---|---|
|Protección por correo electrónico|Sí <br/>- [Examen por correo electrónico con Antivirus de Microsoft Defender](../defender-endpoint/configure-advanced-scan-types-microsoft-defender-antivirus.md)|Sí <br/>- [Exchange Online Protection](../office-365-security/exchange-online-protection-overview.md) <br/>- [Examen por correo electrónico con Antivirus de Microsoft Defender](../defender-endpoint/configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|Protección contra antispam|Sí <br/>- Para dispositivos|Sí <br/>- Para dispositivos<br/>: para Microsoft 365 contenido de correo electrónico, como mensajes y datos adjuntos|
|Protección antimalware|Sí<br/>- Para dispositivos|Sí <br/>- Para dispositivos<br/>: para Microsoft 365 contenido de correo electrónico, como mensajes y datos adjuntos|
|[Protección de última generación](../defender-endpoint/microsoft-defender-antivirus-in-windows-10.md) <br/> (protección antivirus y antimalware)|Sí<br/>- Antivirus de Microsoft Defender se incluye en Windows 10 y versiones posteriores|Sí <br/>- Antivirus de Microsoft Defender se incluye en Windows 10 y versiones posteriores<br/>- Directivas de protección de última generación para dispositivos incorporados|
|[Reducción de la superficie expuesta a ataques](../defender-endpoint/overview-attack-surface-reduction.md) <br/>(Reglas de ASR en Windows 10 o versiones posteriores y protección del firewall)|Sí|Sí|
|[EDR](../defender-endpoint/overview-endpoint-detection-response.md) <br/>(detección basada en comportamiento y acciones de respuesta manual)|Sí|Sí|
|[Investigación y respuesta automatizadas](../defender-endpoint/automated-investigations.md)|Sí|Sí|
|[Administración de vulnerabilidades y amenazas](../defender-endpoint/tvm-dashboard-insights.md)|Sí|Sí|
|Administración centralizada e informes|Sí|Sí|
|[API](../defender-endpoint/apis-intro.md) <br/>(para la integración con aplicaciones personalizadas o soluciones de informes)|Sí|Sí|

## <a name="compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2"></a>Comparar Microsoft Defender para Empresas con los planes 1 y 2 de Microsoft Defender para punto de conexión

Defender for Business ofrece funcionalidades de nivel empresarial de Defender para punto de conexión a pequeñas y medianas empresas.

En la tabla siguiente se comparan las características y funcionalidades de seguridad de Defender para empresas con los planes 1 y 2 de Microsoft Defender para punto de conexión.

|Característica o funcionalidad|[Defender para Empresas](mdb-overview.md)<br/>(independiente; actualmente en versión preliminar)|[Plan 1 de Defender para punto de conexión](../defender-endpoint/defender-endpoint-plan-1.md)|[Plan 2 de Defender para punto de conexión](../defender-endpoint/microsoft-defender-endpoint.md)|
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
|[Compatibilidad multiplataforma](../defender-endpoint/minimum-requirements.md) <br/>(Windows, macOS, iOS y sistema operativo Android)|Sí <sup>[[6](#fn6)]</sup>|Sí|Sí|
|[Expertos en amenazas de Microsoft](../defender-endpoint/microsoft-threat-experts.md)|No|No|Sí|
|API de asociados|Sí|Sí|Sí|
|[integración Microsoft 365 Lighthouse](../../lighthouse/m365-lighthouse-overview.md) <br/>(Para ver los incidentes de seguridad entre los inquilinos del cliente)|Sí|No|No|

(<a id="fn1">1</a>) Incorporación y administración de dispositivos en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) o con Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)).

(<a id="fn2">2</a>) Las funcionalidades de detección y respuesta de puntos de conexión (EDR) en Defender for Business incluyen la detección basada en comportamiento y los cuatro tipos siguientes de acciones de respuesta manual: 
- Ejecutar examen de antivirus
- Aislar el dispositivo
- Detener y poner en cuarentena un archivo
- Adición de un indicador para bloquear o permitir un archivo

(<a id="fn3">3</a>) En Defender para empresas, la investigación y la respuesta automatizadas están activadas de forma predeterminada, en todo el inquilino. Si desactiva la investigación y la respuesta automatizadas, afectará a la protección en tiempo real. Consulte [Revisión de la configuración de las características avanzadas](mdb-configure-security-settings.md#review-settings-for-advanced-features).  

(<a id="fn4">4</a>) No hay ninguna vista de escala de tiempo en Defender para empresas.

(<a id="fn5">5</a>) En Defender para empresas, el análisis de amenazas está optimizado para pequeñas y medianas empresas.

(<a id="fn6">6</a>) Durante el programa de versión preliminar, se admiten Windows dispositivos cliente para la incorporación en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). Puede usar el método de script local. Consulte [Incorporación de dispositivos para Microsoft Defender para Empresas](mdb-onboard-devices.md).

## <a name="next-steps"></a>Siguientes pasos

- [Consulte los requisitos de Microsoft Defender para Empresas](mdb-requirements.md)
- [Obtener Microsoft Defender para Empresas](get-defender-business.md)
- [Aprenda a configurar y configurar Microsoft Defender para Empresas](mdb-setup-configuration.md)
