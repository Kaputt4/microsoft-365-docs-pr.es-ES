---
title: API de Microsoft 365 Defender (versión preliminar) admitidas
description: API de Microsoft 365 Defender (versión preliminar) admitidas
keywords: MTP, API, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: dbb7613dae3755b0fb794a3d68b5b424d765cc62
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719327"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="cae9d-104">API de Microsoft 365 Defender (versión preliminar) admitidas</span><span class="sxs-lookup"><span data-stu-id="cae9d-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="cae9d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="cae9d-105">**Applies to:**</span></span>
- <span data-ttu-id="cae9d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cae9d-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cae9d-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="cae9d-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="cae9d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="cae9d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="cae9d-109">Lista de API disponibles</span><span class="sxs-lookup"><span data-stu-id="cae9d-109">List of available APIs</span></span>

<span data-ttu-id="cae9d-110">Artículo</span><span class="sxs-lookup"><span data-stu-id="cae9d-110">Article</span></span> | <span data-ttu-id="cae9d-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="cae9d-111">Description</span></span>
-|-
[<span data-ttu-id="cae9d-112">API de Búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="cae9d-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="cae9d-113">Ejecutar consultas de búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="cae9d-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="cae9d-114">API de incidentes</span><span class="sxs-lookup"><span data-stu-id="cae9d-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="cae9d-115">Enumerar y actualizar incidentes, junto con otras tareas prácticas.</span><span class="sxs-lookup"><span data-stu-id="cae9d-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="cae9d-116">URI de extremo</span><span class="sxs-lookup"><span data-stu-id="cae9d-116">Endpoint URIs</span></span>

<span data-ttu-id="cae9d-117">El URI base para las dos API principales es: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="cae9d-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="cae9d-118">Para obtener un mejor rendimiento, use un servidor más cercano a su ubicación geográfica:</span><span class="sxs-lookup"><span data-stu-id="cae9d-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="cae9d-119">Estados Unidos: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cae9d-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="cae9d-120">Europa: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cae9d-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="cae9d-121">Reino Unido: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cae9d-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="cae9d-122">El acceso a los tokens puede adquirirse https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="cae9d-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="cae9d-123">Todas las API a lo largo de la `/api` ruta de acceso usan el protocolo [OData](https://docs.microsoft.com/odata/overview) ; por ejemplo, https://api.security.microsoft.com/api/incidents .</span><span class="sxs-lookup"><span data-stu-id="cae9d-123">All APIs along the `/api` path use the [OData](https://docs.microsoft.com/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cae9d-124">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="cae9d-124">Related articles</span></span>

- [<span data-ttu-id="cae9d-125">Información general sobre las API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="cae9d-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="cae9d-126">Acceso a las API de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="cae9d-126">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="cae9d-127">Obtenga información sobre los límites de API y las licencias</span><span class="sxs-lookup"><span data-stu-id="cae9d-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="cae9d-128">Descripción de los códigos de error</span><span class="sxs-lookup"><span data-stu-id="cae9d-128">Understand error codes</span></span>](api-error-codes.md)
