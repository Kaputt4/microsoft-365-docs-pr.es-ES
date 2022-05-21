---
title: Stream Microsoft 365 Defender eventos
description: Aprenda a configurar Microsoft 365 Defender para transmitir eventos de búsqueda avanzada a Event Hubs o a una cuenta de Almacenamiento de Azure
keywords: exportación de datos sin procesar, API de streaming, API, event hubs, almacenamiento de Azure, cuenta de almacenamiento, búsqueda avanzada, uso compartido de datos sin procesar
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d9f980656df636632c5903853c2784de81131d81
ms.sourcegitcommit: 349f0f54b0397cdd7d8fbb9ef07f1b6654a32d6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2022
ms.locfileid: "65621418"
---
# <a name="streaming-api"></a>API de streaming

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Transmita eventos de búsqueda avanzada a Event Hubs o a una cuenta de Almacenamiento de Azure.

Microsoft 365 Defender admite eventos de streaming a través de [búsqueda avanzada](../defender/advanced-hunting-overview.md) a una [cuenta de Almacenamiento de Azure](/azure/event-hubs/) o [Event Hubs](/azure/event-hubs/).

Para obtener más información sobre Microsoft 365 Defender API de streaming, consulte el [vídeo](https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga).

## <a name="in-this-section"></a>En esta sección

Tema | Descripción
:---|:---
[Transmisión de eventos a Azure Event Hubs](streaming-api-event-hub.md)| Obtenga información sobre cómo habilitar la API de streaming en el inquilino y configure Microsoft 365 Defender para transmitir la [búsqueda avanzada](../defender/advanced-hunting-overview.md) a Event Hubs.
[Transmisión de eventos a la cuenta de Azure Storage](streaming-api-storage.md)| Obtenga información sobre cómo habilitar la API de streaming en el inquilino y configure Microsoft 365 Defender para transmitir búsqueda [avanzada](advanced-hunting-overview.md) a la cuenta de Almacenamiento de Azure.
[Tipos de eventos admitidos](supported-event-types.md) | Obtenga información sobre qué tipos de eventos de búsqueda avanzada admite la API de streaming.

Vea este breve vídeo para aprender a configurar la API de streaming para enviar información de eventos directamente a Azure Event Hubs para su consumo por parte de los servicios de visualización, los motores de procesamiento de datos o el almacenamiento de Azure para la retención de datos a largo plazo.  
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]

## <a name="related-topics"></a>Temas relacionados
- [Introducción a la búsqueda avanzada](../defender/advanced-hunting-overview.md)
- [documentación de Azure Event Hubs](/azure/event-hubs/)
- [Documentación de la cuenta de Azure Storage](/azure/storage/common/storage-account-overview)
