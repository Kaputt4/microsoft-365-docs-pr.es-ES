---
title: Obtener información relevante sobre una entidad con go hunt
description: Obtenga información sobre cómo usar la herramienta ir a la búsqueda para consultar rápidamente información relevante sobre una entidad o evento mediante la búsqueda avanzada.
keywords: búsqueda avanzada, incidente, pivot, entidad, ir a buscar, eventos relevantes, búsqueda de amenazas, búsqueda de amenazas cibernéticas, búsqueda, consulta, telemetría, Microsoft 365, Microsoft 365 Defender
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
ms.openlocfilehash: 51d33ea9a372b5bfe017f4c3544e0d6413d53001
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935838"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>Búsqueda rápida de información de entidad o evento con go hunt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Con la *acción ir a la* búsqueda, puede investigar rápidamente eventos y varios tipos de entidad mediante potentes capacidades de búsqueda avanzada basadas en consultas. [](advanced-hunting-overview.md) Esta acción ejecuta automáticamente una consulta de búsqueda avanzada para buscar información relevante sobre el evento o entidad seleccionado.

La *acción ir a la* búsqueda está disponible en varias secciones del centro de seguridad siempre que se muestren los detalles de evento o entidad. Por ejemplo, puede usar *ir a buscar* desde las secciones siguientes:

- En la [página de incidentes,](investigate-incidents.md#summary)puede revisar detalles sobre usuarios, dispositivos y muchas otras entidades asociadas con un incidente. A medida que selecciona una entidad, obtiene información adicional, así como diversas acciones que podría llevar a cabo en esa entitidad. En el ejemplo siguiente, se selecciona un buzón, que muestra detalles sobre el buzón, así como la opción de buscar más información sobre el buzón.

    ![Imagen que muestra los detalles del buzón con la opción ir a la búsqueda](../../media/mtp-ah/go-hunt-email.png)

- En la página de incidentes, también puede obtener acceso a una lista de entidades en la pestaña evidencia. Seleccionar una de estas entidades proporciona una opción para buscar rápidamente información sobre esa entidad.

    ![Imagen que muestra el archivo seleccionado con la opción ir a la búsqueda en la pestaña Evidencia](../../media/mtp-ah/go-hunt-evidence-file.png)


- Al ver la escala de tiempo de un dispositivo, puedes seleccionar un evento en la escala de tiempo para ver información adicional sobre ese evento. Una vez seleccionado un evento, se obtiene la opción de buscar otros eventos relevantes en la búsqueda avanzada.

    ![Imagen que muestra los detalles del evento con la opción ir a la búsqueda](../../media/mtp-ah/go-hunt-event.png)

Al seleccionar **Ir a la búsqueda** o a **La** búsqueda de eventos relacionados, se pasan distintas consultas, según si ha seleccionado una entidad o un evento.

## <a name="query-for-entity-information"></a>Consulta de información de entidad
Al usar *ir a buscar* para consultar información sobre un usuario, dispositivo o cualquier otro tipo de entidad, la consulta comprueba en todas las tablas de esquema relevantes cualquier evento que implique esa entidad. Para que los resultados se puedan administrar, la consulta tiene el ámbito alrededor del mismo período de tiempo que la actividad más temprana de los últimos 30 días que implica a la entidad y está asociada con el incidente.

Este es un ejemplo de la consulta de búsqueda de ir para un dispositivo:

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
### <a name="supported-entity-types"></a>Tipos de entidad compatibles
Puede usar *ir a buscar después* de seleccionar cualquiera de estos tipos de entidad:

- Archivos
- Mensajes de correo electrónico
- Clústeres de correo electrónico
- Buzones
- Usuarios
- Dispositivos
- Direcciones IP
- Direcciones URL

## <a name="query-for-event-information"></a>Consulta de información de eventos
Al usar *ir a buscar* para consultar información sobre un evento de escala de tiempo, la consulta comprueba todas las tablas de esquema relevantes para otros eventos en el momento del evento seleccionado. Por ejemplo, la siguiente consulta enumera los eventos de varias tablas de esquema que se produjeron alrededor del mismo período de tiempo en el mismo dispositivo:

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

## <a name="adjust-the-query"></a>Ajustar la consulta
Con cierto conocimiento del idioma [de consulta,](advanced-hunting-query-language.md)puede ajustar la consulta a su preferencia. Por ejemplo, puede ajustar esta línea, que determina el tamaño de la ventana de tiempo:

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

Además de modificar la consulta para obtener resultados más relevantes, también puede:
- [Ver los resultados como gráficos](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [Crear una regla de detección personalizada](custom-detection-rules.md)

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Reglas de detección personalizada](custom-detection-rules.md)
