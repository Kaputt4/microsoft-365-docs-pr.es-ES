---
title: Técnicas en la escala de tiempo del dispositivo
description: Descripción de la escala de tiempo del dispositivo en Microsoft Defender para endpoint
keywords: escala de tiempo del dispositivo, punto de conexión, MITRE, MITRE ATT&CK, técnicas, tácticas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d6e2c18bd3710e659b5f9887844bc92528da4607
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070139"
---
# <a name="techniques-in-the-device-timeline"></a><span data-ttu-id="0a601-104">Técnicas en la escala de tiempo del dispositivo</span><span class="sxs-lookup"><span data-stu-id="0a601-104">Techniques in the device timeline</span></span>


<span data-ttu-id="0a601-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0a601-105">**Applies to:**</span></span>
- [<span data-ttu-id="0a601-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0a601-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)


<span data-ttu-id="0a601-107">Puedes obtener más información en una investigación analizando los eventos que sucedieron en un dispositivo específico.</span><span class="sxs-lookup"><span data-stu-id="0a601-107">You can gain more insight in an investigation by analyzing the events that happened on a specific device.</span></span> <span data-ttu-id="0a601-108">En primer lugar, selecciona el dispositivo de interés de la [lista Dispositivos](machines-view-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0a601-108">First, select the device of interest from the [Devices list](machines-view-overview.md).</span></span> <span data-ttu-id="0a601-109">En la página del dispositivo, puedes seleccionar la pestaña **Escala** de tiempo para ver todos los eventos que se produjeron en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0a601-109">On the device page, you can select the **Timeline** tab to view all the events that occurred on the device.</span></span>

## <a name="understand-techniques-in-the-timeline"></a><span data-ttu-id="0a601-110">Comprender técnicas en la escala de tiempo</span><span class="sxs-lookup"><span data-stu-id="0a601-110">Understand techniques in the timeline</span></span>

>[!IMPORTANT]
><span data-ttu-id="0a601-111">Parte de la información se relaciona con una característica de producto publicada previamente en la versión preliminar pública que puede modificarse considerablemente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="0a601-111">Some information relates to a prereleased product feature in public preview which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="0a601-112">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="0a601-112">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="0a601-113">En Microsoft Defender para endpoint, **las técnicas son** un tipo de datos adicional en la escala de tiempo del evento.</span><span class="sxs-lookup"><span data-stu-id="0a601-113">In Microsoft Defender for Endpoint, **Techniques** are an additional data type in the event timeline.</span></span> <span data-ttu-id="0a601-114">Las técnicas proporcionan más información sobre las actividades asociadas con [MITRE ATT&técnicas de CK](https://attack.mitre.org/) o sub-técnicas.</span><span class="sxs-lookup"><span data-stu-id="0a601-114">Techniques provide more insight on activities associated with [MITRE ATT&CK](https://attack.mitre.org/) techniques or sub-techniques.</span></span> 

<span data-ttu-id="0a601-115">Esta característica simplifica la experiencia de investigación al ayudar a los analistas a comprender las actividades que se observaron en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0a601-115">This feature simplifies the investigation experience by helping analysts understand the activities that were observed on a device.</span></span> <span data-ttu-id="0a601-116">A continuación, los analistas pueden decidir investigar más a fondo.</span><span class="sxs-lookup"><span data-stu-id="0a601-116">Analysts can then decide to investigate further.</span></span>

<span data-ttu-id="0a601-117">Para la vista previa pública, las técnicas están disponibles de forma predeterminada y se muestran junto con los eventos cuando se visualiza la escala de tiempo de un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0a601-117">For public preview, Techniques are available by default and shown together with events when a device's timeline is viewed.</span></span> 

![Técnicas en la captura de pantalla de la escala de tiempo del dispositivo](images/device-timeline-2.png)

<span data-ttu-id="0a601-119">Las técnicas se resaltan en texto en negrita y aparecen con un icono azul a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="0a601-119">Techniques are highlighted in bold text and appear with a blue icon on the left.</span></span> <span data-ttu-id="0a601-120">El nombre de la técnica y el identificador de CK&MITRE ATT correspondiente también aparecen como etiquetas en Información adicional.</span><span class="sxs-lookup"><span data-stu-id="0a601-120">The corresponding MITRE ATT&CK ID and technique name also appear as tags under Additional information.</span></span> 

<span data-ttu-id="0a601-121">Las opciones de búsqueda y exportación también están disponibles para Técnicas.</span><span class="sxs-lookup"><span data-stu-id="0a601-121">Search and Export options are also available for Techniques.</span></span>

## <a name="investigate-using-the-side-pane"></a><span data-ttu-id="0a601-122">Investigar con el panel lateral</span><span class="sxs-lookup"><span data-stu-id="0a601-122">Investigate using the side pane</span></span>

<span data-ttu-id="0a601-123">Seleccione una técnica para abrir su panel lateral correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0a601-123">Select a Technique to open its corresponding side pane.</span></span> <span data-ttu-id="0a601-124">Aquí puede ver información e información adicionales, como att relacionado&técnicas de CK, tácticas y descripciones.</span><span class="sxs-lookup"><span data-stu-id="0a601-124">Here you can see additional information and insights like related ATT&CK techniques, tactics, and descriptions.</span></span> 

<span data-ttu-id="0a601-125">Seleccione la técnica *de ataque específica* para abrir la página relacionada&técnica de CK de ATT donde encontrará más información al respecto.</span><span class="sxs-lookup"><span data-stu-id="0a601-125">Select the specific *Attack technique* to open the related ATT&CK technique page where you can find more information about it.</span></span>

<span data-ttu-id="0a601-126">Puede copiar los detalles de una entidad cuando vea un icono azul a la derecha.</span><span class="sxs-lookup"><span data-stu-id="0a601-126">You can copy an entity's details when you see a blue icon on the right.</span></span> <span data-ttu-id="0a601-127">Por ejemplo, para copiar el SHA1 de un archivo relacionado, seleccione el icono de página azul.</span><span class="sxs-lookup"><span data-stu-id="0a601-127">For instance, to copy a related file's SHA1, select the blue page icon.</span></span>

![Copiar detalles de entidad](images/techniques-side-pane-clickable.png)

<span data-ttu-id="0a601-129">Puede hacer lo mismo con las líneas de comandos.</span><span class="sxs-lookup"><span data-stu-id="0a601-129">You can do the same for command lines.</span></span>

![Copiar línea de comandos](images/techniques-side-pane-command.png)


## <a name="investigate-related-events"></a><span data-ttu-id="0a601-131">Investigar eventos relacionados</span><span class="sxs-lookup"><span data-stu-id="0a601-131">Investigate related events</span></span>

<span data-ttu-id="0a601-132">Para usar [la búsqueda avanzada](advanced-hunting-overview.md) para buscar eventos relacionados con la técnica seleccionada, seleccione Buscar para eventos **relacionados.**</span><span class="sxs-lookup"><span data-stu-id="0a601-132">To use [advanced hunting](advanced-hunting-overview.md) to find events related to the selected Technique, select **Hunt for related events**.</span></span> <span data-ttu-id="0a601-133">Esto lleva a la página de búsqueda avanzada con una consulta para encontrar eventos relacionados con la técnica.</span><span class="sxs-lookup"><span data-stu-id="0a601-133">This leads to the advanced hunting page with a query to find events related to the Technique.</span></span>

![Buscar eventos relacionados](images/techniques-hunt-for-related-events.png)

>[!NOTE]
><span data-ttu-id="0a601-135">Las consultas con el botón **Buscar** eventos relacionados desde un panel lateral Técnica muestran todos los eventos relacionados con la técnica identificada, pero no incluyen la técnica en sí en los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="0a601-135">Querying using the **Hunt for related events** button from a Technique side pane displays all the events related to the identified technique but does not include the Technique itself in the query results.</span></span>


## <a name="customize-your-device-timeline"></a><span data-ttu-id="0a601-136">Personalizar la escala de tiempo del dispositivo</span><span class="sxs-lookup"><span data-stu-id="0a601-136">Customize your device timeline</span></span>

<span data-ttu-id="0a601-137">En la parte superior derecha de la escala de tiempo del dispositivo, puedes elegir un intervalo de fechas para limitar el número de eventos y técnicas de la escala de tiempo.</span><span class="sxs-lookup"><span data-stu-id="0a601-137">On the upper right-hand side of the device timeline, you can choose a date range to limit the number of events and techniques in the timeline.</span></span> 

<span data-ttu-id="0a601-138">Puede personalizar las columnas que se deben exponer.</span><span class="sxs-lookup"><span data-stu-id="0a601-138">You can customize which columns to expose.</span></span> <span data-ttu-id="0a601-139">También puede filtrar los eventos marcados por tipo de datos o por grupo de eventos.</span><span class="sxs-lookup"><span data-stu-id="0a601-139">You can also filter for flagged events by data type or by event group.</span></span>

### <a name="choose-columns-to-expose"></a><span data-ttu-id="0a601-140">Elegir columnas para exponer</span><span class="sxs-lookup"><span data-stu-id="0a601-140">Choose columns to expose</span></span>
<span data-ttu-id="0a601-141">Puede elegir qué columnas exponer en la escala de tiempo seleccionando el **botón Elegir** columnas.</span><span class="sxs-lookup"><span data-stu-id="0a601-141">You can choose which columns to expose in the timeline by selecting the **Choose columns** button.</span></span>

![Personalizar columnas](images/filter-customize-columns.png)

<span data-ttu-id="0a601-143">Desde allí, puede seleccionar qué conjunto de información incluir.</span><span class="sxs-lookup"><span data-stu-id="0a601-143">From there you can select which information set to include.</span></span>

### <a name="filter-to-view-techniques-or-events-only"></a><span data-ttu-id="0a601-144">Filtrar solo para ver técnicas o eventos</span><span class="sxs-lookup"><span data-stu-id="0a601-144">Filter to view techniques or events only</span></span>

<span data-ttu-id="0a601-145">Para ver solo eventos o técnicas, selecciona **Filtros en** la escala de tiempo del dispositivo y elige el tipo de datos que prefieras ver.</span><span class="sxs-lookup"><span data-stu-id="0a601-145">To view only either events or techniques, select **Filters** from the device timeline and choose your preferred Data type to view.</span></span>

![Captura de pantalla de filtros](images/device-timeline-filters.png)



## <a name="see-also"></a><span data-ttu-id="0a601-147">Ver también</span><span class="sxs-lookup"><span data-stu-id="0a601-147">See also</span></span>
- [<span data-ttu-id="0a601-148">Ver y organizar la lista de dispositivos</span><span class="sxs-lookup"><span data-stu-id="0a601-148">View and organize the Devices list</span></span>](machines-view-overview.md)
- [<span data-ttu-id="0a601-149">Marcas de eventos de escala de tiempo de dispositivo de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0a601-149">Microsoft Defender for Endpoint device timeline event flags</span></span>](device-timeline-event-flag.md) 


 
