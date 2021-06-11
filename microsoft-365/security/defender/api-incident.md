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
ms.openlocfilehash: 0c0c2e280f63076687a0854e25c47577b050a8f7
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888438"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a><span data-ttu-id="e2d9a-104">Microsoft 365 API de incidentes de Defender y el tipo de recurso incidents</span><span class="sxs-lookup"><span data-stu-id="e2d9a-104">Microsoft 365 Defender incidents API and the incidents resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e2d9a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e2d9a-105">**Applies to:**</span></span>

- [<span data-ttu-id="e2d9a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e2d9a-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="e2d9a-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e2d9a-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="e2d9a-109">Un [incidente](incidents-overview.md) es una colección de alertas relacionadas que ayudan a describir un ataque.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="e2d9a-110">Los eventos de diferentes entidades de la organización se agregan automáticamente mediante Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="e2d9a-111">Puede usar la API de incidentes para acceder programativamente a los incidentes de su organización y a las alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="e2d9a-112">Cuotas y asignación de recursos</span><span class="sxs-lookup"><span data-stu-id="e2d9a-112">Quotas and resource allocation</span></span>

<span data-ttu-id="e2d9a-113">Puede solicitar hasta 50 llamadas por minuto o 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="e2d9a-114">Cada método también tiene sus propias cuotas.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-114">Each method also has its own quotas.</span></span> <span data-ttu-id="e2d9a-115">Para obtener más información sobre las cuotas específicas del método, vea el artículo correspondiente para el método que desea usar.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="e2d9a-116">Un código de respuesta HTTP indica que ha alcanzado una cuota, ya sea por número de solicitudes enviadas o por tiempo `429` de ejecución asignado.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="e2d9a-117">El cuerpo de la respuesta incluirá la hora hasta que se restablezca la cuota alcanzada.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="e2d9a-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="e2d9a-118">Permissions</span></span>

<span data-ttu-id="e2d9a-119">La API de incidentes requiere distintos tipos de permisos para cada uno de sus métodos.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="e2d9a-120">Para obtener más información acerca de los permisos necesarios, consulte el artículo del método respectivo.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="e2d9a-121">Métodos</span><span class="sxs-lookup"><span data-stu-id="e2d9a-121">Methods</span></span>

<span data-ttu-id="e2d9a-122">Método</span><span class="sxs-lookup"><span data-stu-id="e2d9a-122">Method</span></span> | <span data-ttu-id="e2d9a-123">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e2d9a-123">Return Type</span></span> | <span data-ttu-id="e2d9a-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2d9a-124">Description</span></span>
-|-|-
[<span data-ttu-id="e2d9a-125">Lista de Incidentes</span><span class="sxs-lookup"><span data-stu-id="e2d9a-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="e2d9a-126">[Lista de](api-incident.md) incidentes</span><span class="sxs-lookup"><span data-stu-id="e2d9a-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="e2d9a-127">Obtener una lista de incidentes.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-127">Get a list of incidents.</span></span>
[<span data-ttu-id="e2d9a-128">Incidente de actualización</span><span class="sxs-lookup"><span data-stu-id="e2d9a-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="e2d9a-129">Incidente</span><span class="sxs-lookup"><span data-stu-id="e2d9a-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="e2d9a-130">Actualice un incidente específico.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-130">Update a specific incident.</span></span>
[<span data-ttu-id="e2d9a-131">Obtener incidente</span><span class="sxs-lookup"><span data-stu-id="e2d9a-131">Get incident</span></span>](api-get-incident.md) | [<span data-ttu-id="e2d9a-132">Incidente</span><span class="sxs-lookup"><span data-stu-id="e2d9a-132">Incident</span></span>](api-incident.md) | <span data-ttu-id="e2d9a-133">Obtener un solo incidente.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-133">Get a single incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="e2d9a-134">Cuerpo de la solicitud, respuesta y ejemplos</span><span class="sxs-lookup"><span data-stu-id="e2d9a-134">Request body, response, and examples</span></span>

<span data-ttu-id="e2d9a-135">Consulte los artículos de método respectivos para obtener más información sobre cómo construir una solicitud o analizar una respuesta, y para obtener ejemplos prácticos.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-135">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="e2d9a-136">Propiedades comunes</span><span class="sxs-lookup"><span data-stu-id="e2d9a-136">Common properties</span></span>

<span data-ttu-id="e2d9a-137">Propiedad</span><span class="sxs-lookup"><span data-stu-id="e2d9a-137">Property</span></span> | <span data-ttu-id="e2d9a-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="e2d9a-138">Type</span></span> | <span data-ttu-id="e2d9a-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2d9a-139">Description</span></span>
-|-|-
<span data-ttu-id="e2d9a-140">incidentId</span><span class="sxs-lookup"><span data-stu-id="e2d9a-140">incidentId</span></span> | <span data-ttu-id="e2d9a-141">largo</span><span class="sxs-lookup"><span data-stu-id="e2d9a-141">long</span></span> | <span data-ttu-id="e2d9a-142">Identificador único de incidente.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-142">Incident unique ID.</span></span>
<span data-ttu-id="e2d9a-143">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="e2d9a-143">redirectIncidentId</span></span> | <span data-ttu-id="e2d9a-144">long nullable</span><span class="sxs-lookup"><span data-stu-id="e2d9a-144">nullable long</span></span> | <span data-ttu-id="e2d9a-145">El identificador de incidente con el que se ha combinado el incidente actual.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-145">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="e2d9a-146">incidentName</span><span class="sxs-lookup"><span data-stu-id="e2d9a-146">incidentName</span></span> | <span data-ttu-id="e2d9a-147">string</span><span class="sxs-lookup"><span data-stu-id="e2d9a-147">string</span></span> | <span data-ttu-id="e2d9a-148">Nombre del incidente.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-148">The name of the Incident.</span></span>
<span data-ttu-id="e2d9a-149">createdTime</span><span class="sxs-lookup"><span data-stu-id="e2d9a-149">createdTime</span></span> | <span data-ttu-id="e2d9a-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="e2d9a-150">DateTimeOffset</span></span> | <span data-ttu-id="e2d9a-151">La fecha y hora (en UTC) que se creó el incidente.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-151">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="e2d9a-152">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="e2d9a-152">lastUpdateTime</span></span> | <span data-ttu-id="e2d9a-153">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="e2d9a-153">DateTimeOffset</span></span> | <span data-ttu-id="e2d9a-154">La fecha y hora (en UTC) se actualizó por última vez el incidente.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-154">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="e2d9a-155">assignedTo</span><span class="sxs-lookup"><span data-stu-id="e2d9a-155">assignedTo</span></span> | <span data-ttu-id="e2d9a-156">string</span><span class="sxs-lookup"><span data-stu-id="e2d9a-156">string</span></span> | <span data-ttu-id="e2d9a-157">Propietario del incidente.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-157">Owner of the Incident.</span></span>
<span data-ttu-id="e2d9a-158">severity</span><span class="sxs-lookup"><span data-stu-id="e2d9a-158">severity</span></span> | <span data-ttu-id="e2d9a-159">Enum</span><span class="sxs-lookup"><span data-stu-id="e2d9a-159">Enum</span></span> | <span data-ttu-id="e2d9a-160">Gravedad del incidente.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-160">Severity of the Incident.</span></span> <span data-ttu-id="e2d9a-161">Los valores posibles son: ```UnSpecified``` , , , y ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="e2d9a-161">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="e2d9a-162">status</span><span class="sxs-lookup"><span data-stu-id="e2d9a-162">status</span></span> | <span data-ttu-id="e2d9a-163">Enum</span><span class="sxs-lookup"><span data-stu-id="e2d9a-163">Enum</span></span> | <span data-ttu-id="e2d9a-164">Especifica el estado actual del incidente.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-164">Specifies the current status of the incident.</span></span> <span data-ttu-id="e2d9a-165">Los valores posibles son: ```Active``` ```Resolved``` , y ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="e2d9a-165">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="e2d9a-166">classification</span><span class="sxs-lookup"><span data-stu-id="e2d9a-166">classification</span></span> | <span data-ttu-id="e2d9a-167">Enum</span><span class="sxs-lookup"><span data-stu-id="e2d9a-167">Enum</span></span> | <span data-ttu-id="e2d9a-168">Especificación del incidente.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-168">Specification of the incident.</span></span> <span data-ttu-id="e2d9a-169">Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-169">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="e2d9a-170">determinación</span><span class="sxs-lookup"><span data-stu-id="e2d9a-170">determination</span></span> | <span data-ttu-id="e2d9a-171">Enum</span><span class="sxs-lookup"><span data-stu-id="e2d9a-171">Enum</span></span> | <span data-ttu-id="e2d9a-172">Especifica la determinación del incidente.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-172">Specifies the determination of the incident.</span></span> <span data-ttu-id="e2d9a-173">Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-173">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="e2d9a-174">tags</span><span class="sxs-lookup"><span data-stu-id="e2d9a-174">tags</span></span> | <span data-ttu-id="e2d9a-175">lista de cadenas</span><span class="sxs-lookup"><span data-stu-id="e2d9a-175">string List</span></span> | <span data-ttu-id="e2d9a-176">Lista de etiquetas de incidentes.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-176">List of Incident tags.</span></span>
<span data-ttu-id="e2d9a-177">comments</span><span class="sxs-lookup"><span data-stu-id="e2d9a-177">comments</span></span> | <span data-ttu-id="e2d9a-178">Lista de comentarios de incidentes</span><span class="sxs-lookup"><span data-stu-id="e2d9a-178">List of incident comments</span></span> | <span data-ttu-id="e2d9a-179">El objeto Incident Comment contiene: cadena de comentario, createdBy string y createTime date time.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-179">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="e2d9a-180">alerts</span><span class="sxs-lookup"><span data-stu-id="e2d9a-180">alerts</span></span> | <span data-ttu-id="e2d9a-181">Lista de alertas</span><span class="sxs-lookup"><span data-stu-id="e2d9a-181">Alert List</span></span> | <span data-ttu-id="e2d9a-182">Lista de alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-182">List of related alerts.</span></span> <span data-ttu-id="e2d9a-183">Vea ejemplos en [Enumerar la documentación de](api-list-incidents.md) la API de incidentes.</span><span class="sxs-lookup"><span data-stu-id="e2d9a-183">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e2d9a-184">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="e2d9a-184">Related articles</span></span>

- [<span data-ttu-id="e2d9a-185">Microsoft 365 Introducción a las API de Defender</span><span class="sxs-lookup"><span data-stu-id="e2d9a-185">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="e2d9a-186">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="e2d9a-186">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e2d9a-187">ENUMERAR LA API de incidentes</span><span class="sxs-lookup"><span data-stu-id="e2d9a-187">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="e2d9a-188">ACTUALIZAR API de incidentes</span><span class="sxs-lookup"><span data-stu-id="e2d9a-188">Update incident API</span></span>](api-update-incidents.md)
