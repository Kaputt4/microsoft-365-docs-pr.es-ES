---
title: Evento Stream De Microsoft Defender para endpoint
description: Obtenga información sobre cómo configurar ATP de Microsoft Defender para transmitir eventos de búsqueda avanzada a centros de eventos o cuenta de Azure Storage
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
ms.openlocfilehash: 22f4e4c974b60e291273eb9bebfa34583f4e2fb7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071883"
---
# <a name="raw-data-streaming-api"></a>API de streaming de datos sin procesar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Transmite eventos de búsqueda avanzada a centros de eventos o cuenta de Azure Storage.

Defender for Endpoint admite la transmisión por streaming de todos los eventos disponibles a través de [la](advanced-hunting-overview.md) búsqueda avanzada a una cuenta [de Centro](https://docs.microsoft.com/azure/event-hubs/) de eventos o [azure storage](https://docs.microsoft.com/azure/event-hubs/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a>En esta sección

Tema | Descripción
:---|:---
[Transmitir eventos de Microsoft Defender para endpoint a Azure Event Hubs](raw-data-export-event-hub.md)| Obtenga información sobre cómo habilitar la API de streaming en el inquilino y configurar Defender for Endpoint para transmitir [la búsqueda avanzada](advanced-hunting-overview.md) a los centros de eventos.
[Stream Defender para eventos de punto de conexión en su cuenta de Azure Storage](raw-data-export-storage.md)| Obtenga información sobre cómo habilitar la API de streaming en el inquilino y configurar Defender for Endpoint para transmitir [la búsqueda avanzada](advanced-hunting-overview.md) a su cuenta de Azure Storage.


## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Documentación de Azure Event Hubs](https://docs.microsoft.com/azure/event-hubs/)
- [Documentación de la cuenta de Azure Storage](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
