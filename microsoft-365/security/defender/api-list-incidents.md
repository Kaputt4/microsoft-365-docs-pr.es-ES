---
title: Enumerar la API de incidentes en Microsoft 365 Defender
description: Obtenga información sobre cómo enumerar la API de incidentes en Microsoft 365 Defender
keywords: lista, incidente, incidentes, api
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
ms.openlocfilehash: 6f0c92371e7e9b7a3348f90df788ee8c3a46374b
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572158"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="d32f9-104">Enumerar la API de incidentes en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d32f9-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d32f9-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d32f9-105">**Applies to:**</span></span>

- <span data-ttu-id="d32f9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d32f9-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d32f9-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="d32f9-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d32f9-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="d32f9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="d32f9-109">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="d32f9-109">API description</span></span>

<span data-ttu-id="d32f9-110">La API de incidentes de lista le permite ordenar los incidentes para crear una respuesta de ciberseguridad informada.</span><span class="sxs-lookup"><span data-stu-id="d32f9-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="d32f9-111">Expone una colección de incidentes marcados en la red, dentro del intervalo de tiempo especificado en la directiva de retención del entorno.</span><span class="sxs-lookup"><span data-stu-id="d32f9-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="d32f9-112">Los incidentes más recientes se muestran en la parte superior de la lista.</span><span class="sxs-lookup"><span data-stu-id="d32f9-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="d32f9-113">Cada incidente contiene una matriz de alertas relacionadas y sus entidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="d32f9-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="d32f9-114">La API admite los siguientes operadores **OData:**</span><span class="sxs-lookup"><span data-stu-id="d32f9-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="d32f9-115">`$filter`en `lastUpdateTime` las `createdTime` propiedades , , `status` y `assignedTo`</span><span class="sxs-lookup"><span data-stu-id="d32f9-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="d32f9-116">`$top`, con un valor máximo de **100**</span><span class="sxs-lookup"><span data-stu-id="d32f9-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="d32f9-117">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="d32f9-117">Limitations</span></span>

1. <span data-ttu-id="d32f9-118">El tamaño máximo de página **es de 100 incidentes.**</span><span class="sxs-lookup"><span data-stu-id="d32f9-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="d32f9-119">La tasa máxima de solicitudes es **de 50 llamadas por minuto** y **1500 llamadas por hora.**</span><span class="sxs-lookup"><span data-stu-id="d32f9-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="d32f9-120">Permisos</span><span class="sxs-lookup"><span data-stu-id="d32f9-120">Permissions</span></span>

<span data-ttu-id="d32f9-121">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="d32f9-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d32f9-122">Para obtener más información, incluido cómo elegir permisos, vea [Access Microsoft 365 Defender API](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="d32f9-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="d32f9-123">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="d32f9-123">Permission type</span></span> | <span data-ttu-id="d32f9-124">Permiso</span><span class="sxs-lookup"><span data-stu-id="d32f9-124">Permission</span></span> | <span data-ttu-id="d32f9-125">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="d32f9-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="d32f9-126">Aplicación</span><span class="sxs-lookup"><span data-stu-id="d32f9-126">Application</span></span> | <span data-ttu-id="d32f9-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="d32f9-127">Incident.Read.All</span></span> | <span data-ttu-id="d32f9-128">Leer todos los incidentes</span><span class="sxs-lookup"><span data-stu-id="d32f9-128">Read all incidents</span></span>
<span data-ttu-id="d32f9-129">Aplicación</span><span class="sxs-lookup"><span data-stu-id="d32f9-129">Application</span></span> | <span data-ttu-id="d32f9-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="d32f9-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="d32f9-131">Leer y escribir todos los incidentes</span><span class="sxs-lookup"><span data-stu-id="d32f9-131">Read and write all incidents</span></span>
<span data-ttu-id="d32f9-132">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="d32f9-132">Delegated (work or school account)</span></span> | <span data-ttu-id="d32f9-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="d32f9-133">Incident.Read</span></span> | <span data-ttu-id="d32f9-134">Leer incidentes</span><span class="sxs-lookup"><span data-stu-id="d32f9-134">Read incidents</span></span>
<span data-ttu-id="d32f9-135">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="d32f9-135">Delegated (work or school account)</span></span> | <span data-ttu-id="d32f9-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d32f9-136">Incident.ReadWrite</span></span> | <span data-ttu-id="d32f9-137">Incidentes de lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="d32f9-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="d32f9-138">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="d32f9-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="d32f9-139">El usuario debe tener permiso de vista para incidentes en el portal.</span><span class="sxs-lookup"><span data-stu-id="d32f9-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="d32f9-140">La respuesta solo incluirá incidentes a los que se expone el usuario.</span><span class="sxs-lookup"><span data-stu-id="d32f9-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="d32f9-141">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="d32f9-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="d32f9-142">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="d32f9-142">Request headers</span></span>

<span data-ttu-id="d32f9-143">Nombre</span><span class="sxs-lookup"><span data-stu-id="d32f9-143">Name</span></span> | <span data-ttu-id="d32f9-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="d32f9-144">Type</span></span> | <span data-ttu-id="d32f9-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="d32f9-145">Description</span></span>
-|-|-
<span data-ttu-id="d32f9-146">Authorization</span><span class="sxs-lookup"><span data-stu-id="d32f9-146">Authorization</span></span> | <span data-ttu-id="d32f9-147">Cadena</span><span class="sxs-lookup"><span data-stu-id="d32f9-147">String</span></span> | <span data-ttu-id="d32f9-148">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="d32f9-148">Bearer {token}.</span></span> <span data-ttu-id="d32f9-149">**Required**</span><span class="sxs-lookup"><span data-stu-id="d32f9-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="d32f9-150">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="d32f9-150">Request body</span></span>

<span data-ttu-id="d32f9-151">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="d32f9-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="d32f9-152">Respuesta</span><span class="sxs-lookup"><span data-stu-id="d32f9-152">Response</span></span>

<span data-ttu-id="d32f9-153">Si se realiza correctamente, este método `200 OK` devuelve y una lista de incidentes [en](api-incident.md) el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="d32f9-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="d32f9-154">Asignación de esquema</span><span class="sxs-lookup"><span data-stu-id="d32f9-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="d32f9-155">Metadatos de incidentes</span><span class="sxs-lookup"><span data-stu-id="d32f9-155">Incident metadata</span></span>

<span data-ttu-id="d32f9-156">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="d32f9-156">Field name</span></span> | <span data-ttu-id="d32f9-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="d32f9-157">Description</span></span> | <span data-ttu-id="d32f9-158">Valor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d32f9-158">Example value</span></span>
-|-|-
<span data-ttu-id="d32f9-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="d32f9-159">incidentId</span></span> | <span data-ttu-id="d32f9-160">Identificador único para representar el incidente</span><span class="sxs-lookup"><span data-stu-id="d32f9-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="d32f9-161">924565</span><span class="sxs-lookup"><span data-stu-id="d32f9-161">924565</span></span>
<span data-ttu-id="d32f9-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="d32f9-162">redirectIncidentId</span></span> | <span data-ttu-id="d32f9-163">Solo se rellena en caso de que un incidente se esté agrupando con otro incidente, como parte de la lógica de procesamiento de incidentes.</span><span class="sxs-lookup"><span data-stu-id="d32f9-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="d32f9-164">924569</span><span class="sxs-lookup"><span data-stu-id="d32f9-164">924569</span></span>
<span data-ttu-id="d32f9-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="d32f9-165">incidentName</span></span> | <span data-ttu-id="d32f9-166">Valor de cadena disponible para cada incidente.</span><span class="sxs-lookup"><span data-stu-id="d32f9-166">String value available for every incident.</span></span> | <span data-ttu-id="d32f9-167">Actividad de ransomware</span><span class="sxs-lookup"><span data-stu-id="d32f9-167">Ransomware activity</span></span>
<span data-ttu-id="d32f9-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="d32f9-168">createdTime</span></span> | <span data-ttu-id="d32f9-169">Hora en la que se creó el incidente por primera vez.</span><span class="sxs-lookup"><span data-stu-id="d32f9-169">Time when incident was first created.</span></span> | <span data-ttu-id="d32f9-170">2020-09-06T14:46:57.073333Z</span><span class="sxs-lookup"><span data-stu-id="d32f9-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="d32f9-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="d32f9-171">lastUpdateTime</span></span> | <span data-ttu-id="d32f9-172">Hora en la que el incidente se actualizó por última vez en el back-end.</span><span class="sxs-lookup"><span data-stu-id="d32f9-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="d32f9-173">Este campo se puede usar al establecer el parámetro de solicitud para el intervalo de tiempo que se recuperan los incidentes.</span><span class="sxs-lookup"><span data-stu-id="d32f9-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="d32f9-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="d32f9-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="d32f9-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="d32f9-175">assignedTo</span></span> | <span data-ttu-id="d32f9-176">Propietario del incidente o *null* si no se asigna ningún propietario.</span><span class="sxs-lookup"><span data-stu-id="d32f9-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="d32f9-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d32f9-177">secop2@contoso.com</span></span>
<span data-ttu-id="d32f9-178">classification</span><span class="sxs-lookup"><span data-stu-id="d32f9-178">classification</span></span> | <span data-ttu-id="d32f9-179">La especificación del incidente.</span><span class="sxs-lookup"><span data-stu-id="d32f9-179">The specification for the incident.</span></span> <span data-ttu-id="d32f9-180">Los valores de propiedad son: *Unknown*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="d32f9-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="d32f9-181">Unknown</span><span class="sxs-lookup"><span data-stu-id="d32f9-181">Unknown</span></span>
<span data-ttu-id="d32f9-182">determinación</span><span class="sxs-lookup"><span data-stu-id="d32f9-182">determination</span></span> | <span data-ttu-id="d32f9-183">Especifica la determinación del incidente.</span><span class="sxs-lookup"><span data-stu-id="d32f9-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="d32f9-184">Los valores de propiedad son: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span><span class="sxs-lookup"><span data-stu-id="d32f9-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="d32f9-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="d32f9-185">NotAvailable</span></span>
<span data-ttu-id="d32f9-186">status</span><span class="sxs-lookup"><span data-stu-id="d32f9-186">status</span></span> | <span data-ttu-id="d32f9-187">Clasifice los incidentes *(como Activos* o *Resueltos).*</span><span class="sxs-lookup"><span data-stu-id="d32f9-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="d32f9-188">Puede ayudarle a organizar y administrar su respuesta a incidentes.</span><span class="sxs-lookup"><span data-stu-id="d32f9-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="d32f9-189">Activa</span><span class="sxs-lookup"><span data-stu-id="d32f9-189">Active</span></span>
<span data-ttu-id="d32f9-190">severity</span><span class="sxs-lookup"><span data-stu-id="d32f9-190">severity</span></span> | <span data-ttu-id="d32f9-191">Indica el posible impacto en los activos.</span><span class="sxs-lookup"><span data-stu-id="d32f9-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="d32f9-192">Cuanto mayor sea la gravedad, mayor será el impacto.</span><span class="sxs-lookup"><span data-stu-id="d32f9-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="d32f9-193">Normalmente, los elementos de mayor gravedad requieren la atención más inmediata.</span><span class="sxs-lookup"><span data-stu-id="d32f9-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="d32f9-194">Uno de los siguientes valores: *Informational*, *Low*, \*Medium y *High*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="d32f9-195">Medio</span><span class="sxs-lookup"><span data-stu-id="d32f9-195">Medium</span></span>
<span data-ttu-id="d32f9-196">tags</span><span class="sxs-lookup"><span data-stu-id="d32f9-196">tags</span></span> | <span data-ttu-id="d32f9-197">Matriz de etiquetas personalizadas asociadas a un incidente, por ejemplo para marcar un grupo de incidentes con una característica común.</span><span class="sxs-lookup"><span data-stu-id="d32f9-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="d32f9-198">comments</span><span class="sxs-lookup"><span data-stu-id="d32f9-198">comments</span></span> | <span data-ttu-id="d32f9-199">Matriz de comentarios creados por secops al administrar el incidente, por ejemplo información adicional sobre la selección de clasificación.</span><span class="sxs-lookup"><span data-stu-id="d32f9-199">Array of comments created by secops when managing the incident, for example additional information about the classification selection.</span></span> | \[\]
<span data-ttu-id="d32f9-200">alerts</span><span class="sxs-lookup"><span data-stu-id="d32f9-200">alerts</span></span> | <span data-ttu-id="d32f9-201">Matriz que contiene todas las alertas relacionadas con el incidente, además de otra información, como la gravedad, las entidades que participaron en la alerta y el origen de las alertas.</span><span class="sxs-lookup"><span data-stu-id="d32f9-201">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="d32f9-202">\[\] (vea los detalles de los campos de alerta a continuación)</span><span class="sxs-lookup"><span data-stu-id="d32f9-202">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="d32f9-203">Metadatos de alertas</span><span class="sxs-lookup"><span data-stu-id="d32f9-203">Alerts metadata</span></span>

<span data-ttu-id="d32f9-204">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="d32f9-204">Field name</span></span> | <span data-ttu-id="d32f9-205">Descripción</span><span class="sxs-lookup"><span data-stu-id="d32f9-205">Description</span></span> | <span data-ttu-id="d32f9-206">Valor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d32f9-206">Example value</span></span>
-|-|-
<span data-ttu-id="d32f9-207">alertId</span><span class="sxs-lookup"><span data-stu-id="d32f9-207">alertId</span></span> | <span data-ttu-id="d32f9-208">Identificador único para representar la alerta</span><span class="sxs-lookup"><span data-stu-id="d32f9-208">Unique identifier to represent the alert</span></span> | <span data-ttu-id="d32f9-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="d32f9-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="d32f9-210">incidentId</span><span class="sxs-lookup"><span data-stu-id="d32f9-210">incidentId</span></span> | <span data-ttu-id="d32f9-211">Identificador único para representar el incidente al que está asociada esta alerta</span><span class="sxs-lookup"><span data-stu-id="d32f9-211">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="d32f9-212">924565</span><span class="sxs-lookup"><span data-stu-id="d32f9-212">924565</span></span>
<span data-ttu-id="d32f9-213">serviceSource</span><span class="sxs-lookup"><span data-stu-id="d32f9-213">serviceSource</span></span> | <span data-ttu-id="d32f9-214">Servicio del que procede la alerta, como Microsoft Defender para endpoint, Microsoft Cloud App Security, Microsoft Defender para Identity o Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="d32f9-214">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="d32f9-215">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="d32f9-215">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="d32f9-216">creationTime</span><span class="sxs-lookup"><span data-stu-id="d32f9-216">creationTime</span></span> | <span data-ttu-id="d32f9-217">Hora en la que se creó la alerta por primera vez.</span><span class="sxs-lookup"><span data-stu-id="d32f9-217">Time when alert was first created.</span></span> | <span data-ttu-id="d32f9-218">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="d32f9-218">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="d32f9-219">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="d32f9-219">lastUpdatedTime</span></span> | <span data-ttu-id="d32f9-220">Hora en la que se actualizó la alerta por última vez en el back-end.</span><span class="sxs-lookup"><span data-stu-id="d32f9-220">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="d32f9-221">2020-09-06T14:46:57.243333Z</span><span class="sxs-lookup"><span data-stu-id="d32f9-221">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="d32f9-222">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="d32f9-222">resolvedTime</span></span> | <span data-ttu-id="d32f9-223">Hora en la que se resolvió la alerta.</span><span class="sxs-lookup"><span data-stu-id="d32f9-223">Time when alert was resolved.</span></span> | <span data-ttu-id="d32f9-224">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="d32f9-224">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="d32f9-225">firstActivity</span><span class="sxs-lookup"><span data-stu-id="d32f9-225">firstActivity</span></span> | <span data-ttu-id="d32f9-226">Hora en la que la alerta informó por primera vez de que la actividad se actualizó en el back-end.</span><span class="sxs-lookup"><span data-stu-id="d32f9-226">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="d32f9-227">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="d32f9-227">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="d32f9-228">title</span><span class="sxs-lookup"><span data-stu-id="d32f9-228">title</span></span> | <span data-ttu-id="d32f9-229">Breve valor de cadena de identificación disponible para cada alerta.</span><span class="sxs-lookup"><span data-stu-id="d32f9-229">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="d32f9-230">Actividad de ransomware</span><span class="sxs-lookup"><span data-stu-id="d32f9-230">Ransomware activity</span></span>
<span data-ttu-id="d32f9-231">description</span><span class="sxs-lookup"><span data-stu-id="d32f9-231">description</span></span> | <span data-ttu-id="d32f9-232">Valor de cadena que describe cada alerta.</span><span class="sxs-lookup"><span data-stu-id="d32f9-232">String value describing each alert.</span></span> | <span data-ttu-id="d32f9-233">El usuario Probar usuario2 (testUser2@contoso.com) manipuló 99 archivos con varias extensiones que terminan con la extensión poco común *herunterladen*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-233">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="d32f9-234">Este es un número inusual de manipulaciones de archivos y es indicativo de un posible ataque de ransomware.</span><span class="sxs-lookup"><span data-stu-id="d32f9-234">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="d32f9-235">categoría</span><span class="sxs-lookup"><span data-stu-id="d32f9-235">category</span></span> | <span data-ttu-id="d32f9-236">Vista visual y numérica de hasta qué punto ha progresado el ataque a lo largo de la cadena de eliminación.</span><span class="sxs-lookup"><span data-stu-id="d32f9-236">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="d32f9-237">Alineado con el marco [&MITRE ATT ™ CK](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="d32f9-237">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="d32f9-238">Impacto</span><span class="sxs-lookup"><span data-stu-id="d32f9-238">Impact</span></span>
<span data-ttu-id="d32f9-239">status</span><span class="sxs-lookup"><span data-stu-id="d32f9-239">status</span></span> | <span data-ttu-id="d32f9-240">Clasificar las alertas *(como Nuevo,* *Activo* o *Resuelto).*</span><span class="sxs-lookup"><span data-stu-id="d32f9-240">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="d32f9-241">Puede ayudarle a organizar y administrar la respuesta a las alertas.</span><span class="sxs-lookup"><span data-stu-id="d32f9-241">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="d32f9-242">Nueva</span><span class="sxs-lookup"><span data-stu-id="d32f9-242">New</span></span>
<span data-ttu-id="d32f9-243">severity</span><span class="sxs-lookup"><span data-stu-id="d32f9-243">severity</span></span> | <span data-ttu-id="d32f9-244">Indica el posible impacto en los activos.</span><span class="sxs-lookup"><span data-stu-id="d32f9-244">Indicates the possible impact on assets.</span></span> <span data-ttu-id="d32f9-245">Cuanto mayor sea la gravedad, mayor será el impacto.</span><span class="sxs-lookup"><span data-stu-id="d32f9-245">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="d32f9-246">Normalmente, los elementos de mayor gravedad requieren la atención más inmediata.</span><span class="sxs-lookup"><span data-stu-id="d32f9-246">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="d32f9-247">Uno de los siguientes valores: *Informational*, *Low*, \*Medium y *High*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-247">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="d32f9-248">Medio</span><span class="sxs-lookup"><span data-stu-id="d32f9-248">Medium</span></span>
<span data-ttu-id="d32f9-249">investigationId</span><span class="sxs-lookup"><span data-stu-id="d32f9-249">investigationId</span></span> | <span data-ttu-id="d32f9-250">El identificador de investigación automatizado desencadenado por esta alerta.</span><span class="sxs-lookup"><span data-stu-id="d32f9-250">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="d32f9-251">1234</span><span class="sxs-lookup"><span data-stu-id="d32f9-251">1234</span></span>
<span data-ttu-id="d32f9-252">investigationState</span><span class="sxs-lookup"><span data-stu-id="d32f9-252">investigationState</span></span> | <span data-ttu-id="d32f9-253">Información sobre el estado actual de la investigación.</span><span class="sxs-lookup"><span data-stu-id="d32f9-253">Information on the investigation's current status.</span></span> <span data-ttu-id="d32f9-254">Uno de los siguientes valores: *Unknown*, *Ended*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-254">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="d32f9-255">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="d32f9-255">UnsupportedAlertType</span></span>
<span data-ttu-id="d32f9-256">classification</span><span class="sxs-lookup"><span data-stu-id="d32f9-256">classification</span></span> | <span data-ttu-id="d32f9-257">La especificación del incidente.</span><span class="sxs-lookup"><span data-stu-id="d32f9-257">The specification for the incident.</span></span> <span data-ttu-id="d32f9-258">Los valores de propiedad *son: Unknown*, *FalsePositive*, *TruePositive* o *null*</span><span class="sxs-lookup"><span data-stu-id="d32f9-258">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="d32f9-259">Unknown</span><span class="sxs-lookup"><span data-stu-id="d32f9-259">Unknown</span></span>
<span data-ttu-id="d32f9-260">determinación</span><span class="sxs-lookup"><span data-stu-id="d32f9-260">determination</span></span> | <span data-ttu-id="d32f9-261">Especifica la determinación del incidente.</span><span class="sxs-lookup"><span data-stu-id="d32f9-261">Specifies the determination of the incident.</span></span> <span data-ttu-id="d32f9-262">Los valores de propiedad son: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* o  *null*</span><span class="sxs-lookup"><span data-stu-id="d32f9-262">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="d32f9-263">Apt</span><span class="sxs-lookup"><span data-stu-id="d32f9-263">Apt</span></span>
<span data-ttu-id="d32f9-264">assignedTo</span><span class="sxs-lookup"><span data-stu-id="d32f9-264">assignedTo</span></span> | <span data-ttu-id="d32f9-265">Propietario del incidente o *null* si no se asigna ningún propietario.</span><span class="sxs-lookup"><span data-stu-id="d32f9-265">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="d32f9-266">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d32f9-266">secop2@contoso.com</span></span>
<span data-ttu-id="d32f9-267">actorName</span><span class="sxs-lookup"><span data-stu-id="d32f9-267">actorName</span></span> | <span data-ttu-id="d32f9-268">El grupo de actividades, si lo hay, el asociado a esta alerta.</span><span class="sxs-lookup"><span data-stu-id="d32f9-268">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="d32f9-269">BORON</span><span class="sxs-lookup"><span data-stu-id="d32f9-269">BORON</span></span>
<span data-ttu-id="d32f9-270">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="d32f9-270">threatFamilyName</span></span> | <span data-ttu-id="d32f9-271">Familia de amenazas asociada a esta alerta.</span><span class="sxs-lookup"><span data-stu-id="d32f9-271">Threat family associated with this alert.</span></span> | <span data-ttu-id="d32f9-272">nulo</span><span class="sxs-lookup"><span data-stu-id="d32f9-272">null</span></span>
<span data-ttu-id="d32f9-273">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="d32f9-273">mitreTechniques</span></span> | <span data-ttu-id="d32f9-274">Las técnicas de ataque, alineadas con el marco de&[CK ™ MITRE ATT.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="d32f9-274">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="d32f9-275">dispositivos</span><span class="sxs-lookup"><span data-stu-id="d32f9-275">devices</span></span> | <span data-ttu-id="d32f9-276">Todos los dispositivos en los que se enviaron alertas relacionadas con el incidente.</span><span class="sxs-lookup"><span data-stu-id="d32f9-276">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="d32f9-277">\[\] (vea los detalles de los campos de entidad a continuación)</span><span class="sxs-lookup"><span data-stu-id="d32f9-277">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="d32f9-278">Formato de dispositivo</span><span class="sxs-lookup"><span data-stu-id="d32f9-278">Device format</span></span>

<span data-ttu-id="d32f9-279">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="d32f9-279">Field name</span></span> | <span data-ttu-id="d32f9-280">Descripción</span><span class="sxs-lookup"><span data-stu-id="d32f9-280">Description</span></span> | <span data-ttu-id="d32f9-281">Valor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d32f9-281">Example value</span></span>
-|-|-
<span data-ttu-id="d32f9-282">DeviceId</span><span class="sxs-lookup"><span data-stu-id="d32f9-282">DeviceId</span></span> | <span data-ttu-id="d32f9-283">El identificador de dispositivo designado en Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="d32f9-283">The device ID as designated in Microsoft Defender for Endpoint.</span></span> | <span data-ttu-id="d32f9-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="d32f9-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="d32f9-285">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="d32f9-285">aadDeviceId</span></span> |  <span data-ttu-id="d32f9-286">El identificador de dispositivo designado en [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="d32f9-286">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="d32f9-287">Solo disponible para dispositivos unidos a un dominio.</span><span class="sxs-lookup"><span data-stu-id="d32f9-287">Only available for domain-joined devices.</span></span> | <span data-ttu-id="d32f9-288">nulo</span><span class="sxs-lookup"><span data-stu-id="d32f9-288">null</span></span>
<span data-ttu-id="d32f9-289">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="d32f9-289">deviceDnsName</span></span> | <span data-ttu-id="d32f9-290">El nombre de dominio completo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d32f9-290">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="d32f9-291">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d32f9-291">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="d32f9-292">osPlatform</span><span class="sxs-lookup"><span data-stu-id="d32f9-292">osPlatform</span></span> | <span data-ttu-id="d32f9-293">La plataforma del sistema operativo que se está ejecutando el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d32f9-293">The OS platform the device is running.</span></span>| <span data-ttu-id="d32f9-294">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="d32f9-294">WindowsServer2016</span></span>
<span data-ttu-id="d32f9-295">osBuild</span><span class="sxs-lookup"><span data-stu-id="d32f9-295">osBuild</span></span> | <span data-ttu-id="d32f9-296">La versión de compilación del sistema operativo que se está ejecutando el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d32f9-296">The build version for the OS the device is running.</span></span> | <span data-ttu-id="d32f9-297">14393</span><span class="sxs-lookup"><span data-stu-id="d32f9-297">14393</span></span>
<span data-ttu-id="d32f9-298">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="d32f9-298">rbacGroupName</span></span> | <span data-ttu-id="d32f9-299">Grupo [de control de acceso basado](/azure/role-based-access-control/overview) en roles (RBAC) asociado al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d32f9-299">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="d32f9-300">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="d32f9-300">WDATP-Ring0</span></span>
<span data-ttu-id="d32f9-301">firstSeen</span><span class="sxs-lookup"><span data-stu-id="d32f9-301">firstSeen</span></span> | <span data-ttu-id="d32f9-302">Hora en la que se vio el dispositivo por primera vez.</span><span class="sxs-lookup"><span data-stu-id="d32f9-302">Time when device was first seen.</span></span> | <span data-ttu-id="d32f9-303">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="d32f9-303">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="d32f9-304">healthStatus</span><span class="sxs-lookup"><span data-stu-id="d32f9-304">healthStatus</span></span> | <span data-ttu-id="d32f9-305">El estado de mantenimiento del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d32f9-305">The health state of the device.</span></span> | <span data-ttu-id="d32f9-306">Activa</span><span class="sxs-lookup"><span data-stu-id="d32f9-306">Active</span></span>
<span data-ttu-id="d32f9-307">riskScore</span><span class="sxs-lookup"><span data-stu-id="d32f9-307">riskScore</span></span> | <span data-ttu-id="d32f9-308">La puntuación de riesgo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d32f9-308">The risk score for the  device.</span></span> | <span data-ttu-id="d32f9-309">Alta</span><span class="sxs-lookup"><span data-stu-id="d32f9-309">High</span></span>
<span data-ttu-id="d32f9-310">entidades</span><span class="sxs-lookup"><span data-stu-id="d32f9-310">entities</span></span> | <span data-ttu-id="d32f9-311">Todas las entidades que se han identificado para formar parte o relacionadas con una alerta determinada.</span><span class="sxs-lookup"><span data-stu-id="d32f9-311">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="d32f9-312">\[\] (vea los detalles de los campos de entidad a continuación)</span><span class="sxs-lookup"><span data-stu-id="d32f9-312">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="d32f9-313">Formato de entidad</span><span class="sxs-lookup"><span data-stu-id="d32f9-313">Entity Format</span></span>

<span data-ttu-id="d32f9-314">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="d32f9-314">Field name</span></span> | <span data-ttu-id="d32f9-315">Descripción</span><span class="sxs-lookup"><span data-stu-id="d32f9-315">Description</span></span> | <span data-ttu-id="d32f9-316">Valor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d32f9-316">Example value</span></span>
-|-|-
<span data-ttu-id="d32f9-317">entityType</span><span class="sxs-lookup"><span data-stu-id="d32f9-317">entityType</span></span> | <span data-ttu-id="d32f9-318">Entidades que se han identificado para formar parte o relacionadas con una alerta determinada.</span><span class="sxs-lookup"><span data-stu-id="d32f9-318">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="d32f9-319">Los valores de propiedades son: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span><span class="sxs-lookup"><span data-stu-id="d32f9-319">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="d32f9-320">Usuario</span><span class="sxs-lookup"><span data-stu-id="d32f9-320">User</span></span>
<span data-ttu-id="d32f9-321">sha1</span><span class="sxs-lookup"><span data-stu-id="d32f9-321">sha1</span></span> | <span data-ttu-id="d32f9-322">Disponible si entityType es *File*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-322">Available if entityType is *File*.</span></span><br><span data-ttu-id="d32f9-323">Hash de archivo para alertas asociadas con un archivo o proceso.</span><span class="sxs-lookup"><span data-stu-id="d32f9-323">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="d32f9-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6d</span><span class="sxs-lookup"><span data-stu-id="d32f9-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="d32f9-325">sha256</span><span class="sxs-lookup"><span data-stu-id="d32f9-325">sha256</span></span> | <span data-ttu-id="d32f9-326">Disponible si entityType es *File*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-326">Available if entityType is *File*.</span></span><br><span data-ttu-id="d32f9-327">Hash de archivo para alertas asociadas con un archivo o proceso.</span><span class="sxs-lookup"><span data-stu-id="d32f9-327">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="d32f9-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="d32f9-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="d32f9-329">fileName</span><span class="sxs-lookup"><span data-stu-id="d32f9-329">fileName</span></span> | <span data-ttu-id="d32f9-330">Disponible si entityType es *File*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-330">Available if entityType is *File*.</span></span><br><span data-ttu-id="d32f9-331">El nombre de archivo de las alertas asociadas a un archivo o proceso</span><span class="sxs-lookup"><span data-stu-id="d32f9-331">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="d32f9-332">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="d32f9-332">Detector.UnitTests.dll</span></span>
<span data-ttu-id="d32f9-333">filePath</span><span class="sxs-lookup"><span data-stu-id="d32f9-333">filePath</span></span> | <span data-ttu-id="d32f9-334">Disponible si entityType es *File*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-334">Available if entityType is *File*.</span></span><br><span data-ttu-id="d32f9-335">Ruta de acceso de archivo para alertas asociadas a un archivo o proceso</span><span class="sxs-lookup"><span data-stu-id="d32f9-335">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="d32f9-336">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="d32f9-336">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="d32f9-337">processId</span><span class="sxs-lookup"><span data-stu-id="d32f9-337">processId</span></span> | <span data-ttu-id="d32f9-338">Disponible si entityType es *Process*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-338">Available if entityType is *Process*.</span></span> | <span data-ttu-id="d32f9-339">24348</span><span class="sxs-lookup"><span data-stu-id="d32f9-339">24348</span></span>
<span data-ttu-id="d32f9-340">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="d32f9-340">processCommandLine</span></span> | <span data-ttu-id="d32f9-341">Disponible si entityType es *Process*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-341">Available if entityType is *Process*.</span></span> | <span data-ttu-id="d32f9-342">"El archivo está listo para descargar \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="d32f9-342">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="d32f9-343">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="d32f9-343">processCreationTime</span></span> | <span data-ttu-id="d32f9-344">Disponible si entityType es *Process*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-344">Available if entityType is *Process*.</span></span> | <span data-ttu-id="d32f9-345">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="d32f9-345">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="d32f9-346">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="d32f9-346">parentProcessId</span></span> | <span data-ttu-id="d32f9-347">Disponible si entityType es *Process*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-347">Available if entityType is *Process*.</span></span> | <span data-ttu-id="d32f9-348">16840</span><span class="sxs-lookup"><span data-stu-id="d32f9-348">16840</span></span>
<span data-ttu-id="d32f9-349">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="d32f9-349">parentProcessCreationTime</span></span> | <span data-ttu-id="d32f9-350">Disponible si entityType es *Process*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-350">Available if entityType is *Process*.</span></span> | <span data-ttu-id="d32f9-351">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="d32f9-351">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="d32f9-352">ipAddress</span><span class="sxs-lookup"><span data-stu-id="d32f9-352">ipAddress</span></span> | <span data-ttu-id="d32f9-353">Disponible si entityType es *Ip*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-353">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="d32f9-354">Dirección IP para alertas asociadas con eventos de red, como *La comunicación a un destino de red malintencionado.*</span><span class="sxs-lookup"><span data-stu-id="d32f9-354">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="d32f9-355">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="d32f9-355">62.216.203.204</span></span>
<span data-ttu-id="d32f9-356">url</span><span class="sxs-lookup"><span data-stu-id="d32f9-356">url</span></span> | <span data-ttu-id="d32f9-357">Disponible si entityType es *Url*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-357">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="d32f9-358">Dirección URL de alertas asociadas a eventos de red, como, *Comunicación a un destino de red malintencionado.*</span><span class="sxs-lookup"><span data-stu-id="d32f9-358">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="d32f9-359">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="d32f9-359">down.esales360.cn</span></span>
<span data-ttu-id="d32f9-360">accountName</span><span class="sxs-lookup"><span data-stu-id="d32f9-360">accountName</span></span> | <span data-ttu-id="d32f9-361">Disponible si entityType es *User*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-361">Available if entityType is *User*.</span></span> | <span data-ttu-id="d32f9-362">testUser2</span><span class="sxs-lookup"><span data-stu-id="d32f9-362">testUser2</span></span>
<span data-ttu-id="d32f9-363">domainName</span><span class="sxs-lookup"><span data-stu-id="d32f9-363">domainName</span></span> | <span data-ttu-id="d32f9-364">Disponible si entityType es *User*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-364">Available if entityType is *User*.</span></span> | <span data-ttu-id="d32f9-365">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="d32f9-365">europe.corp.contoso</span></span>
<span data-ttu-id="d32f9-366">userSid</span><span class="sxs-lookup"><span data-stu-id="d32f9-366">userSid</span></span> | <span data-ttu-id="d32f9-367">Disponible si entityType es *User*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-367">Available if entityType is *User*.</span></span> | <span data-ttu-id="d32f9-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="d32f9-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="d32f9-369">aadUserId</span><span class="sxs-lookup"><span data-stu-id="d32f9-369">aadUserId</span></span> | <span data-ttu-id="d32f9-370">Disponible si entityType es *User*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-370">Available if entityType is *User*.</span></span> | <span data-ttu-id="d32f9-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="d32f9-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="d32f9-372">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="d32f9-372">userPrincipalName</span></span> | <span data-ttu-id="d32f9-373">Disponible si entityType es *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-373">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="d32f9-374">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d32f9-374">testUser2@contoso.com</span></span>
<span data-ttu-id="d32f9-375">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="d32f9-375">mailboxDisplayName</span></span> | <span data-ttu-id="d32f9-376">Disponible si entityType es *MailBox*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-376">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="d32f9-377">user2 de prueba</span><span class="sxs-lookup"><span data-stu-id="d32f9-377">test User2</span></span>
<span data-ttu-id="d32f9-378">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="d32f9-378">mailboxAddress</span></span> | <span data-ttu-id="d32f9-379">Disponible si entityType es *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-379">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="d32f9-380">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d32f9-380">testUser2@contoso.com</span></span>
<span data-ttu-id="d32f9-381">clusterBy</span><span class="sxs-lookup"><span data-stu-id="d32f9-381">clusterBy</span></span> | <span data-ttu-id="d32f9-382">Disponible si entityType es  *MailCluster*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-382">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="d32f9-383">Asunto; P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="d32f9-383">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="d32f9-384">sender</span><span class="sxs-lookup"><span data-stu-id="d32f9-384">sender</span></span> | <span data-ttu-id="d32f9-385">Disponible si entityType es *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-385">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="d32f9-386">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="d32f9-386">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="d32f9-387">destinatario</span><span class="sxs-lookup"><span data-stu-id="d32f9-387">recipient</span></span> | <span data-ttu-id="d32f9-388">Disponible si entityType es *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-388">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="d32f9-389">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d32f9-389">testUser2@contoso.com</span></span>
<span data-ttu-id="d32f9-390">subject</span><span class="sxs-lookup"><span data-stu-id="d32f9-390">subject</span></span> | <span data-ttu-id="d32f9-391">Disponible si entityType es *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-391">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="d32f9-392">\[Atención \] externa</span><span class="sxs-lookup"><span data-stu-id="d32f9-392">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="d32f9-393">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="d32f9-393">deliveryAction</span></span> | <span data-ttu-id="d32f9-394">Disponible si entityType es *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-394">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="d32f9-395">Entregado</span><span class="sxs-lookup"><span data-stu-id="d32f9-395">Delivered</span></span>
<span data-ttu-id="d32f9-396">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="d32f9-396">securityGroupId</span></span> | <span data-ttu-id="d32f9-397">Disponible si entityType es  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-397">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="d32f9-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="d32f9-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="d32f9-399">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="d32f9-399">securityGroupName</span></span> | <span data-ttu-id="d32f9-400">Disponible si entityType es  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-400">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="d32f9-401">Operadores de configuración de red</span><span class="sxs-lookup"><span data-stu-id="d32f9-401">Network Configuration Operators</span></span>
<span data-ttu-id="d32f9-402">registryHive</span><span class="sxs-lookup"><span data-stu-id="d32f9-402">registryHive</span></span> | <span data-ttu-id="d32f9-403">Disponible si entityType es  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-403">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="d32f9-404">MÁQUINA LOCAL HKEY \_ \_</span><span class="sxs-lookup"><span data-stu-id="d32f9-404">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="d32f9-405">registryKey</span><span class="sxs-lookup"><span data-stu-id="d32f9-405">registryKey</span></span> | <span data-ttu-id="d32f9-406">Disponible si entityType es  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-406">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="d32f9-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="d32f9-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="d32f9-408">registryValueType</span><span class="sxs-lookup"><span data-stu-id="d32f9-408">registryValueType</span></span> | <span data-ttu-id="d32f9-409">Disponible si entityType es  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-409">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="d32f9-410">Cadena</span><span class="sxs-lookup"><span data-stu-id="d32f9-410">String</span></span>
<span data-ttu-id="d32f9-411">registryValue</span><span class="sxs-lookup"><span data-stu-id="d32f9-411">registryValue</span></span> | <span data-ttu-id="d32f9-412">Disponible si entityType es  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="d32f9-412">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="d32f9-413">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="d32f9-413">31-00-00-00</span></span>
<span data-ttu-id="d32f9-414">deviceId</span><span class="sxs-lookup"><span data-stu-id="d32f9-414">deviceId</span></span> | <span data-ttu-id="d32f9-415">El identificador, si lo hay, del dispositivo relacionado con la entidad.</span><span class="sxs-lookup"><span data-stu-id="d32f9-415">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="d32f9-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="d32f9-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="d32f9-417">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d32f9-417">Example</span></span>

<span data-ttu-id="d32f9-418">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="d32f9-418">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="d32f9-419">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="d32f9-419">**Response**</span></span>

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a><span data-ttu-id="d32f9-420">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="d32f9-420">Related articles</span></span>

- [<span data-ttu-id="d32f9-421">Acceder a las API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d32f9-421">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="d32f9-422">Más información sobre los límites de api y las licencias</span><span class="sxs-lookup"><span data-stu-id="d32f9-422">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="d32f9-423">Comprender códigos de error</span><span class="sxs-lookup"><span data-stu-id="d32f9-423">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="d32f9-424">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="d32f9-424">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="d32f9-425">API de incidentes</span><span class="sxs-lookup"><span data-stu-id="d32f9-425">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="d32f9-426">ACTUALIZAR API de incidentes</span><span class="sxs-lookup"><span data-stu-id="d32f9-426">Update incident API</span></span>](api-update-incidents.md)
