---
title: Obtener información relevante sobre una entidad con Go Hunt
description: Obtenga información sobre cómo usar la herramienta "ir a la búsqueda" en para consultar rápidamente información relevante sobre una entidad o evento mediante la búsqueda avanzada.
keywords: búsqueda avanzada, incidencia, pivote, entidad, avance, acontecimientos relevantes, caza de amenazas, búsqueda de amenazas en el ciberespacio, búsqueda, consulta, telemetría, Microsoft 365, protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b9afecb3d0efce93ae5d5725bba71d8d9719d17f
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430416"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="b0d2f-104">Búsqueda rápida de información de entidad o eventos con Go Hunt</span><span class="sxs-lookup"><span data-stu-id="b0d2f-104">Quickly hunt for entity or event information with go hunt</span></span>

<span data-ttu-id="b0d2f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b0d2f-105">**Applies to:**</span></span>
- <span data-ttu-id="b0d2f-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0d2f-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b0d2f-107">Con la acción de *búsqueda go* , puede investigar rápidamente eventos y varios tipos de entidades usando funciones eficaces de [búsqueda avanzada](advanced-hunting-overview.md) basadas en consultas.</span><span class="sxs-lookup"><span data-stu-id="b0d2f-107">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="b0d2f-108">Esta acción ejecuta automáticamente una consulta de búsqueda avanzada para buscar información relevante sobre la entidad o el evento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b0d2f-108">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="b0d2f-109">La acción *ir a búsqueda* está disponible en varias secciones del centro de seguridad siempre que se muestran los detalles de la entidad o el evento.</span><span class="sxs-lookup"><span data-stu-id="b0d2f-109">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="b0d2f-110">Por ejemplo, puede usar *Go Hunt* en las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="b0d2f-110">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="b0d2f-111">En la [Página incidente](investigate-incidents.md#incident-overview), puede revisar los detalles de los usuarios, los dispositivos y muchas otras entidades asociadas a un incidente.</span><span class="sxs-lookup"><span data-stu-id="b0d2f-111">In the [incident page](investigate-incidents.md#incident-overview), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="b0d2f-112">Al seleccionar una entidad, obtiene información adicional y varias acciones que puede llevar a cabo en ese entitity.</span><span class="sxs-lookup"><span data-stu-id="b0d2f-112">As you select an entity, you get additional information as well as various actions you could take on that entitity.</span></span> <span data-ttu-id="b0d2f-113">En el ejemplo siguiente, se selecciona un buzón, que muestra los detalles sobre el buzón y la opción de búsqueda para obtener más información sobre el buzón.</span><span class="sxs-lookup"><span data-stu-id="b0d2f-113">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![Imagen que muestra los detalles del buzón con la opción de búsqueda Go](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="b0d2f-115">En la página incidente, también puede tener acceso a una lista de entidades en la pestaña evidencia. al seleccionar una de estas entidades, se obtiene una opción para buscar información sobre dicha entidad rápidamente.</span><span class="sxs-lookup"><span data-stu-id="b0d2f-115">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![Imagen que muestra el archivo seleccionado con la opción go Hunt en la pestaña Evidence](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="b0d2f-117">Al ver la escala de tiempo de un dispositivo, puede seleccionar un evento en la escala de tiempo para ver información adicional sobre el evento.</span><span class="sxs-lookup"><span data-stu-id="b0d2f-117">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="b0d2f-118">Una vez que se selecciona un evento, se obtiene la opción de buscar otros eventos relevantes en la búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="b0d2f-118">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Imagen donde se muestran los detalles del evento con la opción de búsqueda Go](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="b0d2f-120">La selección de ir a la **búsqueda** o **búsqueda de eventos relacionados** pasa distintas consultas, en función de si ha seleccionado una entidad o un evento.</span><span class="sxs-lookup"><span data-stu-id="b0d2f-120">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="b0d2f-121">Consultar la información de la entidad</span><span class="sxs-lookup"><span data-stu-id="b0d2f-121">Query for entity information</span></span>
<span data-ttu-id="b0d2f-122">Cuando se usa *Go* to Query para obtener información sobre un usuario, dispositivo o cualquier otro tipo de entidad, la consulta comprueba todas las tablas del esquema relevantes para los eventos que impliquen esa entidad.</span><span class="sxs-lookup"><span data-stu-id="b0d2f-122">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="b0d2f-123">Para que los resultados sean manejables, la consulta se limita al mismo período de tiempo que la actividad más temprana en los últimos 30 días que implica a la entidad y está asociada con el incidente.</span><span class="sxs-lookup"><span data-stu-id="b0d2f-123">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="b0d2f-124">Este es un ejemplo de la consulta go Hunt para un dispositivo:</span><span class="sxs-lookup"><span data-stu-id="b0d2f-124">Here is an example of the go hunt query for a device:</span></span>

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
### <a name="supported-entity-types"></a><span data-ttu-id="b0d2f-125">Tipos de entidades compatibles</span><span class="sxs-lookup"><span data-stu-id="b0d2f-125">Supported entity types</span></span>
<span data-ttu-id="b0d2f-126">Puede usar la *búsqueda go* después de seleccionar cualquiera de estos tipos de entidad:</span><span class="sxs-lookup"><span data-stu-id="b0d2f-126">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="b0d2f-127">Archivos</span><span class="sxs-lookup"><span data-stu-id="b0d2f-127">Files</span></span>
- <span data-ttu-id="b0d2f-128">Mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="b0d2f-128">Emails</span></span>
- <span data-ttu-id="b0d2f-129">Clústeres de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="b0d2f-129">Email clusters</span></span>
- <span data-ttu-id="b0d2f-130">Buzones</span><span class="sxs-lookup"><span data-stu-id="b0d2f-130">Mailboxes</span></span>
- <span data-ttu-id="b0d2f-131">Usuarios</span><span class="sxs-lookup"><span data-stu-id="b0d2f-131">Users</span></span>
- <span data-ttu-id="b0d2f-132">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="b0d2f-132">Devices</span></span>
- <span data-ttu-id="b0d2f-133">Direcciones IP</span><span class="sxs-lookup"><span data-stu-id="b0d2f-133">IP addresses</span></span>
- <span data-ttu-id="b0d2f-134">Direcciones URL</span><span class="sxs-lookup"><span data-stu-id="b0d2f-134">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="b0d2f-135">Consultar la información de eventos</span><span class="sxs-lookup"><span data-stu-id="b0d2f-135">Query for event information</span></span>
<span data-ttu-id="b0d2f-136">Cuando se usa *Go* to Query para obtener información sobre un evento de escala de tiempo, la consulta comprueba todas las tablas de esquema relevantes en busca de otros eventos alrededor de la hora del evento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b0d2f-136">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="b0d2f-137">Por ejemplo, la siguiente consulta enumera los eventos en varias tablas de esquema que se produjeron alrededor del mismo período de tiempo en el mismo dispositivo:</span><span class="sxs-lookup"><span data-stu-id="b0d2f-137">For example, the following query lists events in various schema tables that occured around the same time period on the same device:</span></span>

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

## <a name="adjust-the-query"></a><span data-ttu-id="b0d2f-138">Ajustar la consulta</span><span class="sxs-lookup"><span data-stu-id="b0d2f-138">Adjust the query</span></span>
<span data-ttu-id="b0d2f-139">Con algún conocimiento del [lenguaje de consulta](advanced-hunting-query-language.md), puede ajustar la consulta a sus preferencias.</span><span class="sxs-lookup"><span data-stu-id="b0d2f-139">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="b0d2f-140">Por ejemplo, puede ajustar esta línea, que determina el tamaño de la ventana de tiempo:</span><span class="sxs-lookup"><span data-stu-id="b0d2f-140">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="b0d2f-141">Además de modificar la consulta para obtener resultados más relevantes, también puede:</span><span class="sxs-lookup"><span data-stu-id="b0d2f-141">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="b0d2f-142">Ver los resultados como gráficos</span><span class="sxs-lookup"><span data-stu-id="b0d2f-142">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="b0d2f-143">Crear una regla de detección personalizada</span><span class="sxs-lookup"><span data-stu-id="b0d2f-143">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="b0d2f-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b0d2f-144">Related topics</span></span>
- [<span data-ttu-id="b0d2f-145">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="b0d2f-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b0d2f-146">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="b0d2f-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b0d2f-147">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="b0d2f-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="b0d2f-148">Reglas de detección personalizadas</span><span class="sxs-lookup"><span data-stu-id="b0d2f-148">Custom detection rules</span></span>](custom-detection-rules.md)