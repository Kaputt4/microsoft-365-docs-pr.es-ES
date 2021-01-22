---
title: Obtener información relevante sobre una entidad con go hunt
description: Aprenda a usar la herramienta de búsqueda de ir para consultar rápidamente información relevante sobre una entidad o evento mediante la búsqueda avanzada.
keywords: búsqueda avanzada, incidente, pivot, entidad, ir a la búsqueda, eventos relevantes, búsqueda de amenazas, búsqueda de ciberamenazas, búsqueda, consulta, telemetría, Microsoft 365, Protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e707fe8b3dff40d0698630cd0592b297042e5fb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929516"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="3c37c-104">Búsqueda rápida de información de entidad o evento con go hunt</span><span class="sxs-lookup"><span data-stu-id="3c37c-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3c37c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3c37c-105">**Applies to:**</span></span>
- <span data-ttu-id="3c37c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c37c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3c37c-107">Con la *acción de búsqueda* go, puede investigar rápidamente eventos y varios tipos de entidad mediante potentes capacidades de búsqueda avanzada [basadas en](advanced-hunting-overview.md) consultas.</span><span class="sxs-lookup"><span data-stu-id="3c37c-107">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="3c37c-108">Esta acción ejecuta automáticamente una consulta de búsqueda avanzada para buscar información relevante sobre el evento o la entidad seleccionados.</span><span class="sxs-lookup"><span data-stu-id="3c37c-108">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="3c37c-109">La *acción de búsqueda* de ir está disponible en varias secciones del centro de seguridad siempre que se muestren detalles de eventos o entidades.</span><span class="sxs-lookup"><span data-stu-id="3c37c-109">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="3c37c-110">Por ejemplo, puede usar *ir a la búsqueda* en las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3c37c-110">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="3c37c-111">En la [página de incidentes,](investigate-incidents.md#incident-overview)puede revisar los detalles sobre usuarios, dispositivos y muchas otras entidades asociadas a un incidente.</span><span class="sxs-lookup"><span data-stu-id="3c37c-111">In the [incident page](investigate-incidents.md#incident-overview), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="3c37c-112">A medida que selecciona una entidad, obtiene información adicional, así como diversas acciones que puede llevar a cabo en esa entidad.</span><span class="sxs-lookup"><span data-stu-id="3c37c-112">As you select an entity, you get additional information as well as various actions you could take on that entitity.</span></span> <span data-ttu-id="3c37c-113">En el siguiente ejemplo, se selecciona un buzón que muestra detalles sobre el buzón, así como la opción de buscar más información sobre el buzón.</span><span class="sxs-lookup"><span data-stu-id="3c37c-113">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![Imagen que muestra los detalles del buzón con la opción ir a la búsqueda](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="3c37c-115">En la página de incidentes, también puede obtener acceso a una lista de entidades en la pestaña Evidencia. La selección de una de estas entidades ofrece una opción para buscar rápidamente información sobre esa entidad.</span><span class="sxs-lookup"><span data-stu-id="3c37c-115">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![Imagen que muestra el archivo seleccionado con la opción ir a la búsqueda en la pestaña Evidencia](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="3c37c-117">Al ver la escala de tiempo de un dispositivo, puedes seleccionar un evento en la escala de tiempo para ver información adicional sobre ese evento.</span><span class="sxs-lookup"><span data-stu-id="3c37c-117">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="3c37c-118">Una vez seleccionado un evento, se obtiene la opción de buscar otros eventos relevantes en la búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="3c37c-118">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Imagen que muestra los detalles del evento con la opción ir a la búsqueda](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="3c37c-120">Al seleccionar **La búsqueda o** **la** búsqueda para eventos relacionados, se pasan distintas consultas, dependiendo de si ha seleccionado una entidad o un evento.</span><span class="sxs-lookup"><span data-stu-id="3c37c-120">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="3c37c-121">Consulta de información de entidad</span><span class="sxs-lookup"><span data-stu-id="3c37c-121">Query for entity information</span></span>
<span data-ttu-id="3c37c-122">Al usar *la* búsqueda go para consultar información sobre un usuario, dispositivo o cualquier otro tipo de entidad, la consulta comprueba todas las tablas de esquema relevantes en busca de eventos relacionados con esa entidad.</span><span class="sxs-lookup"><span data-stu-id="3c37c-122">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="3c37c-123">Para que los resultados se puedan administrar, la consulta se dirige al mismo período de tiempo que la actividad más temprana de los últimos 30 días que implica a la entidad y está asociada con el incidente.</span><span class="sxs-lookup"><span data-stu-id="3c37c-123">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="3c37c-124">Este es un ejemplo de la consulta de búsqueda de destino para un dispositivo:</span><span class="sxs-lookup"><span data-stu-id="3c37c-124">Here is an example of the go hunt query for a device:</span></span>

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
### <a name="supported-entity-types"></a><span data-ttu-id="3c37c-125">Tipos de entidad admitidos</span><span class="sxs-lookup"><span data-stu-id="3c37c-125">Supported entity types</span></span>
<span data-ttu-id="3c37c-126">Puede usar ir *a la búsqueda* después de seleccionar cualquiera de estos tipos de entidad:</span><span class="sxs-lookup"><span data-stu-id="3c37c-126">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="3c37c-127">Archivos</span><span class="sxs-lookup"><span data-stu-id="3c37c-127">Files</span></span>
- <span data-ttu-id="3c37c-128">Mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="3c37c-128">Emails</span></span>
- <span data-ttu-id="3c37c-129">Clústeres de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="3c37c-129">Email clusters</span></span>
- <span data-ttu-id="3c37c-130">Buzones</span><span class="sxs-lookup"><span data-stu-id="3c37c-130">Mailboxes</span></span>
- <span data-ttu-id="3c37c-131">Usuarios</span><span class="sxs-lookup"><span data-stu-id="3c37c-131">Users</span></span>
- <span data-ttu-id="3c37c-132">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="3c37c-132">Devices</span></span>
- <span data-ttu-id="3c37c-133">Direcciones IP</span><span class="sxs-lookup"><span data-stu-id="3c37c-133">IP addresses</span></span>
- <span data-ttu-id="3c37c-134">Direcciones URL</span><span class="sxs-lookup"><span data-stu-id="3c37c-134">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="3c37c-135">Consulta de información de eventos</span><span class="sxs-lookup"><span data-stu-id="3c37c-135">Query for event information</span></span>
<span data-ttu-id="3c37c-136">Al usar *la búsqueda go para* consultar información sobre un evento de escala de tiempo, la consulta comprueba todas las tablas de esquema relevantes para otros eventos en el momento del evento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3c37c-136">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="3c37c-137">Por ejemplo, la siguiente consulta enumera los eventos de varias tablas de esquema que se produjeron alrededor del mismo período de tiempo en el mismo dispositivo:</span><span class="sxs-lookup"><span data-stu-id="3c37c-137">For example, the following query lists events in various schema tables that occured around the same time period on the same device:</span></span>

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

## <a name="adjust-the-query"></a><span data-ttu-id="3c37c-138">Ajustar la consulta</span><span class="sxs-lookup"><span data-stu-id="3c37c-138">Adjust the query</span></span>
<span data-ttu-id="3c37c-139">Con cierto conocimiento del lenguaje [de consulta,](advanced-hunting-query-language.md)puede ajustar la consulta a sus preferencias.</span><span class="sxs-lookup"><span data-stu-id="3c37c-139">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="3c37c-140">Por ejemplo, puede ajustar esta línea, que determina el tamaño de la ventana de tiempo:</span><span class="sxs-lookup"><span data-stu-id="3c37c-140">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="3c37c-141">Además de modificar la consulta para obtener resultados más relevantes, también puede:</span><span class="sxs-lookup"><span data-stu-id="3c37c-141">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="3c37c-142">Ver los resultados como gráficos</span><span class="sxs-lookup"><span data-stu-id="3c37c-142">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="3c37c-143">Crear una regla de detección personalizada</span><span class="sxs-lookup"><span data-stu-id="3c37c-143">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="3c37c-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3c37c-144">Related topics</span></span>
- [<span data-ttu-id="3c37c-145">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="3c37c-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3c37c-146">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="3c37c-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3c37c-147">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="3c37c-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="3c37c-148">Reglas de detección personalizadas</span><span class="sxs-lookup"><span data-stu-id="3c37c-148">Custom detection rules</span></span>](custom-detection-rules.md)
