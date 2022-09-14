---
title: Transmitir eventos de Microsoft Defender para punto de conexión a Azure Event Hubs
description: Obtenga información sobre cómo configurar Microsoft Defender para punto de conexión para transmitir eventos de búsqueda avanzada al centro de eventos.
keywords: exportación de datos sin procesar, API de streaming, API, Azure Event Hubs, almacenamiento de Azure, cuenta de almacenamiento, búsqueda avanzada, uso compartido de datos sin procesar
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 7e3466e5a7ba8a5a8c0a5e2041d2022ffd9ce3ce
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67686799"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a>Configurar Microsoft Defender para punto de conexión para transmitir eventos de búsqueda avanzada a la Azure Event Hubs

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configuresiem-abovefoldlink)

## <a name="before-you-begin"></a>Antes de empezar

1. Cree un [centro de eventos](/azure/event-hubs/) en el inquilino.

2. Inicie sesión en el [inquilino de Azure](https://ms.portal.azure.com/) y vaya a **Suscripciones > Su suscripción > Proveedores de recursos > Registrarse en Microsoft.insights**.

## <a name="enable-raw-data-streaming"></a>Habilitación del streaming de datos sin procesar

1. Inicie sesión en el [Microsoft 365 Defender](https://security.microsoft.com) como ***Administrador global** _ o _*_Administrador de seguridad_**.

2. Vaya a la [página Configuración de exportación de datos](https://security.microsoft.com/interoperability/dataexport) en el portal de Microsoft Defender.

3. Haga clic en **Agregar configuración de exportación de datos**.

4. Elija un nombre para la nueva configuración.

5. Elija **Reenviar eventos para Azure Event Hubs**.

6. Escriba el **nombre de Event Hubs** y el **identificador de recurso de Event Hubs**.

   Para obtener el identificador de **recurso de Event Hubs**, vaya a la página del espacio de nombres de Azure Event Hubs en [la](https://ms.portal.azure.com/) pestaña \> de propiedades de Azure > copie el texto en **Id. de recurso**:

   :::image type="content" source="images/event-hub-resource-id.png" alt-text="Id.1 del recurso de Event Hubs" lightbox="images/event-hub-resource-id.png":::

7. Elija los eventos que desea transmitir y haga clic en **Guardar**.

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a>Esquema de los eventos de Azure Event Hubs

```json
{
    "records": [
                    {
                        "time": "<The time WDATP received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <WDATP Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- Cada mensaje del centro de eventos de Azure Event Hubs contiene una lista de registros.

- Cada registro contiene el nombre del evento, la hora Microsoft Defender para punto de conexión recibió el evento, el inquilino al que pertenece (solo obtendrá eventos del inquilino) y el evento en formato JSON en una propiedad denominada "**properties**".

- Para obtener más información sobre el esquema de eventos de Microsoft Defender para punto de conexión, vea [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md).

- En búsqueda avanzada, la tabla **DeviceInfo** tiene una columna denominada **MachineGroup** que contiene el grupo del dispositivo. Aquí todos los eventos también se decorarán con esta columna. Consulte [Grupos de dispositivos](machine-groups.md) para obtener más información.

## <a name="data-types-mapping"></a>Asignación de tipos de datos

Para obtener los tipos de datos de las propiedades de evento, haga lo siguiente:

1. Inicie sesión en [Microsoft 365 Defender](https://security.microsoft.com) y vaya a la [página Búsqueda avanzada](https://security.microsoft.com/hunting-package).

2. Ejecute la consulta siguiente para obtener la asignación de tipos de datos para cada evento:

   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Este es un ejemplo del evento Device Info:

  :::image type="content" source="images/machine-info-datatype-example.png" alt-text="Id.2 del recurso de Event Hubs" lightbox="images/machine-info-datatype-example.png":::

## <a name="related-topics"></a>Temas relacionados

- [Introducción a la búsqueda avanzada](advanced-hunting-overview.md)
- [MICROSOFT DEFENDER PARA PUNTO DE CONEXIÓN API de streaming](raw-data-export.md)
- [Transmisión de eventos Microsoft Defender para punto de conexión a la cuenta de Azure Storage](raw-data-export-storage.md)
- [documentación de Azure Event Hubs](/azure/event-hubs/)
- [Solución de problemas de conectividad: Azure Event Hubs](/azure/event-hubs/troubleshooting-guide)
