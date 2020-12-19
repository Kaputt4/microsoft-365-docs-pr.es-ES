---
title: API de incidentes de Microsoft 365 defender y el tipo de recurso Incident
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
ms.openlocfilehash: 372c939f5eed29832725e6b048735040ca7391d6
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719339"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="14b41-104">API de incidentes de Microsoft 365 defender y el tipo de recurso Incident</span><span class="sxs-lookup"><span data-stu-id="14b41-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="14b41-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="14b41-105">**Applies to:**</span></span>

- <span data-ttu-id="14b41-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="14b41-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14b41-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="14b41-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="14b41-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="14b41-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="14b41-109">Un [incidente](incidents-overview.md) es una colección de alertas relacionadas que ayudan a describir un ataque.</span><span class="sxs-lookup"><span data-stu-id="14b41-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="14b41-110">Microsoft 365 defender agrega automáticamente eventos de diferentes entidades de la organización.</span><span class="sxs-lookup"><span data-stu-id="14b41-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="14b41-111">Puede usar la API de incidentes para acceder mediante programación a los incidentes de su organización y las alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="14b41-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="14b41-112">Cuotas y asignación de recursos</span><span class="sxs-lookup"><span data-stu-id="14b41-112">Quotas and resource allocation</span></span>

<span data-ttu-id="14b41-113">Puede solicitar hasta 50 llamadas por minuto o 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="14b41-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="14b41-114">Cada método también tiene sus propias cuotas.</span><span class="sxs-lookup"><span data-stu-id="14b41-114">Each method also has its own quotas.</span></span> <span data-ttu-id="14b41-115">Para obtener más información acerca de las cuotas específicas para métodos, vea el artículo correspondiente del método que desee usar.</span><span class="sxs-lookup"><span data-stu-id="14b41-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="14b41-116">Un `429` código de respuesta HTTP indica que ha alcanzado una cuota, ya sea por el número de solicitudes enviadas o por el tiempo de ejecución asignado.</span><span class="sxs-lookup"><span data-stu-id="14b41-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="14b41-117">El cuerpo de la respuesta incluirá el tiempo hasta que se restablezca la cuota que ha alcanzado.</span><span class="sxs-lookup"><span data-stu-id="14b41-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="14b41-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="14b41-118">Permissions</span></span>

<span data-ttu-id="14b41-119">La API de incidentes requiere tipos de permisos diferentes para cada uno de sus métodos.</span><span class="sxs-lookup"><span data-stu-id="14b41-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="14b41-120">Para obtener más información acerca de los permisos necesarios, vea el artículo correspondiente del método.</span><span class="sxs-lookup"><span data-stu-id="14b41-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="14b41-121">Métodos</span><span class="sxs-lookup"><span data-stu-id="14b41-121">Methods</span></span>

<span data-ttu-id="14b41-122">Método</span><span class="sxs-lookup"><span data-stu-id="14b41-122">Method</span></span> | <span data-ttu-id="14b41-123">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="14b41-123">Return Type</span></span> | <span data-ttu-id="14b41-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="14b41-124">Description</span></span>
-|-|-
[<span data-ttu-id="14b41-125">Lista de Incidentes</span><span class="sxs-lookup"><span data-stu-id="14b41-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="14b41-126">Lista de [incidentes](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="14b41-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="14b41-127">Obtener una lista de incidentes.</span><span class="sxs-lookup"><span data-stu-id="14b41-127">Get a list of incidents.</span></span>
[<span data-ttu-id="14b41-128">Incidente de actualización</span><span class="sxs-lookup"><span data-stu-id="14b41-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="14b41-129">Incidentes</span><span class="sxs-lookup"><span data-stu-id="14b41-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="14b41-130">Actualizar un incidente específico.</span><span class="sxs-lookup"><span data-stu-id="14b41-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="14b41-131">Cuerpo de la solicitud, respuesta y ejemplos</span><span class="sxs-lookup"><span data-stu-id="14b41-131">Request body, response, and examples</span></span>

<span data-ttu-id="14b41-132">Consulte los respectivos artículos del método para obtener más información sobre cómo construir una solicitud o analizar una respuesta, y para ver ejemplos prácticos.</span><span class="sxs-lookup"><span data-stu-id="14b41-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="14b41-133">Propiedades comunes</span><span class="sxs-lookup"><span data-stu-id="14b41-133">Common properties</span></span>

<span data-ttu-id="14b41-134">Propiedad</span><span class="sxs-lookup"><span data-stu-id="14b41-134">Property</span></span> | <span data-ttu-id="14b41-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="14b41-135">Type</span></span> | <span data-ttu-id="14b41-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="14b41-136">Description</span></span>
-|-|-
<span data-ttu-id="14b41-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="14b41-137">incidentId</span></span> | <span data-ttu-id="14b41-138">largo</span><span class="sxs-lookup"><span data-stu-id="14b41-138">long</span></span> | <span data-ttu-id="14b41-139">IDENTIFICADOR único de incidente.</span><span class="sxs-lookup"><span data-stu-id="14b41-139">Incident unique ID.</span></span>
<span data-ttu-id="14b41-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="14b41-140">redirectIncidentId</span></span> | <span data-ttu-id="14b41-141">Nullable Long</span><span class="sxs-lookup"><span data-stu-id="14b41-141">nullable long</span></span> | <span data-ttu-id="14b41-142">IDENTIFICADOR del incidente al que se combinó el incidente actual.</span><span class="sxs-lookup"><span data-stu-id="14b41-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="14b41-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="14b41-143">incidentName</span></span> | <span data-ttu-id="14b41-144">cadena</span><span class="sxs-lookup"><span data-stu-id="14b41-144">string</span></span> | <span data-ttu-id="14b41-145">Nombre del incidente.</span><span class="sxs-lookup"><span data-stu-id="14b41-145">The name of the Incident.</span></span>
<span data-ttu-id="14b41-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="14b41-146">createdTime</span></span> | <span data-ttu-id="14b41-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="14b41-147">DateTimeOffset</span></span> | <span data-ttu-id="14b41-148">La fecha y hora (en UTC) en que se creó el incidente.</span><span class="sxs-lookup"><span data-stu-id="14b41-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="14b41-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="14b41-149">lastUpdateTime</span></span> | <span data-ttu-id="14b41-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="14b41-150">DateTimeOffset</span></span> | <span data-ttu-id="14b41-151">La fecha y hora (en UTC) en que se actualizó por última vez el incidente.</span><span class="sxs-lookup"><span data-stu-id="14b41-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="14b41-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="14b41-152">assignedTo</span></span> | <span data-ttu-id="14b41-153">cadena</span><span class="sxs-lookup"><span data-stu-id="14b41-153">string</span></span> | <span data-ttu-id="14b41-154">Propietario del incidente.</span><span class="sxs-lookup"><span data-stu-id="14b41-154">Owner of the Incident.</span></span>
<span data-ttu-id="14b41-155">severity</span><span class="sxs-lookup"><span data-stu-id="14b41-155">severity</span></span> | <span data-ttu-id="14b41-156">Enum</span><span class="sxs-lookup"><span data-stu-id="14b41-156">Enum</span></span> | <span data-ttu-id="14b41-157">Gravedad del incidente.</span><span class="sxs-lookup"><span data-stu-id="14b41-157">Severity of the Incident.</span></span> <span data-ttu-id="14b41-158">Los valores posibles son: ```UnSpecified``` , ```Informational``` , ```Low``` , ```Medium``` y ```High``` .</span><span class="sxs-lookup"><span data-stu-id="14b41-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="14b41-159">status</span><span class="sxs-lookup"><span data-stu-id="14b41-159">status</span></span> | <span data-ttu-id="14b41-160">Enum</span><span class="sxs-lookup"><span data-stu-id="14b41-160">Enum</span></span> | <span data-ttu-id="14b41-161">Especifica el estado actual del incidente.</span><span class="sxs-lookup"><span data-stu-id="14b41-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="14b41-162">Los valores posibles son: ```Active``` , ```Resolved``` y ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="14b41-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="14b41-163">classification</span><span class="sxs-lookup"><span data-stu-id="14b41-163">classification</span></span> | <span data-ttu-id="14b41-164">Enum</span><span class="sxs-lookup"><span data-stu-id="14b41-164">Enum</span></span> | <span data-ttu-id="14b41-165">Especificación del incidente.</span><span class="sxs-lookup"><span data-stu-id="14b41-165">Specification of the incident.</span></span> <span data-ttu-id="14b41-166">Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="14b41-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="14b41-167">cálculo</span><span class="sxs-lookup"><span data-stu-id="14b41-167">determination</span></span> | <span data-ttu-id="14b41-168">Enum</span><span class="sxs-lookup"><span data-stu-id="14b41-168">Enum</span></span> | <span data-ttu-id="14b41-169">Especifica la determinación del incidente.</span><span class="sxs-lookup"><span data-stu-id="14b41-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="14b41-170">Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="14b41-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="14b41-171">tags</span><span class="sxs-lookup"><span data-stu-id="14b41-171">tags</span></span> | <span data-ttu-id="14b41-172">Lista de cadenas</span><span class="sxs-lookup"><span data-stu-id="14b41-172">string List</span></span> | <span data-ttu-id="14b41-173">Lista de etiquetas de incidente.</span><span class="sxs-lookup"><span data-stu-id="14b41-173">List of Incident tags.</span></span>
<span data-ttu-id="14b41-174">alerts</span><span class="sxs-lookup"><span data-stu-id="14b41-174">alerts</span></span> | <span data-ttu-id="14b41-175">Lista de alertas</span><span class="sxs-lookup"><span data-stu-id="14b41-175">Alert List</span></span> | <span data-ttu-id="14b41-176">Lista de alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="14b41-176">List of related alerts.</span></span> <span data-ttu-id="14b41-177">Consulte los ejemplos en la documentación de la API de [incidentes de lista](api-list-incidents.md) .</span><span class="sxs-lookup"><span data-stu-id="14b41-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="14b41-178">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="14b41-178">Related articles</span></span>

- [<span data-ttu-id="14b41-179">Información general sobre las API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="14b41-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="14b41-180">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="14b41-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="14b41-181">API de lista de incidentes</span><span class="sxs-lookup"><span data-stu-id="14b41-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="14b41-182">Actualizar la API de incidentes</span><span class="sxs-lookup"><span data-stu-id="14b41-182">Update incident API</span></span>](api-update-incidents.md)
