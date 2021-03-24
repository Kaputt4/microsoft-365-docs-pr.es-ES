---
title: API de Microsoft 365 Defender (versión preliminar) admitidas
description: API de Microsoft 365 Defender (versión preliminar) admitidas
keywords: MTP, API, api
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
ms.openlocfilehash: b2239b960106d756cbd29504af05af77a553067d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068975"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="bbd27-104">API de Microsoft 365 Defender (versión preliminar) admitidas</span><span class="sxs-lookup"><span data-stu-id="bbd27-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="bbd27-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="bbd27-105">**Applies to:**</span></span>
- <span data-ttu-id="bbd27-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bbd27-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbd27-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="bbd27-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="bbd27-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="bbd27-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="bbd27-109">Lista de API disponibles</span><span class="sxs-lookup"><span data-stu-id="bbd27-109">List of available APIs</span></span>

<span data-ttu-id="bbd27-110">Artículo</span><span class="sxs-lookup"><span data-stu-id="bbd27-110">Article</span></span> | <span data-ttu-id="bbd27-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="bbd27-111">Description</span></span>
-|-
[<span data-ttu-id="bbd27-112">API de Búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="bbd27-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="bbd27-113">Ejecute consultas de búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="bbd27-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="bbd27-114">API de incidentes</span><span class="sxs-lookup"><span data-stu-id="bbd27-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="bbd27-115">Enumerar y actualizar incidentes, junto con otras tareas prácticas.</span><span class="sxs-lookup"><span data-stu-id="bbd27-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="bbd27-116">URI de extremo</span><span class="sxs-lookup"><span data-stu-id="bbd27-116">Endpoint URIs</span></span>

<span data-ttu-id="bbd27-117">El URI base para ambas API principales es: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="bbd27-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="bbd27-118">Para obtener un mejor rendimiento, use un servidor más cercano a la geolocalización:</span><span class="sxs-lookup"><span data-stu-id="bbd27-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="bbd27-119">Estados Unidos: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="bbd27-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="bbd27-120">Europa: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="bbd27-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="bbd27-121">Reino Unido: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="bbd27-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="bbd27-122">Los tokens se pueden adquirir accediendo https://api.security.microsoft.com a .</span><span class="sxs-lookup"><span data-stu-id="bbd27-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="bbd27-123">Todas las API a lo `/api` largo de la ruta de acceso usan el protocolo [OData;](/odata/overview) por ejemplo, https://api.security.microsoft.com/api/incidents .</span><span class="sxs-lookup"><span data-stu-id="bbd27-123">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="bbd27-124">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="bbd27-124">Related articles</span></span>

- [<span data-ttu-id="bbd27-125">Introducción a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bbd27-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="bbd27-126">Obtener acceso a las API de Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bbd27-126">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="bbd27-127">Más información sobre los límites de api y las licencias</span><span class="sxs-lookup"><span data-stu-id="bbd27-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="bbd27-128">Comprender códigos de error</span><span class="sxs-lookup"><span data-stu-id="bbd27-128">Understand error codes</span></span>](api-error-codes.md)