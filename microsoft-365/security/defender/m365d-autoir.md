---
title: Investigación y respuesta automatizadas en Microsoft 365 Defender
description: Obtenga información general sobre las capacidades automatizadas de investigación y respuesta, también denominadas recuperación automática, en Microsoft 365 Defender
keywords: automatizado, investigación, alerta, desencadenador, acción, corrección, recuperación automática
search.appverid: met150
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
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: fcb7283faed6fe8c5af59cedeeb90577b557ab34
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259540"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="9b6d6-104">Investigación y respuesta automatizadas en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b6d6-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9b6d6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9b6d6-105">**Applies to:**</span></span>
- <span data-ttu-id="9b6d6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b6d6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9b6d6-107">Si su organización usa [Microsoft 365 Defender,](microsoft-365-defender.md)el equipo de operaciones de seguridad recibe una alerta en el centro de seguridad de Microsoft 365 siempre que se detecte una actividad o artefacto malintencionados o sospechosos.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-107">If your organization is using [Microsoft 365 Defender](microsoft-365-defender.md), your security operations team receives an alert within the Microsoft 365 security center whenever a malicious or suspicious activity or artifact is detected.</span></span> <span data-ttu-id="9b6d6-108">Dado el flujo aparentemente interminable de amenazas que pueden llegar, los equipos de seguridad a menudo se enfrentan al desafío de abordar el alto volumen de alertas.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-108">Given the seemingly never-ending flow of threats that can come in, security teams often face the challenge of addressing the high volume of alerts.</span></span> <span data-ttu-id="9b6d6-109">Afortunadamente, Microsoft 365 Defender incluye capacidades automatizadas de investigación y corrección (AIR) que pueden ayudar a su equipo de operaciones de seguridad a abordar las amenazas de forma más eficaz y eficaz.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-109">Fortunately, Microsoft 365 Defender includes automated investigation and remediation (AIR) capabilities that can help your security operations team address threats more efficiently and effectively.</span></span>

<span data-ttu-id="9b6d6-110">En este artículo se proporciona información general sobre AIR e incluye vínculos a los siguientes pasos y recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-110">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="9b6d6-111">¿Quiere experimentar Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="9b6d6-111">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="9b6d6-112">Puede [evaluarlo en un entorno de pruebas](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o bien [ejecutar el proyecto piloto en producción](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="9b6d6-112">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="9b6d6-113">Cómo funciona la investigación automatizada y la recuperación automática</span><span class="sxs-lookup"><span data-stu-id="9b6d6-113">How automated investigation and self-healing works</span></span>

<span data-ttu-id="9b6d6-114">A medida que se desencadenan las alertas de seguridad, el equipo de operaciones de seguridad debe buscar esas alertas y tomar medidas para proteger su organización.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-114">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="9b6d6-115">El establecimiento de prioridades y la investigación de las alertas pueden llevar mucho tiempo, sobre todo cuando siguen apareciendo nuevas alertas mientras se está realizando una investigación.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-115">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="9b6d6-116">Los equipos de operaciones de seguridad pueden sentirse abrumados por el gran volumen de amenazas que deben supervisar y ante las que deben protegerse.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-116">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="9b6d6-117">Las capacidades automatizadas de investigación y respuesta, con recuperación automática, en Microsoft 365 Defender pueden ayudar.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-117">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="9b6d6-118">Vea el siguiente vídeo para ver cómo funciona la recuperación automática:</span><span class="sxs-lookup"><span data-stu-id="9b6d6-118">Watch the following video to see how self-healing works:</span></span> <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="9b6d6-119">En Microsoft 365 Defender, la investigación automatizada y la respuesta con capacidades de recuperación automática funcionan en todos los dispositivos, el correo & contenido y las identidades.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-119">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="9b6d6-120">En este artículo se describe cómo funciona la investigación automatizada y la respuesta.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-120">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="9b6d6-121">Para configurar estas capacidades, vea [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="9b6d6-121">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="9b6d6-122">Su propio analista virtual</span><span class="sxs-lookup"><span data-stu-id="9b6d6-122">Your own virtual analyst</span></span>

<span data-ttu-id="9b6d6-123">Imagine un analista virtual en su equipo de operaciones de seguridad de nivel 1 o nivel 2.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-123">Imagine having a virtual analyst in your Tier 1 or Tier 2 security operations team.</span></span> <span data-ttu-id="9b6d6-124">El analista virtual imita los pasos más idóneos que llevarían a cabo las operaciones de seguridad para investigar y solucionar las amenazas.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-124">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="9b6d6-125">El analista virtual podría trabajar 24 x 7, con capacidad ilimitada, y asumir una carga significativa de investigaciones y corrección de amenazas.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-125">The virtual analyst could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="9b6d6-126">Este tipo de analista virtual podría reducir significativamente el tiempo de respuesta, liberando al equipo de operaciones de seguridad para otras amenazas importantes o proyectos estratégicos.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-126">Such a virtual analyst could significantly reduce the time to respond, freeing up your security operations team for other important threats or strategic projects.</span></span> <span data-ttu-id="9b6d6-127">Si este escenario suena a ciencia ficción, no lo es.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-127">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="9b6d6-128">Dicho analista virtual forma parte de su conjunto de Microsoft 365 Defender y su nombre es *investigación y respuesta automatizadas.*</span><span class="sxs-lookup"><span data-stu-id="9b6d6-128">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="9b6d6-129">Las capacidades automatizadas de investigación y respuesta permiten al equipo de operaciones de seguridad aumentar considerablemente la capacidad de su organización para hacer frente a las alertas e incidentes de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-129">Automated investigation and response capabilities enable your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="9b6d6-130">Con la investigación y la respuesta automatizadas, puede reducir el costo de las actividades de investigación y corrección y sacar el máximo partido a su conjunto de protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-130">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="9b6d6-131">Las capacidades automatizadas de investigación y respuesta ayudan al equipo de operaciones de seguridad:</span><span class="sxs-lookup"><span data-stu-id="9b6d6-131">Automated investigation and response capabilities help your security operations team by:</span></span>

1. <span data-ttu-id="9b6d6-132">Determinar si una amenaza requiere acción.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-132">Determining whether a threat requires action.</span></span>
2. <span data-ttu-id="9b6d6-133">Realizar (o recomendar) las acciones de corrección necesarias.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-133">Taking (or recommending) any necessary remediation actions.</span></span>
3. <span data-ttu-id="9b6d6-134">Determinar si deben producirse otras investigaciones y qué otras.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-134">Determining whether and what other investigations should occur.</span></span>
4. <span data-ttu-id="9b6d6-135">Repetir el proceso según sea necesario para otras alertas.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-135">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="9b6d6-136">El proceso de investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="9b6d6-136">The automated investigation process</span></span>

<span data-ttu-id="9b6d6-137">Una alerta crea un incidente, que puede iniciar una investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-137">An alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="9b6d6-138">La investigación automatizada da como resultado un veredicto para cada elemento de evidencia.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-138">The automated investigation results in a verdict for each piece of evidence.</span></span> <span data-ttu-id="9b6d6-139">Los veredictos pueden ser:</span><span class="sxs-lookup"><span data-stu-id="9b6d6-139">Verdicts can be:</span></span>
- <span data-ttu-id="9b6d6-140">*Malintencionada*</span><span class="sxs-lookup"><span data-stu-id="9b6d6-140">*Malicious*</span></span>
- <span data-ttu-id="9b6d6-141">*Sospechoso*</span><span class="sxs-lookup"><span data-stu-id="9b6d6-141">*Suspicious*</span></span> 
- <span data-ttu-id="9b6d6-142">*No se encontraron amenazas*</span><span class="sxs-lookup"><span data-stu-id="9b6d6-142">*No threats found*</span></span> 

<span data-ttu-id="9b6d6-143">Se identifican acciones de corrección para entidades malintencionadas o sospechosas.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-143">Remediation actions for malicious or suspicious entities are identified.</span></span> <span data-ttu-id="9b6d6-144">Algunos ejemplos de acciones de corrección son:</span><span class="sxs-lookup"><span data-stu-id="9b6d6-144">Examples of remediation actions include:</span></span>

- <span data-ttu-id="9b6d6-145">Enviar un archivo a la cuarentena</span><span class="sxs-lookup"><span data-stu-id="9b6d6-145">Sending a file to quarantine</span></span>
- <span data-ttu-id="9b6d6-146">Detención de un proceso</span><span class="sxs-lookup"><span data-stu-id="9b6d6-146">Stopping a process</span></span>
- <span data-ttu-id="9b6d6-147">Aislar un dispositivo</span><span class="sxs-lookup"><span data-stu-id="9b6d6-147">Isolating a device</span></span>
- <span data-ttu-id="9b6d6-148">Bloquear una dirección URL</span><span class="sxs-lookup"><span data-stu-id="9b6d6-148">Blocking a URL</span></span> 
- <span data-ttu-id="9b6d6-149">Otras acciones</span><span class="sxs-lookup"><span data-stu-id="9b6d6-149">Other actions</span></span>

<span data-ttu-id="9b6d6-150">Para obtener más información, vea [Acciones de corrección en Microsoft 365 Defender](m365d-remediation-actions.md).</span><span class="sxs-lookup"><span data-stu-id="9b6d6-150">For more information, see See [Remediation actions in Microsoft 365 Defender](m365d-remediation-actions.md).</span></span>

<span data-ttu-id="9b6d6-151">En función [de cómo se configuren](m365d-configure-auto-investigation-response.md) las capacidades automatizadas de investigación y respuesta para su organización, las acciones de corrección se toman automáticamente o solo tras la aprobación del equipo de operaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-151">Depending on [how automated investigation and response capabilities are configured](m365d-configure-auto-investigation-response.md) for your organization, remediation actions are taken automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="9b6d6-152">Todas las acciones, ya sean pendientes o completadas, se enumeran en el [Centro de acciones](m365d-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="9b6d6-152">All actions, whether pending or completed, are listed in the [Action center](m365d-action-center.md).</span></span>

<span data-ttu-id="9b6d6-153">Durante la ejecución de una investigación, todas las demás alertas relacionadas que puedan surgir se agregarán a la investigación hasta que se finalice.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-153">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="9b6d6-154">Si se ve una entidad afectada en otro lugar, la investigación automatizada expande su ámbito para incluir esa entidad y el proceso de investigación se repite.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-154">If an affected entity is seen elsewhere, the automated investigation expands its scope to include that entity, and the investigation process repeats.</span></span> 

<span data-ttu-id="9b6d6-155">En Microsoft 365 Defender, cada investigación automatizada correlaciona las señales entre Microsoft Defender for Identity, Microsoft Defender para Endpoint y Microsoft Defender para Office 365, como se resume en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="9b6d6-155">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Microsoft Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="9b6d6-156">Entidades</span><span class="sxs-lookup"><span data-stu-id="9b6d6-156">Entities</span></span> |<span data-ttu-id="9b6d6-157">Servicios de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="9b6d6-157">Threat protection services</span></span>  |
|:---------|:---------|
|<span data-ttu-id="9b6d6-158">Dispositivos (también denominados extremos o máquinas)</span><span class="sxs-lookup"><span data-stu-id="9b6d6-158">Devices (also referred to as endpoints or machines)</span></span> |[<span data-ttu-id="9b6d6-159">Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9b6d6-159">Defender for Endpoint</span></span>](../defender-endpoint/automated-investigations.md) |      
|<span data-ttu-id="9b6d6-160">Usuarios locales de Active Directory, comportamiento de entidad y actividades</span><span class="sxs-lookup"><span data-stu-id="9b6d6-160">On-premises Active Directory users, entity behavior, and activities</span></span>     |[<span data-ttu-id="9b6d6-161">Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="9b6d6-161">Defender for Identity</span></span>](/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="9b6d6-162">Contenido de correo electrónico (mensajes de correo electrónico que pueden contener archivos y direcciones URL)</span><span class="sxs-lookup"><span data-stu-id="9b6d6-162">Email content (email messages that can contain files and URLs)</span></span>     |[<span data-ttu-id="9b6d6-163">Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="9b6d6-163">Defender for Office 365</span></span>](../office-365-security/defender-for-office-365.md) |

> [!NOTE]
> <span data-ttu-id="9b6d6-164">No todas las alertas desencadenan una investigación automatizada y no todas las investigaciones tienen como resultado acciones de corrección automatizadas.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-164">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions.</span></span> <span data-ttu-id="9b6d6-165">Depende de cómo se configure la investigación y la respuesta automatizadas para su organización.</span><span class="sxs-lookup"><span data-stu-id="9b6d6-165">It depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="9b6d6-166">Vea [Configure automated investigation and response capabilities](m365d-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="9b6d6-166">See [Configure automated investigation and response capabilities](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="viewing-a-list-of-investigations"></a><span data-ttu-id="9b6d6-167">Visualización de una lista de investigaciones</span><span class="sxs-lookup"><span data-stu-id="9b6d6-167">Viewing a list of investigations</span></span>

<span data-ttu-id="9b6d6-168">Para ver las investigaciones, vaya a la **página Incidentes.**</span><span class="sxs-lookup"><span data-stu-id="9b6d6-168">To view investigations, go to the **Incidents** page.</span></span> <span data-ttu-id="9b6d6-169">Seleccione un incidente y, a continuación, seleccione la **pestaña Investigaciones.** Para obtener más información, vea [Detalles y resultados de una investigación automatizada.](m365d-autoir-results.md)</span><span class="sxs-lookup"><span data-stu-id="9b6d6-169">Select an incident, and then select the **Investigations** tab. To learn more, see [Details and results of an automated investigation](m365d-autoir-results.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="9b6d6-170">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9b6d6-170">Next steps</span></span>

- [<span data-ttu-id="9b6d6-171">Consulte los requisitos previos para la investigación y respuesta automatizadas</span><span class="sxs-lookup"><span data-stu-id="9b6d6-171">See the prerequisites for automated investigation and response</span></span>](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="9b6d6-172">Configurar la investigación automatizada y la respuesta para su organización</span><span class="sxs-lookup"><span data-stu-id="9b6d6-172">Configure automated investigation and response for your organization</span></span>](m365d-configure-auto-investigation-response.md)
- [<span data-ttu-id="9b6d6-173">Más información sobre el Centro de actividades</span><span class="sxs-lookup"><span data-stu-id="9b6d6-173">Learn more about the Action center</span></span>](m365d-action-center.md)
