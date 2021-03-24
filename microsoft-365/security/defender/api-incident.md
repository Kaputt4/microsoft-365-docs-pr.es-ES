---
title: API de incidentes de Microsoft 365 Defender y el tipo de recurso incident
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
ms.openlocfilehash: 0a9022c0448ae0ddc16dc996ca93075abf6b2857
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068984"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="2127f-104">API de incidentes de Microsoft 365 Defender y el tipo de recurso incident</span><span class="sxs-lookup"><span data-stu-id="2127f-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2127f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2127f-105">**Applies to:**</span></span>

- <span data-ttu-id="2127f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2127f-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2127f-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="2127f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2127f-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="2127f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="2127f-109">Un [incidente](incidents-overview.md) es una colección de alertas relacionadas que ayudan a describir un ataque.</span><span class="sxs-lookup"><span data-stu-id="2127f-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="2127f-110">Microsoft 365 Defender agrega automáticamente eventos de distintas entidades de la organización.</span><span class="sxs-lookup"><span data-stu-id="2127f-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="2127f-111">Puede usar la API de incidentes para acceder programativamente a los incidentes de su organización y a las alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="2127f-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="2127f-112">Cuotas y asignación de recursos</span><span class="sxs-lookup"><span data-stu-id="2127f-112">Quotas and resource allocation</span></span>

<span data-ttu-id="2127f-113">Puede solicitar hasta 50 llamadas por minuto o 1500 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="2127f-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="2127f-114">Cada método también tiene sus propias cuotas.</span><span class="sxs-lookup"><span data-stu-id="2127f-114">Each method also has its own quotas.</span></span> <span data-ttu-id="2127f-115">Para obtener más información sobre las cuotas específicas del método, vea el artículo correspondiente para el método que desea usar.</span><span class="sxs-lookup"><span data-stu-id="2127f-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="2127f-116">Un código de respuesta HTTP indica que ha alcanzado una cuota, ya sea por número de solicitudes enviadas o por tiempo `429` de ejecución asignado.</span><span class="sxs-lookup"><span data-stu-id="2127f-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="2127f-117">El cuerpo de la respuesta incluirá la hora hasta que se restablezca la cuota alcanzada.</span><span class="sxs-lookup"><span data-stu-id="2127f-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="2127f-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="2127f-118">Permissions</span></span>

<span data-ttu-id="2127f-119">La API de incidentes requiere distintos tipos de permisos para cada uno de sus métodos.</span><span class="sxs-lookup"><span data-stu-id="2127f-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="2127f-120">Para obtener más información acerca de los permisos necesarios, consulte el artículo del método respectivo.</span><span class="sxs-lookup"><span data-stu-id="2127f-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="2127f-121">Methods</span><span class="sxs-lookup"><span data-stu-id="2127f-121">Methods</span></span>

<span data-ttu-id="2127f-122">Método</span><span class="sxs-lookup"><span data-stu-id="2127f-122">Method</span></span> | <span data-ttu-id="2127f-123">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2127f-123">Return Type</span></span> | <span data-ttu-id="2127f-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="2127f-124">Description</span></span>
-|-|-
[<span data-ttu-id="2127f-125">Lista de Incidentes</span><span class="sxs-lookup"><span data-stu-id="2127f-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="2127f-126">[Lista de](api-incident.md) incidentes</span><span class="sxs-lookup"><span data-stu-id="2127f-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="2127f-127">Obtener una lista de incidentes.</span><span class="sxs-lookup"><span data-stu-id="2127f-127">Get a list of incidents.</span></span>
[<span data-ttu-id="2127f-128">Incidente de actualización</span><span class="sxs-lookup"><span data-stu-id="2127f-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="2127f-129">Incidente</span><span class="sxs-lookup"><span data-stu-id="2127f-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="2127f-130">Actualice un incidente específico.</span><span class="sxs-lookup"><span data-stu-id="2127f-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="2127f-131">Cuerpo de la solicitud, respuesta y ejemplos</span><span class="sxs-lookup"><span data-stu-id="2127f-131">Request body, response, and examples</span></span>

<span data-ttu-id="2127f-132">Consulte los artículos de método respectivos para obtener más información sobre cómo construir una solicitud o analizar una respuesta, y para obtener ejemplos prácticos.</span><span class="sxs-lookup"><span data-stu-id="2127f-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="2127f-133">Propiedades comunes</span><span class="sxs-lookup"><span data-stu-id="2127f-133">Common properties</span></span>

<span data-ttu-id="2127f-134">Propiedad</span><span class="sxs-lookup"><span data-stu-id="2127f-134">Property</span></span> | <span data-ttu-id="2127f-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="2127f-135">Type</span></span> | <span data-ttu-id="2127f-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="2127f-136">Description</span></span>
-|-|-
<span data-ttu-id="2127f-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="2127f-137">incidentId</span></span> | <span data-ttu-id="2127f-138">largo</span><span class="sxs-lookup"><span data-stu-id="2127f-138">long</span></span> | <span data-ttu-id="2127f-139">Identificador único de incidente.</span><span class="sxs-lookup"><span data-stu-id="2127f-139">Incident unique ID.</span></span>
<span data-ttu-id="2127f-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="2127f-140">redirectIncidentId</span></span> | <span data-ttu-id="2127f-141">long nullable</span><span class="sxs-lookup"><span data-stu-id="2127f-141">nullable long</span></span> | <span data-ttu-id="2127f-142">El identificador de incidente con el que se ha combinado el incidente actual.</span><span class="sxs-lookup"><span data-stu-id="2127f-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="2127f-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="2127f-143">incidentName</span></span> | <span data-ttu-id="2127f-144">string</span><span class="sxs-lookup"><span data-stu-id="2127f-144">string</span></span> | <span data-ttu-id="2127f-145">Nombre del incidente.</span><span class="sxs-lookup"><span data-stu-id="2127f-145">The name of the Incident.</span></span>
<span data-ttu-id="2127f-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="2127f-146">createdTime</span></span> | <span data-ttu-id="2127f-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="2127f-147">DateTimeOffset</span></span> | <span data-ttu-id="2127f-148">La fecha y hora (en UTC) que se creó el incidente.</span><span class="sxs-lookup"><span data-stu-id="2127f-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="2127f-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="2127f-149">lastUpdateTime</span></span> | <span data-ttu-id="2127f-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="2127f-150">DateTimeOffset</span></span> | <span data-ttu-id="2127f-151">La fecha y hora (en UTC) se actualizó por última vez el incidente.</span><span class="sxs-lookup"><span data-stu-id="2127f-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="2127f-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="2127f-152">assignedTo</span></span> | <span data-ttu-id="2127f-153">string</span><span class="sxs-lookup"><span data-stu-id="2127f-153">string</span></span> | <span data-ttu-id="2127f-154">Propietario del incidente.</span><span class="sxs-lookup"><span data-stu-id="2127f-154">Owner of the Incident.</span></span>
<span data-ttu-id="2127f-155">severity</span><span class="sxs-lookup"><span data-stu-id="2127f-155">severity</span></span> | <span data-ttu-id="2127f-156">Enum</span><span class="sxs-lookup"><span data-stu-id="2127f-156">Enum</span></span> | <span data-ttu-id="2127f-157">Gravedad del incidente.</span><span class="sxs-lookup"><span data-stu-id="2127f-157">Severity of the Incident.</span></span> <span data-ttu-id="2127f-158">Los valores posibles son: ```UnSpecified``` , , , y ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="2127f-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="2127f-159">status</span><span class="sxs-lookup"><span data-stu-id="2127f-159">status</span></span> | <span data-ttu-id="2127f-160">Enum</span><span class="sxs-lookup"><span data-stu-id="2127f-160">Enum</span></span> | <span data-ttu-id="2127f-161">Especifica el estado actual del incidente.</span><span class="sxs-lookup"><span data-stu-id="2127f-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="2127f-162">Los valores posibles son: ```Active``` ```Resolved``` , y ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="2127f-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="2127f-163">classification</span><span class="sxs-lookup"><span data-stu-id="2127f-163">classification</span></span> | <span data-ttu-id="2127f-164">Enum</span><span class="sxs-lookup"><span data-stu-id="2127f-164">Enum</span></span> | <span data-ttu-id="2127f-165">Especificación del incidente.</span><span class="sxs-lookup"><span data-stu-id="2127f-165">Specification of the incident.</span></span> <span data-ttu-id="2127f-166">Los valores posibles son: ```Unknown```, ```FalsePositive``` y ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="2127f-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="2127f-167">determinación</span><span class="sxs-lookup"><span data-stu-id="2127f-167">determination</span></span> | <span data-ttu-id="2127f-168">Enum</span><span class="sxs-lookup"><span data-stu-id="2127f-168">Enum</span></span> | <span data-ttu-id="2127f-169">Especifica la determinación del incidente.</span><span class="sxs-lookup"><span data-stu-id="2127f-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="2127f-170">Valores posibles: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="2127f-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="2127f-171">tags</span><span class="sxs-lookup"><span data-stu-id="2127f-171">tags</span></span> | <span data-ttu-id="2127f-172">lista de cadenas</span><span class="sxs-lookup"><span data-stu-id="2127f-172">string List</span></span> | <span data-ttu-id="2127f-173">Lista de etiquetas de incidentes.</span><span class="sxs-lookup"><span data-stu-id="2127f-173">List of Incident tags.</span></span>
<span data-ttu-id="2127f-174">alerts</span><span class="sxs-lookup"><span data-stu-id="2127f-174">alerts</span></span> | <span data-ttu-id="2127f-175">Lista de alertas</span><span class="sxs-lookup"><span data-stu-id="2127f-175">Alert List</span></span> | <span data-ttu-id="2127f-176">Lista de alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="2127f-176">List of related alerts.</span></span> <span data-ttu-id="2127f-177">Vea ejemplos en [Enumerar la documentación de](api-list-incidents.md) la API de incidentes.</span><span class="sxs-lookup"><span data-stu-id="2127f-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="2127f-178">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="2127f-178">Related articles</span></span>

- [<span data-ttu-id="2127f-179">Introducción a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2127f-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="2127f-180">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="2127f-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="2127f-181">ENUMERAR LA API de incidentes</span><span class="sxs-lookup"><span data-stu-id="2127f-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="2127f-182">ACTUALIZAR API de incidentes</span><span class="sxs-lookup"><span data-stu-id="2127f-182">Update incident API</span></span>](api-update-incidents.md)
