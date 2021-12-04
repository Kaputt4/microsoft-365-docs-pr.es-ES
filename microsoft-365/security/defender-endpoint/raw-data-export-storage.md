---
title: Transmitir eventos de Microsoft Defender para endpoint a Storage cuenta
description: Obtén información sobre cómo configurar Microsoft Defender para endpoint para transmitir eventos de búsqueda avanzada a tu Storage usuario.
keywords: Exportación de datos sin procesar, API de streaming, API, Centros de eventos, Almacenamiento de Azure, cuenta de almacenamiento, Búsqueda avanzada, uso compartido de datos sin procesar
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
ms.openlocfilehash: f853917497a34ff4cd82f10cc83d23f530572e45
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2021
ms.locfileid: "61301407"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a>Configurar Microsoft Defender para endpoint para transmitir eventos de búsqueda avanzada a su Storage cuenta

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configuresiem-abovefoldlink)

## <a name="before-you-begin"></a>Antes de empezar

1. Cree una [cuenta Storage en](/azure/storage/common/storage-account-overview) el espacio empresarial.

2. Inicie sesión en el inquilino [de Azure,](https://ms.portal.azure.com/)vaya a Suscripciones > Su suscripción > proveedores de recursos > **Registrarse en Microsoft.insights**.

## <a name="enable-raw-data-streaming"></a>Habilitar la transmisión de datos sin procesar

1. Inicie sesión en [el portal de Microsoft Defender para endpoint](https://securitycenter.windows.com) como * Administrador **global** _ o _* Administrador _de seguridad_**.

2. Vaya a [La página Configuración de exportación de](https://securitycenter.windows.com/interoperability/dataexport) datos en Centro de seguridad de Microsoft Defender.

3. Haga clic en **Agregar configuración de exportación de datos.**

4. Elija un nombre para la nueva configuración.

5. Elija **Reenviar eventos para Azure Storage**.

6. Escriba su **Storage de recurso de cuenta**. Para obtener el identificador de **recurso Storage** cuenta, vaya a la página de la cuenta de Storage en la pestaña propiedades de [Azure Portal](https://ms.portal.azure.com/) copie el texto en Storage id. de recurso \> de \> **cuenta:**

   :::image type="content" alt-text="Imagen del id. de recurso del centro de eventos1." source="images/storage-account-resource-id.png" lightbox="images/storage-account-resource-id.png":::

7. Elija los eventos que desea transmitir y haga clic en **Guardar**.

## <a name="the-schema-of-the-events-in-the-storage-account"></a>El esquema de los eventos de la cuenta Storage cuenta

- Se creará un contenedor de blobs para cada tipo de evento:

  :::image type="content" alt-text="Imagen del id. de recurso del centro de eventos2." source="images/storage-account-event-schema.png" lightbox="images/storage-account-event-schema.png":::

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

- Cada fila contiene el nombre del evento, la hora en que Defender para Endpoint recibió el evento, el inquilino al que pertenece (solo recibirá eventos de su inquilino) y el evento en formato JSON en una propiedad denominada "propiedades".

- Para obtener más información sobre el esquema de eventos de Microsoft Defender para endpoint, vea [Advanced Hunting overview](advanced-hunting-overview.md).

- En Búsqueda avanzada, la **tabla DeviceInfo** tiene una columna denominada **MachineGroup** que contiene el grupo del dispositivo. Aquí todos los eventos también se decorarán con esta columna. Consulta [Grupos de dispositivos](machine-groups.md) para obtener más información.

## <a name="data-types-mapping"></a>Asignación de tipos de datos

Para obtener los tipos de datos de nuestras propiedades de eventos, haga lo siguiente:

1. Inicie sesión en [Centro de seguridad de Microsoft Defender](https://securitycenter.windows.com) y vaya a [la página Búsqueda avanzada](https://securitycenter.windows.com/hunting-package).

2. Ejecute la siguiente consulta para obtener la asignación de tipos de datos para cada evento:

   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- Este es un ejemplo para el evento Device Info:

  ![Imagen del recurso del centro de eventos ID3.](images/data-types-mapping-query.png)

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [API de Streaming de Microsoft Defender para endpoints](raw-data-export.md)
- [Transmitir eventos de Microsoft Defender para endpoint a su cuenta de Azure Storage](raw-data-export-storage.md)
- [Azure Storage documentación de la cuenta](/azure/storage/common/storage-account-overview)