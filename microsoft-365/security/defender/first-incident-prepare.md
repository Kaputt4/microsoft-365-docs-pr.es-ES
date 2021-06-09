---
title: Preparar la posición de seguridad para el primer incidente
description: Configure la posición de Microsoft 365 de seguridad del inquilino para su primer incidente en Microsoft 365 Defender.
keywords: incidentes, alertas, investigar, correlación, ataque, equipos, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, Microsoft, M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
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
ms.openlocfilehash: da9147955c5da9ea727854420b3d4d160583ef73
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840951"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a><span data-ttu-id="95e94-104">Preparar la posición de seguridad para el primer incidente</span><span class="sxs-lookup"><span data-stu-id="95e94-104">Prepare your security posture for your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="95e94-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="95e94-105">**Applies to:**</span></span>
- <span data-ttu-id="95e94-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95e94-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="95e94-107">Prepararse para el tratamiento de incidentes implica configurar la protección suficiente de la red de una organización frente a distintos tipos de incidentes de seguridad.</span><span class="sxs-lookup"><span data-stu-id="95e94-107">Preparing for incident handling involves setting up sufficient protection of an organization's network from different kinds of security incidents.</span></span> <span data-ttu-id="95e94-108">Para reducir el riesgo de incidentes de seguridad, el Instituto Nacional de Estándares y Tecnología (NIST) recomienda varias prácticas de seguridad, como evaluaciones de riesgos, protección de la seguridad de host, configuración de redes de forma segura y prevención de malware.</span><span class="sxs-lookup"><span data-stu-id="95e94-108">To reduce the risk of security incidents, National Institute of Standards and Technology (NIST) recommends several security practices including risk assessments, hardening host security, configuring networks securely, and preventing malware.</span></span> 

<span data-ttu-id="95e94-109">Microsoft 365 Defender puede ayudar a abordar varios aspectos de la prevención de incidentes:</span><span class="sxs-lookup"><span data-stu-id="95e94-109">Microsoft 365 Defender can help address several aspects of incident prevention:</span></span> 

- <span data-ttu-id="95e94-110">Implementación de un [marco de confianza](/security/zero-trust/) cero</span><span class="sxs-lookup"><span data-stu-id="95e94-110">Implementing a [Zero Trust](/security/zero-trust/) framework</span></span>
- <span data-ttu-id="95e94-111">Determinación de la posición de seguridad mediante la asignación de una puntuación con [puntuación segura de Microsoft](microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="95e94-111">Determining your security posture by assigning a score with [Microsoft Secure Score](microsoft-secure-score.md)</span></span>
- <span data-ttu-id="95e94-112">Prevención de amenazas mediante evaluaciones de vulnerabilidad en [Administración de amenazas y vulnerabilidades](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="95e94-112">Preventing threats through vulnerability assessments in [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="95e94-113">Descripción de las amenazas de seguridad más recientes para que pueda prepararse para ellas</span><span class="sxs-lookup"><span data-stu-id="95e94-113">Understanding the latest security threats so you can prepare for them</span></span>

## <a name="step-1-implement-zero-trust"></a><span data-ttu-id="95e94-114">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="95e94-114">Step 1.</span></span> <span data-ttu-id="95e94-115">Implementar la confianza cero</span><span class="sxs-lookup"><span data-stu-id="95e94-115">Implement Zero Trust</span></span>

<span data-ttu-id="95e94-116">[Zero Trust](/security/zero-trust/) es una filosofía de seguridad integrada y una estrategia integral que tiene en cuenta la naturaleza compleja de cualquier entorno moderno, incluidos los trabajadores móviles y los usuarios, dispositivos, aplicaciones y datos, dondequiera que estén ubicados.</span><span class="sxs-lookup"><span data-stu-id="95e94-116">[Zero Trust](/security/zero-trust/) is an integrated security philosophy and end-to-end strategy that considers the complex nature of any modern environment, including the mobile workforce and the users, devices, applications and data, wherever they may be located.</span></span> <span data-ttu-id="95e94-117">Al proporcionar un único panel de cristal para administrar todas las detecciones de forma coherente, Microsoft 365 Defender puede facilitar que el equipo de operaciones de seguridad implemente los [principios](/security/zero-trust/#guiding-principles-of-zero-trust) de guía de la confianza cero.</span><span class="sxs-lookup"><span data-stu-id="95e94-117">By providing a single pane of glass to manage all detections in a consistent way, Microsoft 365 Defender can make it easier for your security operations team to implement the [guiding principles](/security/zero-trust/#guiding-principles-of-zero-trust) of Zero Trust.</span></span> 

<span data-ttu-id="95e94-118">Los componentes de Microsoft 365 Defender pueden mostrar infracciones de reglas que se han implementado para establecer directivas de acceso condicional para la confianza cero mediante la integración de datos de Microsoft Defender para endpoint (MDE) u otros proveedores de seguridad móvil como origen de información para las directivas de cumplimiento de dispositivos y la implementación de directivas de acceso condicional basadas en dispositivos.</span><span class="sxs-lookup"><span data-stu-id="95e94-118">Components of Microsoft 365 Defender can display violations of rules that have been implemented to establish Conditional Access policies for Zero Trust by integrating data from Microsoft Defender for Endpoint (MDE) or other mobile security vendors as an information source for device compliance policies and implementation of device-based Conditional Access policies.</span></span> 

<span data-ttu-id="95e94-119">El riesgo del dispositivo influye directamente en los recursos a los que podrá acceder el usuario de ese dispositivo.</span><span class="sxs-lookup"><span data-stu-id="95e94-119">Device risk directly influences what resources will be accessible by the user of that device.</span></span> <span data-ttu-id="95e94-120">La denegación de acceso a los recursos según determinados criterios es el tema principal de La confianza cero y Microsoft 365 Defender proporciona la información necesaria para determinar los criterios de nivel de confianza.</span><span class="sxs-lookup"><span data-stu-id="95e94-120">The denial of access to resources based on certain criteria is the main theme of Zero Trust and Microsoft 365 Defender provides information needed to determine the trust level criteria.</span></span> <span data-ttu-id="95e94-121">Por ejemplo, Microsoft 365 Defender puede proporcionar el nivel de versión de software de un dispositivo a través de la página Administración de amenazas y vulnerabilidades, mientras que las directivas de acceso condicional restringen los dispositivos que tienen versiones obsoletas o vulnerables.</span><span class="sxs-lookup"><span data-stu-id="95e94-121">For example, Microsoft 365 Defender can provide the software version level of a device through the Threat and Vulnerability Management page while Conditional Access policies restrict devices that have outdated or vulnerable versions.</span></span>

<span data-ttu-id="95e94-122">La automatización es una parte fundamental de la implementación y el mantenimiento de un entorno de confianza cero, al tiempo que se reduce el número de alertas que podrían dar lugar a eventos de respuesta a incidentes (IR).</span><span class="sxs-lookup"><span data-stu-id="95e94-122">Automation is a crucial part of implementing and maintaining a Zero Trust environment while also reducing the number of alerts that would potentially lead to incident response (IR) events.</span></span> <span data-ttu-id="95e94-123">Los componentes de Microsoft 365 Defender se [](m365d-autoir.md) pueden automatizar, como acciones de corrección (conocidas como investigaciones de un incidente en el centro de seguridad de Microsoft 365), acciones de notificación e incluso la creación de vales de soporte técnico, como [en ServiceNow](https://microsoft.service-now.com/sp/).</span><span class="sxs-lookup"><span data-stu-id="95e94-123">Components of Microsoft 365 Defender can be automated such as [remediation actions](m365d-autoir.md) (known as investigations for an incident in the Microsoft 365 security center), notification actions, and even the creation of support tickets such as in [ServiceNow](https://microsoft.service-now.com/sp/).</span></span>

## <a name="step-2-determine-your-organizations-security-posture"></a><span data-ttu-id="95e94-124">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="95e94-124">Step 2.</span></span> <span data-ttu-id="95e94-125">Determinar la posición de seguridad de la organización</span><span class="sxs-lookup"><span data-stu-id="95e94-125">Determine your organization’s security posture</span></span>

<span data-ttu-id="95e94-126">A continuación, las organizaciones pueden usar la puntuación segura de [Microsoft](microsoft-secure-score.md) en Microsoft 365 Defender para determinar su posición de seguridad actual y considerar recomendaciones sobre cómo mejorarla.</span><span class="sxs-lookup"><span data-stu-id="95e94-126">Next, organizations can use the [Microsoft Secure Score](microsoft-secure-score.md) in Microsoft 365 Defender to determine your current security posture and consider recommendations on how to improve it.</span></span> <span data-ttu-id="95e94-127">Cuanto mayor sea la puntuación, más recomendaciones de seguridad y acciones de mejora han sido tomadas por la organización.</span><span class="sxs-lookup"><span data-stu-id="95e94-127">The higher the score is, the more security recommendations and improvement actions have been taken by the organization.</span></span> <span data-ttu-id="95e94-128">Las recomendaciones de puntuación segura se pueden tomar en diferentes productos y permitir que las organizaciones eleven sus puntuaciones incluso más alto.</span><span class="sxs-lookup"><span data-stu-id="95e94-128">Secure Score recommendations can be taken across different products and allow organizations to raise their scores even higher.</span></span> 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Ejemplo de puntuación segura de Microsoft en el Centro de seguridad de Microsoft":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a><span data-ttu-id="95e94-130">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="95e94-130">Step 3.</span></span> <span data-ttu-id="95e94-131">Evaluar la exposición a vulnerabilidades de su organización</span><span class="sxs-lookup"><span data-stu-id="95e94-131">Assess your organization’s vulnerability exposure</span></span>

<span data-ttu-id="95e94-132">La prevención de incidentes puede ayudar a simplificar los esfuerzos de las operaciones de seguridad para centrarse en los incidentes de seguridad importantes y críticos en curso.</span><span class="sxs-lookup"><span data-stu-id="95e94-132">Preventing incidents can help streamline security operations efforts to focus on on-going critical and important security incidents.</span></span> <span data-ttu-id="95e94-133">Las vulnerabilidades de software suelen ser un punto de entrada evitable para ataques que pueden provocar el robo de datos, la pérdida de datos o la interrupción de las operaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="95e94-133">Software vulnerabilities are often a preventable entry point for attacks that can lead to data theft, data loss, or disruption of business operations.</span></span> <span data-ttu-id="95e94-134">Si no hay ataques en curso, las operaciones de seguridad deben esforzarse por lograr y mantener un nivel aceptable de exposición a la [vulnerabilidad](../defender-endpoint/tvm-exposure-score.md) en su organización.</span><span class="sxs-lookup"><span data-stu-id="95e94-134">If no attacks are on-going, security operations must strive to achieve and maintain an acceptable level of [vulnerability exposure](../defender-endpoint/tvm-exposure-score.md) in their organization.</span></span>

<span data-ttu-id="95e94-135">Para comprobar el progreso de [](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) la revisión de software, visita la página Administración de amenazas y vulnerabilidades de Defender for Endpoint, a la que puedes acceder desde Microsoft 365 Defender a través de la pestaña Más **recursos.**</span><span class="sxs-lookup"><span data-stu-id="95e94-135">To check your software patching progress, visit the [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) page in Defender for Endpoint, which you can access from Microsoft 365 Defender through the **More resources** tab.</span></span>

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Ejemplo de la página Amenaza y vulnerabilidad en el Centro de seguridad de Microsoft"::: 
 
## <a name="4-understand-emerging-threats"></a><span data-ttu-id="95e94-137">4. Comprender las amenazas emergentes</span><span class="sxs-lookup"><span data-stu-id="95e94-137">4. Understand emerging threats</span></span>

<span data-ttu-id="95e94-138">Use [el análisis de](threat-analytics.md) amenazas en el Microsoft 365 de seguridad para mantenerse al día con el panorama actual de amenazas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="95e94-138">Use [threat analytics](threat-analytics.md) in the Microsoft 365 security center to keep up-to-date with the current security threat landscape.</span></span> <span data-ttu-id="95e94-139">Los expertos investigadores de seguridad de Microsoft crean informes que describen en detalle las últimas amenazas cibernéticas para que pueda comprender cómo pueden afectar a su suscripción Microsoft 365, dispositivos y usuarios.</span><span class="sxs-lookup"><span data-stu-id="95e94-139">Expert Microsoft security researchers create reports that describe the latest cyber-threats in detail so you can understand how they might affect your Microsoft 365 subscription, devices, and users.</span></span> <span data-ttu-id="95e94-140">Estos informes pueden incluir:</span><span class="sxs-lookup"><span data-stu-id="95e94-140">These reports can include:</span></span>

- <span data-ttu-id="95e94-141">Actores de amenazas activas y sus campañas</span><span class="sxs-lookup"><span data-stu-id="95e94-141">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="95e94-142">Técnicas de ataque populares y nuevas</span><span class="sxs-lookup"><span data-stu-id="95e94-142">Popular and new attack techniques</span></span>
- <span data-ttu-id="95e94-143">Vulnerabilidades críticas</span><span class="sxs-lookup"><span data-stu-id="95e94-143">Critical vulnerabilities</span></span>
- <span data-ttu-id="95e94-144">Superficies de ataque comunes</span><span class="sxs-lookup"><span data-stu-id="95e94-144">Common attack surfaces</span></span>
- <span data-ttu-id="95e94-145">Malware común</span><span class="sxs-lookup"><span data-stu-id="95e94-145">Prevalent malware</span></span>

<span data-ttu-id="95e94-146">El análisis de amenazas también examina la configuración y las alertas para determinar el riesgo que tiene y si hay alertas activas aplicables a un informe.</span><span class="sxs-lookup"><span data-stu-id="95e94-146">Threat analytics also looks at your configuration and alerts to determine how at-risk you are and if there are active alerts applicable to a report.</span></span>

<span data-ttu-id="95e94-147">Puedes implementar las recomendaciones de una amenaza emergente para reforzar tu posición de seguridad y minimizar la superficie de ataque.</span><span class="sxs-lookup"><span data-stu-id="95e94-147">You can implement the recommendations of an emerging threat to strengthen your security posture and minimize your attack surface area.</span></span>

<span data-ttu-id="95e94-148">Haga tiempo en su programación para comprobar periódicamente la sección [Análisis](threat-analytics.md) de amenazas del centro de Microsoft 365 seguridad.</span><span class="sxs-lookup"><span data-stu-id="95e94-148">Make time in your schedule to regularly check the [Threat Analytics](threat-analytics.md) section of the Microsoft 365 security center.</span></span>

## <a name="next-step"></a><span data-ttu-id="95e94-149">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="95e94-149">Next step</span></span>

<span data-ttu-id="95e94-150">[![Paso 1: Información sobre cómo triage and analyze incidents](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span><span class="sxs-lookup"><span data-stu-id="95e94-150">[![Step 1: Learn how to triage and analyze incidents](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span></span>

<span data-ttu-id="95e94-151">Obtenga información sobre [cómo triage and analyze incidents](first-incident-analyze.md).</span><span class="sxs-lookup"><span data-stu-id="95e94-151">Learn how to [triage and analyze incidents](first-incident-analyze.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="95e94-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="95e94-152">See also</span></span>

- [<span data-ttu-id="95e94-153">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="95e94-153">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="95e94-154">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="95e94-154">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="95e94-155">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="95e94-155">Manage incidents</span></span>](manage-incidents.md)
