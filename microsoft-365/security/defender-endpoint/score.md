---
title: Propiedades y métodos de puntuación
description: Recupera la puntuación de exposición de la organización, la puntuación segura del dispositivo y la puntuación de exposición por grupo de dispositivos
keywords: api, api de gráfico, api admitidas, puntuación, puntuación de exposición, puntuación segura del dispositivo, puntuación de exposición por grupo de dispositivos
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 72dacca8529b54b082590d911f03aaa86bfe9097
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200166"
---
# <a name="score-resource-type"></a><span data-ttu-id="2beaa-104">Tipo de recurso Score</span><span class="sxs-lookup"><span data-stu-id="2beaa-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2beaa-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2beaa-105">**Applies to:**</span></span>
- [<span data-ttu-id="2beaa-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2beaa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="2beaa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2beaa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2beaa-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="2beaa-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2beaa-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="2beaa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="2beaa-110">Methods</span><span class="sxs-lookup"><span data-stu-id="2beaa-110">Methods</span></span>

<span data-ttu-id="2beaa-111">Método</span><span class="sxs-lookup"><span data-stu-id="2beaa-111">Method</span></span> |<span data-ttu-id="2beaa-112">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2beaa-112">Return Type</span></span> |<span data-ttu-id="2beaa-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="2beaa-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="2beaa-114">Obtener puntuación de exposición</span><span class="sxs-lookup"><span data-stu-id="2beaa-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="2beaa-115">Puntuación</span><span class="sxs-lookup"><span data-stu-id="2beaa-115">Score</span></span>](score.md) | <span data-ttu-id="2beaa-116">Obtener la puntuación de exposición de la organización.</span><span class="sxs-lookup"><span data-stu-id="2beaa-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="2beaa-117">Obtener puntuación segura del dispositivo</span><span class="sxs-lookup"><span data-stu-id="2beaa-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="2beaa-118">Puntuación</span><span class="sxs-lookup"><span data-stu-id="2beaa-118">Score</span></span>](score.md) | <span data-ttu-id="2beaa-119">Obtiene la puntuación segura del dispositivo de la organización.</span><span class="sxs-lookup"><span data-stu-id="2beaa-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="2beaa-120">Puntuación de exposición de lista por grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="2beaa-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="2beaa-121">Puntuación</span><span class="sxs-lookup"><span data-stu-id="2beaa-121">Score</span></span>](score.md) | <span data-ttu-id="2beaa-122">Enumera las puntuaciones por grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2beaa-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="2beaa-123">Propiedades</span><span class="sxs-lookup"><span data-stu-id="2beaa-123">Properties</span></span>

<span data-ttu-id="2beaa-124">Propiedad</span><span class="sxs-lookup"><span data-stu-id="2beaa-124">Property</span></span> |  <span data-ttu-id="2beaa-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="2beaa-125">Type</span></span>    |   <span data-ttu-id="2beaa-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="2beaa-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="2beaa-127">Puntuación</span><span class="sxs-lookup"><span data-stu-id="2beaa-127">Score</span></span> | <span data-ttu-id="2beaa-128">Doble</span><span class="sxs-lookup"><span data-stu-id="2beaa-128">Double</span></span> | <span data-ttu-id="2beaa-129">La puntuación actual.</span><span class="sxs-lookup"><span data-stu-id="2beaa-129">The current score.</span></span>
<span data-ttu-id="2beaa-130">Hora</span><span class="sxs-lookup"><span data-stu-id="2beaa-130">Time</span></span> | <span data-ttu-id="2beaa-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="2beaa-131">DateTime</span></span> | <span data-ttu-id="2beaa-132">La fecha y hora en que se realizó la llamada para esta API.</span><span class="sxs-lookup"><span data-stu-id="2beaa-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="2beaa-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="2beaa-133">RbacGroupName</span></span> | <span data-ttu-id="2beaa-134">Cadena</span><span class="sxs-lookup"><span data-stu-id="2beaa-134">String</span></span> | <span data-ttu-id="2beaa-135">El nombre del grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2beaa-135">The device group name.</span></span>
