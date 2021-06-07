---
title: Transmitir eventos Microsoft 365 Defender
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
ms.openlocfilehash: 971cc757dcbd0a190917d2a5f11eb7f68b758008
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778202"
---
# <a name="streaming-api"></a><span data-ttu-id="2655a-104">Streaming API</span><span class="sxs-lookup"><span data-stu-id="2655a-104">Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2655a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2655a-105">**Applies to:**</span></span>
- [<span data-ttu-id="2655a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2655a-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="2655a-107">Transmite eventos de búsqueda avanzada a centros de eventos o cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="2655a-107">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="2655a-108">Microsoft 365 Defender admite la transmisión por streaming de todos los eventos disponibles a través [de la búsqueda avanzada](../defender/advanced-hunting-overview.md) a un centro de [eventos](/azure/event-hubs/) o una cuenta de [Azure Storage.](/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="2655a-108">Microsoft 365 Defender supports streaming all the events available through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>



## <a name="in-this-section"></a><span data-ttu-id="2655a-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2655a-109">In this section</span></span>

<span data-ttu-id="2655a-110">Tema</span><span class="sxs-lookup"><span data-stu-id="2655a-110">Topic</span></span> | <span data-ttu-id="2655a-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="2655a-111">Description</span></span>
:---|:---
[<span data-ttu-id="2655a-112">Transmitir eventos a Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="2655a-112">Stream events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="2655a-113">Obtenga información sobre cómo habilitar la API de streaming en el inquilino y configurar Microsoft 365 Defender para transmitir [la búsqueda avanzada](../defender/advanced-hunting-overview.md) a los centros de eventos.</span><span class="sxs-lookup"><span data-stu-id="2655a-113">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="2655a-114">Transmitir eventos a su cuenta de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="2655a-114">Stream events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="2655a-115">Obtenga información sobre cómo habilitar la API de streaming en el inquilino y configurar Microsoft 365 Defender para transmitir [la búsqueda avanzada](../defender/advanced-hunting-overview.md) a su cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="2655a-115">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="2655a-116">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2655a-116">Related topics</span></span>
- [<span data-ttu-id="2655a-117">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="2655a-117">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="2655a-118">Documentación de Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="2655a-118">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="2655a-119">Azure Storage Documentación de la cuenta</span><span class="sxs-lookup"><span data-stu-id="2655a-119">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
