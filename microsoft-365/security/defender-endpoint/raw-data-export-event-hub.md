---
title: Transmitir eventos de Microsoft Defender para endpoint a Azure Event Hubs
description: Obtén información sobre cómo configurar Microsoft Defender para endpoint para transmitir eventos de búsqueda avanzada a tu centro de eventos.
keywords: Exportación de datos sin procesar, API de streaming, API, Azure Event Hubs, Almacenamiento de Azure, cuenta de almacenamiento, Búsqueda avanzada, uso compartido de datos sin procesar
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
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 0dddebc27f776e317090ac3424c27f01f26126ed
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2021
ms.locfileid: "61300194"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a>Configurar Microsoft Defender para endpoint para transmitir eventos de búsqueda avanzada a los centros de eventos de Azure

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configuresiem-abovefoldlink)

## <a name="before-you-begin"></a>Antes de empezar

1. Cree un [centro de eventos](/azure/event-hubs/) en el espacio empresarial.

2. Inicie sesión en el inquilino de [Azure,](https://ms.portal.azure.com/)vaya a **Suscripciones > Su suscripción > proveedores de recursos > Registrarse en **Microsoft.insights****.

## <a name="enable-raw-data-streaming"></a>Habilitar la transmisión de datos sin procesar

1. Inicie sesión en el [Centro de seguridad de Microsoft Defender](https://securitycenter.windows.com) como administrador **global** _ o _*_Administrador de seguridad_**.

2. Vaya a la [página Configuración de exportación de](https://securitycenter.windows.com/interoperability/dataexport) datos en Centro de seguridad de Microsoft Defender.

3. Haga clic en **Agregar configuración de exportación de datos.**

4. Elija un nombre para la nueva configuración.

5. Elija **Reenviar eventos a Azure Event Hubs**.

6. Escriba el **nombre de event hubs** y el **identificador de recurso de Event Hubs**.

   Para obtener el identificador de recurso **de Event Hubs,** vaya a la página de espacio de nombres de Azure Event Hubs en la pestaña propiedades de [Azure](https://ms.portal.azure.com/) > copie el texto en \> **Id. de recurso:**

   :::image type="content" alt-text="Imagen del recurso del centro de eventos Id1." source="images/event-hub-resource-id.png" lightbox="images/event-hub-resource-id.png":::

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

- Cada registro contiene el nombre del evento, la hora en que Microsoft Defender para Endpoint recibió el evento, el inquilino al que pertenece (solo recibirá eventos del inquilino) y el evento en formato JSON en una propiedad denominada "**properties**".

- Para obtener más información sobre el esquema de eventos de Microsoft Defender para endpoint, vea [Advanced Hunting overview](advanced-hunting-overview.md).

- En Búsqueda avanzada, la **tabla DeviceInfo** tiene una columna denominada **MachineGroup** que contiene el grupo del dispositivo. Aquí todos los eventos también se decorarán con esta columna. Consulta [Grupos de dispositivos](machine-groups.md) para obtener más información.

## <a name="data-types-mapping"></a>Asignación de tipos de datos

Para obtener los tipos de datos de las propiedades de evento, haga lo siguiente:

1. Inicie sesión en [Centro de seguridad de Microsoft Defender](https://securitycenter.windows.com) y vaya a [la página Búsqueda avanzada](https://securitycenter.windows.com/hunting-package).

2. Ejecute la siguiente consulta para obtener la asignación de tipos de datos para cada evento:

   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Este es un ejemplo para el evento Device Info:

  ![Imagen del recurso del centro de eventos Id2.](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [API de streaming de Microsoft Defender para endpoints](raw-data-export.md)
- [Transmitir eventos de Microsoft Defender para endpoint a su cuenta de Azure Storage](raw-data-export-storage.md)
- [Documentación de Azure Event Hubs](/azure/event-hubs/)
- [Solucionar problemas de conectividad: Azure Event Hubs](/azure/event-hubs/troubleshooting-guide)
