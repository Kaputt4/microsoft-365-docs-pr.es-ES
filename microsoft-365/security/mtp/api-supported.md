---
title: API de Protección contra amenazas de Microsoft compatibles
description: API de Protección contra amenazas de Microsoft compatibles
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
ms.openlocfilehash: fda90945f09abfadfe56ea11469687130d88b2a7
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203700"
---
# <a name="supported-microsoft-threat-protection-apis"></a><span data-ttu-id="1361f-104">API de Protección contra amenazas de Microsoft compatibles</span><span class="sxs-lookup"><span data-stu-id="1361f-104">Supported Microsoft Threat Protection APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1361f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="1361f-105">**Applies to:**</span></span>
- <span data-ttu-id="1361f-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="1361f-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="1361f-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="1361f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1361f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="1361f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


### <a name="end-point-uris"></a><span data-ttu-id="1361f-109">URI de punto final:</span><span class="sxs-lookup"><span data-stu-id="1361f-109">End Point URIs:</span></span>

- <span data-ttu-id="1361f-110">El URI de la base del servicio es: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1361f-110">The service base URI is: https://api.security.microsoft.com</span></span> <br>

>[!NOTE]
><span data-ttu-id="1361f-111">Para obtener un mejor rendimiento, puede usar el servidor más cerca de la ubicación geográfica:</span><span class="sxs-lookup"><span data-stu-id="1361f-111">For better performance, you can use server closer to your Geo location:</span></span>
> - <span data-ttu-id="1361f-112">api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1361f-112">api-us.security.microsoft.com</span></span>
> - <span data-ttu-id="1361f-113">api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1361f-113">api-eu.security.microsoft.com</span></span>
> - <span data-ttu-id="1361f-114">api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1361f-114">api-uk.security.microsoft.com</span></span>

 - <span data-ttu-id="1361f-115">El recurso para la adquisición de token debe ser: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1361f-115">The resource for token acquisition should be: https://api.security.microsoft.com</span></span>

 - <span data-ttu-id="1361f-116">Todas las API de ```/api``` ruta de acceso son API de oData.</span><span class="sxs-lookup"><span data-stu-id="1361f-116">All the APIs under ```/api``` path are OData APIs.</span></span> <span data-ttu-id="1361f-117">p.ej. ```https://api.security.microsoft.com/api/incidents```</span><span class="sxs-lookup"><span data-stu-id="1361f-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="1361f-118">Lista de API disponibles:</span><span class="sxs-lookup"><span data-stu-id="1361f-118">List of available APIs:</span></span>

<span data-ttu-id="1361f-119">Tema</span><span class="sxs-lookup"><span data-stu-id="1361f-119">Topic</span></span> | <span data-ttu-id="1361f-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="1361f-120">Description</span></span>
:---|:---
[<span data-ttu-id="1361f-121">API de Búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="1361f-121">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="1361f-122">Ejecutar consultas de búsqueda avanzada desde la API.</span><span class="sxs-lookup"><span data-stu-id="1361f-122">Run Advanced Hunting queries from API.</span></span>
[<span data-ttu-id="1361f-123">API de incidentes</span><span class="sxs-lookup"><span data-stu-id="1361f-123">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="1361f-124">Ejecutar llamadas API relacionadas con incidentes como: enumerar incidentes, actualizar incidente y más.</span><span class="sxs-lookup"><span data-stu-id="1361f-124">Run incident related API calls such as: list incidents, update incident and more.</span></span>
