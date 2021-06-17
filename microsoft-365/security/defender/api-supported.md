---
title: API de Microsoft 365 Defender (versión preliminar) admitidas
description: API de Microsoft 365 Defender (versión preliminar) admitidas
keywords: Microsoft 365 Defender, API, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: acd8ec28fb1d78e3724cb0ca0ebee48133e7310f
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985089"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="f0432-104">API de Microsoft 365 Defender (versión preliminar) admitidas</span><span class="sxs-lookup"><span data-stu-id="f0432-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f0432-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f0432-105">**Applies to:**</span></span>
- <span data-ttu-id="f0432-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f0432-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0432-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="f0432-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f0432-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="f0432-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="f0432-109">Lista de API disponibles</span><span class="sxs-lookup"><span data-stu-id="f0432-109">List of available APIs</span></span>

<span data-ttu-id="f0432-110">Artículo</span><span class="sxs-lookup"><span data-stu-id="f0432-110">Article</span></span> | <span data-ttu-id="f0432-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0432-111">Description</span></span>
-|-
[<span data-ttu-id="f0432-112">API de Búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="f0432-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="f0432-113">Ejecute consultas de búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="f0432-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="f0432-114">API de incidentes</span><span class="sxs-lookup"><span data-stu-id="f0432-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="f0432-115">Enumerar y actualizar incidentes, junto con otras tareas prácticas.</span><span class="sxs-lookup"><span data-stu-id="f0432-115">List and update incidents, along with other practical tasks.</span></span>
<span data-ttu-id="f0432-116">[API de streaming](streaming-api.md) (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="f0432-116">[Streaming API](streaming-api.md) (Preview)</span></span> | <span data-ttu-id="f0432-117">Envíe alertas y eventos en tiempo real a medida que se produzcan en un único flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="f0432-117">Ship real-time events and alerts as they occur in a single data stream.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="f0432-118">URI de extremo</span><span class="sxs-lookup"><span data-stu-id="f0432-118">Endpoint URIs</span></span>

<span data-ttu-id="f0432-119">El URI base para ambas API principales es: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="f0432-119">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="f0432-120">Para obtener un mejor rendimiento, use un servidor más cercano a la geolocalización:</span><span class="sxs-lookup"><span data-stu-id="f0432-120">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="f0432-121">Estados Unidos: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f0432-121">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="f0432-122">Europa: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f0432-122">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="f0432-123">Reino Unido: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f0432-123">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="f0432-124">Los tokens se pueden adquirir accediendo https://api.security.microsoft.com a .</span><span class="sxs-lookup"><span data-stu-id="f0432-124">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="f0432-125">Todas las API a lo `/api` largo de la ruta de acceso usan el protocolo [OData;](/odata/overview) por ejemplo, https://api.security.microsoft.com/api/incidents .</span><span class="sxs-lookup"><span data-stu-id="f0432-125">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f0432-126">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="f0432-126">Related articles</span></span>

- [<span data-ttu-id="f0432-127">Microsoft 365 Defender Introducción a las API</span><span class="sxs-lookup"><span data-stu-id="f0432-127">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="f0432-128">Obtener acceso a Microsoft 365 Defender API de acceso</span><span class="sxs-lookup"><span data-stu-id="f0432-128">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="f0432-129">API de streaming</span><span class="sxs-lookup"><span data-stu-id="f0432-129">Streaming API</span></span>](../defender-endpoint/raw-data-export.md)
- [<span data-ttu-id="f0432-130">Más información sobre los límites de api y las licencias</span><span class="sxs-lookup"><span data-stu-id="f0432-130">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="f0432-131">Comprender códigos de error</span><span class="sxs-lookup"><span data-stu-id="f0432-131">Understand error codes</span></span>](api-error-codes.md)
