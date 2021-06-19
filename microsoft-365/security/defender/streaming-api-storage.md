---
title: Transmitir Microsoft 365 Defender eventos a su Almacenamiento cuenta
description: Obtén información sobre cómo configurar Microsoft 365 Defender para transmitir eventos de búsqueda avanzada a tu Almacenamiento cuenta.
keywords: Exportación de datos sin procesar, API de streaming, API, Centros de eventos, Almacenamiento de Azure, cuenta de almacenamiento, Búsqueda avanzada, uso compartido de datos sin procesar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fa61e2fd0591d375a17bad6e166a76c1ca40862e
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028900"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a>Configurar Microsoft 365 Defender para transmitir eventos de búsqueda avanzada a su Almacenamiento cuenta

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a>Antes de empezar:

1. Cree una [Almacenamiento en](/azure/storage/common/storage-account-overview) el espacio empresarial.

2. Inicie sesión en el inquilino [de Azure,](https://ms.portal.azure.com/)vaya a Suscripciones > Su suscripción > proveedores de recursos > **Registrarse en Microsoft.Ideas**.

## <a name="enable-raw-data-streaming"></a>Habilitar la transmisión de datos sin procesar:

1. Inicie sesión en [Microsoft 365 Defender de seguridad](https://security.microsoft.com) como un * Administrador **global** _ o _* Administrador _de seguridad_**.

2. Vaya a [La página Configuración de exportación de](https://security.microsoft.com/settings/mtp_settings/raw_data_export) datos en Centro de seguridad de Microsoft Defender.

3. Haga clic en **Agregar configuración de exportación de datos.**

4. Elija un nombre para la nueva configuración.

5. Elija **Reenviar eventos para Almacenamiento de Azure**.

6. Escriba su **Almacenamiento de recurso de cuenta**. Para obtener el identificador de recurso de cuenta de **Almacenamiento,** vaya a la página de la cuenta de Almacenamiento en la pestaña propiedades de [Azure Portal](https://ms.portal.azure.com/) > para > copiar el texto en Almacenamiento **Id.** de recurso de cuenta:

   ![Imagen del id. de recurso del centro de eventos1](../defender-endpoint/images/storage-account-resource-id.png)

7. Elija los eventos que desea transmitir y haga clic en **Guardar**.

## <a name="the-schema-of-the-events-in-the-storage-account"></a>Esquema de los eventos de la cuenta Almacenamiento:

- Se creará un contenedor de blobs para cada tipo de evento: 

  ![Imagen del id. de recurso del centro de eventos2](../defender-endpoint/images/storage-account-event-schema.png)

- El esquema de cada fila de un blob es el siguiente JSON: 

  ```
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

1. Inicie sesión en [el Microsoft 365 seguridad y](https://security.microsoft.com) vaya a la página Búsqueda [avanzada](https://security.microsoft.com/hunting-package).

2. Ejecute la siguiente consulta para obtener la asignación de tipos de datos para cada evento: 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Este es un ejemplo para el evento Device Info: 

  ![Imagen del id. de recurso del centro de eventos3](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](../defender/advanced-hunting-overview.md)
- [Microsoft 365 Defender Streaming API](streaming-api.md)
- [Transmitir Microsoft 365 Defender eventos a su cuenta de Azure Storage](streaming-api-storage.md)
- [Almacenamiento de Azure Documentación de la cuenta](/azure/storage/common/storage-account-overview)
