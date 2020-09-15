---
title: API de protección contra amenazas de Microsoft admitidas
description: API de protección contra amenazas de Microsoft admitidas
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
ms.openlocfilehash: 49fa182a6142748ca7769411fe74389f365ba75f
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650522"
---
# <a name="supported-microsoft-threat-protection-apis"></a><span data-ttu-id="9d400-104">API de protección contra amenazas de Microsoft admitidas</span><span class="sxs-lookup"><span data-stu-id="9d400-104">Supported Microsoft Threat Protection APIs</span></span> 
<span data-ttu-id="9d400-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9d400-105">**Applies to:**</span></span>
- <span data-ttu-id="9d400-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="9d400-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="9d400-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="9d400-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="9d400-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="9d400-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


### <a name="end-point-uris"></a><span data-ttu-id="9d400-109">URI de punto final:</span><span class="sxs-lookup"><span data-stu-id="9d400-109">End Point URIs:</span></span>

- <span data-ttu-id="9d400-110">El URI de la base del servicio es: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9d400-110">The service base URI is: https://api.security.microsoft.com</span></span> <br>

>[!NOTE]
><span data-ttu-id="9d400-111">Para obtener un mejor rendimiento, puede usar el servidor más cerca de la ubicación geográfica:</span><span class="sxs-lookup"><span data-stu-id="9d400-111">For better performance, you can use server closer to your Geo location:</span></span>
> - <span data-ttu-id="9d400-112">api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9d400-112">api-us.security.microsoft.com</span></span>
> - <span data-ttu-id="9d400-113">api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9d400-113">api-eu.security.microsoft.com</span></span>
> - <span data-ttu-id="9d400-114">api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9d400-114">api-uk.security.microsoft.com</span></span>

 - <span data-ttu-id="9d400-115">El recurso para la adquisición de token debe ser: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9d400-115">The resource for token acquisition should be: https://api.security.microsoft.com</span></span>

 - <span data-ttu-id="9d400-116">Todas las API de ```/api``` ruta de acceso son API de oData.</span><span class="sxs-lookup"><span data-stu-id="9d400-116">All the APIs under ```/api``` path are OData APIs.</span></span> <span data-ttu-id="9d400-117">p.ej. ```https://api.security.microsoft.com/api/incidents```</span><span class="sxs-lookup"><span data-stu-id="9d400-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="9d400-118">Lista de API disponibles:</span><span class="sxs-lookup"><span data-stu-id="9d400-118">List of available APIs:</span></span>

<span data-ttu-id="9d400-119">Tema</span><span class="sxs-lookup"><span data-stu-id="9d400-119">Topic</span></span> | <span data-ttu-id="9d400-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d400-120">Description</span></span>
:---|:---
[<span data-ttu-id="9d400-121">API de búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="9d400-121">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="9d400-122">Ejecutar consultas de búsqueda avanzada desde la API.</span><span class="sxs-lookup"><span data-stu-id="9d400-122">Run Advanced Hunting queries from API.</span></span>
[<span data-ttu-id="9d400-123">API de incidentes</span><span class="sxs-lookup"><span data-stu-id="9d400-123">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="9d400-124">Ejecutar llamadas API relacionadas con incidentes como: enumerar incidentes, actualizar incidente y más.</span><span class="sxs-lookup"><span data-stu-id="9d400-124">Run incident related API calls such as: list incidents, update incident and more.</span></span>
