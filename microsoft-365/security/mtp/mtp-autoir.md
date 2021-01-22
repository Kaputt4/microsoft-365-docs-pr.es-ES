---
title: Investigación y respuesta automatizadas en Microsoft 365 Defender
description: Obtenga información general sobre las capacidades automatizadas de investigación y respuesta, también denominada recuperación automática, en Microsoft 365 Defender
keywords: automatizado, investigación, alerta, desencadenador, acción, corrección, recuperación automática
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 905455e4cd70485e099f8005b5f8876b1a5d9caf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930335"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="f085d-104">Investigación y respuesta automatizadas en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f085d-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f085d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f085d-105">**Applies to:**</span></span>
- <span data-ttu-id="f085d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f085d-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="f085d-107">¿Desea experimentar Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="f085d-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="f085d-108">Puede [evaluarlo en un entorno de laboratorio o](https://aka.ms/mtp-trial-lab) ejecutar el proyecto piloto en [producción.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="f085d-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="f085d-109">Cómo funciona la investigación automatizada y la recuperación automática</span><span class="sxs-lookup"><span data-stu-id="f085d-109">How automated investigation and self-healing works</span></span>

<span data-ttu-id="f085d-110">A medida que se desencadenan las alertas de seguridad, es el equipo de operaciones de seguridad quien debe buscar esas alertas y tomar medidas para proteger su organización.</span><span class="sxs-lookup"><span data-stu-id="f085d-110">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="f085d-111">El establecimiento de prioridades y la investigación de las alertas pueden llevar mucho tiempo, sobre todo cuando siguen apareciendo nuevas alertas mientras se está realizando una investigación.</span><span class="sxs-lookup"><span data-stu-id="f085d-111">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="f085d-112">Los equipos de operaciones de seguridad pueden sentirse abrumados por el gran volumen de amenazas que deben supervisar y ante las que deben protegerse.</span><span class="sxs-lookup"><span data-stu-id="f085d-112">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="f085d-113">Las capacidades automatizadas de investigación y respuesta, con recuperación automática, en Microsoft 365 Defender pueden ayudar.</span><span class="sxs-lookup"><span data-stu-id="f085d-113">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="f085d-114">Vea el siguiente vídeo para ver cómo funciona la recuperación automática:</span><span class="sxs-lookup"><span data-stu-id="f085d-114">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="f085d-115">En Microsoft 365 Defender, la investigación automatizada y la respuesta con capacidades de recuperación automática funcionan en sus dispositivos, correo electrónico & contenido e identidades.</span><span class="sxs-lookup"><span data-stu-id="f085d-115">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="f085d-116">En este artículo se describe cómo funciona la investigación automatizada y la respuesta.</span><span class="sxs-lookup"><span data-stu-id="f085d-116">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="f085d-117">Para configurar estas capacidades, vea Configurar las capacidades automatizadas de investigación y respuesta [en Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="f085d-117">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="f085d-118">Su propio analista virtual</span><span class="sxs-lookup"><span data-stu-id="f085d-118">Your own virtual analyst</span></span>

<span data-ttu-id="f085d-119">Imagínese tener un analista virtual en su equipo de operaciones de seguridad de nivel 1/nivel 2.</span><span class="sxs-lookup"><span data-stu-id="f085d-119">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="f085d-120">El analista virtual imita los pasos más idóneos que llevarían a cabo las operaciones de seguridad para investigar y solucionar las amenazas.</span><span class="sxs-lookup"><span data-stu-id="f085d-120">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="f085d-121">El asistente virtual podría funcionar de forma permanente y con capacidad ilimitada realizando una carga considerable de investigación y corrección de amenazas.</span><span class="sxs-lookup"><span data-stu-id="f085d-121">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="f085d-122">Ese asistente virtual podría reducir el tiempo de respuesta considerablemente, lo que permitiría al equipo de operaciones de seguridad trabajar en otros proyectos estratégicos importantes.</span><span class="sxs-lookup"><span data-stu-id="f085d-122">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="f085d-123">Si este escenario parece ciencia-ciencia, no es así.</span><span class="sxs-lookup"><span data-stu-id="f085d-123">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="f085d-124">Este analista virtual forma parte de su conjunto de aplicaciones de Microsoft 365 Defender y su nombre es *investigación y respuesta automatizadas.*</span><span class="sxs-lookup"><span data-stu-id="f085d-124">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="f085d-125">La investigación y la respuesta automatizadas permiten al equipo de operaciones de seguridad aumentar considerablemente la capacidad de su organización para hacer frente a alertas e incidentes de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f085d-125">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="f085d-126">Con la investigación y respuesta automatizadas, puede reducir el costo de trabajar con actividades de investigación y corrección y sacar el máximo partido a su conjunto de protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="f085d-126">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="f085d-127">la investigación automatizada y la respuesta ayudan al equipo de operaciones de seguridad a:</span><span class="sxs-lookup"><span data-stu-id="f085d-127">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="f085d-128">Determinar si una amenaza requiere una acción;</span><span class="sxs-lookup"><span data-stu-id="f085d-128">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="f085d-129">Llevar a cabo (o recomendar) todas las acciones de corrección necesarias;</span><span class="sxs-lookup"><span data-stu-id="f085d-129">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="f085d-130">Determinar qué investigaciones adicionales deben realizarse; y</span><span class="sxs-lookup"><span data-stu-id="f085d-130">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="f085d-131">Repetir el proceso según sea necesario para otras alertas.</span><span class="sxs-lookup"><span data-stu-id="f085d-131">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="f085d-132">El proceso de investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="f085d-132">The automated investigation process</span></span>

<span data-ttu-id="f085d-133">**Alerta** > **incidente** > **investigación automatizada** > **veredicto** > **acción de corrección**</span><span class="sxs-lookup"><span data-stu-id="f085d-133">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="f085d-134">Una alerta desencadenada crea un incidente, que puede iniciar una investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="f085d-134">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="f085d-135">Esa investigación puede dar como resultado una o varias acciones correctivas.</span><span class="sxs-lookup"><span data-stu-id="f085d-135">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="f085d-136">En Microsoft 365 Defender, cada investigación automatizada correlaciona las señales en Microsoft Defender para Identity, Microsoft Defender para Endpoint y Defender para Office 365, como se resume en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="f085d-136">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="f085d-137">Entidades</span><span class="sxs-lookup"><span data-stu-id="f085d-137">Entities</span></span> |<span data-ttu-id="f085d-138">Servicios de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="f085d-138">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="f085d-139">Dispositivos (también denominados puntos de conexión)</span><span class="sxs-lookup"><span data-stu-id="f085d-139">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="f085d-140">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="f085d-140">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="f085d-141">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="f085d-141">Microsoft Defender for Identity</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="f085d-142">Contenido de correo electrónico (archivos y mensajes de los buzones)</span><span class="sxs-lookup"><span data-stu-id="f085d-142">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="f085d-143">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="f085d-143">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="f085d-144">Cada investigación genera veredictos *(malintencionados,* sospechosos o *sin* amenazas encontradas) para cada evidencia investigada.</span><span class="sxs-lookup"><span data-stu-id="f085d-144">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="f085d-145">Según el tipo de amenaza y el veredicto resultante, las acciones de corrección se producen automáticamente o tras la aprobación por parte del equipo de operaciones de seguridad de la organización.</span><span class="sxs-lookup"><span data-stu-id="f085d-145">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="f085d-146">Las acciones pendientes y completadas se muestran en el [Centro de actividades](mtp-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="f085d-146">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="f085d-147">Durante la ejecución de una investigación, todas las demás alertas relacionadas que puedan surgir se agregarán a la investigación hasta que se finalice.</span><span class="sxs-lookup"><span data-stu-id="f085d-147">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="f085d-148">Si se detecta una entidad involucrada en otro lugar, la investigación automatizada ampliará el ámbito para incluir esa entidad y se ejecutará un cuaderno de estrategias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f085d-148">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="f085d-149">No todas las alertas desencadenan una investigación automatizada y no todas las investigaciones tienen como resultado acciones de corrección automatizadas; todo depende de cómo se configure la investigación y respuesta automatizadas para su organización.</span><span class="sxs-lookup"><span data-stu-id="f085d-149">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="f085d-150">Consulte [Configurar las capacidades automatizadas de investigación y respuesta en Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="f085d-150">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="f085d-151">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="f085d-151">Next steps</span></span>

- [<span data-ttu-id="f085d-152">Ver los requisitos previos para la investigación automatizada y la respuesta en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f085d-152">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="f085d-153">Configurar la investigación automatizada y la respuesta para su organización</span><span class="sxs-lookup"><span data-stu-id="f085d-153">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="f085d-154">Más información sobre el Centro de actividades</span><span class="sxs-lookup"><span data-stu-id="f085d-154">Learn more about the Action center</span></span>](mtp-action-center.md)
