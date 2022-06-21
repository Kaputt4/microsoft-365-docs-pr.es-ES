---
title: Transmitir eventos de Microsoft 365 Defender a Azure Event Hubs
description: Obtenga información sobre cómo configurar Microsoft 365 Defender para transmitir eventos de búsqueda avanzada a Event Hubs.
keywords: exportación de datos sin procesar, API de streaming, API, Azure Event Hubs, almacenamiento de Azure, cuenta de almacenamiento, búsqueda avanzada, uso compartido de datos sin procesar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ec18c23df27329598b6e48446ccf43d062b163ad
ms.sourcegitcommit: af2b570e76e074bbef98b665b5f9a731350eda58
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2022
ms.locfileid: "66185377"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hub"></a>Configuración de Microsoft 365 Defender para transmitir eventos de búsqueda avanzada al centro de eventos de Azure

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="prerequisites"></a>Requisitos previos

Antes de configurar Microsoft 365 Defender para transmitir datos a Event Hubs, asegúrese de que se cumplen los siguientes requisitos previos:

1. Crear una instancia de Event Hubs (para obtener información, consulte [Configuración de Event Hubs](configure-event-hub.md#set-up-event-hubs)).

2. Creación de un espacio de nombres de Event Hubs (para obtener información, consulte [Configuración del espacio de nombres de Event Hubs](configure-event-hub.md#set-up-event-hubs-namespace)).

3. Agregue permisos a la entidad que tiene los privilegios de un **colaborador** para que esta entidad pueda exportar datos a Event Hubs. Para obtener más información sobre cómo agregar permisos, vea [Agregar permisos](configure-event-hub.md#add-permissions).

> [!NOTE]
> La API de streaming se puede integrar a través de Event Hubs o Azure Storage Account.

## <a name="enable-raw-data-streaming"></a>Habilitación del streaming de datos sin procesar

1. Inicie sesión en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a> como ***Administrador global** _ o _*_Administrador de seguridad_**.

2. Vaya a la [página Configuración de Streaming API](https://security.microsoft.com/settings/mtp_settings/raw_data_export).

3. Haga clic en **Agregar**.

4. Elija un nombre para la nueva configuración.

5. Elija **Reenviar eventos a Azure Event Hub**.

6. Puede seleccionar si desea exportar los datos de eventos a un único centro de eventos o exportar cada tabla de eventos a un centro de eventos diferente en el espacio de nombres de Event Hubs.

7. Para exportar los datos de eventos a un único centro de eventos, escriba el **nombre del centro de eventos** y el **identificador de recurso del centro de eventos**.

   Para obtener el **identificador de recurso de Event Hub**, vaya a la página del espacio de nombres Azure Event Hubs de la pestaña **Propiedades** de [Azure](https://ms.portal.azure.com/) >  > copie el texto en **Id. de recurso**:

   :::image type="content" source="../defender-endpoint/images/event-hub-resource-id.png" alt-text="Un identificador de recurso del centro de eventos" lightbox="../defender-endpoint/images/event-hub-resource-id.png":::

8. Vaya a [los tipos de eventos Microsoft 365 Defender admitidos en la API de streaming](supported-event-types.md) de eventos para revisar el estado de soporte técnico de los tipos de eventos en Microsoft 365 Streaming API.

9. Elija los eventos que desea transmitir y haga clic en **Guardar**.

## <a name="the-schema-of-the-events-in-azure-event-hub"></a>Esquema de los eventos en Azure Event Hub

```JSON
{
   "records": [
               {
                  "time": "<The time Microsoft 365 Defender received the event>"
                  "tenantId": "<The Id of the tenant that the event belongs to>"
                  "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                  "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
               }
               ...
            ]
}
```

- Cada mensaje de Event Hubs de Azure Event Hubs contiene una lista de registros.

- Cada registro contiene el nombre del evento, la hora Microsoft 365 Defender recibió el evento, el inquilino al que pertenece (solo obtendrá eventos del inquilino) y el evento en formato JSON en una propiedad denominada "**properties**".

- Para obtener más información sobre el esquema de eventos de Microsoft 365 Defender, vea [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md).

- En búsqueda avanzada, la tabla **DeviceInfo** tiene una columna denominada **MachineGroup** que contiene el grupo del dispositivo. Aquí todos los eventos también se decorarán con esta columna.

## <a name="data-types-mapping"></a>Asignación de tipos de datos

Para obtener los tipos de datos de las propiedades de evento, siga estos pasos:

1. Inicie sesión en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> y vaya a la [página Búsqueda avanzada](https://security.microsoft.com/hunting-package).

2. Ejecute la consulta siguiente para obtener la asignación de tipos de datos para cada evento:

   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- Este es un ejemplo del evento Device Info:

  :::image type="content" source="../defender-endpoint/images/machine-info-datatype-example.png" alt-text="Consulta de ejemplo para la información del dispositivo" lightbox="../defender-endpoint/images/machine-info-datatype-example.png":::

## <a name="estimating-initial-event-hub-capacity"></a>Estimación de la capacidad inicial del centro de eventos
La siguiente consulta de búsqueda avanzada puede ayudar a proporcionar una estimación aproximada del rendimiento del volumen de datos y la capacidad inicial del centro de eventos en función de los eventos por segundo y los MB/s estimados. Se recomienda ejecutar la consulta durante el horario comercial normal para capturar el rendimiento "real".
 
```kusto 
let bytes_ = 500;
union withsource=MDTables*
| where Timestamp > startofday(ago(6h))
| summarize count() by bin(Timestamp, 1m), MDTables
| extend EPS = count_ /60
| summarize avg(EPS), estimatedMBPerSec = (avg(EPS) * bytes_ ) / (1024*1024) by MDTables
| sort by toint(estimatedMBPerSec) desc
```

## <a name="monitoring-created-resources"></a>Supervisión de los recursos creados

Puede supervisar los recursos creados por la API de streaming mediante **Azure Monitor**. Para más información, consulte [Exportación de datos del área de trabajo de Log Analytics en Azure Monitor](/azure/azure-monitor/logs/logs-data-export). 

## <a name="related-topics"></a>Temas relacionados

- [Introducción a la búsqueda avanzada](advanced-hunting-overview.md)
- [API de streaming de Microsoft 365 Defender](streaming-api.md)
- [Tipos de eventos de Microsoft 365 Defender admitidos en la API de streaming de eventos](supported-event-types.md)
- [Transmitir eventos Microsoft 365 Defender a la cuenta de Azure Storage](streaming-api-storage.md)
- [documentación de Azure Event Hubs](/azure/event-hubs/)
- [Solución de problemas de conectividad: Azure Event Hubs](/azure/event-hubs/troubleshooting-guide)
