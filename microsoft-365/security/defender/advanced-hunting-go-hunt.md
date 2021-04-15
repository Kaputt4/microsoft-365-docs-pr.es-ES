---
title: Obtener información relevante sobre una entidad con go hunt
description: Obtenga información sobre cómo usar la herramienta ir a la búsqueda para consultar rápidamente información relevante sobre una entidad o evento mediante la búsqueda avanzada.
keywords: búsqueda avanzada, incidente, pivot, entidad, ir a buscar, eventos relevantes, búsqueda de amenazas, búsqueda de amenazas cibernéticas, búsqueda, consulta, telemetría, Microsoft 365, Protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 0f09f74a1cefad5a9b6b438752ebe57e583397c7
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759983"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="018a9-104">Búsqueda rápida de información de entidad o evento con go hunt</span><span class="sxs-lookup"><span data-stu-id="018a9-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="018a9-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="018a9-105">**Applies to:**</span></span>
- <span data-ttu-id="018a9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="018a9-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="018a9-107">Con la *acción ir a la* búsqueda, puede investigar rápidamente eventos y varios tipos de entidad mediante potentes capacidades de búsqueda avanzada basadas en consultas. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="018a9-107">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="018a9-108">Esta acción ejecuta automáticamente una consulta de búsqueda avanzada para buscar información relevante sobre el evento o entidad seleccionado.</span><span class="sxs-lookup"><span data-stu-id="018a9-108">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="018a9-109">La *acción ir a la* búsqueda está disponible en varias secciones del centro de seguridad siempre que se muestren los detalles de evento o entidad.</span><span class="sxs-lookup"><span data-stu-id="018a9-109">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="018a9-110">Por ejemplo, puede usar *ir a buscar* desde las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="018a9-110">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="018a9-111">En la [página de incidentes,](investigate-incidents.md#summary)puede revisar detalles sobre usuarios, dispositivos y muchas otras entidades asociadas con un incidente.</span><span class="sxs-lookup"><span data-stu-id="018a9-111">In the [incident page](investigate-incidents.md#summary), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="018a9-112">A medida que selecciona una entidad, obtiene información adicional, así como diversas acciones que podría llevar a cabo en esa entitidad.</span><span class="sxs-lookup"><span data-stu-id="018a9-112">As you select an entity, you get additional information as well as various actions you could take on that entitity.</span></span> <span data-ttu-id="018a9-113">En el ejemplo siguiente, se selecciona un buzón, que muestra detalles sobre el buzón, así como la opción de buscar más información sobre el buzón.</span><span class="sxs-lookup"><span data-stu-id="018a9-113">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![Imagen que muestra los detalles del buzón con la opción ir a la búsqueda](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="018a9-115">En la página de incidentes, también puede obtener acceso a una lista de entidades en la pestaña evidencia. Seleccionar una de estas entidades proporciona una opción para buscar rápidamente información sobre esa entidad.</span><span class="sxs-lookup"><span data-stu-id="018a9-115">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![Imagen que muestra el archivo seleccionado con la opción ir a la búsqueda en la pestaña Evidencia](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="018a9-117">Al ver la escala de tiempo de un dispositivo, puedes seleccionar un evento en la escala de tiempo para ver información adicional sobre ese evento.</span><span class="sxs-lookup"><span data-stu-id="018a9-117">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="018a9-118">Una vez seleccionado un evento, se obtiene la opción de buscar otros eventos relevantes en la búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="018a9-118">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Imagen que muestra los detalles del evento con la opción ir a la búsqueda](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="018a9-120">Al seleccionar **Ir a la búsqueda** o a **La** búsqueda de eventos relacionados, se pasan distintas consultas, según si ha seleccionado una entidad o un evento.</span><span class="sxs-lookup"><span data-stu-id="018a9-120">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="018a9-121">Consulta de información de entidad</span><span class="sxs-lookup"><span data-stu-id="018a9-121">Query for entity information</span></span>
<span data-ttu-id="018a9-122">Al usar *ir a buscar* para consultar información sobre un usuario, dispositivo o cualquier otro tipo de entidad, la consulta comprueba en todas las tablas de esquema relevantes cualquier evento que implique esa entidad.</span><span class="sxs-lookup"><span data-stu-id="018a9-122">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="018a9-123">Para que los resultados se puedan administrar, la consulta tiene el ámbito alrededor del mismo período de tiempo que la actividad más temprana de los últimos 30 días que implica a la entidad y está asociada con el incidente.</span><span class="sxs-lookup"><span data-stu-id="018a9-123">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="018a9-124">Este es un ejemplo de la consulta de búsqueda de ir para un dispositivo:</span><span class="sxs-lookup"><span data-stu-id="018a9-124">Here is an example of the go hunt query for a device:</span></span>

```kusto
let selectedTimestamp = datetime(2020-06-02T02:06:47.1167157Z);
let deviceName = "fv-az770.example.com";
let deviceId = "device-guid";
search in (DeviceLogonEvents, DeviceProcessEvents, DeviceNetworkEvents, DeviceFileEvents, DeviceRegistryEvents, DeviceImageLoadEvents, DeviceEvents, DeviceImageLoadEvents, IdentityLogonEvents, IdentityQueryEvents)
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
and DeviceName == deviceName
// or RemoteDeviceName == deviceName
// or DeviceId == deviceId
| take 100
```
### <a name="supported-entity-types"></a><span data-ttu-id="018a9-125">Tipos de entidad compatibles</span><span class="sxs-lookup"><span data-stu-id="018a9-125">Supported entity types</span></span>
<span data-ttu-id="018a9-126">Puede usar *ir a buscar después* de seleccionar cualquiera de estos tipos de entidad:</span><span class="sxs-lookup"><span data-stu-id="018a9-126">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="018a9-127">Archivos</span><span class="sxs-lookup"><span data-stu-id="018a9-127">Files</span></span>
- <span data-ttu-id="018a9-128">Mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="018a9-128">Emails</span></span>
- <span data-ttu-id="018a9-129">Clústeres de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="018a9-129">Email clusters</span></span>
- <span data-ttu-id="018a9-130">Buzones</span><span class="sxs-lookup"><span data-stu-id="018a9-130">Mailboxes</span></span>
- <span data-ttu-id="018a9-131">Usuarios</span><span class="sxs-lookup"><span data-stu-id="018a9-131">Users</span></span>
- <span data-ttu-id="018a9-132">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="018a9-132">Devices</span></span>
- <span data-ttu-id="018a9-133">Direcciones IP</span><span class="sxs-lookup"><span data-stu-id="018a9-133">IP addresses</span></span>
- <span data-ttu-id="018a9-134">Direcciones URL</span><span class="sxs-lookup"><span data-stu-id="018a9-134">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="018a9-135">Consulta de información de eventos</span><span class="sxs-lookup"><span data-stu-id="018a9-135">Query for event information</span></span>
<span data-ttu-id="018a9-136">Al usar *ir a buscar* para consultar información sobre un evento de escala de tiempo, la consulta comprueba todas las tablas de esquema relevantes para otros eventos en el momento del evento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="018a9-136">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="018a9-137">Por ejemplo, la siguiente consulta enumera los eventos de varias tablas de esquema que se produjeron alrededor del mismo período de tiempo en el mismo dispositivo:</span><span class="sxs-lookup"><span data-stu-id="018a9-137">For example, the following query lists events in various schema tables that occured around the same time period on the same device:</span></span>

```kusto
// List relevant events 30 minutes before and after selected LogonAttempted event
let selectedEventTimestamp = datetime(2020-06-04T01:29:09.2496688Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "079ecf9c5798d249128817619606c1c47369eb3e"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a><span data-ttu-id="018a9-138">Ajustar la consulta</span><span class="sxs-lookup"><span data-stu-id="018a9-138">Adjust the query</span></span>
<span data-ttu-id="018a9-139">Con cierto conocimiento del idioma [de consulta,](advanced-hunting-query-language.md)puede ajustar la consulta a su preferencia.</span><span class="sxs-lookup"><span data-stu-id="018a9-139">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="018a9-140">Por ejemplo, puede ajustar esta línea, que determina el tamaño de la ventana de tiempo:</span><span class="sxs-lookup"><span data-stu-id="018a9-140">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="018a9-141">Además de modificar la consulta para obtener resultados más relevantes, también puede:</span><span class="sxs-lookup"><span data-stu-id="018a9-141">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="018a9-142">Ver los resultados como gráficos</span><span class="sxs-lookup"><span data-stu-id="018a9-142">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="018a9-143">Crear una regla de detección personalizada</span><span class="sxs-lookup"><span data-stu-id="018a9-143">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="018a9-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="018a9-144">Related topics</span></span>
- [<span data-ttu-id="018a9-145">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="018a9-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="018a9-146">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="018a9-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="018a9-147">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="018a9-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="018a9-148">Reglas de detección personalizada</span><span class="sxs-lookup"><span data-stu-id="018a9-148">Custom detection rules</span></span>](custom-detection-rules.md)
