---
title: Obtener información relevante sobre una entidad con go hunt
description: Obtenga información sobre cómo usar la herramienta go hunt para consultar rápidamente información relevante sobre una entidad o evento mediante la búsqueda avanzada.
keywords: advanced hunting, incident, pivot, entity, go hunt, relevant events, threat hunting, cyber threat hunting, search, query, telemetry, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.topic: conceptual
ms.openlocfilehash: 4dfa6afcaeee3cadb8dd683ca973654e9398c1dd
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68622758"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>Búsqueda rápida de información de entidades o eventos con go hunt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

Con la acción *de búsqueda go* , puede investigar rápidamente eventos y varios tipos de entidad mediante eficaces funcionalidades de [búsqueda avanzada](advanced-hunting-overview.md) basadas en consultas. Esta acción ejecuta automáticamente una consulta de búsqueda avanzada para buscar información relevante sobre el evento o la entidad seleccionados.

La acción *go hunt* está disponible en varias secciones de Defender for Cloud. Esta acción está disponible para ver una vez que se muestran los detalles de eventos o entidades. Por ejemplo, puede usar la opción *go hunt* en las secciones siguientes:

- En la [página del incidente](investigate-incidents.md#summary), puede revisar los detalles sobre los usuarios, los dispositivos y muchas otras entidades asociadas a un incidente. Al seleccionar una entidad, obtendrá información adicional y las distintas acciones que podría realizar en esa entidad. En el ejemplo siguiente, se selecciona un buzón, que muestra detalles sobre el buzón y la opción para buscar más información sobre el buzón.

    :::image type="content" source="../../media/go-hunt-1-incident.png" alt-text="Página Buzones con la opción Búsqueda de Go en el portal de Microsoft 365 Defender" lightbox="../../media/go-hunt-1-incident.png":::

- En la página incidente, también puede acceder a una lista de entidades en la pestaña **Evidencia** . La selección de una de esas entidades proporciona una opción para buscar rápidamente información sobre esa entidad.

    :::image type="content" source="../../media/go-hunt-2-entity.png" alt-text="La opción Búsqueda de Go para un fragmento de evidencia en la página Incidente de Microsoft 365 Defender portal" lightbox="../../media/go-hunt-2-entity.png":::


- Al ver la escala de tiempo de un dispositivo, puede seleccionar un evento en la escala de tiempo para ver información adicional sobre ese evento. Una vez seleccionado un evento, obtendrá la opción de buscar otros eventos relevantes en la búsqueda avanzada.

    :::image type="content" source="../../media/go-hunt-3-event.png" alt-text="La opción Buscar eventos relacionados en la página de un evento en la pestaña Escalas de tiempo de Microsoft 365 Defender portal" lightbox="../../media/go-hunt-3-event.png":::

Al seleccionar **Buscar** o **Buscar eventos relacionados** , se pasan consultas diferentes, en función de si ha seleccionado una entidad o un evento.

## <a name="query-for-entity-information"></a>Consulta de información de entidad
Puede usar *go hunt* para consultar información sobre un usuario, dispositivo o cualquier otro tipo de entidad; la consulta comprueba todas las tablas de esquema pertinentes para ver si hay eventos que impliquen a esa entidad para devolver información. Para mantener los resultados administrables, la consulta es:
- en torno al mismo período de tiempo que la actividad más antigua de los últimos 30 días que implica la entidad
- asociado al incidente.

Este es un ejemplo de la consulta go hunt para un dispositivo:

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
### <a name="supported-entity-types"></a>Tipos de entidad admitidos
Puede usar la opción *go hunt* después de seleccionar cualquiera de estos tipos de entidad:

- Archivos
- Mensajes de correo electrónico
- clústeres de Email
- Buzones
- Usuarios
- Dispositivos
- Direcciones IP
- Direcciones URL

## <a name="query-for-event-information"></a>Consulta de información de eventos
Cuando se usa *go hunt* para consultar información sobre un evento de escala de tiempo, la consulta comprueba todas las tablas de esquema pertinentes para otros eventos alrededor del momento del evento seleccionado. Por ejemplo, en la consulta siguiente se enumeran los eventos de varias tablas de esquema que se produjeron alrededor del mismo período de tiempo en el mismo dispositivo:

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

## <a name="adjust-the-query"></a>Ajuste de la consulta
Con algunos conocimientos del [lenguaje de consulta](advanced-hunting-query-language.md), puede ajustar la consulta a sus preferencias. Por ejemplo, puede ajustar esta línea, que determina el tamaño del período de tiempo:

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

Además de modificar la consulta para obtener resultados más relevantes, también puede:
- [Visualización de los resultados como gráficos](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [Creación de una regla de detección personalizada](custom-detection-rules.md)

>[!NOTE]
>Es posible que algunas tablas de este artículo no estén disponibles en Microsoft Defender para punto de conexión. [Active Microsoft 365 Defender](m365d-enable.md) para buscar amenazas mediante más orígenes de datos. Para mover los flujos de trabajo de búsqueda avanzados de Microsoft Defender para punto de conexión a Microsoft 365 Defender, siga los pasos descritos en [Migración de consultas de búsqueda avanzadas desde Microsoft Defender para punto de conexión](advanced-hunting-migrate-from-mde.md) .

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Reglas de detección personalizada](custom-detection-rules.md)
