---
title: Tipo de recurso Incident en la API de Microsoft Threat Protection
description: Obtenga información sobre los métodos y las propiedades del tipo de recurso Incident en la protección contra amenazas de Microsoft
keywords: incidente, incidentes, API
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
ms.openlocfilehash: ac149ca7263b8ef8bb37a7dd18bf0787a3114b37
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201308"
---
# <a name="incident-resource-type"></a><span data-ttu-id="25350-104">Tipo de recurso Incident</span><span class="sxs-lookup"><span data-stu-id="25350-104">Incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="25350-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="25350-105">**Applies to:**</span></span>
- <span data-ttu-id="25350-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="25350-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="25350-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="25350-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="25350-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="25350-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="methods"></a><span data-ttu-id="25350-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="25350-109">Methods</span></span>

<span data-ttu-id="25350-110">Método</span><span class="sxs-lookup"><span data-stu-id="25350-110">Method</span></span> |<span data-ttu-id="25350-111">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="25350-111">Return Type</span></span> |<span data-ttu-id="25350-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="25350-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="25350-113">Lista de Incidentes</span><span class="sxs-lookup"><span data-stu-id="25350-113">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="25350-114">Lista de [incidentes](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="25350-114">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="25350-115">Obtener una lista de incidentes.</span><span class="sxs-lookup"><span data-stu-id="25350-115">Get a list of incidents.</span></span>
[<span data-ttu-id="25350-116">Incidente de actualización</span><span class="sxs-lookup"><span data-stu-id="25350-116">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="25350-117">Incidentes</span><span class="sxs-lookup"><span data-stu-id="25350-117">Incident</span></span>](api-incident.md) | <span data-ttu-id="25350-118">Actualizar incidente específico.</span><span class="sxs-lookup"><span data-stu-id="25350-118">Update specific incident.</span></span>


## <a name="properties"></a><span data-ttu-id="25350-119">Propiedades</span><span class="sxs-lookup"><span data-stu-id="25350-119">Properties</span></span>

<span data-ttu-id="25350-120">Propiedad</span><span class="sxs-lookup"><span data-stu-id="25350-120">Property</span></span> |    <span data-ttu-id="25350-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="25350-121">Type</span></span>    |    <span data-ttu-id="25350-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="25350-122">Description</span></span>
:---|:---|:---
<span data-ttu-id="25350-123">incidentId</span><span class="sxs-lookup"><span data-stu-id="25350-123">incidentId</span></span> | <span data-ttu-id="25350-124">largo</span><span class="sxs-lookup"><span data-stu-id="25350-124">long</span></span> | <span data-ttu-id="25350-125">IDENTIFICADOR único de incidente.</span><span class="sxs-lookup"><span data-stu-id="25350-125">Incident unique ID.</span></span>
<span data-ttu-id="25350-126">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="25350-126">redirectIncidentId</span></span> | <span data-ttu-id="25350-127">Nullable Long</span><span class="sxs-lookup"><span data-stu-id="25350-127">nullable long</span></span> | <span data-ttu-id="25350-128">IDENTIFICADOR del incidente al que se combinó el incidente actual.</span><span class="sxs-lookup"><span data-stu-id="25350-128">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="25350-129">incidentName</span><span class="sxs-lookup"><span data-stu-id="25350-129">incidentName</span></span> | <span data-ttu-id="25350-130">string</span><span class="sxs-lookup"><span data-stu-id="25350-130">string</span></span> | <span data-ttu-id="25350-131">Nombre del incidente.</span><span class="sxs-lookup"><span data-stu-id="25350-131">The name of the Incident.</span></span>
<span data-ttu-id="25350-132">createdTime</span><span class="sxs-lookup"><span data-stu-id="25350-132">createdTime</span></span> | <span data-ttu-id="25350-133">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="25350-133">DateTimeOffset</span></span> | <span data-ttu-id="25350-134">La fecha y hora (en UTC) en que se creó el incidente.</span><span class="sxs-lookup"><span data-stu-id="25350-134">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="25350-135">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="25350-135">lastUpdateTime</span></span> | <span data-ttu-id="25350-136">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="25350-136">DateTimeOffset</span></span> | <span data-ttu-id="25350-137">La fecha y hora (en UTC) en que se actualizó por última vez el incidente.</span><span class="sxs-lookup"><span data-stu-id="25350-137">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="25350-138">assignedTo</span><span class="sxs-lookup"><span data-stu-id="25350-138">assignedTo</span></span> | <span data-ttu-id="25350-139">string</span><span class="sxs-lookup"><span data-stu-id="25350-139">string</span></span> | <span data-ttu-id="25350-140">Propietario del incidente.</span><span class="sxs-lookup"><span data-stu-id="25350-140">Owner of the Incident.</span></span>
<span data-ttu-id="25350-141">severity</span><span class="sxs-lookup"><span data-stu-id="25350-141">severity</span></span> | <span data-ttu-id="25350-142">Enum</span><span class="sxs-lookup"><span data-stu-id="25350-142">Enum</span></span> | <span data-ttu-id="25350-143">Gravedad del incidente.</span><span class="sxs-lookup"><span data-stu-id="25350-143">Severity of the Incident.</span></span> <span data-ttu-id="25350-144">Los valores posibles son: ```UnSpecified``` ,, ```Informational``` ```Low``` ```Medium``` y ```High``` .</span><span class="sxs-lookup"><span data-stu-id="25350-144">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium``` and ```High```.</span></span>
<span data-ttu-id="25350-145">status</span><span class="sxs-lookup"><span data-stu-id="25350-145">status</span></span> | <span data-ttu-id="25350-146">Enum</span><span class="sxs-lookup"><span data-stu-id="25350-146">Enum</span></span> | <span data-ttu-id="25350-147">Especifica el estado actual del incidente.</span><span class="sxs-lookup"><span data-stu-id="25350-147">Specifies the current status of the incident.</span></span> <span data-ttu-id="25350-148">Los valores posibles son ```Active``` : ```Resolved``` y ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="25350-148">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="25350-149">classification</span><span class="sxs-lookup"><span data-stu-id="25350-149">classification</span></span> | <span data-ttu-id="25350-150">Enum</span><span class="sxs-lookup"><span data-stu-id="25350-150">Enum</span></span> | <span data-ttu-id="25350-151">Especificación del incidente.</span><span class="sxs-lookup"><span data-stu-id="25350-151">Specification of the incident.</span></span> <span data-ttu-id="25350-152">Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="25350-152">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="25350-153">cálculo</span><span class="sxs-lookup"><span data-stu-id="25350-153">determination</span></span> | <span data-ttu-id="25350-154">Enum</span><span class="sxs-lookup"><span data-stu-id="25350-154">Enum</span></span> | <span data-ttu-id="25350-155">Especifica la determinación del incidente.</span><span class="sxs-lookup"><span data-stu-id="25350-155">Specifies the determination of the incident.</span></span> <span data-ttu-id="25350-156">Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="25350-156">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="25350-157">tags</span><span class="sxs-lookup"><span data-stu-id="25350-157">tags</span></span> | <span data-ttu-id="25350-158">Lista de cadenas</span><span class="sxs-lookup"><span data-stu-id="25350-158">string List</span></span> | <span data-ttu-id="25350-159">Lista de etiquetas de incidente.</span><span class="sxs-lookup"><span data-stu-id="25350-159">List of Incident tags.</span></span>
<span data-ttu-id="25350-160">alerts</span><span class="sxs-lookup"><span data-stu-id="25350-160">alerts</span></span> | <span data-ttu-id="25350-161">Lista de alertas</span><span class="sxs-lookup"><span data-stu-id="25350-161">Alert List</span></span> | <span data-ttu-id="25350-162">Lista de alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="25350-162">List of related alerts.</span></span> <span data-ttu-id="25350-163">Consulte los ejemplos en la documentación de la API de [incidentes de lista](api-list-incidents.md) .</span><span class="sxs-lookup"><span data-stu-id="25350-163">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>
