---
title: Propiedades y métodos de puntuación
description: Recupera la puntuación de exposición de la organización, la puntuación segura del dispositivo y la puntuación de exposición por grupo de dispositivos
keywords: api, api de gráfico, api admitidas, puntuación, puntuación de exposición, puntuación segura del dispositivo, puntuación de exposición por grupo de dispositivos
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 89012dce4aa5b74d09f071b23f7709b4bd0bf03c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771436"
---
# <a name="score-resource-type"></a><span data-ttu-id="ba53f-104">Tipo de recurso Score</span><span class="sxs-lookup"><span data-stu-id="ba53f-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ba53f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ba53f-105">**Applies to:**</span></span>
- [<span data-ttu-id="ba53f-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="ba53f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="ba53f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ba53f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ba53f-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="ba53f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ba53f-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="ba53f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="ba53f-110">Métodos</span><span class="sxs-lookup"><span data-stu-id="ba53f-110">Methods</span></span>

<span data-ttu-id="ba53f-111">Método</span><span class="sxs-lookup"><span data-stu-id="ba53f-111">Method</span></span> |<span data-ttu-id="ba53f-112">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ba53f-112">Return Type</span></span> |<span data-ttu-id="ba53f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba53f-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="ba53f-114">Obtener puntuación de exposición</span><span class="sxs-lookup"><span data-stu-id="ba53f-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="ba53f-115">Puntuación</span><span class="sxs-lookup"><span data-stu-id="ba53f-115">Score</span></span>](score.md) | <span data-ttu-id="ba53f-116">Obtener la puntuación de exposición de la organización.</span><span class="sxs-lookup"><span data-stu-id="ba53f-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="ba53f-117">Obtener puntuación segura para dispositivos</span><span class="sxs-lookup"><span data-stu-id="ba53f-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="ba53f-118">Puntuación</span><span class="sxs-lookup"><span data-stu-id="ba53f-118">Score</span></span>](score.md) | <span data-ttu-id="ba53f-119">Obtiene la puntuación segura del dispositivo de la organización.</span><span class="sxs-lookup"><span data-stu-id="ba53f-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="ba53f-120">Puntuación de exposición de lista por grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="ba53f-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="ba53f-121">Puntuación</span><span class="sxs-lookup"><span data-stu-id="ba53f-121">Score</span></span>](score.md) | <span data-ttu-id="ba53f-122">Enumera las puntuaciones por grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ba53f-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="ba53f-123">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ba53f-123">Properties</span></span>

<span data-ttu-id="ba53f-124">Propiedad</span><span class="sxs-lookup"><span data-stu-id="ba53f-124">Property</span></span> |  <span data-ttu-id="ba53f-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="ba53f-125">Type</span></span>    |   <span data-ttu-id="ba53f-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba53f-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="ba53f-127">Puntuación</span><span class="sxs-lookup"><span data-stu-id="ba53f-127">Score</span></span> | <span data-ttu-id="ba53f-128">Doble</span><span class="sxs-lookup"><span data-stu-id="ba53f-128">Double</span></span> | <span data-ttu-id="ba53f-129">La puntuación actual.</span><span class="sxs-lookup"><span data-stu-id="ba53f-129">The current score.</span></span>
<span data-ttu-id="ba53f-130">Hora</span><span class="sxs-lookup"><span data-stu-id="ba53f-130">Time</span></span> | <span data-ttu-id="ba53f-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="ba53f-131">DateTime</span></span> | <span data-ttu-id="ba53f-132">La fecha y hora en que se realizó la llamada para esta API.</span><span class="sxs-lookup"><span data-stu-id="ba53f-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="ba53f-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="ba53f-133">RbacGroupName</span></span> | <span data-ttu-id="ba53f-134">Cadena</span><span class="sxs-lookup"><span data-stu-id="ba53f-134">String</span></span> | <span data-ttu-id="ba53f-135">El nombre del grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ba53f-135">The device group name.</span></span>
