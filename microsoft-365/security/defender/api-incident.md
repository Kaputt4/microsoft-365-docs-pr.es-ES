---
title: Microsoft 365 API de incidentes de Defender y el tipo de recurso incidentes
description: Obtenga información sobre los métodos y propiedades del tipo de recurso Incidents en Microsoft 365 Defender
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 587d6107b0c09b2178311d8da6606968e7fda083
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730935"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a><span data-ttu-id="6943d-104">Microsoft 365 API de incidentes de Defender y el tipo de recurso incidents</span><span class="sxs-lookup"><span data-stu-id="6943d-104">Microsoft 365 Defender incidents API and the incidents resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6943d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6943d-105">**Applies to:**</span></span>

- [<span data-ttu-id="6943d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6943d-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="6943d-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="6943d-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6943d-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="6943d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="6943d-109">Un [incidente](incidents-overview.md) es una colección de alertas relacionadas que ayudan a describir un ataque.</span><span class="sxs-lookup"><span data-stu-id="6943d-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="6943d-110">Los eventos de diferentes entidades de la organización se agregan automáticamente mediante Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6943d-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="6943d-111">Puede usar la API de incidentes para acceder programativamente a los incidentes de su organización y a las alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="6943d-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="6943d-112">Cuotas y asignación de recursos</span><span class="sxs-lookup"><span data-stu-id="6943d-112">Quotas and resource allocation</span></span>

<span data-ttu-id="6943d-113">Puede solicitar hasta 50 llamadas por minuto o 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="6943d-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="6943d-114">Cada método también tiene sus propias cuotas.</span><span class="sxs-lookup"><span data-stu-id="6943d-114">Each method also has its own quotas.</span></span> <span data-ttu-id="6943d-115">Para obtener más información sobre las cuotas específicas del método, vea el artículo correspondiente para el método que desea usar.</span><span class="sxs-lookup"><span data-stu-id="6943d-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="6943d-116">Un código de respuesta HTTP indica que ha alcanzado una cuota, ya sea por número de solicitudes enviadas o por tiempo `429` de ejecución asignado.</span><span class="sxs-lookup"><span data-stu-id="6943d-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="6943d-117">El cuerpo de la respuesta incluirá la hora hasta que se restablezca la cuota alcanzada.</span><span class="sxs-lookup"><span data-stu-id="6943d-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="6943d-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="6943d-118">Permissions</span></span>

<span data-ttu-id="6943d-119">La API de incidentes requiere distintos tipos de permisos para cada uno de sus métodos.</span><span class="sxs-lookup"><span data-stu-id="6943d-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="6943d-120">Para obtener más información acerca de los permisos necesarios, consulte el artículo del método respectivo.</span><span class="sxs-lookup"><span data-stu-id="6943d-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="6943d-121">Métodos</span><span class="sxs-lookup"><span data-stu-id="6943d-121">Methods</span></span>

<span data-ttu-id="6943d-122">Método</span><span class="sxs-lookup"><span data-stu-id="6943d-122">Method</span></span> | <span data-ttu-id="6943d-123">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6943d-123">Return Type</span></span> | <span data-ttu-id="6943d-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="6943d-124">Description</span></span>
-|-|-
[<span data-ttu-id="6943d-125">Lista de Incidentes</span><span class="sxs-lookup"><span data-stu-id="6943d-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="6943d-126">[Lista de](api-incident.md) incidentes</span><span class="sxs-lookup"><span data-stu-id="6943d-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="6943d-127">Obtener una lista de incidentes.</span><span class="sxs-lookup"><span data-stu-id="6943d-127">Get a list of incidents.</span></span>
[<span data-ttu-id="6943d-128">Incidente de actualización</span><span class="sxs-lookup"><span data-stu-id="6943d-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="6943d-129">Incidente</span><span class="sxs-lookup"><span data-stu-id="6943d-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="6943d-130">Actualice un incidente específico.</span><span class="sxs-lookup"><span data-stu-id="6943d-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="6943d-131">Cuerpo de la solicitud, respuesta y ejemplos</span><span class="sxs-lookup"><span data-stu-id="6943d-131">Request body, response, and examples</span></span>

<span data-ttu-id="6943d-132">Consulte los artículos de método respectivos para obtener más información sobre cómo construir una solicitud o analizar una respuesta, y para obtener ejemplos prácticos.</span><span class="sxs-lookup"><span data-stu-id="6943d-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="6943d-133">Propiedades comunes</span><span class="sxs-lookup"><span data-stu-id="6943d-133">Common properties</span></span>

<span data-ttu-id="6943d-134">Propiedad</span><span class="sxs-lookup"><span data-stu-id="6943d-134">Property</span></span> | <span data-ttu-id="6943d-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="6943d-135">Type</span></span> | <span data-ttu-id="6943d-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="6943d-136">Description</span></span>
-|-|-
<span data-ttu-id="6943d-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="6943d-137">incidentId</span></span> | <span data-ttu-id="6943d-138">largo</span><span class="sxs-lookup"><span data-stu-id="6943d-138">long</span></span> | <span data-ttu-id="6943d-139">Identificador único de incidente.</span><span class="sxs-lookup"><span data-stu-id="6943d-139">Incident unique ID.</span></span>
<span data-ttu-id="6943d-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="6943d-140">redirectIncidentId</span></span> | <span data-ttu-id="6943d-141">long nullable</span><span class="sxs-lookup"><span data-stu-id="6943d-141">nullable long</span></span> | <span data-ttu-id="6943d-142">El identificador de incidente con el que se ha combinado el incidente actual.</span><span class="sxs-lookup"><span data-stu-id="6943d-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="6943d-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="6943d-143">incidentName</span></span> | <span data-ttu-id="6943d-144">string</span><span class="sxs-lookup"><span data-stu-id="6943d-144">string</span></span> | <span data-ttu-id="6943d-145">Nombre del incidente.</span><span class="sxs-lookup"><span data-stu-id="6943d-145">The name of the Incident.</span></span>
<span data-ttu-id="6943d-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="6943d-146">createdTime</span></span> | <span data-ttu-id="6943d-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="6943d-147">DateTimeOffset</span></span> | <span data-ttu-id="6943d-148">La fecha y hora (en UTC) que se creó el incidente.</span><span class="sxs-lookup"><span data-stu-id="6943d-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="6943d-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="6943d-149">lastUpdateTime</span></span> | <span data-ttu-id="6943d-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="6943d-150">DateTimeOffset</span></span> | <span data-ttu-id="6943d-151">La fecha y hora (en UTC) se actualizó por última vez el incidente.</span><span class="sxs-lookup"><span data-stu-id="6943d-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="6943d-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="6943d-152">assignedTo</span></span> | <span data-ttu-id="6943d-153">string</span><span class="sxs-lookup"><span data-stu-id="6943d-153">string</span></span> | <span data-ttu-id="6943d-154">Propietario del incidente.</span><span class="sxs-lookup"><span data-stu-id="6943d-154">Owner of the Incident.</span></span>
<span data-ttu-id="6943d-155">severity</span><span class="sxs-lookup"><span data-stu-id="6943d-155">severity</span></span> | <span data-ttu-id="6943d-156">Enum</span><span class="sxs-lookup"><span data-stu-id="6943d-156">Enum</span></span> | <span data-ttu-id="6943d-157">Gravedad del incidente.</span><span class="sxs-lookup"><span data-stu-id="6943d-157">Severity of the Incident.</span></span> <span data-ttu-id="6943d-158">Los valores posibles son: ```UnSpecified``` , , , y ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="6943d-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="6943d-159">status</span><span class="sxs-lookup"><span data-stu-id="6943d-159">status</span></span> | <span data-ttu-id="6943d-160">Enum</span><span class="sxs-lookup"><span data-stu-id="6943d-160">Enum</span></span> | <span data-ttu-id="6943d-161">Especifica el estado actual del incidente.</span><span class="sxs-lookup"><span data-stu-id="6943d-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="6943d-162">Los valores posibles son: ```Active``` ```Resolved``` , y ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="6943d-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="6943d-163">classification</span><span class="sxs-lookup"><span data-stu-id="6943d-163">classification</span></span> | <span data-ttu-id="6943d-164">Enum</span><span class="sxs-lookup"><span data-stu-id="6943d-164">Enum</span></span> | <span data-ttu-id="6943d-165">Especificación del incidente.</span><span class="sxs-lookup"><span data-stu-id="6943d-165">Specification of the incident.</span></span> <span data-ttu-id="6943d-166">Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="6943d-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="6943d-167">determinación</span><span class="sxs-lookup"><span data-stu-id="6943d-167">determination</span></span> | <span data-ttu-id="6943d-168">Enum</span><span class="sxs-lookup"><span data-stu-id="6943d-168">Enum</span></span> | <span data-ttu-id="6943d-169">Especifica la determinación del incidente.</span><span class="sxs-lookup"><span data-stu-id="6943d-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="6943d-170">Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="6943d-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="6943d-171">tags</span><span class="sxs-lookup"><span data-stu-id="6943d-171">tags</span></span> | <span data-ttu-id="6943d-172">lista de cadenas</span><span class="sxs-lookup"><span data-stu-id="6943d-172">string List</span></span> | <span data-ttu-id="6943d-173">Lista de etiquetas de incidentes.</span><span class="sxs-lookup"><span data-stu-id="6943d-173">List of Incident tags.</span></span>
<span data-ttu-id="6943d-174">comments</span><span class="sxs-lookup"><span data-stu-id="6943d-174">comments</span></span> | <span data-ttu-id="6943d-175">Lista de comentarios de incidentes</span><span class="sxs-lookup"><span data-stu-id="6943d-175">List of incident comments</span></span> | <span data-ttu-id="6943d-176">El objeto Incident Comment contiene: cadena de comentario, createdBy string y createTime date time.</span><span class="sxs-lookup"><span data-stu-id="6943d-176">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="6943d-177">alerts</span><span class="sxs-lookup"><span data-stu-id="6943d-177">alerts</span></span> | <span data-ttu-id="6943d-178">Lista de alertas</span><span class="sxs-lookup"><span data-stu-id="6943d-178">Alert List</span></span> | <span data-ttu-id="6943d-179">Lista de alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="6943d-179">List of related alerts.</span></span> <span data-ttu-id="6943d-180">Vea ejemplos en [Enumerar la documentación de](api-list-incidents.md) la API de incidentes.</span><span class="sxs-lookup"><span data-stu-id="6943d-180">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6943d-181">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="6943d-181">Related articles</span></span>

- [<span data-ttu-id="6943d-182">Microsoft 365 Introducción a las API de Defender</span><span class="sxs-lookup"><span data-stu-id="6943d-182">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="6943d-183">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="6943d-183">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="6943d-184">ENUMERAR LA API de incidentes</span><span class="sxs-lookup"><span data-stu-id="6943d-184">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="6943d-185">ACTUALIZAR API de incidentes</span><span class="sxs-lookup"><span data-stu-id="6943d-185">Update incident API</span></span>](api-update-incidents.md)
