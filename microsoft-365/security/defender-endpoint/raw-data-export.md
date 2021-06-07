---
title: Evento Stream De Microsoft Defender para endpoint
description: Obtenga información sobre cómo configurar Microsoft Defender para endpoint para transmitir eventos de búsqueda avanzada a centros de eventos o cuenta de Azure Storage
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
ms.openlocfilehash: 27d1b36f3e49112a2da95f9268c0e05fcaa72c89
ms.sourcegitcommit: f0118e61e490496cb23189cc5c73b23e2ba939be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2021
ms.locfileid: "52780146"
---
# <a name="raw-data-streaming-api"></a><span data-ttu-id="ec0e4-104">API de streaming de datos sin procesar</span><span class="sxs-lookup"><span data-stu-id="ec0e4-104">Raw Data Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ec0e4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ec0e4-105">**Applies to:**</span></span>
- [<span data-ttu-id="ec0e4-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="ec0e4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="ec0e4-107">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="ec0e4-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ec0e4-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="ec0e4-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="ec0e4-109">Transmite eventos de búsqueda avanzada a centros de eventos o cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="ec0e4-109">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="ec0e4-110">Defender for Endpoint admite la transmisión por streaming de todos los eventos disponibles a través de [la](advanced-hunting-overview.md) búsqueda avanzada a una cuenta [de Centro](/azure/event-hubs/) de eventos o [azure storage](/azure/event-hubs/).</span><span class="sxs-lookup"><span data-stu-id="ec0e4-110">Defender for Endpoint supports streaming all the events available through [Advanced Hunting](advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a><span data-ttu-id="ec0e4-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ec0e4-111">In this section</span></span>

<span data-ttu-id="ec0e4-112">Tema</span><span class="sxs-lookup"><span data-stu-id="ec0e4-112">Topic</span></span> | <span data-ttu-id="ec0e4-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec0e4-113">Description</span></span>
:---|:---
[<span data-ttu-id="ec0e4-114">Transmitir eventos de Microsoft Defender para endpoint a Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="ec0e4-114">Stream Microsoft Defender for Endpoint events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="ec0e4-115">Obtenga información sobre cómo habilitar la API de streaming en el inquilino y configurar Defender for Endpoint para transmitir [la búsqueda avanzada](advanced-hunting-overview.md) a los centros de eventos.</span><span class="sxs-lookup"><span data-stu-id="ec0e4-115">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="ec0e4-116">Stream Defender para eventos de punto de conexión en su cuenta de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="ec0e4-116">Stream Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="ec0e4-117">Obtenga información sobre cómo habilitar la API de streaming en el inquilino y configurar Defender for Endpoint para transmitir [la búsqueda avanzada](advanced-hunting-overview.md) a su cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="ec0e4-117">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ec0e4-118">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ec0e4-118">Related topics</span></span>
- [<span data-ttu-id="ec0e4-119">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="ec0e4-119">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ec0e4-120">Documentación de Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="ec0e4-120">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="ec0e4-121">Azure Storage Documentación de la cuenta</span><span class="sxs-lookup"><span data-stu-id="ec0e4-121">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)