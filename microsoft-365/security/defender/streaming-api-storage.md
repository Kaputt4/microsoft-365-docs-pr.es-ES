---
title: Transmitir eventos de Microsoft 365 Defender a la cuenta de almacenamiento
description: Obtenga información sobre cómo configurar Microsoft 365 Defender para transmitir eventos de búsqueda avanzada a la cuenta de Storage.
keywords: exportación de datos sin procesar, API de streaming, API, Event Hubs, Almacenamiento de Azure, cuenta de almacenamiento, Búsqueda avanzada, uso compartido de datos sin procesar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.openlocfilehash: e1119fbb07f38d4cb9375af99ded96026102ef56
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68084603"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a>Configuración de Microsoft 365 Defender para transmitir eventos de búsqueda avanzada a la cuenta de almacenamiento

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a>Antes de empezar

1. Cree una [cuenta de almacenamiento](/azure/storage/common/storage-account-overview) en el inquilino.

2. Inicie sesión en el [inquilino de Azure](https://ms.portal.azure.com/) y vaya a **Suscripciones > Su suscripción > Proveedores de recursos > Registrarse en Microsoft.Insights**.

### <a name="add-contributor-permissions"></a>Agregar permisos de colaborador

Una vez creada la cuenta de almacenamiento, deberá hacer lo siguiente:

1. Defina el usuario que iniciará sesión en Microsoft 365 Defender como Colaborador.

    Vaya a **Cuenta de almacenamiento > Control de acceso (IAM) > Agregar** y comprobar en **Asignaciones de roles**.

## <a name="enable-raw-data-streaming"></a>Habilitación del streaming de datos sin procesar

1. Inicie sesión en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> como ***Administrador global** _ o _*_Administrador de seguridad_**.

2. Vaya a **Configuración** \> **Microsoft 365 Defender** \> **Streaming API**. Para ir directamente a la página **de Streaming API** , use <https://security.microsoft.com/settings/mtp_settings/raw_data_export>.

3. Haga clic en **Agregar**.

4. En el control flotante **Agregar nueva configuración de Streaming API** que aparece, configure las siguientes opciones:
   1. **Nombre**: elija un nombre para la nueva configuración.
   2. Seleccione **Reenviar eventos a Azure Storage**.
   3. En el cuadro **Id. de recurso de la cuenta de almacenamiento** que aparece, escriba el **identificador de recurso de la cuenta de almacenamiento**. Para obtener el **identificador de recurso de la cuenta de almacenamiento**, abra el Azure Portal en <https://portal.azure.com>, haga clic en **Cuentas** \> de almacenamiento vaya a la pestaña \> propiedades y copie el texto en **Id. de recurso de la cuenta de almacenamiento**.

      :::image type="content" source="../defender-endpoint/images/storage-account-resource-id.png" alt-text="Un identificador de recurso de cuenta de almacenamiento" lightbox="../defender-endpoint/images/storage-account-resource-id.png":::

   4. De nuevo en el control flotante **Agregar nueva configuración de Streaming API** , elija los **tipos de eventos** que desea transmitir.

   Cuando haya terminado, haga clic en **Enviar**.

## <a name="the-schema-of-the-events-in-the-storage-account"></a>Esquema de los eventos de la cuenta de almacenamiento

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

- Cada fila contiene el nombre del evento, la hora en que Defender para punto de conexión recibió el evento, el inquilino al que pertenece (solo obtendrá eventos del inquilino) y el evento en formato JSON en una propiedad denominada "properties".

- Para obtener más información sobre el esquema de eventos de Microsoft 365 Defender, vea [Información general sobre la búsqueda avanzada](../defender/advanced-hunting-overview.md).

## <a name="data-types-mapping"></a>Asignación de tipos de datos

Para obtener los tipos de datos de nuestras propiedades de eventos, haga lo siguiente:

1. Inicie sesión para <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> y vaya a Búsqueda **avanzada** de **caza**\>. Para ir directamente a la página **Búsqueda avanzada** , use <security.microsoft.com/advanced-hunting>.

2. En la pestaña **Consulta** , ejecute la consulta siguiente para obtener la asignación de tipos de datos para cada evento:

   ```text
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- Este es un ejemplo del evento Device Info:

  :::image type="content" source="../defender-endpoint/images/machine-info-datatype-example.png" alt-text="Consulta de información de dispositivo de ejemplo" lightbox="../defender-endpoint/images/machine-info-datatype-example.png":::

## <a name="monitoring-created-resources"></a>Supervisión de los recursos creados

Puede supervisar los recursos creados por la API de streaming mediante **Azure Monitor**. Para obtener más información, consulte [Supervisión de destinos: Azure Monitor | Microsoft Docs](/azure/azure-monitor/logs/logs-data-export?tabs=portal#monitor-destinations).

## <a name="related-topics"></a>Temas relacionados

- [Introducción a la búsqueda avanzada](../defender/advanced-hunting-overview.md)
- [API de streaming de Microsoft 365 Defender](streaming-api.md)
- [Transmitir eventos Microsoft 365 Defender a la cuenta de Azure Storage](streaming-api-storage.md)
- [Documentación de la cuenta de Azure Storage](/azure/storage/common/storage-account-overview)
