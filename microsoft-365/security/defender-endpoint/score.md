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
ms.technology: mde
ms.openlocfilehash: 1c287a72318cfb2e6e4e3860ac90a90e561040fe
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500955"
---
# <a name="score-resource-type"></a><span data-ttu-id="b7f45-104">Tipo de recurso Score</span><span class="sxs-lookup"><span data-stu-id="b7f45-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b7f45-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b7f45-105">**Applies to:**</span></span>
- [<span data-ttu-id="b7f45-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b7f45-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="b7f45-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7f45-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b7f45-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="b7f45-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b7f45-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="b7f45-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="b7f45-110">Métodos</span><span class="sxs-lookup"><span data-stu-id="b7f45-110">Methods</span></span>

<span data-ttu-id="b7f45-111">Método</span><span class="sxs-lookup"><span data-stu-id="b7f45-111">Method</span></span> |<span data-ttu-id="b7f45-112">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b7f45-112">Return Type</span></span> |<span data-ttu-id="b7f45-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7f45-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="b7f45-114">Obtener puntuación de exposición</span><span class="sxs-lookup"><span data-stu-id="b7f45-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="b7f45-115">Puntuación</span><span class="sxs-lookup"><span data-stu-id="b7f45-115">Score</span></span>](score.md) | <span data-ttu-id="b7f45-116">Obtener la puntuación de exposición de la organización.</span><span class="sxs-lookup"><span data-stu-id="b7f45-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="b7f45-117">Obtener puntuación segura para dispositivos</span><span class="sxs-lookup"><span data-stu-id="b7f45-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="b7f45-118">Puntuación</span><span class="sxs-lookup"><span data-stu-id="b7f45-118">Score</span></span>](score.md) | <span data-ttu-id="b7f45-119">Obtiene la puntuación segura del dispositivo de la organización.</span><span class="sxs-lookup"><span data-stu-id="b7f45-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="b7f45-120">Puntuación de exposición de lista por grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="b7f45-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="b7f45-121">Puntuación</span><span class="sxs-lookup"><span data-stu-id="b7f45-121">Score</span></span>](score.md) | <span data-ttu-id="b7f45-122">Enumera las puntuaciones por grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b7f45-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="b7f45-123">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b7f45-123">Properties</span></span>

<span data-ttu-id="b7f45-124">Propiedad</span><span class="sxs-lookup"><span data-stu-id="b7f45-124">Property</span></span> |  <span data-ttu-id="b7f45-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="b7f45-125">Type</span></span>    |   <span data-ttu-id="b7f45-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7f45-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="b7f45-127">Puntuación</span><span class="sxs-lookup"><span data-stu-id="b7f45-127">Score</span></span> | <span data-ttu-id="b7f45-128">Doble</span><span class="sxs-lookup"><span data-stu-id="b7f45-128">Double</span></span> | <span data-ttu-id="b7f45-129">La puntuación actual.</span><span class="sxs-lookup"><span data-stu-id="b7f45-129">The current score.</span></span>
<span data-ttu-id="b7f45-130">Hora</span><span class="sxs-lookup"><span data-stu-id="b7f45-130">Time</span></span> | <span data-ttu-id="b7f45-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="b7f45-131">DateTime</span></span> | <span data-ttu-id="b7f45-132">La fecha y hora en que se realizó la llamada para esta API.</span><span class="sxs-lookup"><span data-stu-id="b7f45-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="b7f45-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="b7f45-133">RbacGroupName</span></span> | <span data-ttu-id="b7f45-134">Cadena</span><span class="sxs-lookup"><span data-stu-id="b7f45-134">String</span></span> | <span data-ttu-id="b7f45-135">El nombre del grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b7f45-135">The device group name.</span></span>
