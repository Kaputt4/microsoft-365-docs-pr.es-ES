---
title: Informe de protección contra amenazas en ATP de Microsoft Defender
description: Realizar un seguimiento de las detecciones de alertas, categorías y gravedad con el informe de protección contra amenazas
keywords: detección de alertas, origen, alerta por categoría, gravedad de alerta, clasificación de alertas, determinación
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4ecd2df31e1e03da5134d3d4180dcba75d3cee26
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183842"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="7ad96-104">Informe de protección contra amenazas en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="7ad96-104">Threat protection report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7ad96-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7ad96-105">**Applies to:**</span></span>
- [<span data-ttu-id="7ad96-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="7ad96-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7ad96-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ad96-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="7ad96-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="7ad96-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7ad96-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="7ad96-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="7ad96-110">El informe de protección contra amenazas proporciona información de alto nivel sobre las alertas generadas en la organización.</span><span class="sxs-lookup"><span data-stu-id="7ad96-110">The threat protection report provides high-level information about alerts generated in your organization.</span></span> <span data-ttu-id="7ad96-111">El informe incluye información de tendencias que muestra los orígenes de detección, categorías, gravedades, estados, clasificaciones y determinaciones de alertas a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="7ad96-111">The report includes trending information showing the detection sources, categories, severities, statuses, classifications, and determinations of alerts across time.</span></span>

<span data-ttu-id="7ad96-112">El panel está estructurado en dos secciones:</span><span class="sxs-lookup"><span data-stu-id="7ad96-112">The dashboard is structured into two sections:</span></span>

![Imagen del informe de protección contra amenazas](images/threat-protection-reports.png)

<span data-ttu-id="7ad96-114">Section</span><span class="sxs-lookup"><span data-stu-id="7ad96-114">Section</span></span> | <span data-ttu-id="7ad96-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ad96-115">Description</span></span> 
:---|:---
<span data-ttu-id="7ad96-116">1</span><span class="sxs-lookup"><span data-stu-id="7ad96-116">1</span></span> | <span data-ttu-id="7ad96-117">Tendencias de alertas</span><span class="sxs-lookup"><span data-stu-id="7ad96-117">Alerts trends</span></span>
<span data-ttu-id="7ad96-118">2</span><span class="sxs-lookup"><span data-stu-id="7ad96-118">2</span></span> | <span data-ttu-id="7ad96-119">Resumen de alertas</span><span class="sxs-lookup"><span data-stu-id="7ad96-119">Alert summary</span></span>

## <a name="alert-trends"></a><span data-ttu-id="7ad96-120">Tendencias de alerta</span><span class="sxs-lookup"><span data-stu-id="7ad96-120">Alert trends</span></span>
<span data-ttu-id="7ad96-121">De forma predeterminada, las tendencias de alerta muestran información de alerta del período de 30 días que termina en el último día completo.</span><span class="sxs-lookup"><span data-stu-id="7ad96-121">By default, the alert trends display alert information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="7ad96-122">Para obtener una mejor perspectiva de las tendencias que se producen en su organización, puede ajustar el período de informes ajustando el período de tiempo que se muestra.</span><span class="sxs-lookup"><span data-stu-id="7ad96-122">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="7ad96-123">Para ajustar el período de tiempo, seleccione un intervalo de tiempo en las opciones desplegables:</span><span class="sxs-lookup"><span data-stu-id="7ad96-123">To adjust the time period, select a time range from the drop-down options:</span></span>

- <span data-ttu-id="7ad96-124">30 días</span><span class="sxs-lookup"><span data-stu-id="7ad96-124">30 days</span></span>
- <span data-ttu-id="7ad96-125">3 meses</span><span class="sxs-lookup"><span data-stu-id="7ad96-125">3 months</span></span>
- <span data-ttu-id="7ad96-126">6 meses</span><span class="sxs-lookup"><span data-stu-id="7ad96-126">6 months</span></span>
- <span data-ttu-id="7ad96-127">Personalizado</span><span class="sxs-lookup"><span data-stu-id="7ad96-127">Custom</span></span>

>[!NOTE]
><span data-ttu-id="7ad96-128">Estos filtros solo se aplican en la sección de tendencias de alerta.</span><span class="sxs-lookup"><span data-stu-id="7ad96-128">These filters are only applied on the alert trends section.</span></span> <span data-ttu-id="7ad96-129">No afecta a la sección de resumen de alertas.</span><span class="sxs-lookup"><span data-stu-id="7ad96-129">It doesn't affect the alert summary section.</span></span>


## <a name="alert-summary"></a><span data-ttu-id="7ad96-130">Resumen de alertas</span><span class="sxs-lookup"><span data-stu-id="7ad96-130">Alert summary</span></span>
<span data-ttu-id="7ad96-131">Aunque las tendencias de alerta muestran información de alerta de tendencias, el resumen de alerta muestra información de alerta en el ámbito del día actual.</span><span class="sxs-lookup"><span data-stu-id="7ad96-131">While the alert trends shows trending alert information, the alert summary shows alert information scoped to the current day.</span></span>

 <span data-ttu-id="7ad96-132">El resumen de alerta le permite explorar en profundidad una cola de alertas determinada con el filtro correspondiente aplicado.</span><span class="sxs-lookup"><span data-stu-id="7ad96-132">The alert summary allows you to drill down to a particular alert queue with the corresponding filter applied to it.</span></span> <span data-ttu-id="7ad96-133">Por ejemplo, al hacer clic en la barra de EDR de la tarjeta Orígenes de detección, aparecerá la cola de alertas con resultados que muestran solo alertas generadas a partir de detecciones de EDR.</span><span class="sxs-lookup"><span data-stu-id="7ad96-133">For example, clicking on the EDR bar in the Detection sources card will bring you the alerts queue with results showing only alerts generated from EDR detections.</span></span> 

>[!NOTE]
><span data-ttu-id="7ad96-134">Los datos reflejados en la sección de resumen están en el ámbito de 180 días antes de la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="7ad96-134">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="7ad96-135">Por ejemplo, si la fecha de hoy es el 5 de noviembre de 2019, los datos de la sección de resumen reflejarán números a partir del 5 de mayo de 2019 al 5 de noviembre de 2019.</span><span class="sxs-lookup"><span data-stu-id="7ad96-135">For example if today's date is November 5, 2019, the data on the summary section will reflect numbers starting from May 5, 2019 to November 5, 2019.</span></span><br>
> <span data-ttu-id="7ad96-136">El filtro aplicado en la sección tendencias no se aplica en la sección de resumen.</span><span class="sxs-lookup"><span data-stu-id="7ad96-136">The filter applied on the trends section is not applied on the summary section.</span></span> 

## <a name="alert-attributes"></a><span data-ttu-id="7ad96-137">Atributos de alerta</span><span class="sxs-lookup"><span data-stu-id="7ad96-137">Alert attributes</span></span>
<span data-ttu-id="7ad96-138">El informe está hecho de tarjetas que muestran los siguientes atributos de alerta:</span><span class="sxs-lookup"><span data-stu-id="7ad96-138">The report is made up of cards that display the following alert attributes:</span></span>

- <span data-ttu-id="7ad96-139">**Orígenes de detección:** muestra información sobre los sensores y las tecnologías de detección que proporcionan los datos usados por Microsoft Defender para endpoint para desencadenar alertas.</span><span class="sxs-lookup"><span data-stu-id="7ad96-139">**Detection sources**: shows information about the sensors and detection technologies that provide the data used by Microsoft Defender for Endpoint to trigger alerts.</span></span>

- <span data-ttu-id="7ad96-140">**Categorías de amenazas:** muestra los tipos de actividad de amenazas o ataques que desencadenaron alertas, lo que indica posibles áreas de foco para las operaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7ad96-140">**Threat categories**: shows the types of threat or attack activity that triggered alerts, indicating possible focus areas for your security operations.</span></span>

- <span data-ttu-id="7ad96-141">**Gravedad:** muestra el nivel de gravedad de las alertas, lo que indica el impacto potencial colectivo de las amenazas en su organización y el nivel de respuesta necesario para abordarlas.</span><span class="sxs-lookup"><span data-stu-id="7ad96-141">**Severity**: shows the severity level of alerts, indicating the collective potential impact of threats to your organization and the level of response needed to address them.</span></span>

- <span data-ttu-id="7ad96-142">**Estado:** muestra el estado de resolución de las alertas, lo que indica la eficacia de las respuestas de alerta manual y de la corrección automatizada (si está habilitada).</span><span class="sxs-lookup"><span data-stu-id="7ad96-142">**Status**: shows the resolution status of alerts, indicating the efficiency of your manual alert responses and of automated remediation (if enabled).</span></span> 

- <span data-ttu-id="7ad96-143">**Clasificación & determinación:** muestra cómo ha clasificado las alertas tras la resolución, si las ha clasificado como amenazas reales (alertas verdaderas) o como detecciones incorrectas (alertas falsas).</span><span class="sxs-lookup"><span data-stu-id="7ad96-143">**Classification & determination**: shows how you have classified alerts upon resolution, whether you have classified them as actual threats (true alerts) or as incorrect detections (false alerts).</span></span> <span data-ttu-id="7ad96-144">Estas tarjetas también muestran la determinación de alertas resueltas, lo que proporciona información adicional como los tipos de amenazas reales encontradas o las actividades legítimas que se detectaron incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="7ad96-144">These cards also show the determination of resolved alerts, providing additional insight like the types of actual threats found or the legitimate activities that were incorrectly detected.</span></span>


 

## <a name="filter-data"></a><span data-ttu-id="7ad96-145">Filtrar datos</span><span class="sxs-lookup"><span data-stu-id="7ad96-145">Filter data</span></span>

<span data-ttu-id="7ad96-146">Use los filtros proporcionados para incluir o excluir alertas con determinados atributos.</span><span class="sxs-lookup"><span data-stu-id="7ad96-146">Use the provided filters to include or exclude alerts with certain attributes.</span></span>

>[!NOTE]
><span data-ttu-id="7ad96-147">Estos filtros se aplican a **todas** las tarjetas del informe.</span><span class="sxs-lookup"><span data-stu-id="7ad96-147">These filters apply to **all** the cards in the report.</span></span>

<span data-ttu-id="7ad96-148">Por ejemplo, para mostrar solo datos sobre alertas de gravedad alta:</span><span class="sxs-lookup"><span data-stu-id="7ad96-148">For example, to show data about high-severity alerts only:</span></span>

1. <span data-ttu-id="7ad96-149">En **Filters > Severity**, seleccione **High**</span><span class="sxs-lookup"><span data-stu-id="7ad96-149">Under **Filters > Severity**, select **High**</span></span>
2. <span data-ttu-id="7ad96-150">Asegúrese de que todas las demás opciones en **Gravedad** están deseleccionados.</span><span class="sxs-lookup"><span data-stu-id="7ad96-150">Ensure that all other options under **Severity** are deselected.</span></span>
3. <span data-ttu-id="7ad96-151">Seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="7ad96-151">Select **Apply**.</span></span> 

## <a name="related-topic"></a><span data-ttu-id="7ad96-152">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="7ad96-152">Related topic</span></span>
- [<span data-ttu-id="7ad96-153">Informe de cumplimiento y estado del dispositivo</span><span class="sxs-lookup"><span data-stu-id="7ad96-153">Device health and compliance report</span></span>](machine-reports.md)
