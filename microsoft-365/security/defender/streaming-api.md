---
title: Transmitir Microsoft 365 Defender eventos
description: Obtenga información sobre cómo configurar Microsoft 365 Defender para transmitir eventos de búsqueda avanzada a centros de eventos o cuenta de Azure Storage
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
ms.openlocfilehash: d350dc66306bd46b37723743043e03ba0e7e3f53e7651b9c6def265b6d374ce5
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53838600"
---
# <a name="streaming-api"></a>API de streaming

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Transmite eventos de búsqueda avanzada a centros de eventos o cuenta de Azure Storage.

Microsoft 365 Defender permite transmitir eventos a través [de búsqueda avanzada](../defender/advanced-hunting-overview.md) a un centro de [eventos](/azure/event-hubs/) o una cuenta de [Azure Storage](/azure/event-hubs/).

Para obtener más información Microsoft 365 Defender la API de streaming, vea el [vídeo](https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga).

## <a name="in-this-section"></a>En esta sección

Tema | Descripción
:---|:---
[Transmitir eventos a Azure Event Hubs](streaming-api-event-hub.md)| Obtenga información sobre cómo habilitar la API de streaming en el espacio empresarial y configurar Microsoft 365 Defender para transmitir [la búsqueda avanzada](../defender/advanced-hunting-overview.md) a los centros de eventos.
[Transmitir eventos a su cuenta de Azure Storage](streaming-api-storage.md)| Obtenga información sobre cómo habilitar la API de streaming en el inquilino y configurar Microsoft 365 Defender para transmitir [la búsqueda avanzada](advanced-hunting-overview.md) a su cuenta de Azure Storage.


## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](../defender/advanced-hunting-overview.md)
- [Documentación de Azure Event Hubs](/azure/event-hubs/)
- [Azure Storage Documentación de la cuenta](/azure/storage/common/storage-account-overview)
