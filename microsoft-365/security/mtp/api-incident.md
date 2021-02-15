---
title: API de incidentes de Microsoft 365 Defender y el tipo de recurso de incidente
description: Obtenga información sobre los métodos y propiedades del tipo de recurso Incidente en Microsoft 365 Defender
keywords: incidente, incidentes, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 37413c3c7458527e90d4657ddfb3afb058e1dfaa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928359"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="78ae6-104">API de incidentes de Microsoft 365 Defender y el tipo de recurso de incidente</span><span class="sxs-lookup"><span data-stu-id="78ae6-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="78ae6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="78ae6-105">**Applies to:**</span></span>

- <span data-ttu-id="78ae6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="78ae6-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78ae6-107">Parte de la información está relacionada con el producto de versión preliminar que puede modificarse considerablemente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="78ae6-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="78ae6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="78ae6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="78ae6-109">Un [incidente es](incidents-overview.md) una colección de alertas relacionadas que ayudan a describir un ataque.</span><span class="sxs-lookup"><span data-stu-id="78ae6-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="78ae6-110">Microsoft 365 Defender agrega automáticamente eventos de diferentes entidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="78ae6-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="78ae6-111">Puede usar la API de incidentes para acceder mediante programación a los incidentes de su organización y a las alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="78ae6-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="78ae6-112">Cuotas y asignación de recursos</span><span class="sxs-lookup"><span data-stu-id="78ae6-112">Quotas and resource allocation</span></span>

<span data-ttu-id="78ae6-113">Puede solicitar hasta 50 llamadas por minuto o 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="78ae6-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="78ae6-114">Cada método también tiene sus propias cuotas.</span><span class="sxs-lookup"><span data-stu-id="78ae6-114">Each method also has its own quotas.</span></span> <span data-ttu-id="78ae6-115">Para obtener más información sobre las cuotas específicas del método, consulta el artículo correspondiente sobre el método que quieres usar.</span><span class="sxs-lookup"><span data-stu-id="78ae6-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="78ae6-116">Un código de respuesta HTTP indica que ha alcanzado una cuota, ya sea por número de solicitudes enviadas o por tiempo `429` de ejecución asignado.</span><span class="sxs-lookup"><span data-stu-id="78ae6-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="78ae6-117">El cuerpo de la respuesta incluirá el tiempo hasta que se restablezca la cuota alcanzada.</span><span class="sxs-lookup"><span data-stu-id="78ae6-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="78ae6-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="78ae6-118">Permissions</span></span>

<span data-ttu-id="78ae6-119">La API de incidentes requiere diferentes tipos de permisos para cada uno de sus métodos.</span><span class="sxs-lookup"><span data-stu-id="78ae6-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="78ae6-120">Para obtener más información acerca de los permisos necesarios, vea el artículo del método respectivo.</span><span class="sxs-lookup"><span data-stu-id="78ae6-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="78ae6-121">Methods</span><span class="sxs-lookup"><span data-stu-id="78ae6-121">Methods</span></span>

<span data-ttu-id="78ae6-122">Método</span><span class="sxs-lookup"><span data-stu-id="78ae6-122">Method</span></span> | <span data-ttu-id="78ae6-123">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="78ae6-123">Return Type</span></span> | <span data-ttu-id="78ae6-124">Description</span><span class="sxs-lookup"><span data-stu-id="78ae6-124">Description</span></span>
-|-|-
[<span data-ttu-id="78ae6-125">Lista de Incidentes</span><span class="sxs-lookup"><span data-stu-id="78ae6-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="78ae6-126">[Lista de](api-incident.md) incidentes</span><span class="sxs-lookup"><span data-stu-id="78ae6-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="78ae6-127">Obtener una lista de incidentes.</span><span class="sxs-lookup"><span data-stu-id="78ae6-127">Get a list of incidents.</span></span>
[<span data-ttu-id="78ae6-128">Incidente de actualización</span><span class="sxs-lookup"><span data-stu-id="78ae6-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="78ae6-129">Incidente</span><span class="sxs-lookup"><span data-stu-id="78ae6-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="78ae6-130">Actualizar un incidente específico.</span><span class="sxs-lookup"><span data-stu-id="78ae6-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="78ae6-131">Cuerpo de la solicitud, respuesta y ejemplos</span><span class="sxs-lookup"><span data-stu-id="78ae6-131">Request body, response, and examples</span></span>

<span data-ttu-id="78ae6-132">Consulte los artículos de métodos respectivos para obtener más información sobre cómo construir una solicitud o analizar una respuesta, y para obtener ejemplos prácticos.</span><span class="sxs-lookup"><span data-stu-id="78ae6-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="78ae6-133">Propiedades comunes</span><span class="sxs-lookup"><span data-stu-id="78ae6-133">Common properties</span></span>

<span data-ttu-id="78ae6-134">Propiedad</span><span class="sxs-lookup"><span data-stu-id="78ae6-134">Property</span></span> | <span data-ttu-id="78ae6-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="78ae6-135">Type</span></span> | <span data-ttu-id="78ae6-136">Description</span><span class="sxs-lookup"><span data-stu-id="78ae6-136">Description</span></span>
-|-|-
<span data-ttu-id="78ae6-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="78ae6-137">incidentId</span></span> | <span data-ttu-id="78ae6-138">largo</span><span class="sxs-lookup"><span data-stu-id="78ae6-138">long</span></span> | <span data-ttu-id="78ae6-139">Identificador único del incidente.</span><span class="sxs-lookup"><span data-stu-id="78ae6-139">Incident unique ID.</span></span>
<span data-ttu-id="78ae6-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="78ae6-140">redirectIncidentId</span></span> | <span data-ttu-id="78ae6-141">long que admite valores NULL</span><span class="sxs-lookup"><span data-stu-id="78ae6-141">nullable long</span></span> | <span data-ttu-id="78ae6-142">El identificador de incidente con el que se ha combinado el incidente actual.</span><span class="sxs-lookup"><span data-stu-id="78ae6-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="78ae6-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="78ae6-143">incidentName</span></span> | <span data-ttu-id="78ae6-144">string</span><span class="sxs-lookup"><span data-stu-id="78ae6-144">string</span></span> | <span data-ttu-id="78ae6-145">El nombre del incidente.</span><span class="sxs-lookup"><span data-stu-id="78ae6-145">The name of the Incident.</span></span>
<span data-ttu-id="78ae6-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="78ae6-146">createdTime</span></span> | <span data-ttu-id="78ae6-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="78ae6-147">DateTimeOffset</span></span> | <span data-ttu-id="78ae6-148">Fecha y hora (en UTC) en que se creó el incidente.</span><span class="sxs-lookup"><span data-stu-id="78ae6-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="78ae6-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="78ae6-149">lastUpdateTime</span></span> | <span data-ttu-id="78ae6-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="78ae6-150">DateTimeOffset</span></span> | <span data-ttu-id="78ae6-151">Fecha y hora (en UTC) en que se actualizó por última vez el incidente.</span><span class="sxs-lookup"><span data-stu-id="78ae6-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="78ae6-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="78ae6-152">assignedTo</span></span> | <span data-ttu-id="78ae6-153">string</span><span class="sxs-lookup"><span data-stu-id="78ae6-153">string</span></span> | <span data-ttu-id="78ae6-154">Propietario del incidente.</span><span class="sxs-lookup"><span data-stu-id="78ae6-154">Owner of the Incident.</span></span>
<span data-ttu-id="78ae6-155">severity</span><span class="sxs-lookup"><span data-stu-id="78ae6-155">severity</span></span> | <span data-ttu-id="78ae6-156">Enum</span><span class="sxs-lookup"><span data-stu-id="78ae6-156">Enum</span></span> | <span data-ttu-id="78ae6-157">Gravedad del incidente.</span><span class="sxs-lookup"><span data-stu-id="78ae6-157">Severity of the Incident.</span></span> <span data-ttu-id="78ae6-158">Los valores posibles ```UnSpecified``` son: ```Informational``` , , y ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="78ae6-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="78ae6-159">status</span><span class="sxs-lookup"><span data-stu-id="78ae6-159">status</span></span> | <span data-ttu-id="78ae6-160">Enum</span><span class="sxs-lookup"><span data-stu-id="78ae6-160">Enum</span></span> | <span data-ttu-id="78ae6-161">Especifica el estado actual del incidente.</span><span class="sxs-lookup"><span data-stu-id="78ae6-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="78ae6-162">Los valores posibles son: ```Active``` ```Resolved``` , y ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="78ae6-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="78ae6-163">classification</span><span class="sxs-lookup"><span data-stu-id="78ae6-163">classification</span></span> | <span data-ttu-id="78ae6-164">Enum</span><span class="sxs-lookup"><span data-stu-id="78ae6-164">Enum</span></span> | <span data-ttu-id="78ae6-165">Especificación del incidente.</span><span class="sxs-lookup"><span data-stu-id="78ae6-165">Specification of the incident.</span></span> <span data-ttu-id="78ae6-166">Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="78ae6-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="78ae6-167">determinación</span><span class="sxs-lookup"><span data-stu-id="78ae6-167">determination</span></span> | <span data-ttu-id="78ae6-168">Enum</span><span class="sxs-lookup"><span data-stu-id="78ae6-168">Enum</span></span> | <span data-ttu-id="78ae6-169">Especifica la determinación del incidente.</span><span class="sxs-lookup"><span data-stu-id="78ae6-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="78ae6-170">Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="78ae6-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="78ae6-171">tags</span><span class="sxs-lookup"><span data-stu-id="78ae6-171">tags</span></span> | <span data-ttu-id="78ae6-172">lista de cadenas</span><span class="sxs-lookup"><span data-stu-id="78ae6-172">string List</span></span> | <span data-ttu-id="78ae6-173">Lista de etiquetas de incidentes.</span><span class="sxs-lookup"><span data-stu-id="78ae6-173">List of Incident tags.</span></span>
<span data-ttu-id="78ae6-174">alerts</span><span class="sxs-lookup"><span data-stu-id="78ae6-174">alerts</span></span> | <span data-ttu-id="78ae6-175">Lista de alertas</span><span class="sxs-lookup"><span data-stu-id="78ae6-175">Alert List</span></span> | <span data-ttu-id="78ae6-176">Lista de alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="78ae6-176">List of related alerts.</span></span> <span data-ttu-id="78ae6-177">Vea ejemplos en la [documentación de la](api-list-incidents.md) API de incidentes de lista.</span><span class="sxs-lookup"><span data-stu-id="78ae6-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="78ae6-178">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="78ae6-178">Related articles</span></span>

- [<span data-ttu-id="78ae6-179">Introducción a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="78ae6-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="78ae6-180">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="78ae6-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="78ae6-181">ENUMERAR LA API de incidentes</span><span class="sxs-lookup"><span data-stu-id="78ae6-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="78ae6-182">ACTUALIZAR API de incidentes</span><span class="sxs-lookup"><span data-stu-id="78ae6-182">Update incident API</span></span>](api-update-incidents.md)
