---
title: Investigar dominios de Punto de conexión de Microsoft Defender
description: Use las opciones de investigación para ver si los dispositivos y servidores se han estado comunicando con dominios malintencionados.
keywords: investigar dominio, dominio, dominio malintencionado, Microsoft Defender para extremo, alerta, dirección URL
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
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 7826229ba67384137c033745a5b85e557fc9c4a7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933474"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="c8a25-104">Investigar un dominio asociado a una alerta de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c8a25-104">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c8a25-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c8a25-105">**Applies to:**</span></span>
- [<span data-ttu-id="c8a25-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c8a25-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c8a25-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c8a25-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c8a25-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c8a25-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c8a25-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="c8a25-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatedomain-abovefoldlink) 

<span data-ttu-id="c8a25-110">Investigar un dominio para ver si los dispositivos y servidores de la red empresarial se han estado comunicando con un dominio malintencionado conocido.</span><span class="sxs-lookup"><span data-stu-id="c8a25-110">Investigate a domain to see if devices and servers in your enterprise network have been communicating with a known malicious domain.</span></span>

<span data-ttu-id="c8a25-111">Puedes investigar un dominio mediante la característica de búsqueda o haciendo clic en un vínculo de dominio desde la escala de tiempo **del dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="c8a25-111">You can investigate a domain by using the search feature or by clicking on a domain link from the **Device timeline**.</span></span>

<span data-ttu-id="c8a25-112">Puede ver información de las siguientes secciones en la vista DIRECCIÓN URL:</span><span class="sxs-lookup"><span data-stu-id="c8a25-112">You can see information from the following sections in the URL view:</span></span>

- <span data-ttu-id="c8a25-113">Detalles de dirección URL, Contactos, Servidores de nombres</span><span class="sxs-lookup"><span data-stu-id="c8a25-113">URL details, Contacts, Nameservers</span></span>
- <span data-ttu-id="c8a25-114">Alertas relacionadas con esta dirección URL</span><span class="sxs-lookup"><span data-stu-id="c8a25-114">Alerts related to this URL</span></span> 
- <span data-ttu-id="c8a25-115">DIRECCIÓN URL en la organización</span><span class="sxs-lookup"><span data-stu-id="c8a25-115">URL in organization</span></span>
- <span data-ttu-id="c8a25-116">Dispositivos observados más recientes con dirección URL</span><span class="sxs-lookup"><span data-stu-id="c8a25-116">Most recent observed devices with URL</span></span>

## <a name="url-worldwide"></a><span data-ttu-id="c8a25-117">DIRECCIÓN URL en todo el mundo</span><span class="sxs-lookup"><span data-stu-id="c8a25-117">URL worldwide</span></span>

<span data-ttu-id="c8a25-118">La **sección Dirección URL** en todo el mundo enumera la dirección URL, un vínculo a más detalles en Whois, el número de incidentes abiertos relacionados y el número de alertas activas.</span><span class="sxs-lookup"><span data-stu-id="c8a25-118">The **URL Worldwide** section lists the URL, a link to further details at Whois, the number of related open incidents, and the number of active alerts.</span></span>

## <a name="incident"></a><span data-ttu-id="c8a25-119">Incidente</span><span class="sxs-lookup"><span data-stu-id="c8a25-119">Incident</span></span>

<span data-ttu-id="c8a25-120">La **tarjeta Incidentes** muestra un gráfico de barras de todas las alertas activas en incidentes de los últimos 180 días.</span><span class="sxs-lookup"><span data-stu-id="c8a25-120">The **Incident** card displays a bar chart of all active alerts in incidents over the past 180 days.</span></span>

## <a name="prevalence"></a><span data-ttu-id="c8a25-121">Prevalencia</span><span class="sxs-lookup"><span data-stu-id="c8a25-121">Prevalence</span></span>

<span data-ttu-id="c8a25-122">La **tarjeta de prevalencia** proporciona detalles sobre la prevalencia de la dirección URL dentro de la organización, durante un período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="c8a25-122">The **Prevalence** card provides details on the prevalence of the URL within the organization, over a specified period of time.</span></span>

<span data-ttu-id="c8a25-123">Aunque el período de tiempo predeterminado es de los últimos 30 días, puede personalizar el intervalo seleccionando la flecha hacia abajo en la esquina de la tarjeta.</span><span class="sxs-lookup"><span data-stu-id="c8a25-123">Although the default time period is the past 30 days, you can customize the range by selecting the downward-pointing arrow in the corner of the card.</span></span> <span data-ttu-id="c8a25-124">El intervalo más corto disponible es el de prevalencia del último día, mientras que el intervalo más largo es el de los últimos 6 meses.</span><span class="sxs-lookup"><span data-stu-id="c8a25-124">The shortest range available is for prevalence over the past day, while the longest range is over the past 6 months.</span></span>

## <a name="alerts"></a><span data-ttu-id="c8a25-125">Alertas</span><span class="sxs-lookup"><span data-stu-id="c8a25-125">Alerts</span></span>

<span data-ttu-id="c8a25-126">La **pestaña** Alertas proporciona una lista de alertas asociadas a la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="c8a25-126">The **Alerts** tab provides a list of alerts that are associated with the URL.</span></span> <span data-ttu-id="c8a25-127">La tabla que se muestra aquí es una versión filtrada de las alertas visibles en la pantalla Cola de alertas, que muestra solo alertas asociadas con el dominio, su gravedad, estado, incidente asociado, clasificación, estado de investigación, etc.</span><span class="sxs-lookup"><span data-stu-id="c8a25-127">The table shown here is a filtered version of the alerts visible on the Alert queue screen, showing only alerts associated with the domain, their severity, status, the associated incident, classification, investigation state, and more.</span></span>

<span data-ttu-id="c8a25-128">La pestaña Alertas se puede ajustar para mostrar  más o menos información, seleccionando Personalizar columnas en el menú de acciones encima de los encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="c8a25-128">The Alerts tab can be adjusted to show more or less information, by selecting **Customize columns** from the action menu above the column headers.</span></span> <span data-ttu-id="c8a25-129">El número de elementos que se muestran también se puede ajustar seleccionando elementos **por página** en el mismo menú.</span><span class="sxs-lookup"><span data-stu-id="c8a25-129">The number of items displayed can also be adjusted, by selecting **items per page** on the same menu.</span></span>

## <a name="observed-in-organization"></a><span data-ttu-id="c8a25-130">Observado en la organización</span><span class="sxs-lookup"><span data-stu-id="c8a25-130">Observed in organization</span></span>

<span data-ttu-id="c8a25-131">La **pestaña Observed in organization** proporciona una vista cronológica de los eventos y alertas asociadas que se observaron en la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="c8a25-131">The **Observed in organization** tab provides a chronological view on the events and associated alerts that were observed on the URL.</span></span> <span data-ttu-id="c8a25-132">Esta pestaña incluye una escala de tiempo y una tabla personalizable que enumera los detalles del evento, como la hora, el dispositivo y una breve descripción de lo que ocurrió.</span><span class="sxs-lookup"><span data-stu-id="c8a25-132">This tab includes a timeline and a customizable table listing event details, such as the time, device, and a brief description of what happened.</span></span> 

<span data-ttu-id="c8a25-133">Puede ver eventos de diferentes períodos de tiempo especificando las fechas en los campos de texto encima de los encabezados de tabla.</span><span class="sxs-lookup"><span data-stu-id="c8a25-133">You can view events from different periods of time by entering the dates into the text fields above the table headers.</span></span> <span data-ttu-id="c8a25-134">También puedes personalizar el intervalo de tiempo seleccionando diferentes áreas de la escala de tiempo.</span><span class="sxs-lookup"><span data-stu-id="c8a25-134">You can also customize the time range by selecting different areas of the timeline.</span></span>

<span data-ttu-id="c8a25-135">**Investigar un dominio:**</span><span class="sxs-lookup"><span data-stu-id="c8a25-135">**Investigate a domain:**</span></span>

1. <span data-ttu-id="c8a25-136">Seleccione **DIRECCIÓN URL** en el **menú** desplegable De la barra de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c8a25-136">Select **URL** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="c8a25-137">Escriba la dirección URL en el **campo** Búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c8a25-137">Enter the URL in the **Search** field.</span></span>
3. <span data-ttu-id="c8a25-138">Haga clic en el icono de búsqueda o presione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="c8a25-138">Click the search icon   or press **Enter**.</span></span> <span data-ttu-id="c8a25-139">Se muestran los detalles sobre la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="c8a25-139">Details about the URL are displayed.</span></span> <span data-ttu-id="c8a25-140">Nota: los resultados de la búsqueda solo se devolverán para las direcciones URL observadas en las comunicaciones de los dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="c8a25-140">Note: search results will only be returned for URLs observed in communications from devices in the organization.</span></span>
4. <span data-ttu-id="c8a25-141">Use los filtros de búsqueda para definir los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c8a25-141">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="c8a25-142">También puede usar el cuadro de búsqueda de escala de tiempo para filtrar los resultados mostrados de todos los dispositivos de la organización observados que se comunican con la dirección URL, el archivo asociado a la comunicación y la última fecha observada.</span><span class="sxs-lookup"><span data-stu-id="c8a25-142">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the URL, the file associated with the communication and the last date observed.</span></span>
5. <span data-ttu-id="c8a25-143">Hacer clic en cualquiera de los nombres de dispositivo te llevará a la vista de ese dispositivo, donde puedes seguir investigando alertas, comportamientos y eventos notificados.</span><span class="sxs-lookup"><span data-stu-id="c8a25-143">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c8a25-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c8a25-144">Related topics</span></span>
- [<span data-ttu-id="c8a25-145">Ver y organizar la cola de Alertas de punto de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c8a25-145">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="c8a25-146">Administrar alertas de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="c8a25-146">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="c8a25-147">Investigar alertas de punto de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c8a25-147">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="c8a25-148">Investigar un archivo asociado a una alerta de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c8a25-148">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="c8a25-149">Investigar dispositivos en la lista Microsoft Defender para dispositivos de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c8a25-149">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="c8a25-150">Investigar una dirección IP asociada a una alerta de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c8a25-150">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="c8a25-151">Investigar una cuenta de usuario en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="c8a25-151">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
