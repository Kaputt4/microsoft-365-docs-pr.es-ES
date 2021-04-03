---
title: Investigar alertas en Microsoft 365 Defender
description: Investigar las alertas que se ven en dispositivos, usuarios y buzones.
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
ms.openlocfilehash: 989574a860bea798c48e077f5633c31eb857e85e
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500942"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="3ae33-104">Investigar alertas en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ae33-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3ae33-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3ae33-105">**Applies to:**</span></span>
- <span data-ttu-id="3ae33-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ae33-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="3ae33-107">Las alertas son la base de todos los incidentes e indican la aparición de eventos malintencionados o sospechosos en su entorno.</span><span class="sxs-lookup"><span data-stu-id="3ae33-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="3ae33-108">Las alertas suelen formar parte de un ataque más amplio y proporcionan fragmentos de pistas sobre un incidente.</span><span class="sxs-lookup"><span data-stu-id="3ae33-108">Alerts are typically part of a broader attack and provide pieces of clues about an incident.</span></span>

<span data-ttu-id="3ae33-109">En Microsoft 365 Defender, las alertas relacionadas se agregan juntas para formar incidentes.</span><span class="sxs-lookup"><span data-stu-id="3ae33-109">In Microsoft 365 Defender, related alerts are aggregated together to form incidents.</span></span> <span data-ttu-id="3ae33-110">Los incidentes siempre proporcionarán el contexto más amplio de un ataque, pero la investigación de alertas puede ser valiosa cuando se requiere un análisis más profundo.</span><span class="sxs-lookup"><span data-stu-id="3ae33-110">Incidents will always provide the broader context of an attack, however, investigating alerts can be valuable when deeper analysis is required.</span></span> 



## <a name="using-alert-pages-in-investigations"></a><span data-ttu-id="3ae33-111">Uso de páginas de alerta en investigaciones</span><span class="sxs-lookup"><span data-stu-id="3ae33-111">Using alert pages in investigations</span></span>

<span data-ttu-id="3ae33-112">En la pestaña Alertas de cualquier página de incidentes, la selección de una alerta le lleva a las páginas de alerta individuales.</span><span class="sxs-lookup"><span data-stu-id="3ae33-112">From the Alerts tab of any incident page, selecting an alert brings you to the individual alert pages.</span></span> <span data-ttu-id="3ae33-113">Una página de alerta se compone de tres secciones: activos afectados, artículo de alerta y el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="3ae33-113">An alert page is composed of three sections: affected assets, alert story, and the details pane.</span></span>

![Imagen de la página de alerta de ejemplo](../../media/new-alert-page2.png)

<span data-ttu-id="3ae33-115">A lo largo de una página de alerta, puede seleccionar el icono de tres puntos (**...**) junto a cualquier entidad para que pueda ver acciones disponibles como abrir la página de activos específica o realizar pasos de corrección específicos.</span><span class="sxs-lookup"><span data-stu-id="3ae33-115">Throughout an alert page, you can select the three-dot icon (**...**) beside any entity so you can see available actions like opening the specific asset page or doing specific remediation steps.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="3ae33-116">Analizar activos afectados</span><span class="sxs-lookup"><span data-stu-id="3ae33-116">Analyze affected assets</span></span>
<span data-ttu-id="3ae33-117">La sección activos afectados enumera buzones, dispositivos y usuarios afectados por esta alerta.</span><span class="sxs-lookup"><span data-stu-id="3ae33-117">The affected assets section lists mailboxes, devices, and users affected by this alert.</span></span> <span data-ttu-id="3ae33-118">Al seleccionar cualquiera de las tarjetas de activos, se rellena el panel lateral de detalles con información, incluidas otras alertas que se produjeron relacionadas con los activos, si las hubiera.</span><span class="sxs-lookup"><span data-stu-id="3ae33-118">Selecting any of the asset cards populates the details side pane with information, including other alerts that occurred involving the assets, if any.</span></span>


### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="3ae33-119">Seguimiento del rol de una alerta en el artículo de alerta</span><span class="sxs-lookup"><span data-stu-id="3ae33-119">Trace an alert's role in the alert story</span></span>
<span data-ttu-id="3ae33-120">El artículo de alerta muestra todos los activos o entidades relacionados con la alerta en una vista de árbol de proceso.</span><span class="sxs-lookup"><span data-stu-id="3ae33-120">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="3ae33-121">La alerta del título es la que está en foco cuando se aterriza por primera vez en la página de la alerta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3ae33-121">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="3ae33-122">Los activos del artículo de alerta se pueden expandir y hacer clic.</span><span class="sxs-lookup"><span data-stu-id="3ae33-122">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="3ae33-123">Proporcionan información adicional y aceleran la respuesta, ya que permiten realizar acciones directamente en el contexto de la página de alerta.</span><span class="sxs-lookup"><span data-stu-id="3ae33-123">They provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="3ae33-124">La sección de artículo de alerta puede contener más de una alerta, con alertas adicionales relacionadas con el mismo árbol de ejecución que aparecen antes o después de la alerta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3ae33-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-in-the-details-pane"></a><span data-ttu-id="3ae33-125">Ver más información de alerta en el panel de detalles</span><span class="sxs-lookup"><span data-stu-id="3ae33-125">View more alert information in the details pane</span></span>

<span data-ttu-id="3ae33-126">El panel de detalles muestra los detalles de la alerta seleccionada al principio, con detalles y acciones relacionadas con ella.</span><span class="sxs-lookup"><span data-stu-id="3ae33-126">The details pane shows the details of the selected alert at first, with details and actions related to it.</span></span> <span data-ttu-id="3ae33-127">Si selecciona cualquiera de los activos o entidades afectados en el artículo de alerta, el panel de detalles cambia para proporcionar información contextual y acciones para el objeto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3ae33-127">If you select any of the affected assets or entities in the alert story, the details pane changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="3ae33-128">Una vez que haya seleccionado una entidad de interés, el panel de detalles cambia para mostrar información sobre el tipo de entidad seleccionada, información histórica cuando está disponible y opciones para realizar acciones en esta entidad directamente desde la página de alerta.</span><span class="sxs-lookup"><span data-stu-id="3ae33-128">Once you've selected an entity of interest, the details pane changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

### <a name="manage-alerts"></a><span data-ttu-id="3ae33-129">Administrar alertas</span><span class="sxs-lookup"><span data-stu-id="3ae33-129">Manage alerts</span></span>

<span data-ttu-id="3ae33-130">Una vez que haya terminado de investigar las alertas, puede volver a la alerta con la que empezó, marcar el estado de la alerta como Resuelto y clasificarla como alerta False o Alerta True.</span><span class="sxs-lookup"><span data-stu-id="3ae33-130">Once you're done investigating the alerts, you can go back to the alert you started with, mark the alert's status as Resolved and classify it as either a False alert or True alert.</span></span> <span data-ttu-id="3ae33-131">Clasificar alertas ayuda a ajustar el producto para proporcionar alertas más verdaderas y menos falsas.</span><span class="sxs-lookup"><span data-stu-id="3ae33-131">Classifying alerts helps tune your product to provide more true alerts and less false alerts.</span></span>

> [!NOTE]
> <span data-ttu-id="3ae33-132">Una forma de administrar alertas mediante el uso de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="3ae33-132">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="3ae33-133">La funcionalidad de etiquetado de Microsoft Defender para Office 365 se está implantando de forma incremental y se encuentra actualmente en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="3ae33-133">The tagging capability for Microsoft Defender for Office 365 in incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="3ae33-134">Actualmente, los nombres de etiqueta modificados solo se aplican a las alertas *creadas después de* la actualización.</span><span class="sxs-lookup"><span data-stu-id="3ae33-134">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="3ae33-135">Las alertas que se generaron antes de la modificación no reflejarán el nombre de la etiqueta actualizada.</span><span class="sxs-lookup"><span data-stu-id="3ae33-135">Alerts that were generated prior to the modification will not reflect the updated tag name.</span></span> 


## <a name="manage-the-unified-alert-queue"></a><span data-ttu-id="3ae33-136">Administrar la cola de alertas unificada</span><span class="sxs-lookup"><span data-stu-id="3ae33-136">Manage the unified alert queue</span></span>

<span data-ttu-id="3ae33-137">Al seleccionar Alertas en Incidentes & alertas en el panel de navegación del centro de seguridad de Microsoft 365, se llega a la cola de alertas unificada.</span><span class="sxs-lookup"><span data-stu-id="3ae33-137">Selecting Alerts under Incidents & Alerts in the Microsoft 365 security center navigation pane brings you to the unified alert queue.</span></span> <span data-ttu-id="3ae33-138">Las alertas de diferentes soluciones de seguridad de Microsoft como Microsoft Defender para endpoint, Microsoft Defender para Office 365 y Microsoft 365 Defender aparecen en esta sección.</span><span class="sxs-lookup"><span data-stu-id="3ae33-138">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear in this section.</span></span> 

![Imagen de la página de alerta de ejemplo](../../media/unified-alert-queue.png)

<span data-ttu-id="3ae33-140">La cola De alertas muestra una lista de alertas que se marcaron en la red.</span><span class="sxs-lookup"><span data-stu-id="3ae33-140">The Alerts queue shows a list of alerts that were flagged in your network.</span></span> <span data-ttu-id="3ae33-141">De forma predeterminada, la cola muestra alertas vistas en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="3ae33-141">By default, the queue displays alerts seen in the last 30 days.</span></span> <span data-ttu-id="3ae33-142">Las alertas más recientes se muestran en la parte superior de la lista, lo que le ayudará a ver primero las alertas más recientes.</span><span class="sxs-lookup"><span data-stu-id="3ae33-142">The most recent alerts are shown at the top of the list helping you see the most recent alerts first.</span></span>

> [!NOTE]
> <span data-ttu-id="3ae33-143">En el momento del inicio, la cola de alertas unificadas solo tendrá 7 días de alertas de Microsoft Defender para Office 365 disponibles.</span><span class="sxs-lookup"><span data-stu-id="3ae33-143">At the time of launch, the unified alerts queue will only have 7 days’ worth of Microsoft Defender for Office 365 alerts available.</span></span> <span data-ttu-id="3ae33-144">La cola seguirá compilando con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="3ae33-144">The queue will continue to build over time.</span></span> <span data-ttu-id="3ae33-145">Si necesita realizar una triage alerts antes del inicio de la cola de alertas unificadas, use la cola de alertas en el [Centro de seguridad y cumplimiento](https://protection.office.com/viewalerts).</span><span class="sxs-lookup"><span data-stu-id="3ae33-145">If you need to triage alerts prior to the launch of the unified alerts queue, use the alerts queue in the [Security and Compliance Center](https://protection.office.com/viewalerts).</span></span>


<span data-ttu-id="3ae33-146">En la navegación superior, puede:</span><span class="sxs-lookup"><span data-stu-id="3ae33-146">On the top navigation, you can:</span></span>

- <span data-ttu-id="3ae33-147">Aplicar filtros</span><span class="sxs-lookup"><span data-stu-id="3ae33-147">Apply filters</span></span>
- <span data-ttu-id="3ae33-148">Personalizar columnas para agregar o quitar columnas</span><span class="sxs-lookup"><span data-stu-id="3ae33-148">Customize columns to add or remove columns</span></span>
- <span data-ttu-id="3ae33-149">Exportar datos</span><span class="sxs-lookup"><span data-stu-id="3ae33-149">Export data</span></span>

<span data-ttu-id="3ae33-150">También puede filtrar alertas según diferentes criterios:</span><span class="sxs-lookup"><span data-stu-id="3ae33-150">You can also filter alerts according to different criteria:</span></span>

- <span data-ttu-id="3ae33-151">Severity</span><span class="sxs-lookup"><span data-stu-id="3ae33-151">Severity</span></span>
- <span data-ttu-id="3ae33-152">Estado</span><span class="sxs-lookup"><span data-stu-id="3ae33-152">Status</span></span>
- <span data-ttu-id="3ae33-153">Categoría</span><span class="sxs-lookup"><span data-stu-id="3ae33-153">Category</span></span>
- <span data-ttu-id="3ae33-154">Origen de detección</span><span class="sxs-lookup"><span data-stu-id="3ae33-154">Detection source</span></span>
- <span data-ttu-id="3ae33-155">Policy</span><span class="sxs-lookup"><span data-stu-id="3ae33-155">Policy</span></span>
- <span data-ttu-id="3ae33-156">Activos afectados</span><span class="sxs-lookup"><span data-stu-id="3ae33-156">Impacted assets</span></span>
- <span data-ttu-id="3ae33-157">Primera actividad</span><span class="sxs-lookup"><span data-stu-id="3ae33-157">First activity</span></span>
- <span data-ttu-id="3ae33-158">Última actividad</span><span class="sxs-lookup"><span data-stu-id="3ae33-158">Last activity</span></span>


<span data-ttu-id="3ae33-159">Para iniciar una investigación sobre un incidente, lea [Investigar incidentes en Microsoft 365 Defender](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="3ae33-159">To start an investigation on an incident, read [Investigate incidents in Microsoft 365 Defender](investigate-incidents.md)</span></span>
## <a name="see-also"></a><span data-ttu-id="3ae33-160">Consulta también</span><span class="sxs-lookup"><span data-stu-id="3ae33-160">See also</span></span>

- [<span data-ttu-id="3ae33-161">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="3ae33-161">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="3ae33-162">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="3ae33-162">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="3ae33-163">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="3ae33-163">Manage incidents</span></span>](manage-incidents.md)
