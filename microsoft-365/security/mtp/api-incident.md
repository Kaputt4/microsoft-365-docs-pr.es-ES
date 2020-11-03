---
title: Tipo de recurso Incident en la API de Microsoft 365 defender
description: Obtenga información sobre los métodos y las propiedades del tipo de recurso Incident en Microsoft 365 defender
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
ms.openlocfilehash: 68bee647cdd5687dbaad08ce3cd01b427dabf030
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844025"
---
# <a name="incident-resource-type"></a><span data-ttu-id="ade74-104">Tipo de recurso Incident</span><span class="sxs-lookup"><span data-stu-id="ade74-104">Incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ade74-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ade74-105">**Applies to:**</span></span>
- <span data-ttu-id="ade74-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="ade74-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="ade74-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="ade74-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="ade74-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="ade74-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="methods"></a><span data-ttu-id="ade74-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="ade74-109">Methods</span></span>

<span data-ttu-id="ade74-110">Método</span><span class="sxs-lookup"><span data-stu-id="ade74-110">Method</span></span> |<span data-ttu-id="ade74-111">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ade74-111">Return Type</span></span> |<span data-ttu-id="ade74-112">Description</span><span class="sxs-lookup"><span data-stu-id="ade74-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="ade74-113">Lista de Incidentes</span><span class="sxs-lookup"><span data-stu-id="ade74-113">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="ade74-114">Lista de [incidentes](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="ade74-114">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="ade74-115">Obtener una lista de incidentes.</span><span class="sxs-lookup"><span data-stu-id="ade74-115">Get a list of incidents.</span></span>
[<span data-ttu-id="ade74-116">Incidente de actualización</span><span class="sxs-lookup"><span data-stu-id="ade74-116">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="ade74-117">Incidentes</span><span class="sxs-lookup"><span data-stu-id="ade74-117">Incident</span></span>](api-incident.md) | <span data-ttu-id="ade74-118">Actualizar incidente específico.</span><span class="sxs-lookup"><span data-stu-id="ade74-118">Update specific incident.</span></span>


## <a name="properties"></a><span data-ttu-id="ade74-119">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ade74-119">Properties</span></span>

<span data-ttu-id="ade74-120">Propiedad</span><span class="sxs-lookup"><span data-stu-id="ade74-120">Property</span></span> |    <span data-ttu-id="ade74-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="ade74-121">Type</span></span>    |    <span data-ttu-id="ade74-122">Description</span><span class="sxs-lookup"><span data-stu-id="ade74-122">Description</span></span>
:---|:---|:---
<span data-ttu-id="ade74-123">incidentId</span><span class="sxs-lookup"><span data-stu-id="ade74-123">incidentId</span></span> | <span data-ttu-id="ade74-124">largo</span><span class="sxs-lookup"><span data-stu-id="ade74-124">long</span></span> | <span data-ttu-id="ade74-125">IDENTIFICADOR único de incidente.</span><span class="sxs-lookup"><span data-stu-id="ade74-125">Incident unique ID.</span></span>
<span data-ttu-id="ade74-126">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="ade74-126">redirectIncidentId</span></span> | <span data-ttu-id="ade74-127">Nullable Long</span><span class="sxs-lookup"><span data-stu-id="ade74-127">nullable long</span></span> | <span data-ttu-id="ade74-128">IDENTIFICADOR del incidente al que se combinó el incidente actual.</span><span class="sxs-lookup"><span data-stu-id="ade74-128">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="ade74-129">incidentName</span><span class="sxs-lookup"><span data-stu-id="ade74-129">incidentName</span></span> | <span data-ttu-id="ade74-130">string</span><span class="sxs-lookup"><span data-stu-id="ade74-130">string</span></span> | <span data-ttu-id="ade74-131">Nombre del incidente.</span><span class="sxs-lookup"><span data-stu-id="ade74-131">The name of the Incident.</span></span>
<span data-ttu-id="ade74-132">createdTime</span><span class="sxs-lookup"><span data-stu-id="ade74-132">createdTime</span></span> | <span data-ttu-id="ade74-133">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="ade74-133">DateTimeOffset</span></span> | <span data-ttu-id="ade74-134">La fecha y hora (en UTC) en que se creó el incidente.</span><span class="sxs-lookup"><span data-stu-id="ade74-134">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="ade74-135">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="ade74-135">lastUpdateTime</span></span> | <span data-ttu-id="ade74-136">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="ade74-136">DateTimeOffset</span></span> | <span data-ttu-id="ade74-137">La fecha y hora (en UTC) en que se actualizó por última vez el incidente.</span><span class="sxs-lookup"><span data-stu-id="ade74-137">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="ade74-138">assignedTo</span><span class="sxs-lookup"><span data-stu-id="ade74-138">assignedTo</span></span> | <span data-ttu-id="ade74-139">string</span><span class="sxs-lookup"><span data-stu-id="ade74-139">string</span></span> | <span data-ttu-id="ade74-140">Propietario del incidente.</span><span class="sxs-lookup"><span data-stu-id="ade74-140">Owner of the Incident.</span></span>
<span data-ttu-id="ade74-141">severity</span><span class="sxs-lookup"><span data-stu-id="ade74-141">severity</span></span> | <span data-ttu-id="ade74-142">Enum</span><span class="sxs-lookup"><span data-stu-id="ade74-142">Enum</span></span> | <span data-ttu-id="ade74-143">Gravedad del incidente.</span><span class="sxs-lookup"><span data-stu-id="ade74-143">Severity of the Incident.</span></span> <span data-ttu-id="ade74-144">Los valores posibles son: ```UnSpecified``` ,, ```Informational``` ```Low``` ```Medium``` y ```High``` .</span><span class="sxs-lookup"><span data-stu-id="ade74-144">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium``` and ```High```.</span></span>
<span data-ttu-id="ade74-145">status</span><span class="sxs-lookup"><span data-stu-id="ade74-145">status</span></span> | <span data-ttu-id="ade74-146">Enum</span><span class="sxs-lookup"><span data-stu-id="ade74-146">Enum</span></span> | <span data-ttu-id="ade74-147">Especifica el estado actual del incidente.</span><span class="sxs-lookup"><span data-stu-id="ade74-147">Specifies the current status of the incident.</span></span> <span data-ttu-id="ade74-148">Los valores posibles son ```Active``` : ```Resolved``` y ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="ade74-148">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="ade74-149">classification</span><span class="sxs-lookup"><span data-stu-id="ade74-149">classification</span></span> | <span data-ttu-id="ade74-150">Enum</span><span class="sxs-lookup"><span data-stu-id="ade74-150">Enum</span></span> | <span data-ttu-id="ade74-151">Especificación del incidente.</span><span class="sxs-lookup"><span data-stu-id="ade74-151">Specification of the incident.</span></span> <span data-ttu-id="ade74-152">Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="ade74-152">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="ade74-153">cálculo</span><span class="sxs-lookup"><span data-stu-id="ade74-153">determination</span></span> | <span data-ttu-id="ade74-154">Enum</span><span class="sxs-lookup"><span data-stu-id="ade74-154">Enum</span></span> | <span data-ttu-id="ade74-155">Especifica la determinación del incidente.</span><span class="sxs-lookup"><span data-stu-id="ade74-155">Specifies the determination of the incident.</span></span> <span data-ttu-id="ade74-156">Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="ade74-156">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="ade74-157">tags</span><span class="sxs-lookup"><span data-stu-id="ade74-157">tags</span></span> | <span data-ttu-id="ade74-158">Lista de cadenas</span><span class="sxs-lookup"><span data-stu-id="ade74-158">string List</span></span> | <span data-ttu-id="ade74-159">Lista de etiquetas de incidente.</span><span class="sxs-lookup"><span data-stu-id="ade74-159">List of Incident tags.</span></span>
<span data-ttu-id="ade74-160">alerts</span><span class="sxs-lookup"><span data-stu-id="ade74-160">alerts</span></span> | <span data-ttu-id="ade74-161">Lista de alertas</span><span class="sxs-lookup"><span data-stu-id="ade74-161">Alert List</span></span> | <span data-ttu-id="ade74-162">Lista de alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="ade74-162">List of related alerts.</span></span> <span data-ttu-id="ade74-163">Consulte los ejemplos en la documentación de la API de [incidentes de lista](api-list-incidents.md) .</span><span class="sxs-lookup"><span data-stu-id="ade74-163">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>
