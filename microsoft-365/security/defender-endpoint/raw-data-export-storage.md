---
title: Transmisión de eventos de Microsoft Defender para punto de conexión a la cuenta de Storage
description: Obtenga información sobre cómo configurar Microsoft Defender para punto de conexión para transmitir eventos de búsqueda avanzada a su cuenta de Storage.
keywords: exportación de datos sin procesar, API de streaming, API, Event Hubs, Almacenamiento de Azure, cuenta de almacenamiento, Búsqueda avanzada, uso compartido de datos sin procesar
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
ms.openlocfilehash: d5d4917e2464964da819af0a06f0b8e4883dfea9
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783895"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a>Configuración de Microsoft Defender para punto de conexión para transmitir eventos de búsqueda avanzada a la cuenta de Storage

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> ¿Desea experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configuresiem-abovefoldlink)

## <a name="before-you-begin"></a>Antes de empezar

1. Cree una [cuenta de Storage](/azure/storage/common/storage-account-overview) en el inquilino.

2. Inicie sesión en el [inquilino de Azure](https://ms.portal.azure.com/) y vaya a **Suscripciones > Su suscripción > Proveedores de recursos > Registrarse en Microsoft.insights**.

## <a name="enable-raw-data-streaming"></a>Habilitación del streaming de datos sin procesar

1. Inicie sesión en [Microsoft 365 Defender](https://security.microsoft.com) como ***Administrador global** _ o _*_Administrador de seguridad_**.

2. Vaya a la [página Configuración de exportación de datos](https://security.microsoft.com/interoperability/dataexport) en Microsoft 365 Defender.

3. Haga clic en **Agregar configuración de exportación de datos**.

4. Elija un nombre para la nueva configuración.

5. Elija **Reenviar eventos para Azure Storage**.

6. Escriba el **identificador de recurso de la cuenta de Storage**. Para obtener el identificador de recurso de la **cuenta de Storage**, vaya a la página de Storage cuenta en [Azure Portal](https://ms.portal.azure.com/) \> pestaña \> propiedades copie el texto en **Storage id. de recurso de cuenta**:

   :::image type="content" source="images/storage-account-resource-id.png" alt-text="Event Hubs con id. de recurso1" lightbox="images/storage-account-resource-id.png":::

7. Elija los eventos que desea transmitir y haga clic en **Guardar**.

## <a name="the-schema-of-the-events-in-the-storage-account"></a>Esquema de los eventos de la cuenta de Storage

- Se creará un contenedor de blobs para cada tipo de evento:

  :::image type="content" source="images/storage-account-event-schema.png" alt-text="Event Hubs con id. de recurso2" lightbox="images/storage-account-event-schema.png":::

- El esquema de cada fila de un blob es el siguiente JSON:

  ```json
  {
    "time": "<The time WDATP received the event>"
    "tenantId": "<Your tenant ID>"
    "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
    "properties": { <WDATP Advanced Hunting event as Json> }
  }
  ```

- Cada blob contiene varias filas.

- Cada fila contiene el nombre del evento, la hora en que Defender para punto de conexión recibió el evento, el inquilino al que pertenece (solo obtendrá eventos del inquilino) y el evento en formato JSON en una propiedad denominada "properties".

- Para obtener más información sobre el esquema de eventos de Microsoft Defender para punto de conexión, vea [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md).

- En búsqueda avanzada, la tabla **DeviceInfo** tiene una columna denominada **MachineGroup** que contiene el grupo del dispositivo. Aquí todos los eventos también se decorarán con esta columna. Consulte [Grupos de dispositivos](machine-groups.md) para obtener más información.

## <a name="data-types-mapping"></a>Asignación de tipos de datos

Para obtener los tipos de datos de nuestras propiedades de eventos, haga lo siguiente:

1. Inicie sesión en [Microsoft 365 Defender](https://security.microsoft.com) y vaya a la [página Búsqueda avanzada](https://security.microsoft.com/hunting-package).

2. Ejecute la consulta siguiente para obtener la asignación de tipos de datos para cada evento:

   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- Este es un ejemplo del evento Device Info:

  :::image type="content" source="images/data-types-mapping-query.png" alt-text="Event Hubs con id. de recurso3" lightbox="images/data-types-mapping-query.png":::

## <a name="related-topics"></a>Temas relacionados

- [Introducción a la búsqueda avanzada](advanced-hunting-overview.md)
- [API de streaming de Microsoft Defender para punto de conexión](raw-data-export.md)
- [Transmisión de eventos Microsoft Defender para punto de conexión a la cuenta de Azure Storage](raw-data-export-storage.md)
- [Documentación de la cuenta de Azure Storage](/azure/storage/common/storage-account-overview)
