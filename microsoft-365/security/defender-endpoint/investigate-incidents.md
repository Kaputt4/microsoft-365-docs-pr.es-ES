---
title: Investigar incidentes en Microsoft Defender para endpoint
description: Ver alertas asociadas, administrar el incidente y ver metadatos de alerta para ayudarle a investigar un incidente
keywords: investigar, incidente, alertas, metadatos, riesgo, origen de detección, dispositivos afectados, patrones, correlación
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0b52b6f9b457dbe1a5984c3d68c7077f7037d498
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845083"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="79bfe-104">Investigar incidentes en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="79bfe-104">Investigate incidents in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="79bfe-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="79bfe-105">**Applies to:**</span></span>
- [<span data-ttu-id="79bfe-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="79bfe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="79bfe-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79bfe-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="79bfe-108">Investigar incidentes que afectan a la red, comprender lo que significan y recopilar evidencias para resolverlos.</span><span class="sxs-lookup"><span data-stu-id="79bfe-108">Investigate incidents that affect your network, understand what they mean, and collate evidence to resolve them.</span></span> 

<span data-ttu-id="79bfe-109">Cuando investigues un incidente, verás lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="79bfe-109">When you investigate an incident, you'll see:</span></span>
- <span data-ttu-id="79bfe-110">Detalles del incidente</span><span class="sxs-lookup"><span data-stu-id="79bfe-110">Incident details</span></span>
- <span data-ttu-id="79bfe-111">Comentarios y acciones de incidentes</span><span class="sxs-lookup"><span data-stu-id="79bfe-111">Incident comments and actions</span></span>
- <span data-ttu-id="79bfe-112">Pestañas (alertas, dispositivos, investigaciones, evidencias, gráfico)</span><span class="sxs-lookup"><span data-stu-id="79bfe-112">Tabs (alerts, devices, investigations, evidence, graph)</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUV]


## <a name="analyze-incident-details"></a><span data-ttu-id="79bfe-113">Analizar detalles de incidentes</span><span class="sxs-lookup"><span data-stu-id="79bfe-113">Analyze incident details</span></span> 
<span data-ttu-id="79bfe-114">Haga clic en un incidente para ver **el panel Incidente**.</span><span class="sxs-lookup"><span data-stu-id="79bfe-114">Click an incident to see the **Incident pane**.</span></span> <span data-ttu-id="79bfe-115">Seleccione **Abrir página de incidentes** para ver los detalles del incidente y la información relacionada (alertas, dispositivos, investigaciones, evidencias, gráfico).</span><span class="sxs-lookup"><span data-stu-id="79bfe-115">Select **Open incident page** to see the incident details and related information (alerts, devices, investigations, evidence, graph).</span></span> 

![Imagen de detalles de incidentes1](images/atp-incident-details.png)

### <a name="alerts"></a><span data-ttu-id="79bfe-117">Alertas</span><span class="sxs-lookup"><span data-stu-id="79bfe-117">Alerts</span></span>
<span data-ttu-id="79bfe-118">Puede investigar las alertas y ver cómo se vincularon en un incidente.</span><span class="sxs-lookup"><span data-stu-id="79bfe-118">You can investigate the alerts and see how they were linked together in an incident.</span></span> <span data-ttu-id="79bfe-119">Las alertas se agrupan en incidentes en función de los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="79bfe-119">Alerts are grouped into incidents based on the following reasons:</span></span>
- <span data-ttu-id="79bfe-120">Investigación automatizada: la investigación automatizada desencadenó la alerta vinculada mientras se investigaba la alerta original.</span><span class="sxs-lookup"><span data-stu-id="79bfe-120">Automated investigation - The automated investigation triggered the linked alert while investigating the original alert</span></span> 
- <span data-ttu-id="79bfe-121">Características del archivo: los archivos asociados a la alerta tienen características similares</span><span class="sxs-lookup"><span data-stu-id="79bfe-121">File characteristics - The files associated with the alert have similar characteristics</span></span>
- <span data-ttu-id="79bfe-122">Asociación manual: un usuario vinculó manualmente las alertas</span><span class="sxs-lookup"><span data-stu-id="79bfe-122">Manual association - A user manually linked the alerts</span></span>
- <span data-ttu-id="79bfe-123">Tiempo próxima: las alertas se desencadenaron en el mismo dispositivo en un período de tiempo determinado</span><span class="sxs-lookup"><span data-stu-id="79bfe-123">Proximate time - The alerts were triggered on the same device within a certain timeframe</span></span>
- <span data-ttu-id="79bfe-124">Mismo archivo: los archivos asociados con la alerta son exactamente los mismos</span><span class="sxs-lookup"><span data-stu-id="79bfe-124">Same file - The files associated with the alert are exactly the same</span></span>
- <span data-ttu-id="79bfe-125">Misma dirección URL: la dirección URL que desencadenó la alerta es exactamente la misma</span><span class="sxs-lookup"><span data-stu-id="79bfe-125">Same URL - The URL that triggered the alert is exactly the same</span></span>

![Imagen de la pestaña alertas con la página de detalles del incidente que muestra los motivos por los que las alertas se vincularon juntas en ese incidente](images/atp-incidents-alerts-reason.png)

<span data-ttu-id="79bfe-127">También puede administrar una alerta y ver metadatos de alerta junto con otra información.</span><span class="sxs-lookup"><span data-stu-id="79bfe-127">You can also manage an alert and see alert metadata along with other information.</span></span> <span data-ttu-id="79bfe-128">Para obtener más información, vea [Investigar alertas](investigate-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="79bfe-128">For more information, see [Investigate alerts](investigate-alerts.md).</span></span> 

### <a name="devices"></a><span data-ttu-id="79bfe-129">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="79bfe-129">Devices</span></span>
<span data-ttu-id="79bfe-130">También puedes investigar los dispositivos que forman parte de un incidente determinado o están relacionados con ellos.</span><span class="sxs-lookup"><span data-stu-id="79bfe-130">You can also investigate the devices that are part of, or related to, a given incident.</span></span> <span data-ttu-id="79bfe-131">Para obtener más información, vea [Investigar dispositivos](investigate-machines.md).</span><span class="sxs-lookup"><span data-stu-id="79bfe-131">For more information, see [Investigate devices](investigate-machines.md).</span></span>

![Pestaña Imagen de dispositivos en la página detalles de incidentes](images/atp-incident-device-tab.png)

### <a name="investigations"></a><span data-ttu-id="79bfe-133">Investigaciones</span><span class="sxs-lookup"><span data-stu-id="79bfe-133">Investigations</span></span>
<span data-ttu-id="79bfe-134">Seleccione **Investigaciones para** ver todas las investigaciones automáticas iniciadas por el sistema en respuesta a las alertas de incidentes.</span><span class="sxs-lookup"><span data-stu-id="79bfe-134">Select **Investigations** to see all the automatic investigations launched by the system in response to the incident alerts.</span></span>

![Imagen de la pestaña investigaciones en la página de detalles de incidentes](images/atp-incident-investigations-tab.png)

## <a name="going-through-the-evidence"></a><span data-ttu-id="79bfe-136">Pasar por la evidencia</span><span class="sxs-lookup"><span data-stu-id="79bfe-136">Going through the evidence</span></span>
<span data-ttu-id="79bfe-137">Microsoft Defender para endpoint investiga automáticamente todos los eventos admitidos por los incidentes y las entidades sospechosas de las alertas, lo que le proporciona una respuesta automática e información sobre los archivos, procesos, servicios y mucho más importantes.</span><span class="sxs-lookup"><span data-stu-id="79bfe-137">Microsoft Defender for Endpoint automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, and more.</span></span> 

<span data-ttu-id="79bfe-138">Cada una de las entidades analizadas se marcará como infectado, corregido o sospechoso.</span><span class="sxs-lookup"><span data-stu-id="79bfe-138">Each of the analyzed entities will be marked as infected, remediated, or suspicious.</span></span> 

![Imagen de la pestaña evidencia en la página de detalles del incidente](images/atp-incident-evidence-tab.png)

## <a name="visualizing-associated-cybersecurity-threats"></a><span data-ttu-id="79bfe-140">Visualización de amenazas de ciberseguridad asociadas</span><span class="sxs-lookup"><span data-stu-id="79bfe-140">Visualizing associated cybersecurity threats</span></span> 
<span data-ttu-id="79bfe-141">Microsoft Defender para endpoint agrega la información de amenazas en un incidente para que pueda ver los patrones y correlaciones que vienen desde varios puntos de datos.</span><span class="sxs-lookup"><span data-stu-id="79bfe-141">Microsoft Defender for Endpoint aggregates the threat information into an incident so you can see the patterns and correlations coming in from various data points.</span></span> <span data-ttu-id="79bfe-142">Puede ver dicha correlación a través del gráfico de incidentes.</span><span class="sxs-lookup"><span data-stu-id="79bfe-142">You can view such correlation through the incident graph.</span></span>

### <a name="incident-graph"></a><span data-ttu-id="79bfe-143">Gráfico de incidentes</span><span class="sxs-lookup"><span data-stu-id="79bfe-143">Incident graph</span></span>
<span data-ttu-id="79bfe-144">El **Graph** cuenta la historia del ataque de ciberseguridad.</span><span class="sxs-lookup"><span data-stu-id="79bfe-144">The **Graph** tells the story of the cybersecurity attack.</span></span> <span data-ttu-id="79bfe-145">Por ejemplo, muestra cuál era el punto de entrada, qué indicador de riesgo o actividad se observó en qué dispositivo.</span><span class="sxs-lookup"><span data-stu-id="79bfe-145">For example, it shows you what was the entry point, which indicator of compromise or activity was observed on which device.</span></span> <span data-ttu-id="79bfe-146">etc.</span><span class="sxs-lookup"><span data-stu-id="79bfe-146">etc.</span></span>

![Imagen del gráfico de incidentes](images/atp-incident-graph-tab.png)

<span data-ttu-id="79bfe-148">Puede hacer clic en los círculos del gráfico de incidentes para ver los detalles de los archivos malintencionados, las detecciones de archivos asociados, cuántas instancias ha habido en todo el mundo, si se ha observado en su organización, si es así, cuántas instancias.</span><span class="sxs-lookup"><span data-stu-id="79bfe-148">You can click the circles on the incident graph to view the details of the malicious files, associated file detections, how many instances have there been worldwide, whether it’s been observed in your organization, if so, how many instances.</span></span>

![Imagen de los detalles del incidente](images/atp-incident-graph-details.png)

## <a name="related-topics"></a><span data-ttu-id="79bfe-150">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="79bfe-150">Related topics</span></span>
- [<span data-ttu-id="79bfe-151">Cola de incidentes</span><span class="sxs-lookup"><span data-stu-id="79bfe-151">Incidents queue</span></span>](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="79bfe-152">Investigar incidentes en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="79bfe-152">Investigate incidents in Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/investigate-incidents)
- [<span data-ttu-id="79bfe-153">Administrar Microsoft Defender para incidentes de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="79bfe-153">Manage Microsoft Defender for Endpoint incidents</span></span>](/microsoft-365/security/defender-endpoint/manage-incidents)
