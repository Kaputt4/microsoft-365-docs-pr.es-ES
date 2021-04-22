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
ms.openlocfilehash: 7fb0de4f8dc67331e7acca59e70d061fe7c19493
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935742"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="0c254-104">Enumerar la API de incidentes en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c254-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0c254-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0c254-105">**Applies to:**</span></span>

- <span data-ttu-id="0c254-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c254-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c254-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="0c254-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="0c254-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="0c254-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="0c254-109">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="0c254-109">API description</span></span>

<span data-ttu-id="0c254-110">La API de incidentes de lista le permite ordenar los incidentes para crear una respuesta de ciberseguridad informada.</span><span class="sxs-lookup"><span data-stu-id="0c254-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="0c254-111">Expone una colección de incidentes marcados en la red, dentro del intervalo de tiempo especificado en la directiva de retención del entorno.</span><span class="sxs-lookup"><span data-stu-id="0c254-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="0c254-112">Los incidentes más recientes se muestran en la parte superior de la lista.</span><span class="sxs-lookup"><span data-stu-id="0c254-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="0c254-113">Cada incidente contiene una matriz de alertas relacionadas y sus entidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="0c254-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="0c254-114">La API admite los siguientes operadores **OData:**</span><span class="sxs-lookup"><span data-stu-id="0c254-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="0c254-115">`$filter`en `lastUpdateTime` las `createdTime` propiedades , , `status` y `assignedTo`</span><span class="sxs-lookup"><span data-stu-id="0c254-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="0c254-116">`$top`, con un valor máximo de **100**</span><span class="sxs-lookup"><span data-stu-id="0c254-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="0c254-117">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="0c254-117">Limitations</span></span>

1. <span data-ttu-id="0c254-118">El tamaño máximo de página **es de 100 incidentes.**</span><span class="sxs-lookup"><span data-stu-id="0c254-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="0c254-119">La tasa máxima de solicitudes es **de 50 llamadas por minuto** y **1500 llamadas por hora.**</span><span class="sxs-lookup"><span data-stu-id="0c254-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="0c254-120">Permisos</span><span class="sxs-lookup"><span data-stu-id="0c254-120">Permissions</span></span>

<span data-ttu-id="0c254-121">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="0c254-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0c254-122">Para obtener más información, incluido cómo elegir permisos, vea [Access Microsoft 365 Defender API](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="0c254-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="0c254-123">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="0c254-123">Permission type</span></span> | <span data-ttu-id="0c254-124">Permiso</span><span class="sxs-lookup"><span data-stu-id="0c254-124">Permission</span></span> | <span data-ttu-id="0c254-125">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="0c254-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="0c254-126">Aplicación</span><span class="sxs-lookup"><span data-stu-id="0c254-126">Application</span></span> | <span data-ttu-id="0c254-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="0c254-127">Incident.Read.All</span></span> | <span data-ttu-id="0c254-128">Leer todos los incidentes</span><span class="sxs-lookup"><span data-stu-id="0c254-128">Read all incidents</span></span>
<span data-ttu-id="0c254-129">Aplicación</span><span class="sxs-lookup"><span data-stu-id="0c254-129">Application</span></span> | <span data-ttu-id="0c254-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="0c254-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="0c254-131">Leer y escribir todos los incidentes</span><span class="sxs-lookup"><span data-stu-id="0c254-131">Read and write all incidents</span></span>
<span data-ttu-id="0c254-132">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="0c254-132">Delegated (work or school account)</span></span> | <span data-ttu-id="0c254-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="0c254-133">Incident.Read</span></span> | <span data-ttu-id="0c254-134">Leer incidentes</span><span class="sxs-lookup"><span data-stu-id="0c254-134">Read incidents</span></span>
<span data-ttu-id="0c254-135">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="0c254-135">Delegated (work or school account)</span></span> | <span data-ttu-id="0c254-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="0c254-136">Incident.ReadWrite</span></span> | <span data-ttu-id="0c254-137">Incidentes de lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="0c254-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="0c254-138">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="0c254-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="0c254-139">El usuario debe tener permiso de vista para incidentes en el portal.</span><span class="sxs-lookup"><span data-stu-id="0c254-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="0c254-140">La respuesta solo incluirá incidentes a los que se expone el usuario.</span><span class="sxs-lookup"><span data-stu-id="0c254-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="0c254-141">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="0c254-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="0c254-142">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="0c254-142">Request headers</span></span>

<span data-ttu-id="0c254-143">Nombre</span><span class="sxs-lookup"><span data-stu-id="0c254-143">Name</span></span> | <span data-ttu-id="0c254-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="0c254-144">Type</span></span> | <span data-ttu-id="0c254-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c254-145">Description</span></span>
-|-|-
<span data-ttu-id="0c254-146">Authorization</span><span class="sxs-lookup"><span data-stu-id="0c254-146">Authorization</span></span> | <span data-ttu-id="0c254-147">Cadena</span><span class="sxs-lookup"><span data-stu-id="0c254-147">String</span></span> | <span data-ttu-id="0c254-148">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="0c254-148">Bearer {token}.</span></span> <span data-ttu-id="0c254-149">**Required**</span><span class="sxs-lookup"><span data-stu-id="0c254-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="0c254-150">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="0c254-150">Request body</span></span>

<span data-ttu-id="0c254-151">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="0c254-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="0c254-152">Respuesta</span><span class="sxs-lookup"><span data-stu-id="0c254-152">Response</span></span>

<span data-ttu-id="0c254-153">Si se realiza correctamente, este método `200 OK` devuelve y una lista de incidentes [en](api-incident.md) el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="0c254-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="0c254-154">Asignación de esquema</span><span class="sxs-lookup"><span data-stu-id="0c254-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="0c254-155">Metadatos de incidentes</span><span class="sxs-lookup"><span data-stu-id="0c254-155">Incident metadata</span></span>

<span data-ttu-id="0c254-156">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="0c254-156">Field name</span></span> | <span data-ttu-id="0c254-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c254-157">Description</span></span> | <span data-ttu-id="0c254-158">Valor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c254-158">Example value</span></span>
-|-|-
<span data-ttu-id="0c254-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="0c254-159">incidentId</span></span> | <span data-ttu-id="0c254-160">Identificador único para representar el incidente</span><span class="sxs-lookup"><span data-stu-id="0c254-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="0c254-161">924565</span><span class="sxs-lookup"><span data-stu-id="0c254-161">924565</span></span>
<span data-ttu-id="0c254-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="0c254-162">redirectIncidentId</span></span> | <span data-ttu-id="0c254-163">Solo se rellena en caso de que un incidente se esté agrupando con otro incidente, como parte de la lógica de procesamiento de incidentes.</span><span class="sxs-lookup"><span data-stu-id="0c254-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="0c254-164">924569</span><span class="sxs-lookup"><span data-stu-id="0c254-164">924569</span></span>
<span data-ttu-id="0c254-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="0c254-165">incidentName</span></span> | <span data-ttu-id="0c254-166">Valor de cadena disponible para cada incidente.</span><span class="sxs-lookup"><span data-stu-id="0c254-166">String value available for every incident.</span></span> | <span data-ttu-id="0c254-167">Actividad ransomware</span><span class="sxs-lookup"><span data-stu-id="0c254-167">Ransomware activity</span></span>
<span data-ttu-id="0c254-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="0c254-168">createdTime</span></span> | <span data-ttu-id="0c254-169">Hora en la que se creó el incidente por primera vez.</span><span class="sxs-lookup"><span data-stu-id="0c254-169">Time when incident was first created.</span></span> | <span data-ttu-id="0c254-170">2020-09-06T14:46:57.073333Z</span><span class="sxs-lookup"><span data-stu-id="0c254-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="0c254-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="0c254-171">lastUpdateTime</span></span> | <span data-ttu-id="0c254-172">Hora en la que el incidente se actualizó por última vez en el back-end.</span><span class="sxs-lookup"><span data-stu-id="0c254-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="0c254-173">Este campo se puede usar al establecer el parámetro de solicitud para el intervalo de tiempo que se recuperan los incidentes.</span><span class="sxs-lookup"><span data-stu-id="0c254-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="0c254-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="0c254-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="0c254-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="0c254-175">assignedTo</span></span> | <span data-ttu-id="0c254-176">Propietario del incidente o *null* si no se asigna ningún propietario.</span><span class="sxs-lookup"><span data-stu-id="0c254-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="0c254-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0c254-177">secop2@contoso.com</span></span>
<span data-ttu-id="0c254-178">classification</span><span class="sxs-lookup"><span data-stu-id="0c254-178">classification</span></span> | <span data-ttu-id="0c254-179">La especificación del incidente.</span><span class="sxs-lookup"><span data-stu-id="0c254-179">The specification for the incident.</span></span> <span data-ttu-id="0c254-180">Los valores de propiedad son: *Unknown*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="0c254-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="0c254-181">Unknown</span><span class="sxs-lookup"><span data-stu-id="0c254-181">Unknown</span></span>
<span data-ttu-id="0c254-182">determinación</span><span class="sxs-lookup"><span data-stu-id="0c254-182">determination</span></span> | <span data-ttu-id="0c254-183">Especifica la determinación del incidente.</span><span class="sxs-lookup"><span data-stu-id="0c254-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="0c254-184">Los valores de propiedad son: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span><span class="sxs-lookup"><span data-stu-id="0c254-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="0c254-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="0c254-185">NotAvailable</span></span>
<span data-ttu-id="0c254-186">status</span><span class="sxs-lookup"><span data-stu-id="0c254-186">status</span></span> | <span data-ttu-id="0c254-187">Clasifice los incidentes *(como Activos* o *Resueltos).*</span><span class="sxs-lookup"><span data-stu-id="0c254-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="0c254-188">Puede ayudarle a organizar y administrar su respuesta a incidentes.</span><span class="sxs-lookup"><span data-stu-id="0c254-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="0c254-189">Activo</span><span class="sxs-lookup"><span data-stu-id="0c254-189">Active</span></span>
<span data-ttu-id="0c254-190">severity</span><span class="sxs-lookup"><span data-stu-id="0c254-190">severity</span></span> | <span data-ttu-id="0c254-191">Indica el posible impacto en los activos.</span><span class="sxs-lookup"><span data-stu-id="0c254-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="0c254-192">Cuanto mayor sea la gravedad, mayor será el impacto.</span><span class="sxs-lookup"><span data-stu-id="0c254-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="0c254-193">Normalmente, los elementos de mayor gravedad requieren la atención más inmediata.</span><span class="sxs-lookup"><span data-stu-id="0c254-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="0c254-194">Uno de los siguientes valores: *Informational*, *Low*, \*Medium y *High*.</span><span class="sxs-lookup"><span data-stu-id="0c254-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="0c254-195">Mediano</span><span class="sxs-lookup"><span data-stu-id="0c254-195">Medium</span></span>
<span data-ttu-id="0c254-196">tags</span><span class="sxs-lookup"><span data-stu-id="0c254-196">tags</span></span> | <span data-ttu-id="0c254-197">Matriz de etiquetas personalizadas asociadas a un incidente, por ejemplo para marcar un grupo de incidentes con una característica común.</span><span class="sxs-lookup"><span data-stu-id="0c254-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="0c254-198">alerts</span><span class="sxs-lookup"><span data-stu-id="0c254-198">alerts</span></span> | <span data-ttu-id="0c254-199">Matriz que contiene todas las alertas relacionadas con el incidente, además de otra información, como la gravedad, las entidades que participaron en la alerta y el origen de las alertas.</span><span class="sxs-lookup"><span data-stu-id="0c254-199">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="0c254-200">\[\] (vea los detalles de los campos de alerta a continuación)</span><span class="sxs-lookup"><span data-stu-id="0c254-200">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="0c254-201">Metadatos de alertas</span><span class="sxs-lookup"><span data-stu-id="0c254-201">Alerts metadata</span></span>

<span data-ttu-id="0c254-202">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="0c254-202">Field name</span></span> | <span data-ttu-id="0c254-203">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c254-203">Description</span></span> | <span data-ttu-id="0c254-204">Valor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c254-204">Example value</span></span>
-|-|-
<span data-ttu-id="0c254-205">alertId</span><span class="sxs-lookup"><span data-stu-id="0c254-205">alertId</span></span> | <span data-ttu-id="0c254-206">Identificador único para representar la alerta</span><span class="sxs-lookup"><span data-stu-id="0c254-206">Unique identifier to represent the alert</span></span> | <span data-ttu-id="0c254-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="0c254-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="0c254-208">incidentId</span><span class="sxs-lookup"><span data-stu-id="0c254-208">incidentId</span></span> | <span data-ttu-id="0c254-209">Identificador único para representar el incidente al que está asociada esta alerta</span><span class="sxs-lookup"><span data-stu-id="0c254-209">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="0c254-210">924565</span><span class="sxs-lookup"><span data-stu-id="0c254-210">924565</span></span>
<span data-ttu-id="0c254-211">serviceSource</span><span class="sxs-lookup"><span data-stu-id="0c254-211">serviceSource</span></span> | <span data-ttu-id="0c254-212">Servicio del que procede la alerta, como Microsoft Defender para endpoint, Microsoft Cloud App Security, Microsoft Defender para Identity o Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c254-212">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="0c254-213">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="0c254-213">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="0c254-214">creationTime</span><span class="sxs-lookup"><span data-stu-id="0c254-214">creationTime</span></span> | <span data-ttu-id="0c254-215">Hora en la que se creó la alerta por primera vez.</span><span class="sxs-lookup"><span data-stu-id="0c254-215">Time when alert was first created.</span></span> | <span data-ttu-id="0c254-216">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="0c254-216">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="0c254-217">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="0c254-217">lastUpdatedTime</span></span> | <span data-ttu-id="0c254-218">Hora en la que se actualizó la alerta por última vez en el back-end.</span><span class="sxs-lookup"><span data-stu-id="0c254-218">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="0c254-219">2020-09-06T14:46:57.243333Z</span><span class="sxs-lookup"><span data-stu-id="0c254-219">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="0c254-220">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="0c254-220">resolvedTime</span></span> | <span data-ttu-id="0c254-221">Hora en la que se resolvió la alerta.</span><span class="sxs-lookup"><span data-stu-id="0c254-221">Time when alert was resolved.</span></span> | <span data-ttu-id="0c254-222">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="0c254-222">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="0c254-223">firstActivity</span><span class="sxs-lookup"><span data-stu-id="0c254-223">firstActivity</span></span> | <span data-ttu-id="0c254-224">Hora en la que la alerta informó por primera vez de que la actividad se actualizó en el back-end.</span><span class="sxs-lookup"><span data-stu-id="0c254-224">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="0c254-225">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="0c254-225">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="0c254-226">title</span><span class="sxs-lookup"><span data-stu-id="0c254-226">title</span></span> | <span data-ttu-id="0c254-227">Breve valor de cadena de identificación disponible para cada alerta.</span><span class="sxs-lookup"><span data-stu-id="0c254-227">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="0c254-228">Actividad ransomware</span><span class="sxs-lookup"><span data-stu-id="0c254-228">Ransomware activity</span></span>
<span data-ttu-id="0c254-229">description</span><span class="sxs-lookup"><span data-stu-id="0c254-229">description</span></span> | <span data-ttu-id="0c254-230">Valor de cadena que describe cada alerta.</span><span class="sxs-lookup"><span data-stu-id="0c254-230">String value describing each alert.</span></span> | <span data-ttu-id="0c254-231">El usuario Probar usuario2 (testUser2@contoso.com) manipuló 99 archivos con varias extensiones que terminan con la extensión poco común *herunterladen*.</span><span class="sxs-lookup"><span data-stu-id="0c254-231">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="0c254-232">Este es un número inusual de manipulaciones de archivos y es indicativo de un posible ataque de ransomware.</span><span class="sxs-lookup"><span data-stu-id="0c254-232">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="0c254-233">categoría</span><span class="sxs-lookup"><span data-stu-id="0c254-233">category</span></span> | <span data-ttu-id="0c254-234">Vista visual y numérica de hasta qué punto ha progresado el ataque a lo largo de la cadena de eliminación.</span><span class="sxs-lookup"><span data-stu-id="0c254-234">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="0c254-235">Alineado con el marco [&MITRE ATT ™ CK](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="0c254-235">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="0c254-236">Impacto</span><span class="sxs-lookup"><span data-stu-id="0c254-236">Impact</span></span>
<span data-ttu-id="0c254-237">status</span><span class="sxs-lookup"><span data-stu-id="0c254-237">status</span></span> | <span data-ttu-id="0c254-238">Clasificar las alertas *(como Nuevo,* *Activo* o *Resuelto).*</span><span class="sxs-lookup"><span data-stu-id="0c254-238">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="0c254-239">Puede ayudarle a organizar y administrar la respuesta a las alertas.</span><span class="sxs-lookup"><span data-stu-id="0c254-239">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="0c254-240">Nueva</span><span class="sxs-lookup"><span data-stu-id="0c254-240">New</span></span>
<span data-ttu-id="0c254-241">severity</span><span class="sxs-lookup"><span data-stu-id="0c254-241">severity</span></span> | <span data-ttu-id="0c254-242">Indica el posible impacto en los activos.</span><span class="sxs-lookup"><span data-stu-id="0c254-242">Indicates the possible impact on assets.</span></span> <span data-ttu-id="0c254-243">Cuanto mayor sea la gravedad, mayor será el impacto.</span><span class="sxs-lookup"><span data-stu-id="0c254-243">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="0c254-244">Normalmente, los elementos de mayor gravedad requieren la atención más inmediata.</span><span class="sxs-lookup"><span data-stu-id="0c254-244">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="0c254-245">Uno de los siguientes valores: *Informational*, *Low*, \*Medium y *High*.</span><span class="sxs-lookup"><span data-stu-id="0c254-245">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="0c254-246">Mediano</span><span class="sxs-lookup"><span data-stu-id="0c254-246">Medium</span></span>
<span data-ttu-id="0c254-247">investigationId</span><span class="sxs-lookup"><span data-stu-id="0c254-247">investigationId</span></span> | <span data-ttu-id="0c254-248">El identificador de investigación automatizado desencadenado por esta alerta.</span><span class="sxs-lookup"><span data-stu-id="0c254-248">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="0c254-249">1234</span><span class="sxs-lookup"><span data-stu-id="0c254-249">1234</span></span>
<span data-ttu-id="0c254-250">investigationState</span><span class="sxs-lookup"><span data-stu-id="0c254-250">investigationState</span></span> | <span data-ttu-id="0c254-251">Información sobre el estado actual de la investigación.</span><span class="sxs-lookup"><span data-stu-id="0c254-251">Information on the investigation's current status.</span></span> <span data-ttu-id="0c254-252">Uno de los siguientes valores: *Unknown*, *Ended*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="0c254-252">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="0c254-253">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="0c254-253">UnsupportedAlertType</span></span>
<span data-ttu-id="0c254-254">classification</span><span class="sxs-lookup"><span data-stu-id="0c254-254">classification</span></span> | <span data-ttu-id="0c254-255">La especificación del incidente.</span><span class="sxs-lookup"><span data-stu-id="0c254-255">The specification for the incident.</span></span> <span data-ttu-id="0c254-256">Los valores de propiedad *son: Unknown*, *FalsePositive*, *TruePositive* o *null*</span><span class="sxs-lookup"><span data-stu-id="0c254-256">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="0c254-257">Unknown</span><span class="sxs-lookup"><span data-stu-id="0c254-257">Unknown</span></span>
<span data-ttu-id="0c254-258">determinación</span><span class="sxs-lookup"><span data-stu-id="0c254-258">determination</span></span> | <span data-ttu-id="0c254-259">Especifica la determinación del incidente.</span><span class="sxs-lookup"><span data-stu-id="0c254-259">Specifies the determination of the incident.</span></span> <span data-ttu-id="0c254-260">Los valores de propiedad son: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* o  *null*</span><span class="sxs-lookup"><span data-stu-id="0c254-260">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="0c254-261">Apt</span><span class="sxs-lookup"><span data-stu-id="0c254-261">Apt</span></span>
<span data-ttu-id="0c254-262">assignedTo</span><span class="sxs-lookup"><span data-stu-id="0c254-262">assignedTo</span></span> | <span data-ttu-id="0c254-263">Propietario del incidente o *null* si no se asigna ningún propietario.</span><span class="sxs-lookup"><span data-stu-id="0c254-263">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="0c254-264">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0c254-264">secop2@contoso.com</span></span>
<span data-ttu-id="0c254-265">actorName</span><span class="sxs-lookup"><span data-stu-id="0c254-265">actorName</span></span> | <span data-ttu-id="0c254-266">El grupo de actividades, si lo hay, el asociado a esta alerta.</span><span class="sxs-lookup"><span data-stu-id="0c254-266">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="0c254-267">BORON</span><span class="sxs-lookup"><span data-stu-id="0c254-267">BORON</span></span>
<span data-ttu-id="0c254-268">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="0c254-268">threatFamilyName</span></span> | <span data-ttu-id="0c254-269">Familia de amenazas asociada a esta alerta.</span><span class="sxs-lookup"><span data-stu-id="0c254-269">Threat family associated with this alert.</span></span> | <span data-ttu-id="0c254-270">nulo</span><span class="sxs-lookup"><span data-stu-id="0c254-270">null</span></span>
<span data-ttu-id="0c254-271">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="0c254-271">mitreTechniques</span></span> | <span data-ttu-id="0c254-272">Las técnicas de ataque, alineadas con el marco de&[CK ™ MITRE ATT.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="0c254-272">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="0c254-273">dispositivos</span><span class="sxs-lookup"><span data-stu-id="0c254-273">devices</span></span> | <span data-ttu-id="0c254-274">Todos los dispositivos en los que se enviaron alertas relacionadas con el incidente.</span><span class="sxs-lookup"><span data-stu-id="0c254-274">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="0c254-275">\[\] (vea los detalles de los campos de entidad a continuación)</span><span class="sxs-lookup"><span data-stu-id="0c254-275">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="0c254-276">Formato de dispositivo</span><span class="sxs-lookup"><span data-stu-id="0c254-276">Device format</span></span>

<span data-ttu-id="0c254-277">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="0c254-277">Field name</span></span> | <span data-ttu-id="0c254-278">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c254-278">Description</span></span> | <span data-ttu-id="0c254-279">Valor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c254-279">Example value</span></span>
-|-|-
<span data-ttu-id="0c254-280">DeviceId</span><span class="sxs-lookup"><span data-stu-id="0c254-280">DeviceId</span></span> | <span data-ttu-id="0c254-281">El identificador de dispositivo designado en Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="0c254-281">The device ID as designated in Microsoft Defender for Endpoint.</span></span> | <span data-ttu-id="0c254-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="0c254-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="0c254-283">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="0c254-283">aadDeviceId</span></span> |  <span data-ttu-id="0c254-284">El identificador de dispositivo designado en [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="0c254-284">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="0c254-285">Solo disponible para dispositivos unidos a un dominio.</span><span class="sxs-lookup"><span data-stu-id="0c254-285">Only available for domain-joined devices.</span></span> | <span data-ttu-id="0c254-286">nulo</span><span class="sxs-lookup"><span data-stu-id="0c254-286">null</span></span>
<span data-ttu-id="0c254-287">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="0c254-287">deviceDnsName</span></span> | <span data-ttu-id="0c254-288">El nombre de dominio completo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0c254-288">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="0c254-289">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0c254-289">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="0c254-290">osPlatform</span><span class="sxs-lookup"><span data-stu-id="0c254-290">osPlatform</span></span> | <span data-ttu-id="0c254-291">La plataforma del sistema operativo que se está ejecutando el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0c254-291">The OS platform the device is running.</span></span>| <span data-ttu-id="0c254-292">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="0c254-292">WindowsServer2016</span></span>
<span data-ttu-id="0c254-293">osBuild</span><span class="sxs-lookup"><span data-stu-id="0c254-293">osBuild</span></span> | <span data-ttu-id="0c254-294">La versión de compilación del sistema operativo que se está ejecutando el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0c254-294">The build version for the OS the device is running.</span></span> | <span data-ttu-id="0c254-295">14393</span><span class="sxs-lookup"><span data-stu-id="0c254-295">14393</span></span>
<span data-ttu-id="0c254-296">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="0c254-296">rbacGroupName</span></span> | <span data-ttu-id="0c254-297">Grupo [de control de acceso basado](/azure/role-based-access-control/overview) en roles (RBAC) asociado al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0c254-297">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="0c254-298">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="0c254-298">WDATP-Ring0</span></span>
<span data-ttu-id="0c254-299">firstSeen</span><span class="sxs-lookup"><span data-stu-id="0c254-299">firstSeen</span></span> | <span data-ttu-id="0c254-300">Hora en la que se vio el dispositivo por primera vez.</span><span class="sxs-lookup"><span data-stu-id="0c254-300">Time when device was first seen.</span></span> | <span data-ttu-id="0c254-301">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="0c254-301">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="0c254-302">healthStatus</span><span class="sxs-lookup"><span data-stu-id="0c254-302">healthStatus</span></span> | <span data-ttu-id="0c254-303">El estado de mantenimiento del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0c254-303">The health state of the device.</span></span> | <span data-ttu-id="0c254-304">Activo</span><span class="sxs-lookup"><span data-stu-id="0c254-304">Active</span></span>
<span data-ttu-id="0c254-305">riskScore</span><span class="sxs-lookup"><span data-stu-id="0c254-305">riskScore</span></span> | <span data-ttu-id="0c254-306">La puntuación de riesgo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0c254-306">The risk score for the  device.</span></span> | <span data-ttu-id="0c254-307">Alto</span><span class="sxs-lookup"><span data-stu-id="0c254-307">High</span></span>
<span data-ttu-id="0c254-308">entidades</span><span class="sxs-lookup"><span data-stu-id="0c254-308">entities</span></span> | <span data-ttu-id="0c254-309">Todas las entidades que se han identificado para formar parte o relacionadas con una alerta determinada.</span><span class="sxs-lookup"><span data-stu-id="0c254-309">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="0c254-310">\[\] (vea los detalles de los campos de entidad a continuación)</span><span class="sxs-lookup"><span data-stu-id="0c254-310">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="0c254-311">Formato de entidad</span><span class="sxs-lookup"><span data-stu-id="0c254-311">Entity Format</span></span>

<span data-ttu-id="0c254-312">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="0c254-312">Field name</span></span> | <span data-ttu-id="0c254-313">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c254-313">Description</span></span> | <span data-ttu-id="0c254-314">Valor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c254-314">Example value</span></span>
-|-|-
<span data-ttu-id="0c254-315">entityType</span><span class="sxs-lookup"><span data-stu-id="0c254-315">entityType</span></span> | <span data-ttu-id="0c254-316">Entidades que se han identificado para formar parte o relacionadas con una alerta determinada.</span><span class="sxs-lookup"><span data-stu-id="0c254-316">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="0c254-317">Los valores de propiedades son: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span><span class="sxs-lookup"><span data-stu-id="0c254-317">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="0c254-318">Usuario</span><span class="sxs-lookup"><span data-stu-id="0c254-318">User</span></span>
<span data-ttu-id="0c254-319">sha1</span><span class="sxs-lookup"><span data-stu-id="0c254-319">sha1</span></span> | <span data-ttu-id="0c254-320">Disponible si entityType es *File*.</span><span class="sxs-lookup"><span data-stu-id="0c254-320">Available if entityType is *File*.</span></span><br><span data-ttu-id="0c254-321">Hash de archivo para alertas asociadas con un archivo o proceso.</span><span class="sxs-lookup"><span data-stu-id="0c254-321">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="0c254-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6d</span><span class="sxs-lookup"><span data-stu-id="0c254-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="0c254-323">sha256</span><span class="sxs-lookup"><span data-stu-id="0c254-323">sha256</span></span> | <span data-ttu-id="0c254-324">Disponible si entityType es *File*.</span><span class="sxs-lookup"><span data-stu-id="0c254-324">Available if entityType is *File*.</span></span><br><span data-ttu-id="0c254-325">Hash de archivo para alertas asociadas con un archivo o proceso.</span><span class="sxs-lookup"><span data-stu-id="0c254-325">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="0c254-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="0c254-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="0c254-327">fileName</span><span class="sxs-lookup"><span data-stu-id="0c254-327">fileName</span></span> | <span data-ttu-id="0c254-328">Disponible si entityType es *File*.</span><span class="sxs-lookup"><span data-stu-id="0c254-328">Available if entityType is *File*.</span></span><br><span data-ttu-id="0c254-329">El nombre de archivo de las alertas asociadas a un archivo o proceso</span><span class="sxs-lookup"><span data-stu-id="0c254-329">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="0c254-330">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="0c254-330">Detector.UnitTests.dll</span></span>
<span data-ttu-id="0c254-331">filePath</span><span class="sxs-lookup"><span data-stu-id="0c254-331">filePath</span></span> | <span data-ttu-id="0c254-332">Disponible si entityType es *File*.</span><span class="sxs-lookup"><span data-stu-id="0c254-332">Available if entityType is *File*.</span></span><br><span data-ttu-id="0c254-333">Ruta de acceso de archivo para alertas asociadas a un archivo o proceso</span><span class="sxs-lookup"><span data-stu-id="0c254-333">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="0c254-334">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="0c254-334">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="0c254-335">processId</span><span class="sxs-lookup"><span data-stu-id="0c254-335">processId</span></span> | <span data-ttu-id="0c254-336">Disponible si entityType es *Process*.</span><span class="sxs-lookup"><span data-stu-id="0c254-336">Available if entityType is *Process*.</span></span> | <span data-ttu-id="0c254-337">24348</span><span class="sxs-lookup"><span data-stu-id="0c254-337">24348</span></span>
<span data-ttu-id="0c254-338">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="0c254-338">processCommandLine</span></span> | <span data-ttu-id="0c254-339">Disponible si entityType es *Process*.</span><span class="sxs-lookup"><span data-stu-id="0c254-339">Available if entityType is *Process*.</span></span> | <span data-ttu-id="0c254-340">"El archivo está listo para descargar \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="0c254-340">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="0c254-341">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="0c254-341">processCreationTime</span></span> | <span data-ttu-id="0c254-342">Disponible si entityType es *Process*.</span><span class="sxs-lookup"><span data-stu-id="0c254-342">Available if entityType is *Process*.</span></span> | <span data-ttu-id="0c254-343">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="0c254-343">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="0c254-344">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="0c254-344">parentProcessId</span></span> | <span data-ttu-id="0c254-345">Disponible si entityType es *Process*.</span><span class="sxs-lookup"><span data-stu-id="0c254-345">Available if entityType is *Process*.</span></span> | <span data-ttu-id="0c254-346">16840</span><span class="sxs-lookup"><span data-stu-id="0c254-346">16840</span></span>
<span data-ttu-id="0c254-347">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="0c254-347">parentProcessCreationTime</span></span> | <span data-ttu-id="0c254-348">Disponible si entityType es *Process*.</span><span class="sxs-lookup"><span data-stu-id="0c254-348">Available if entityType is *Process*.</span></span> | <span data-ttu-id="0c254-349">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="0c254-349">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="0c254-350">ipAddress</span><span class="sxs-lookup"><span data-stu-id="0c254-350">ipAddress</span></span> | <span data-ttu-id="0c254-351">Disponible si entityType es *Ip*.</span><span class="sxs-lookup"><span data-stu-id="0c254-351">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="0c254-352">Dirección IP para alertas asociadas con eventos de red, como *La comunicación a un destino de red malintencionado.*</span><span class="sxs-lookup"><span data-stu-id="0c254-352">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="0c254-353">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="0c254-353">62.216.203.204</span></span>
<span data-ttu-id="0c254-354">url</span><span class="sxs-lookup"><span data-stu-id="0c254-354">url</span></span> | <span data-ttu-id="0c254-355">Disponible si entityType es *Url*.</span><span class="sxs-lookup"><span data-stu-id="0c254-355">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="0c254-356">Dirección URL de alertas asociadas a eventos de red, como, *Comunicación a un destino de red malintencionado.*</span><span class="sxs-lookup"><span data-stu-id="0c254-356">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="0c254-357">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="0c254-357">down.esales360.cn</span></span>
<span data-ttu-id="0c254-358">accountName</span><span class="sxs-lookup"><span data-stu-id="0c254-358">accountName</span></span> | <span data-ttu-id="0c254-359">Disponible si entityType es *User*.</span><span class="sxs-lookup"><span data-stu-id="0c254-359">Available if entityType is *User*.</span></span> | <span data-ttu-id="0c254-360">testUser2</span><span class="sxs-lookup"><span data-stu-id="0c254-360">testUser2</span></span>
<span data-ttu-id="0c254-361">domainName</span><span class="sxs-lookup"><span data-stu-id="0c254-361">domainName</span></span> | <span data-ttu-id="0c254-362">Disponible si entityType es *User*.</span><span class="sxs-lookup"><span data-stu-id="0c254-362">Available if entityType is *User*.</span></span> | <span data-ttu-id="0c254-363">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="0c254-363">europe.corp.contoso</span></span>
<span data-ttu-id="0c254-364">userSid</span><span class="sxs-lookup"><span data-stu-id="0c254-364">userSid</span></span> | <span data-ttu-id="0c254-365">Disponible si entityType es *User*.</span><span class="sxs-lookup"><span data-stu-id="0c254-365">Available if entityType is *User*.</span></span> | <span data-ttu-id="0c254-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="0c254-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="0c254-367">aadUserId</span><span class="sxs-lookup"><span data-stu-id="0c254-367">aadUserId</span></span> | <span data-ttu-id="0c254-368">Disponible si entityType es *User*.</span><span class="sxs-lookup"><span data-stu-id="0c254-368">Available if entityType is *User*.</span></span> | <span data-ttu-id="0c254-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="0c254-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="0c254-370">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="0c254-370">userPrincipalName</span></span> | <span data-ttu-id="0c254-371">Disponible si entityType es *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="0c254-371">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="0c254-372">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0c254-372">testUser2@contoso.com</span></span>
<span data-ttu-id="0c254-373">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="0c254-373">mailboxDisplayName</span></span> | <span data-ttu-id="0c254-374">Disponible si entityType es *MailBox*.</span><span class="sxs-lookup"><span data-stu-id="0c254-374">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="0c254-375">user2 de prueba</span><span class="sxs-lookup"><span data-stu-id="0c254-375">test User2</span></span>
<span data-ttu-id="0c254-376">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="0c254-376">mailboxAddress</span></span> | <span data-ttu-id="0c254-377">Disponible si entityType es *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="0c254-377">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="0c254-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0c254-378">testUser2@contoso.com</span></span>
<span data-ttu-id="0c254-379">clusterBy</span><span class="sxs-lookup"><span data-stu-id="0c254-379">clusterBy</span></span> | <span data-ttu-id="0c254-380">Disponible si entityType es  *MailCluster*.</span><span class="sxs-lookup"><span data-stu-id="0c254-380">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="0c254-381">Asunto; P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="0c254-381">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="0c254-382">sender</span><span class="sxs-lookup"><span data-stu-id="0c254-382">sender</span></span> | <span data-ttu-id="0c254-383">Disponible si entityType es *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="0c254-383">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="0c254-384">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="0c254-384">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="0c254-385">destinatario</span><span class="sxs-lookup"><span data-stu-id="0c254-385">recipient</span></span> | <span data-ttu-id="0c254-386">Disponible si entityType es *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="0c254-386">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="0c254-387">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0c254-387">testUser2@contoso.com</span></span>
<span data-ttu-id="0c254-388">subject</span><span class="sxs-lookup"><span data-stu-id="0c254-388">subject</span></span> | <span data-ttu-id="0c254-389">Disponible si entityType es *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="0c254-389">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="0c254-390">\[Atención \] externa</span><span class="sxs-lookup"><span data-stu-id="0c254-390">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="0c254-391">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="0c254-391">deliveryAction</span></span> | <span data-ttu-id="0c254-392">Disponible si entityType es *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="0c254-392">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="0c254-393">Entregado</span><span class="sxs-lookup"><span data-stu-id="0c254-393">Delivered</span></span>
<span data-ttu-id="0c254-394">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="0c254-394">securityGroupId</span></span> | <span data-ttu-id="0c254-395">Disponible si entityType es  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="0c254-395">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="0c254-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="0c254-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="0c254-397">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="0c254-397">securityGroupName</span></span> | <span data-ttu-id="0c254-398">Disponible si entityType es  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="0c254-398">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="0c254-399">Operadores de configuración de red</span><span class="sxs-lookup"><span data-stu-id="0c254-399">Network Configuration Operators</span></span>
<span data-ttu-id="0c254-400">registryHive</span><span class="sxs-lookup"><span data-stu-id="0c254-400">registryHive</span></span> | <span data-ttu-id="0c254-401">Disponible si entityType es  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="0c254-401">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="0c254-402">MÁQUINA LOCAL HKEY \_ \_</span><span class="sxs-lookup"><span data-stu-id="0c254-402">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="0c254-403">registryKey</span><span class="sxs-lookup"><span data-stu-id="0c254-403">registryKey</span></span> | <span data-ttu-id="0c254-404">Disponible si entityType es  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="0c254-404">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="0c254-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="0c254-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="0c254-406">registryValueType</span><span class="sxs-lookup"><span data-stu-id="0c254-406">registryValueType</span></span> | <span data-ttu-id="0c254-407">Disponible si entityType es  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="0c254-407">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="0c254-408">Cadena</span><span class="sxs-lookup"><span data-stu-id="0c254-408">String</span></span>
<span data-ttu-id="0c254-409">registryValue</span><span class="sxs-lookup"><span data-stu-id="0c254-409">registryValue</span></span> | <span data-ttu-id="0c254-410">Disponible si entityType es  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="0c254-410">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="0c254-411">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="0c254-411">31-00-00-00</span></span>
<span data-ttu-id="0c254-412">deviceId</span><span class="sxs-lookup"><span data-stu-id="0c254-412">deviceId</span></span> | <span data-ttu-id="0c254-413">El identificador, si lo hay, del dispositivo relacionado con la entidad.</span><span class="sxs-lookup"><span data-stu-id="0c254-413">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="0c254-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="0c254-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="0c254-415">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c254-415">Example</span></span>

<span data-ttu-id="0c254-416">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="0c254-416">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="0c254-417">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="0c254-417">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="0c254-418">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="0c254-418">Related articles</span></span>

- [<span data-ttu-id="0c254-419">Obtener acceso a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c254-419">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="0c254-420">Más información sobre los límites de api y las licencias</span><span class="sxs-lookup"><span data-stu-id="0c254-420">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="0c254-421">Comprender códigos de error</span><span class="sxs-lookup"><span data-stu-id="0c254-421">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="0c254-422">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="0c254-422">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="0c254-423">API de incidentes</span><span class="sxs-lookup"><span data-stu-id="0c254-423">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="0c254-424">ACTUALIZAR API de incidentes</span><span class="sxs-lookup"><span data-stu-id="0c254-424">Update incident API</span></span>](api-update-incidents.md)