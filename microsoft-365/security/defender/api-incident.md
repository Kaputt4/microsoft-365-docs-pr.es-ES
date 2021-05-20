---
title: Microsoft 365 Defender incidentes API y el tipo de recurso incidente
description: Obtenga información sobre los métodos y propiedades del tipo de recurso Incidente en Microsoft 365 Defender
keywords: incidentes, incidentes, api
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
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="fd636-104">Microsoft 365 Defender incidentes API y el tipo de recurso incidente</span><span class="sxs-lookup"><span data-stu-id="fd636-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="fd636-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="fd636-105">**Applies to:**</span></span>

- <span data-ttu-id="fd636-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd636-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd636-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="fd636-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="fd636-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="fd636-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="fd636-109">Un [incidente](incidents-overview.md) es una colección de alertas relacionadas que ayudan a describir un ataque.</span><span class="sxs-lookup"><span data-stu-id="fd636-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="fd636-110">Los eventos de diferentes entidades de la organización se agregan automáticamente por Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="fd636-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="fd636-111">Puede usar la API de incidentes para tener acceso mediante programación a los incidentes de su organización y a las alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="fd636-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="fd636-112">Cuotas y asignación de recursos</span><span class="sxs-lookup"><span data-stu-id="fd636-112">Quotas and resource allocation</span></span>

<span data-ttu-id="fd636-113">Puede solicitar hasta 50 llamadas por minuto o 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="fd636-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="fd636-114">Cada método también tiene sus propias cuotas.</span><span class="sxs-lookup"><span data-stu-id="fd636-114">Each method also has its own quotas.</span></span> <span data-ttu-id="fd636-115">Para obtener más información sobre las cuotas específicas del método, consulte el artículo correspondiente para el método que desea usar.</span><span class="sxs-lookup"><span data-stu-id="fd636-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="fd636-116">Un `429` código de respuesta HTTP indica que ha alcanzado una cuota, ya sea por número de solicitudes enviadas o por el tiempo de ejecución asignado.</span><span class="sxs-lookup"><span data-stu-id="fd636-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="fd636-117">El cuerpo de respuesta incluirá el tiempo hasta que se restablezca la cuota a la que llegó.</span><span class="sxs-lookup"><span data-stu-id="fd636-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="fd636-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="fd636-118">Permissions</span></span>

<span data-ttu-id="fd636-119">La API de incidentes requiere diferentes tipos de permisos para cada uno de sus métodos.</span><span class="sxs-lookup"><span data-stu-id="fd636-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="fd636-120">Para obtener más información acerca de los permisos necesarios, consulte el artículo del método respectivo.</span><span class="sxs-lookup"><span data-stu-id="fd636-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="fd636-121">Métodos</span><span class="sxs-lookup"><span data-stu-id="fd636-121">Methods</span></span>

<span data-ttu-id="fd636-122">Método</span><span class="sxs-lookup"><span data-stu-id="fd636-122">Method</span></span> | <span data-ttu-id="fd636-123">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fd636-123">Return Type</span></span> | <span data-ttu-id="fd636-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd636-124">Description</span></span>
-|-|-
[<span data-ttu-id="fd636-125">Lista de Incidentes</span><span class="sxs-lookup"><span data-stu-id="fd636-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="fd636-126">[Lista de incidentes](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="fd636-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="fd636-127">Obtenga una lista de incidentes.</span><span class="sxs-lookup"><span data-stu-id="fd636-127">Get a list of incidents.</span></span>
[<span data-ttu-id="fd636-128">Incidente de actualización</span><span class="sxs-lookup"><span data-stu-id="fd636-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="fd636-129">Incidente</span><span class="sxs-lookup"><span data-stu-id="fd636-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="fd636-130">Actualice un incidente específico.</span><span class="sxs-lookup"><span data-stu-id="fd636-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="fd636-131">Solicitar cuerpo, respuesta y ejemplos</span><span class="sxs-lookup"><span data-stu-id="fd636-131">Request body, response, and examples</span></span>

<span data-ttu-id="fd636-132">Consulte los artículos de método respectivos para obtener más detalles sobre cómo construir una solicitud o analizar una respuesta y ejemplos prácticos.</span><span class="sxs-lookup"><span data-stu-id="fd636-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="fd636-133">Propiedades comunes</span><span class="sxs-lookup"><span data-stu-id="fd636-133">Common properties</span></span>

<span data-ttu-id="fd636-134">Propiedad</span><span class="sxs-lookup"><span data-stu-id="fd636-134">Property</span></span> | <span data-ttu-id="fd636-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="fd636-135">Type</span></span> | <span data-ttu-id="fd636-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd636-136">Description</span></span>
-|-|-
<span data-ttu-id="fd636-137">incidenteId</span><span class="sxs-lookup"><span data-stu-id="fd636-137">incidentId</span></span> | <span data-ttu-id="fd636-138">largo</span><span class="sxs-lookup"><span data-stu-id="fd636-138">long</span></span> | <span data-ttu-id="fd636-139">Id. único del incidente.</span><span class="sxs-lookup"><span data-stu-id="fd636-139">Incident unique ID.</span></span>
<span data-ttu-id="fd636-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="fd636-140">redirectIncidentId</span></span> | <span data-ttu-id="fd636-141">nullable largo</span><span class="sxs-lookup"><span data-stu-id="fd636-141">nullable long</span></span> | <span data-ttu-id="fd636-142">El id. de incidente al que se fusionó el incidente actual.</span><span class="sxs-lookup"><span data-stu-id="fd636-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="fd636-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="fd636-143">incidentName</span></span> | <span data-ttu-id="fd636-144">cadena</span><span class="sxs-lookup"><span data-stu-id="fd636-144">string</span></span> | <span data-ttu-id="fd636-145">El nombre del incidente.</span><span class="sxs-lookup"><span data-stu-id="fd636-145">The name of the Incident.</span></span>
<span data-ttu-id="fd636-146">creóTime</span><span class="sxs-lookup"><span data-stu-id="fd636-146">createdTime</span></span> | <span data-ttu-id="fd636-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="fd636-147">DateTimeOffset</span></span> | <span data-ttu-id="fd636-148">La fecha y hora (en UTC) se creó el incidente.</span><span class="sxs-lookup"><span data-stu-id="fd636-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="fd636-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="fd636-149">lastUpdateTime</span></span> | <span data-ttu-id="fd636-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="fd636-150">DateTimeOffset</span></span> | <span data-ttu-id="fd636-151">La fecha y hora (en UTC) el incidente se actualizó por última vez.</span><span class="sxs-lookup"><span data-stu-id="fd636-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="fd636-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="fd636-152">assignedTo</span></span> | <span data-ttu-id="fd636-153">cadena</span><span class="sxs-lookup"><span data-stu-id="fd636-153">string</span></span> | <span data-ttu-id="fd636-154">Propietario del incidente.</span><span class="sxs-lookup"><span data-stu-id="fd636-154">Owner of the Incident.</span></span>
<span data-ttu-id="fd636-155">severity</span><span class="sxs-lookup"><span data-stu-id="fd636-155">severity</span></span> | <span data-ttu-id="fd636-156">Enum</span><span class="sxs-lookup"><span data-stu-id="fd636-156">Enum</span></span> | <span data-ttu-id="fd636-157">Gravedad del incidente.</span><span class="sxs-lookup"><span data-stu-id="fd636-157">Severity of the Incident.</span></span> <span data-ttu-id="fd636-158">Los valores posibles son: ```UnSpecified``` , , , y ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="fd636-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="fd636-159">status</span><span class="sxs-lookup"><span data-stu-id="fd636-159">status</span></span> | <span data-ttu-id="fd636-160">Enum</span><span class="sxs-lookup"><span data-stu-id="fd636-160">Enum</span></span> | <span data-ttu-id="fd636-161">Especifica el estado actual del incidente.</span><span class="sxs-lookup"><span data-stu-id="fd636-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="fd636-162">Los valores posibles son: ```Active``` ```Resolved``` , y ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="fd636-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="fd636-163">classification</span><span class="sxs-lookup"><span data-stu-id="fd636-163">classification</span></span> | <span data-ttu-id="fd636-164">Enum</span><span class="sxs-lookup"><span data-stu-id="fd636-164">Enum</span></span> | <span data-ttu-id="fd636-165">Especificación del incidente.</span><span class="sxs-lookup"><span data-stu-id="fd636-165">Specification of the incident.</span></span> <span data-ttu-id="fd636-166">Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="fd636-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="fd636-167">determinación</span><span class="sxs-lookup"><span data-stu-id="fd636-167">determination</span></span> | <span data-ttu-id="fd636-168">Enum</span><span class="sxs-lookup"><span data-stu-id="fd636-168">Enum</span></span> | <span data-ttu-id="fd636-169">Especifica la determinación del incidente.</span><span class="sxs-lookup"><span data-stu-id="fd636-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="fd636-170">Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="fd636-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="fd636-171">tags</span><span class="sxs-lookup"><span data-stu-id="fd636-171">tags</span></span> | <span data-ttu-id="fd636-172">Lista de cuerdas</span><span class="sxs-lookup"><span data-stu-id="fd636-172">string List</span></span> | <span data-ttu-id="fd636-173">Lista de etiquetas incidente.</span><span class="sxs-lookup"><span data-stu-id="fd636-173">List of Incident tags.</span></span>
<span data-ttu-id="fd636-174">comments</span><span class="sxs-lookup"><span data-stu-id="fd636-174">comments</span></span> | <span data-ttu-id="fd636-175">Lista de comentarios de incidentes</span><span class="sxs-lookup"><span data-stu-id="fd636-175">List of incident comments</span></span> | <span data-ttu-id="fd636-176">El objeto Comment de incidente contiene: cadena de comentario, cadena createdBy y hora de fecha createTime.</span><span class="sxs-lookup"><span data-stu-id="fd636-176">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="fd636-177">alerts</span><span class="sxs-lookup"><span data-stu-id="fd636-177">alerts</span></span> | <span data-ttu-id="fd636-178">Lista de alertas</span><span class="sxs-lookup"><span data-stu-id="fd636-178">Alert List</span></span> | <span data-ttu-id="fd636-179">Lista de alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="fd636-179">List of related alerts.</span></span> <span data-ttu-id="fd636-180">Consulte ejemplos en La documentación de la API [De incidentes](api-list-incidents.md) de lista.</span><span class="sxs-lookup"><span data-stu-id="fd636-180">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="fd636-181">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="fd636-181">Related articles</span></span>

- [<span data-ttu-id="fd636-182">Microsoft 365 Descripción general de las API de Defender</span><span class="sxs-lookup"><span data-stu-id="fd636-182">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="fd636-183">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="fd636-183">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="fd636-184">Enumerar incidentes API</span><span class="sxs-lookup"><span data-stu-id="fd636-184">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="fd636-185">Actualizar api incidentes</span><span class="sxs-lookup"><span data-stu-id="fd636-185">Update incident API</span></span>](api-update-incidents.md)
