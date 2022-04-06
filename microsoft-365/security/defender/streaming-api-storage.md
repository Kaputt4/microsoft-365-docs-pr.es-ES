---
title: Transmitir Microsoft 365 Defender eventos a su Storage cuenta
description: Obtenga información sobre cómo configurar Microsoft 365 Defender para transmitir eventos de búsqueda avanzada a su Storage cuenta.
keywords: Exportación de datos sin procesar, API de streaming, API, Centros de eventos, Almacenamiento de Azure, cuenta de almacenamiento, Búsqueda avanzada, uso compartido de datos sin procesar
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
ms.openlocfilehash: ed62807c0efc7003bab8fc725c2753c3d91ef1d6
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2022
ms.locfileid: "64501231"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a>Configurar Microsoft 365 Defender para transmitir eventos de búsqueda avanzada a tu cuenta Storage usuario

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a>Antes de empezar

1. Cree una [cuenta Storage en](/azure/storage/common/storage-account-overview) el espacio empresarial.

2. Inicie sesión en el inquilino [de Azure](https://ms.portal.azure.com/), vaya a Suscripciones > Su suscripción > proveedores de recursos > **Registrarse en Microsoft.Ideas**.

## <a name="enable-raw-data-streaming"></a>Habilitar la transmisión de datos sin procesar

1. Inicie sesión en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> como ***Administrador global** _ o _*_Administrador de seguridad_**.

2. Vaya a **Configuración** \> **Microsoft 365 Defender** \> **API de streaming**. Para ir directamente a la página **de la API de streaming** , use <https://security.microsoft.com/settings/mtp_settings/raw_data_export>.

3. Seleccione **Agregar**.

4. En el **menú desplegable Agregar nueva configuración de la API** de streaming que aparece, configure las siguientes opciones:
   1. **Nombre**: elija un nombre para la nueva configuración.
   2. Seleccione **Reenviar eventos para Azure Storage**.
   3. En el **Storage id.** de recurso de cuenta que aparece, escriba el **Storage de recurso de cuenta**. Para obtener el identificador **Storage recurso** de cuenta, abra Azure Portal <https://portal.azure.com>en , haga clic en Storage **cuentas** \> \> vaya a la pestaña propiedades copie el texto en Storage Id. de recurso de **cuenta**.

      :::image type="content" source="../defender-endpoint/images/storage-account-resource-id.png" alt-text="Un Storage de recurso de cuenta" lightbox="../defender-endpoint/images/storage-account-resource-id.png":::

   4. En el menú desplegable **Agregar nueva configuración de la API de streaming** , elija los **tipos de eventos** que desea transmitir.

   Cuando haya terminado, haga clic en **Enviar**.

## <a name="the-schema-of-the-events-in-the-storage-account"></a>El esquema de los eventos de la cuenta Storage cuenta

- Se creará un contenedor de blobs para cada tipo de evento:

  :::image type="content" source="../defender-endpoint/images/storage-account-event-schema.png" alt-text="Ejemplo de un contenedor de blobs" lightbox="../defender-endpoint/images/storage-account-event-schema.png":::

- El esquema de cada fila de un blob es el siguiente JSON:

  ```JSON
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }
  ```

- Cada blob contiene varias filas.

- Cada fila contiene el nombre del evento, la hora en que Defender para Endpoint recibió el evento, el inquilino al que pertenece (solo recibirá eventos de su inquilino) y el evento en formato JSON en una propiedad denominada "propiedades".

- Para obtener más información sobre el esquema de Microsoft 365 Defender eventos, vea [Advanced Hunting overview](../defender/advanced-hunting-overview.md).

## <a name="data-types-mapping"></a>Asignación de tipos de datos

Para obtener los tipos de datos de nuestras propiedades de eventos, haga lo siguiente:

1. Inicie sesión en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> y vaya a **Búsqueda** \> **avanzada de búsqueda**. Para ir directamente a la **página Búsqueda avanzada** , use <security.microsoft.com/advanced-hunting>.

2. En la **pestaña Consulta** , ejecute la siguiente consulta para obtener la asignación de tipos de datos para cada evento:

   ```text
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- Este es un ejemplo para el evento Device Info:

  :::image type="content" source="../defender-endpoint/images/machine-info-datatype-example.png" alt-text="Una consulta de información de dispositivo de ejemplo" lightbox="../defender-endpoint/images/machine-info-datatype-example.png":::

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre la búsqueda avanzada](../defender/advanced-hunting-overview.md)
- [Microsoft 365 Defender API de streaming](streaming-api.md)
- [Transmitir Microsoft 365 Defender eventos a su cuenta de Azure Storage](streaming-api-storage.md)
- [Azure Storage de cuenta](/azure/storage/common/storage-account-overview)
