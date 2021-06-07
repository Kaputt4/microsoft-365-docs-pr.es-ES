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
ms.openlocfilehash: fad3dd64c9acf079bd8da778d417240c44031569
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772535"
---
# <a name="streaming-api"></a><span data-ttu-id="bcc91-104">Streaming API</span><span class="sxs-lookup"><span data-stu-id="bcc91-104">Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bcc91-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="bcc91-105">**Applies to:**</span></span>
- [<span data-ttu-id="bcc91-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bcc91-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="bcc91-107">Transmite eventos de búsqueda avanzada a centros de eventos o cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="bcc91-107">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="bcc91-108">Microsoft 365 Defender admite la transmisión por streaming de todos los eventos disponibles a través [de la búsqueda avanzada](../defender/advanced-hunting-overview.md) a un centro de [eventos](/azure/event-hubs/) o una cuenta de [Azure Storage.](/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="bcc91-108">Microsoft 365 Defender supports streaming all the events available through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>



## <a name="in-this-section"></a><span data-ttu-id="bcc91-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bcc91-109">In this section</span></span>

<span data-ttu-id="bcc91-110">Tema</span><span class="sxs-lookup"><span data-stu-id="bcc91-110">Topic</span></span> | <span data-ttu-id="bcc91-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="bcc91-111">Description</span></span>
:---|:---
[<span data-ttu-id="bcc91-112">Transmitir eventos a Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="bcc91-112">Stream events to Azure Event Hubs</span></span>](streaming-api-event-hub.md)| <span data-ttu-id="bcc91-113">Obtenga información sobre cómo habilitar la API de streaming en el inquilino y configurar Microsoft 365 Defender para transmitir [la búsqueda avanzada](../defender/advanced-hunting-overview.md) a los centros de eventos.</span><span class="sxs-lookup"><span data-stu-id="bcc91-113">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="bcc91-114">Transmitir eventos a su cuenta de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="bcc91-114">Stream events to your Azure storage account</span></span>](streaming-api-storage.md)| <span data-ttu-id="bcc91-115">Obtenga información sobre cómo habilitar la API de streaming en el inquilino y configurar Microsoft 365 Defender para transmitir [la búsqueda avanzada](advanced-hunting-overview.md) a su cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="bcc91-115">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="bcc91-116">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bcc91-116">Related topics</span></span>
- [<span data-ttu-id="bcc91-117">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="bcc91-117">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="bcc91-118">Documentación de Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="bcc91-118">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="bcc91-119">Azure Storage Documentación de la cuenta</span><span class="sxs-lookup"><span data-stu-id="bcc91-119">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
