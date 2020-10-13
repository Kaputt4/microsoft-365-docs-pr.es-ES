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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 4abbedc34b6d77e785c2096d9f334000f9ffb02f
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430472"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>Búsqueda rápida de información de entidad o eventos con Go Hunt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft

Con la acción de *búsqueda go* , puede investigar rápidamente eventos y varios tipos de entidades usando funciones eficaces de [búsqueda avanzada](advanced-hunting-overview.md) basadas en consultas. Esta acción ejecuta automáticamente una consulta de búsqueda avanzada para buscar información relevante sobre la entidad o el evento seleccionado.

La acción *ir a búsqueda* está disponible en varias secciones del centro de seguridad siempre que se muestran los detalles de la entidad o el evento. Por ejemplo, puede usar *Go Hunt* en las siguientes secciones:

- En la [Página incidente](investigate-incidents.md#incident-overview), puede revisar los detalles de los usuarios, los dispositivos y muchas otras entidades asociadas a un incidente. Al seleccionar una entidad, obtiene información adicional y varias acciones que puede llevar a cabo en ese entitity. En el ejemplo siguiente, se selecciona un buzón, que muestra los detalles sobre el buzón y la opción de búsqueda para obtener más información sobre el buzón.

    ![Imagen que muestra los detalles del buzón con la opción de búsqueda Go](../../media/mtp-ah/go-hunt-email.png)

- En la página incidente, también puede tener acceso a una lista de entidades en la pestaña evidencia. La selección de una de estas entidades proporciona una opción para buscar información sobre la entidad rápidamente.

    ![Imagen que muestra el archivo seleccionado con la opción go Hunt en la pestaña Evidence](../../media/mtp-ah/go-hunt-evidence-file.png)


- Al ver la escala de tiempo de un dispositivo, puede seleccionar un evento en la escala de tiempo para ver información adicional sobre el evento. Una vez que se selecciona un evento, se obtiene la opción de buscar otros eventos relevantes en la búsqueda avanzada.

    ![Imagen donde se muestran los detalles del evento con la opción de búsqueda Go](../../media/mtp-ah/go-hunt-event.png)

La selección de ir a la **búsqueda** o **búsqueda de eventos relacionados** pasa distintas consultas, en función de si ha seleccionado una entidad o un evento.

## <a name="query-for-entity-information"></a>Consultar la información de la entidad
Cuando se usa *Go* to Query para obtener información sobre un usuario, dispositivo o cualquier otro tipo de entidad, la consulta comprueba todas las tablas del esquema relevantes para los eventos que impliquen esa entidad. Para que los resultados sean manejables, la consulta se limita al mismo período de tiempo que la actividad más temprana en los últimos 30 días que implica a la entidad y está asociada con el incidente.

Este es un ejemplo de la consulta go Hunt para un dispositivo:

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
### <a name="supported-entity-types"></a>Tipos de entidades compatibles
Puede usar la *búsqueda go* después de seleccionar cualquiera de estos tipos de entidad:

- Archivos
- Mensajes de correo electrónico
- Clústeres de correo electrónico
- Buzones
- Usuarios
- Dispositivos
- Direcciones IP
- Direcciones URL

## <a name="query-for-event-information"></a>Consultar la información de eventos
Cuando se usa *Go* to Query para obtener información sobre un evento de escala de tiempo, la consulta comprueba todas las tablas de esquema relevantes en busca de otros eventos alrededor de la hora del evento seleccionado. Por ejemplo, la siguiente consulta enumera los eventos en varias tablas de esquema que se produjeron alrededor del mismo período de tiempo en el mismo dispositivo:

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
Con algún conocimiento del [lenguaje de consulta](advanced-hunting-query-language.md), puede ajustar la consulta a sus preferencias. Por ejemplo, puede ajustar esta línea, que determina el tamaño de la ventana de tiempo:

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

Además de modificar la consulta para obtener resultados más relevantes, también puede:
- [Ver los resultados como gráficos](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [Crear una regla de detección personalizada](custom-detection-rules.md)

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Reglas de detección personalizadas](custom-detection-rules.md)
