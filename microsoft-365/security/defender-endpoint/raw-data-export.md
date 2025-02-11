---
title: Stream Microsoft Defender para punto de conexión evento
description: Aprenda a configurar Microsoft Defender para punto de conexión para transmitir eventos de búsqueda avanzada a Event Hubs o a una cuenta de Azure Storage
keywords: exportación de datos sin procesar, API de streaming, API, event hubs, almacenamiento de Azure, cuenta de almacenamiento, búsqueda avanzada, uso compartido de datos sin procesar
ms.service: microsoft-365-security
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
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 7b232e01894472b3a01c9f13c02f0b3447ae3c30
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68644535"
---
# <a name="raw-data-streaming-api"></a>API de streaming de datos sin procesar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configuresiem-abovefoldlink)

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Transmisión de eventos de búsqueda avanzada a Event Hubs o a una cuenta de Azure Storage

Microsoft Defender para punto de conexión admite eventos de streaming disponibles a través de [búsqueda avanzada](../defender/advanced-hunting-overview.md) en una [cuenta de Almacenamiento de Azure](/azure/storage/common/storage-account-overview) o [Event Hubs](/azure/event-hubs/).

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4r4ga]

## <a name="in-this-section"></a>En esta sección

Tema|Descripción
:---|:---
[Transmisión de eventos Microsoft Defender para punto de conexión a Azure Event Hubs](raw-data-export-event-hub.md)|Obtenga información sobre cómo habilitar la API de streaming en el inquilino y configurar Defender para punto de conexión para transmitir la [búsqueda avanzada](advanced-hunting-overview.md) a Event Hubs.
[Transmisión de eventos de Defender para punto de conexión a la cuenta de Azure Storage](raw-data-export-storage.md)|Obtenga información sobre cómo habilitar la API de streaming en el inquilino y configure Defender para punto de conexión para transmitir la [búsqueda avanzada](advanced-hunting-overview.md) a la cuenta de Almacenamiento de Azure.

## <a name="related-topics"></a>Temas relacionados

- [Introducción a la búsqueda avanzada](advanced-hunting-overview.md)
- [Documentación de Azure Event Hubs](/azure/event-hubs/)
- [Documentación de la cuenta de Azure Storage](/azure/storage/common/storage-account-overview)