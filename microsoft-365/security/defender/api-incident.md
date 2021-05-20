---
title: Microsoft 365 API de incidentes de Defender y el tipo de recurso incident
description: Obtenga información sobre los métodos y propiedades del tipo de recurso Incident en Microsoft 365 Defender
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
ms.openlocfilehash: 5cc149668e49e21b38b5fb95ae3f40db6c296e1d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572590"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="17850-104">Microsoft 365 API de incidentes de Defender y el tipo de recurso incident</span><span class="sxs-lookup"><span data-stu-id="17850-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="17850-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="17850-105">**Applies to:**</span></span>

- <span data-ttu-id="17850-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="17850-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17850-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="17850-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="17850-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="17850-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="17850-109">Un [incidente](incidents-overview.md) es una colección de alertas relacionadas que ayudan a describir un ataque.</span><span class="sxs-lookup"><span data-stu-id="17850-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="17850-110">Los eventos de diferentes entidades de la organización se agregan automáticamente mediante Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="17850-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="17850-111">Puede usar la API de incidentes para acceder programativamente a los incidentes de su organización y a las alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="17850-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="17850-112">Cuotas y asignación de recursos</span><span class="sxs-lookup"><span data-stu-id="17850-112">Quotas and resource allocation</span></span>

<span data-ttu-id="17850-113">Puede solicitar hasta 50 llamadas por minuto o 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="17850-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="17850-114">Cada método también tiene sus propias cuotas.</span><span class="sxs-lookup"><span data-stu-id="17850-114">Each method also has its own quotas.</span></span> <span data-ttu-id="17850-115">Para obtener más información sobre las cuotas específicas del método, vea el artículo correspondiente para el método que desea usar.</span><span class="sxs-lookup"><span data-stu-id="17850-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="17850-116">Un código de respuesta HTTP indica que ha alcanzado una cuota, ya sea por número de solicitudes enviadas o por tiempo `429` de ejecución asignado.</span><span class="sxs-lookup"><span data-stu-id="17850-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="17850-117">El cuerpo de la respuesta incluirá la hora hasta que se restablezca la cuota alcanzada.</span><span class="sxs-lookup"><span data-stu-id="17850-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="17850-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="17850-118">Permissions</span></span>

<span data-ttu-id="17850-119">La API de incidentes requiere distintos tipos de permisos para cada uno de sus métodos.</span><span class="sxs-lookup"><span data-stu-id="17850-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="17850-120">Para obtener más información acerca de los permisos necesarios, consulte el artículo del método respectivo.</span><span class="sxs-lookup"><span data-stu-id="17850-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="17850-121">Methods</span><span class="sxs-lookup"><span data-stu-id="17850-121">Methods</span></span>

<span data-ttu-id="17850-122">Método</span><span class="sxs-lookup"><span data-stu-id="17850-122">Method</span></span> | <span data-ttu-id="17850-123">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="17850-123">Return Type</span></span> | <span data-ttu-id="17850-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="17850-124">Description</span></span>
-|-|-
[<span data-ttu-id="17850-125">Lista de Incidentes</span><span class="sxs-lookup"><span data-stu-id="17850-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="17850-126">[Lista de](api-incident.md) incidentes</span><span class="sxs-lookup"><span data-stu-id="17850-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="17850-127">Obtener una lista de incidentes.</span><span class="sxs-lookup"><span data-stu-id="17850-127">Get a list of incidents.</span></span>
[<span data-ttu-id="17850-128">Incidente de actualización</span><span class="sxs-lookup"><span data-stu-id="17850-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="17850-129">Incidente</span><span class="sxs-lookup"><span data-stu-id="17850-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="17850-130">Actualice un incidente específico.</span><span class="sxs-lookup"><span data-stu-id="17850-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="17850-131">Cuerpo de la solicitud, respuesta y ejemplos</span><span class="sxs-lookup"><span data-stu-id="17850-131">Request body, response, and examples</span></span>

<span data-ttu-id="17850-132">Consulte los artículos de método respectivos para obtener más información sobre cómo construir una solicitud o analizar una respuesta, y para obtener ejemplos prácticos.</span><span class="sxs-lookup"><span data-stu-id="17850-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="17850-133">Propiedades comunes</span><span class="sxs-lookup"><span data-stu-id="17850-133">Common properties</span></span>

<span data-ttu-id="17850-134">Propiedad</span><span class="sxs-lookup"><span data-stu-id="17850-134">Property</span></span> | <span data-ttu-id="17850-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="17850-135">Type</span></span> | <span data-ttu-id="17850-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="17850-136">Description</span></span>
-|-|-
<span data-ttu-id="17850-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="17850-137">incidentId</span></span> | <span data-ttu-id="17850-138">largo</span><span class="sxs-lookup"><span data-stu-id="17850-138">long</span></span> | <span data-ttu-id="17850-139">Identificador único de incidente.</span><span class="sxs-lookup"><span data-stu-id="17850-139">Incident unique ID.</span></span>
<span data-ttu-id="17850-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="17850-140">redirectIncidentId</span></span> | <span data-ttu-id="17850-141">long nullable</span><span class="sxs-lookup"><span data-stu-id="17850-141">nullable long</span></span> | <span data-ttu-id="17850-142">El identificador de incidente con el que se ha combinado el incidente actual.</span><span class="sxs-lookup"><span data-stu-id="17850-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="17850-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="17850-143">incidentName</span></span> | <span data-ttu-id="17850-144">string</span><span class="sxs-lookup"><span data-stu-id="17850-144">string</span></span> | <span data-ttu-id="17850-145">Nombre del incidente.</span><span class="sxs-lookup"><span data-stu-id="17850-145">The name of the Incident.</span></span>
<span data-ttu-id="17850-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="17850-146">createdTime</span></span> | <span data-ttu-id="17850-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="17850-147">DateTimeOffset</span></span> | <span data-ttu-id="17850-148">La fecha y hora (en UTC) que se creó el incidente.</span><span class="sxs-lookup"><span data-stu-id="17850-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="17850-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="17850-149">lastUpdateTime</span></span> | <span data-ttu-id="17850-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="17850-150">DateTimeOffset</span></span> | <span data-ttu-id="17850-151">La fecha y hora (en UTC) se actualizó por última vez el incidente.</span><span class="sxs-lookup"><span data-stu-id="17850-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="17850-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="17850-152">assignedTo</span></span> | <span data-ttu-id="17850-153">string</span><span class="sxs-lookup"><span data-stu-id="17850-153">string</span></span> | <span data-ttu-id="17850-154">Propietario del incidente.</span><span class="sxs-lookup"><span data-stu-id="17850-154">Owner of the Incident.</span></span>
<span data-ttu-id="17850-155">severity</span><span class="sxs-lookup"><span data-stu-id="17850-155">severity</span></span> | <span data-ttu-id="17850-156">Enum</span><span class="sxs-lookup"><span data-stu-id="17850-156">Enum</span></span> | <span data-ttu-id="17850-157">Gravedad del incidente.</span><span class="sxs-lookup"><span data-stu-id="17850-157">Severity of the Incident.</span></span> <span data-ttu-id="17850-158">Los valores posibles son: ```UnSpecified``` , , , y ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="17850-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="17850-159">status</span><span class="sxs-lookup"><span data-stu-id="17850-159">status</span></span> | <span data-ttu-id="17850-160">Enum</span><span class="sxs-lookup"><span data-stu-id="17850-160">Enum</span></span> | <span data-ttu-id="17850-161">Especifica el estado actual del incidente.</span><span class="sxs-lookup"><span data-stu-id="17850-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="17850-162">Los valores posibles son: ```Active``` ```Resolved``` , y ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="17850-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="17850-163">classification</span><span class="sxs-lookup"><span data-stu-id="17850-163">classification</span></span> | <span data-ttu-id="17850-164">Enum</span><span class="sxs-lookup"><span data-stu-id="17850-164">Enum</span></span> | <span data-ttu-id="17850-165">Especificación del incidente.</span><span class="sxs-lookup"><span data-stu-id="17850-165">Specification of the incident.</span></span> <span data-ttu-id="17850-166">Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="17850-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="17850-167">determinación</span><span class="sxs-lookup"><span data-stu-id="17850-167">determination</span></span> | <span data-ttu-id="17850-168">Enum</span><span class="sxs-lookup"><span data-stu-id="17850-168">Enum</span></span> | <span data-ttu-id="17850-169">Especifica la determinación del incidente.</span><span class="sxs-lookup"><span data-stu-id="17850-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="17850-170">Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="17850-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="17850-171">tags</span><span class="sxs-lookup"><span data-stu-id="17850-171">tags</span></span> | <span data-ttu-id="17850-172">lista de cadenas</span><span class="sxs-lookup"><span data-stu-id="17850-172">string List</span></span> | <span data-ttu-id="17850-173">Lista de etiquetas de incidentes.</span><span class="sxs-lookup"><span data-stu-id="17850-173">List of Incident tags.</span></span>
<span data-ttu-id="17850-174">comments</span><span class="sxs-lookup"><span data-stu-id="17850-174">comments</span></span> | <span data-ttu-id="17850-175">Lista de comentarios de incidentes</span><span class="sxs-lookup"><span data-stu-id="17850-175">List of incident comments</span></span> | <span data-ttu-id="17850-176">El objeto Incident Comment contiene: cadena de comentario, createdBy string y createTime date time.</span><span class="sxs-lookup"><span data-stu-id="17850-176">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="17850-177">alerts</span><span class="sxs-lookup"><span data-stu-id="17850-177">alerts</span></span> | <span data-ttu-id="17850-178">Lista de alertas</span><span class="sxs-lookup"><span data-stu-id="17850-178">Alert List</span></span> | <span data-ttu-id="17850-179">Lista de alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="17850-179">List of related alerts.</span></span> <span data-ttu-id="17850-180">Vea ejemplos en [Enumerar la documentación de](api-list-incidents.md) la API de incidentes.</span><span class="sxs-lookup"><span data-stu-id="17850-180">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="17850-181">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="17850-181">Related articles</span></span>

- [<span data-ttu-id="17850-182">Microsoft 365 Introducción a las API de Defender</span><span class="sxs-lookup"><span data-stu-id="17850-182">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="17850-183">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="17850-183">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="17850-184">ENUMERAR LA API de incidentes</span><span class="sxs-lookup"><span data-stu-id="17850-184">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="17850-185">ACTUALIZAR API de incidentes</span><span class="sxs-lookup"><span data-stu-id="17850-185">Update incident API</span></span>](api-update-incidents.md)
