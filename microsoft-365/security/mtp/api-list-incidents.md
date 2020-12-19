---
title: API de lista de incidentes en Microsoft 365 defender
description: Obtenga información sobre cómo enumerar la API de incidentes en Microsoft 365 defender
keywords: lista, incidente, incidentes, API
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
ms.openlocfilehash: 13508d3ad9d61797517ccb55a27152883947843a
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719433"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="f541e-104">API de lista de incidentes en Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="f541e-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f541e-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f541e-105">**Applies to:**</span></span>

- <span data-ttu-id="f541e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f541e-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f541e-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="f541e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f541e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="f541e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="f541e-109">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="f541e-109">API description</span></span>

<span data-ttu-id="f541e-110">La API de incidentes de lista permite ordenar los incidentes para crear una respuesta Cybersecurity informada.</span><span class="sxs-lookup"><span data-stu-id="f541e-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="f541e-111">Expone una colección de incidentes que se marcaron en la red, dentro del intervalo de tiempo especificado en la Directiva de retención del entorno.</span><span class="sxs-lookup"><span data-stu-id="f541e-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="f541e-112">Los incidentes más recientes se muestran en la parte superior de la lista.</span><span class="sxs-lookup"><span data-stu-id="f541e-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="f541e-113">Cada incidente contiene una matriz de alertas relacionadas y sus entidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="f541e-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="f541e-114">La API admite los siguientes operadores **OData** :</span><span class="sxs-lookup"><span data-stu-id="f541e-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="f541e-115">`$filter`en las `lastUpdateTime` propiedades,, `createdTime` `status` y `assignedTo`</span><span class="sxs-lookup"><span data-stu-id="f541e-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="f541e-116">`$top`, con un valor máximo de **100**</span><span class="sxs-lookup"><span data-stu-id="f541e-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="f541e-117">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="f541e-117">Limitations</span></span>

1. <span data-ttu-id="f541e-118">El tamaño máximo de página es de **100 incidentes**.</span><span class="sxs-lookup"><span data-stu-id="f541e-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="f541e-119">La tasa de solicitudes máxima es de **50 llamadas por minuto** y **1500 de llamadas por hora**.</span><span class="sxs-lookup"><span data-stu-id="f541e-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="f541e-120">Permisos</span><span class="sxs-lookup"><span data-stu-id="f541e-120">Permissions</span></span>

<span data-ttu-id="f541e-121">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="f541e-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f541e-122">Para obtener más información, incluido cómo elegir permisos, consulte [Access Microsoft 365 API de defender](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="f541e-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="f541e-123">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="f541e-123">Permission type</span></span> | <span data-ttu-id="f541e-124">Permiso</span><span class="sxs-lookup"><span data-stu-id="f541e-124">Permission</span></span> | <span data-ttu-id="f541e-125">Nombre para mostrar del permiso</span><span class="sxs-lookup"><span data-stu-id="f541e-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="f541e-126">Aplicación</span><span class="sxs-lookup"><span data-stu-id="f541e-126">Application</span></span> | <span data-ttu-id="f541e-127">Incident. Read. All</span><span class="sxs-lookup"><span data-stu-id="f541e-127">Incident.Read.All</span></span> | <span data-ttu-id="f541e-128">Leer todos los incidentes</span><span class="sxs-lookup"><span data-stu-id="f541e-128">Read all incidents</span></span>
<span data-ttu-id="f541e-129">Aplicación</span><span class="sxs-lookup"><span data-stu-id="f541e-129">Application</span></span> | <span data-ttu-id="f541e-130">Incident. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="f541e-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="f541e-131">Leer y escribir todos los incidentes</span><span class="sxs-lookup"><span data-stu-id="f541e-131">Read and write all incidents</span></span>
<span data-ttu-id="f541e-132">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="f541e-132">Delegated (work or school account)</span></span> | <span data-ttu-id="f541e-133">Incident. Read</span><span class="sxs-lookup"><span data-stu-id="f541e-133">Incident.Read</span></span> | <span data-ttu-id="f541e-134">Incidentes de lectura</span><span class="sxs-lookup"><span data-stu-id="f541e-134">Read incidents</span></span>
<span data-ttu-id="f541e-135">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="f541e-135">Delegated (work or school account)</span></span> | <span data-ttu-id="f541e-136">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="f541e-136">Incident.ReadWrite</span></span> | <span data-ttu-id="f541e-137">Leer y escribir incidentes</span><span class="sxs-lookup"><span data-stu-id="f541e-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="f541e-138">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="f541e-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="f541e-139">El usuario debe tener permiso de visualización para incidentes en el portal.</span><span class="sxs-lookup"><span data-stu-id="f541e-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="f541e-140">La respuesta solo incluirá los incidentes a los que el usuario está expuesto.</span><span class="sxs-lookup"><span data-stu-id="f541e-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="f541e-141">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="f541e-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="f541e-142">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="f541e-142">Request headers</span></span>

<span data-ttu-id="f541e-143">Nombre</span><span class="sxs-lookup"><span data-stu-id="f541e-143">Name</span></span> | <span data-ttu-id="f541e-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="f541e-144">Type</span></span> | <span data-ttu-id="f541e-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="f541e-145">Description</span></span>
-|-|-
<span data-ttu-id="f541e-146">Authorization</span><span class="sxs-lookup"><span data-stu-id="f541e-146">Authorization</span></span> | <span data-ttu-id="f541e-147">Cadena</span><span class="sxs-lookup"><span data-stu-id="f541e-147">String</span></span> | <span data-ttu-id="f541e-148">{Token} de portador.</span><span class="sxs-lookup"><span data-stu-id="f541e-148">Bearer {token}.</span></span> <span data-ttu-id="f541e-149">**Required**</span><span class="sxs-lookup"><span data-stu-id="f541e-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="f541e-150">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="f541e-150">Request body</span></span>

<span data-ttu-id="f541e-151">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="f541e-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="f541e-152">Respuesta</span><span class="sxs-lookup"><span data-stu-id="f541e-152">Response</span></span>

<span data-ttu-id="f541e-153">Si se ejecuta correctamente, este método devuelve `200 OK` y una lista de [incidentes](api-incident.md) en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="f541e-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="f541e-154">Asignación del esquema</span><span class="sxs-lookup"><span data-stu-id="f541e-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="f541e-155">Metadatos del incidente</span><span class="sxs-lookup"><span data-stu-id="f541e-155">Incident metadata</span></span>

<span data-ttu-id="f541e-156">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="f541e-156">Field name</span></span> | <span data-ttu-id="f541e-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="f541e-157">Description</span></span> | <span data-ttu-id="f541e-158">Valor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="f541e-158">Example value</span></span>
-|-|-
<span data-ttu-id="f541e-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="f541e-159">incidentId</span></span> | <span data-ttu-id="f541e-160">Identificador único que representa el incidente</span><span class="sxs-lookup"><span data-stu-id="f541e-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="f541e-161">924565</span><span class="sxs-lookup"><span data-stu-id="f541e-161">924565</span></span>
<span data-ttu-id="f541e-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="f541e-162">redirectIncidentId</span></span> | <span data-ttu-id="f541e-163">Solo se rellena en caso de que un incidente se agrupe con otro incidente, como parte de la lógica de procesamiento de incidentes.</span><span class="sxs-lookup"><span data-stu-id="f541e-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="f541e-164">924569</span><span class="sxs-lookup"><span data-stu-id="f541e-164">924569</span></span>
<span data-ttu-id="f541e-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="f541e-165">incidentName</span></span> | <span data-ttu-id="f541e-166">Valor de cadena disponible para cada incidente.</span><span class="sxs-lookup"><span data-stu-id="f541e-166">String value available for every incident.</span></span> | <span data-ttu-id="f541e-167">Actividad de ransomware</span><span class="sxs-lookup"><span data-stu-id="f541e-167">Ransomware activity</span></span>
<span data-ttu-id="f541e-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="f541e-168">createdTime</span></span> | <span data-ttu-id="f541e-169">Hora a la que se creó el incidente por primera vez.</span><span class="sxs-lookup"><span data-stu-id="f541e-169">Time when incident was first created.</span></span> | <span data-ttu-id="f541e-170">2020-09-06T14:46:57.0733333 Z</span><span class="sxs-lookup"><span data-stu-id="f541e-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="f541e-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="f541e-171">lastUpdateTime</span></span> | <span data-ttu-id="f541e-172">Hora en la que se actualizó por última vez el incidente en el back-end.</span><span class="sxs-lookup"><span data-stu-id="f541e-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="f541e-173">Este campo se puede usar al establecer el parámetro de solicitud para el intervalo de tiempo durante el que se recuperan los incidentes.</span><span class="sxs-lookup"><span data-stu-id="f541e-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="f541e-174">2020-09-06T14:46:57.29 Z</span><span class="sxs-lookup"><span data-stu-id="f541e-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="f541e-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="f541e-175">assignedTo</span></span> | <span data-ttu-id="f541e-176">Propietario del incidente, o *null* si no hay ningún propietario asignado.</span><span class="sxs-lookup"><span data-stu-id="f541e-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="f541e-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f541e-177">secop2@contoso.com</span></span>
<span data-ttu-id="f541e-178">classification</span><span class="sxs-lookup"><span data-stu-id="f541e-178">classification</span></span> | <span data-ttu-id="f541e-179">La especificación del incidente.</span><span class="sxs-lookup"><span data-stu-id="f541e-179">The specification for the incident.</span></span> <span data-ttu-id="f541e-180">Los valores de la propiedad son: *Unknown*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="f541e-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="f541e-181">Unknown</span><span class="sxs-lookup"><span data-stu-id="f541e-181">Unknown</span></span>
<span data-ttu-id="f541e-182">cálculo</span><span class="sxs-lookup"><span data-stu-id="f541e-182">determination</span></span> | <span data-ttu-id="f541e-183">Especifica la determinación del incidente.</span><span class="sxs-lookup"><span data-stu-id="f541e-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="f541e-184">Los valores de la propiedad son: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other*</span><span class="sxs-lookup"><span data-stu-id="f541e-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="f541e-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="f541e-185">NotAvailable</span></span>
<span data-ttu-id="f541e-186">status</span><span class="sxs-lookup"><span data-stu-id="f541e-186">status</span></span> | <span data-ttu-id="f541e-187">Clasifique los incidentes (como *activos* o *resueltos*).</span><span class="sxs-lookup"><span data-stu-id="f541e-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="f541e-188">Puede ayudarle a organizar y administrar la respuesta a incidentes.</span><span class="sxs-lookup"><span data-stu-id="f541e-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="f541e-189">Activo</span><span class="sxs-lookup"><span data-stu-id="f541e-189">Active</span></span>
<span data-ttu-id="f541e-190">severity</span><span class="sxs-lookup"><span data-stu-id="f541e-190">severity</span></span> | <span data-ttu-id="f541e-191">Indica el posible impacto en los activos.</span><span class="sxs-lookup"><span data-stu-id="f541e-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="f541e-192">Cuanto mayor sea la gravedad, mayor será el impacto.</span><span class="sxs-lookup"><span data-stu-id="f541e-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="f541e-193">Normalmente, los elementos de mayor gravedad requieren la atención más inmediata.</span><span class="sxs-lookup"><span data-stu-id="f541e-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="f541e-194">Uno de los siguientes valores: *informativo*, *bajo*, \* medio y *alto*.</span><span class="sxs-lookup"><span data-stu-id="f541e-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="f541e-195">Mediano</span><span class="sxs-lookup"><span data-stu-id="f541e-195">Medium</span></span>
<span data-ttu-id="f541e-196">tags</span><span class="sxs-lookup"><span data-stu-id="f541e-196">tags</span></span> | <span data-ttu-id="f541e-197">Matriz de etiquetas personalizadas asociadas a un incidente, por ejemplo, para marcar un grupo de incidentes con una característica común.</span><span class="sxs-lookup"><span data-stu-id="f541e-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="f541e-198">alerts</span><span class="sxs-lookup"><span data-stu-id="f541e-198">alerts</span></span> | <span data-ttu-id="f541e-199">Matriz que contiene todas las alertas relacionadas con el incidente, además de otra información, como la gravedad, las entidades involucradas en la alerta y el origen de las alertas.</span><span class="sxs-lookup"><span data-stu-id="f541e-199">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="f541e-200">\[\] (consulte los detalles de los campos de alerta a continuación)</span><span class="sxs-lookup"><span data-stu-id="f541e-200">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="f541e-201">Metadatos de alertas</span><span class="sxs-lookup"><span data-stu-id="f541e-201">Alerts metadata</span></span>

<span data-ttu-id="f541e-202">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="f541e-202">Field name</span></span> | <span data-ttu-id="f541e-203">Descripción</span><span class="sxs-lookup"><span data-stu-id="f541e-203">Description</span></span> | <span data-ttu-id="f541e-204">Valor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="f541e-204">Example value</span></span>
-|-|-
<span data-ttu-id="f541e-205">alertId</span><span class="sxs-lookup"><span data-stu-id="f541e-205">alertId</span></span> | <span data-ttu-id="f541e-206">Identificador único que representa la alerta</span><span class="sxs-lookup"><span data-stu-id="f541e-206">Unique identifier to represent the alert</span></span> | <span data-ttu-id="f541e-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="f541e-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="f541e-208">incidentId</span><span class="sxs-lookup"><span data-stu-id="f541e-208">incidentId</span></span> | <span data-ttu-id="f541e-209">Identificador único que representa el incidente al que está asociada esta alerta</span><span class="sxs-lookup"><span data-stu-id="f541e-209">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="f541e-210">924565</span><span class="sxs-lookup"><span data-stu-id="f541e-210">924565</span></span>
<span data-ttu-id="f541e-211">serviceSource</span><span class="sxs-lookup"><span data-stu-id="f541e-211">serviceSource</span></span> | <span data-ttu-id="f541e-212">Servicio del que procede la alerta, como Microsoft defender para el punto de conexión, Microsoft Cloud App Security, Microsoft defender para identidad o Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="f541e-212">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="f541e-213">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="f541e-213">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="f541e-214">creationTime</span><span class="sxs-lookup"><span data-stu-id="f541e-214">creationTime</span></span> | <span data-ttu-id="f541e-215">Hora a la que se creó la alerta por primera vez.</span><span class="sxs-lookup"><span data-stu-id="f541e-215">Time when alert was first created.</span></span> | <span data-ttu-id="f541e-216">2020-09-06T14:46:55.7182276 Z</span><span class="sxs-lookup"><span data-stu-id="f541e-216">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="f541e-217">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="f541e-217">lastUpdatedTime</span></span> | <span data-ttu-id="f541e-218">Hora de la última actualización de la alerta en el back-end.</span><span class="sxs-lookup"><span data-stu-id="f541e-218">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="f541e-219">2020-09-06T14:46:57.2433333 Z</span><span class="sxs-lookup"><span data-stu-id="f541e-219">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="f541e-220">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="f541e-220">resolvedTime</span></span> | <span data-ttu-id="f541e-221">Hora a la que se resolvió la alerta.</span><span class="sxs-lookup"><span data-stu-id="f541e-221">Time when alert was resolved.</span></span> | <span data-ttu-id="f541e-222">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="f541e-222">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="f541e-223">firstActivity</span><span class="sxs-lookup"><span data-stu-id="f541e-223">firstActivity</span></span> | <span data-ttu-id="f541e-224">Hora en que la alerta notificó por primera vez que se actualizó la actividad en el back-end.</span><span class="sxs-lookup"><span data-stu-id="f541e-224">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="f541e-225">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="f541e-225">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="f541e-226">title</span><span class="sxs-lookup"><span data-stu-id="f541e-226">title</span></span> | <span data-ttu-id="f541e-227">Valor de cadena de identificación breve disponible para cada alerta.</span><span class="sxs-lookup"><span data-stu-id="f541e-227">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="f541e-228">Actividad de ransomware</span><span class="sxs-lookup"><span data-stu-id="f541e-228">Ransomware activity</span></span>
<span data-ttu-id="f541e-229">description</span><span class="sxs-lookup"><span data-stu-id="f541e-229">description</span></span> | <span data-ttu-id="f541e-230">Valor de cadena que describe cada alerta.</span><span class="sxs-lookup"><span data-stu-id="f541e-230">String value describing each alert.</span></span> | <span data-ttu-id="f541e-231">El usuario de prueba user2 (testUser2@contoso.com) ha manipulado 99 archivos con varias extensiones que finalizan con la extensión no común *herunterladen*.</span><span class="sxs-lookup"><span data-stu-id="f541e-231">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="f541e-232">Se trata de un número inusual de manipulaciones de archivos e indica un posible ataque de ransomware.</span><span class="sxs-lookup"><span data-stu-id="f541e-232">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="f541e-233">categoría</span><span class="sxs-lookup"><span data-stu-id="f541e-233">category</span></span> | <span data-ttu-id="f541e-234">Vista visual y numérica de cuánto ha progresado el ataque a lo largo de la cadena de eliminación.</span><span class="sxs-lookup"><span data-stu-id="f541e-234">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="f541e-235">Se alinea a la [Mitre de ATT&CK™ Framework](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="f541e-235">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="f541e-236">Impacto</span><span class="sxs-lookup"><span data-stu-id="f541e-236">Impact</span></span>
<span data-ttu-id="f541e-237">status</span><span class="sxs-lookup"><span data-stu-id="f541e-237">status</span></span> | <span data-ttu-id="f541e-238">Clasifique las alertas (como *nuevas*, *activas* o *resueltas*).</span><span class="sxs-lookup"><span data-stu-id="f541e-238">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="f541e-239">Puede ayudarle a organizar y administrar la respuesta a las alertas.</span><span class="sxs-lookup"><span data-stu-id="f541e-239">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="f541e-240">Nuevo</span><span class="sxs-lookup"><span data-stu-id="f541e-240">New</span></span>
<span data-ttu-id="f541e-241">severity</span><span class="sxs-lookup"><span data-stu-id="f541e-241">severity</span></span> | <span data-ttu-id="f541e-242">Indica el posible impacto en los activos.</span><span class="sxs-lookup"><span data-stu-id="f541e-242">Indicates the possible impact on assets.</span></span> <span data-ttu-id="f541e-243">Cuanto mayor sea la gravedad, mayor será el impacto.</span><span class="sxs-lookup"><span data-stu-id="f541e-243">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="f541e-244">Normalmente, los elementos de mayor gravedad requieren la atención más inmediata.</span><span class="sxs-lookup"><span data-stu-id="f541e-244">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="f541e-245">Uno de los siguientes valores: *informativo*, *bajo*, \* medio y *alto*.</span><span class="sxs-lookup"><span data-stu-id="f541e-245">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="f541e-246">Mediano</span><span class="sxs-lookup"><span data-stu-id="f541e-246">Medium</span></span>
<span data-ttu-id="f541e-247">investigationId</span><span class="sxs-lookup"><span data-stu-id="f541e-247">investigationId</span></span> | <span data-ttu-id="f541e-248">El identificador de investigación automatizada desencadenada por esta alerta.</span><span class="sxs-lookup"><span data-stu-id="f541e-248">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="f541e-249">1234</span><span class="sxs-lookup"><span data-stu-id="f541e-249">1234</span></span>
<span data-ttu-id="f541e-250">investigationState</span><span class="sxs-lookup"><span data-stu-id="f541e-250">investigationState</span></span> | <span data-ttu-id="f541e-251">Información sobre el estado actual de la investigación.</span><span class="sxs-lookup"><span data-stu-id="f541e-251">Information on the investigation's current status.</span></span> <span data-ttu-id="f541e-252">Uno de los siguientes valores: *Unknown*, *terminated*, *SuccessfullyRemediated*, *benigno*, *failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated* *, TerminatedByUser,* *TerminatedBySystem*, *queued*, *InnerFailure*, *PreexistingAlert*, *unsupports*, *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="f541e-252">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="f541e-253">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="f541e-253">UnsupportedAlertType</span></span>
<span data-ttu-id="f541e-254">classification</span><span class="sxs-lookup"><span data-stu-id="f541e-254">classification</span></span> | <span data-ttu-id="f541e-255">La especificación del incidente.</span><span class="sxs-lookup"><span data-stu-id="f541e-255">The specification for the incident.</span></span> <span data-ttu-id="f541e-256">Los valores de la propiedad son: *Unknown*, *FalsePositive*, *TruePositive* o *null*</span><span class="sxs-lookup"><span data-stu-id="f541e-256">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="f541e-257">Unknown</span><span class="sxs-lookup"><span data-stu-id="f541e-257">Unknown</span></span>
<span data-ttu-id="f541e-258">cálculo</span><span class="sxs-lookup"><span data-stu-id="f541e-258">determination</span></span> | <span data-ttu-id="f541e-259">Especifica la determinación del incidente.</span><span class="sxs-lookup"><span data-stu-id="f541e-259">Specifies the determination of the incident.</span></span> <span data-ttu-id="f541e-260">Los valores de la propiedad son: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other* o  *null*</span><span class="sxs-lookup"><span data-stu-id="f541e-260">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="f541e-261">Apt</span><span class="sxs-lookup"><span data-stu-id="f541e-261">Apt</span></span>
<span data-ttu-id="f541e-262">assignedTo</span><span class="sxs-lookup"><span data-stu-id="f541e-262">assignedTo</span></span> | <span data-ttu-id="f541e-263">Propietario del incidente, o *null* si no hay ningún propietario asignado.</span><span class="sxs-lookup"><span data-stu-id="f541e-263">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="f541e-264">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f541e-264">secop2@contoso.com</span></span>
<span data-ttu-id="f541e-265">actorName</span><span class="sxs-lookup"><span data-stu-id="f541e-265">actorName</span></span> | <span data-ttu-id="f541e-266">El grupo de actividad, si lo hubiera, asociado con esta alerta.</span><span class="sxs-lookup"><span data-stu-id="f541e-266">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="f541e-267">BORO</span><span class="sxs-lookup"><span data-stu-id="f541e-267">BORON</span></span>
<span data-ttu-id="f541e-268">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="f541e-268">threatFamilyName</span></span> | <span data-ttu-id="f541e-269">Familia de amenazas asociada a esta alerta.</span><span class="sxs-lookup"><span data-stu-id="f541e-269">Threat family associated with this alert.</span></span> | <span data-ttu-id="f541e-270">nulo</span><span class="sxs-lookup"><span data-stu-id="f541e-270">null</span></span>
<span data-ttu-id="f541e-271">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="f541e-271">mitreTechniques</span></span> | <span data-ttu-id="f541e-272">Las técnicas de ataque, que se alinean con el marco de [Mitre ATT&CK](https://attack.mitre.org/)™.</span><span class="sxs-lookup"><span data-stu-id="f541e-272">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="f541e-273">equipos</span><span class="sxs-lookup"><span data-stu-id="f541e-273">devices</span></span> | <span data-ttu-id="f541e-274">Todos los dispositivos en los que se enviaron alertas relacionadas con el incidente.</span><span class="sxs-lookup"><span data-stu-id="f541e-274">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="f541e-275">\[\] (vea los detalles de los campos de entidad a continuación)</span><span class="sxs-lookup"><span data-stu-id="f541e-275">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="f541e-276">Formato de dispositivo</span><span class="sxs-lookup"><span data-stu-id="f541e-276">Device format</span></span>

<span data-ttu-id="f541e-277">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="f541e-277">Field name</span></span> | <span data-ttu-id="f541e-278">Descripción</span><span class="sxs-lookup"><span data-stu-id="f541e-278">Description</span></span> | <span data-ttu-id="f541e-279">Valor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="f541e-279">Example value</span></span>
-|-|-
<span data-ttu-id="f541e-280">DeviceId</span><span class="sxs-lookup"><span data-stu-id="f541e-280">DeviceId</span></span> | <span data-ttu-id="f541e-281">El identificador del dispositivo tal como se ha designado en ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="f541e-281">The device ID as designated in Microsoft Defender ATP.</span></span> | <span data-ttu-id="f541e-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="f541e-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="f541e-283">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="f541e-283">aadDeviceId</span></span> |  <span data-ttu-id="f541e-284">El identificador de dispositivo tal como se ha designado en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="f541e-284">The device ID as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="f541e-285">Solo está disponible para los dispositivos Unidos a un dominio.</span><span class="sxs-lookup"><span data-stu-id="f541e-285">Only available for domain-joined devices.</span></span> | <span data-ttu-id="f541e-286">nulo</span><span class="sxs-lookup"><span data-stu-id="f541e-286">null</span></span>
<span data-ttu-id="f541e-287">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="f541e-287">deviceDnsName</span></span> | <span data-ttu-id="f541e-288">Nombre de dominio completo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f541e-288">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="f541e-289">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f541e-289">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="f541e-290">osPlatform</span><span class="sxs-lookup"><span data-stu-id="f541e-290">osPlatform</span></span> | <span data-ttu-id="f541e-291">La plataforma de sistema operativo que el dispositivo está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="f541e-291">The OS platform the device is running.</span></span>| <span data-ttu-id="f541e-292">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="f541e-292">WindowsServer2016</span></span>
<span data-ttu-id="f541e-293">osBuild</span><span class="sxs-lookup"><span data-stu-id="f541e-293">osBuild</span></span> | <span data-ttu-id="f541e-294">La versión de compilación para el sistema operativo que el dispositivo está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="f541e-294">The build version for the OS the device is running.</span></span> | <span data-ttu-id="f541e-295">14393</span><span class="sxs-lookup"><span data-stu-id="f541e-295">14393</span></span>
<span data-ttu-id="f541e-296">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="f541e-296">rbacGroupName</span></span> | <span data-ttu-id="f541e-297">El grupo [de control de acceso basado en roles](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) asociado al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f541e-297">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="f541e-298">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="f541e-298">WDATP-Ring0</span></span>
<span data-ttu-id="f541e-299">firstSeen</span><span class="sxs-lookup"><span data-stu-id="f541e-299">firstSeen</span></span> | <span data-ttu-id="f541e-300">Hora en que se ha visto el dispositivo por primera vez.</span><span class="sxs-lookup"><span data-stu-id="f541e-300">Time when device was first seen.</span></span> | <span data-ttu-id="f541e-301">2020-02-06T14:16:01.9330135 Z</span><span class="sxs-lookup"><span data-stu-id="f541e-301">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="f541e-302">healthStatus</span><span class="sxs-lookup"><span data-stu-id="f541e-302">healthStatus</span></span> | <span data-ttu-id="f541e-303">El estado de mantenimiento del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f541e-303">The health state of the device.</span></span> | <span data-ttu-id="f541e-304">Activo</span><span class="sxs-lookup"><span data-stu-id="f541e-304">Active</span></span>
<span data-ttu-id="f541e-305">riskScore</span><span class="sxs-lookup"><span data-stu-id="f541e-305">riskScore</span></span> | <span data-ttu-id="f541e-306">La puntuación de riesgo para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f541e-306">The risk score for the  device.</span></span> | <span data-ttu-id="f541e-307">Alto</span><span class="sxs-lookup"><span data-stu-id="f541e-307">High</span></span>
<span data-ttu-id="f541e-308">organismos</span><span class="sxs-lookup"><span data-stu-id="f541e-308">entities</span></span> | <span data-ttu-id="f541e-309">Todas las entidades que se han identificado como parte de una alerta determinada o están relacionadas con ella.</span><span class="sxs-lookup"><span data-stu-id="f541e-309">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="f541e-310">\[\] (vea los detalles de los campos de entidad a continuación)</span><span class="sxs-lookup"><span data-stu-id="f541e-310">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="f541e-311">Formato de la entidad</span><span class="sxs-lookup"><span data-stu-id="f541e-311">Entity Format</span></span>

<span data-ttu-id="f541e-312">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="f541e-312">Field name</span></span> | <span data-ttu-id="f541e-313">Descripción</span><span class="sxs-lookup"><span data-stu-id="f541e-313">Description</span></span> | <span data-ttu-id="f541e-314">Valor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="f541e-314">Example value</span></span>
-|-|-
<span data-ttu-id="f541e-315">entityType</span><span class="sxs-lookup"><span data-stu-id="f541e-315">entityType</span></span> | <span data-ttu-id="f541e-316">Entidades que se han identificado como parte de una alerta determinada o están relacionadas con ella.</span><span class="sxs-lookup"><span data-stu-id="f541e-316">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="f541e-317">Los valores de las propiedades son: *usuario*, *IP*, *dirección URL*, *archivo*, *proceso*, *buzón*, *MailMessage*, *MailCluster*, *registro*</span><span class="sxs-lookup"><span data-stu-id="f541e-317">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="f541e-318">Usuario</span><span class="sxs-lookup"><span data-stu-id="f541e-318">User</span></span>
<span data-ttu-id="f541e-319">SHA1</span><span class="sxs-lookup"><span data-stu-id="f541e-319">sha1</span></span> | <span data-ttu-id="f541e-320">Disponible si entityType es *File*.</span><span class="sxs-lookup"><span data-stu-id="f541e-320">Available if entityType is *File*.</span></span><br><span data-ttu-id="f541e-321">Hash de archivo de alertas asociadas a un archivo o proceso.</span><span class="sxs-lookup"><span data-stu-id="f541e-321">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="f541e-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="f541e-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="f541e-323">SHA256</span><span class="sxs-lookup"><span data-stu-id="f541e-323">sha256</span></span> | <span data-ttu-id="f541e-324">Disponible si entityType es *File*.</span><span class="sxs-lookup"><span data-stu-id="f541e-324">Available if entityType is *File*.</span></span><br><span data-ttu-id="f541e-325">Hash de archivo de alertas asociadas a un archivo o proceso.</span><span class="sxs-lookup"><span data-stu-id="f541e-325">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="f541e-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="f541e-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="f541e-327">fileName</span><span class="sxs-lookup"><span data-stu-id="f541e-327">fileName</span></span> | <span data-ttu-id="f541e-328">Disponible si entityType es *File*.</span><span class="sxs-lookup"><span data-stu-id="f541e-328">Available if entityType is *File*.</span></span><br><span data-ttu-id="f541e-329">El nombre de archivo de las alertas asociadas a un archivo o proceso</span><span class="sxs-lookup"><span data-stu-id="f541e-329">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="f541e-330">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="f541e-330">Detector.UnitTests.dll</span></span>
<span data-ttu-id="f541e-331">Rutaarchivo</span><span class="sxs-lookup"><span data-stu-id="f541e-331">filePath</span></span> | <span data-ttu-id="f541e-332">Disponible si entityType es *File*.</span><span class="sxs-lookup"><span data-stu-id="f541e-332">Available if entityType is *File*.</span></span><br><span data-ttu-id="f541e-333">La ruta de acceso del archivo para las alertas asociadas a un archivo o proceso</span><span class="sxs-lookup"><span data-stu-id="f541e-333">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="f541e-334">C: \\ \ agent_work_temp \deploy\system\2020-09-06 12_14_54 \ salida</span><span class="sxs-lookup"><span data-stu-id="f541e-334">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="f541e-335">Idproceso</span><span class="sxs-lookup"><span data-stu-id="f541e-335">processId</span></span> | <span data-ttu-id="f541e-336">Disponible si entityType es *Process*.</span><span class="sxs-lookup"><span data-stu-id="f541e-336">Available if entityType is *Process*.</span></span> | <span data-ttu-id="f541e-337">24348</span><span class="sxs-lookup"><span data-stu-id="f541e-337">24348</span></span>
<span data-ttu-id="f541e-338">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="f541e-338">processCommandLine</span></span> | <span data-ttu-id="f541e-339">Disponible si entityType es *Process*.</span><span class="sxs-lookup"><span data-stu-id="f541e-339">Available if entityType is *Process*.</span></span> | <span data-ttu-id="f541e-340">"El archivo está listo para descargar \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="f541e-340">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="f541e-341">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="f541e-341">processCreationTime</span></span> | <span data-ttu-id="f541e-342">Disponible si entityType es *Process*.</span><span class="sxs-lookup"><span data-stu-id="f541e-342">Available if entityType is *Process*.</span></span> | <span data-ttu-id="f541e-343">2020-07-18T03:25:38.5269993 Z</span><span class="sxs-lookup"><span data-stu-id="f541e-343">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="f541e-344">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="f541e-344">parentProcessId</span></span> | <span data-ttu-id="f541e-345">Disponible si entityType es *Process*.</span><span class="sxs-lookup"><span data-stu-id="f541e-345">Available if entityType is *Process*.</span></span> | <span data-ttu-id="f541e-346">16840</span><span class="sxs-lookup"><span data-stu-id="f541e-346">16840</span></span>
<span data-ttu-id="f541e-347">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="f541e-347">parentProcessCreationTime</span></span> | <span data-ttu-id="f541e-348">Disponible si entityType es *Process*.</span><span class="sxs-lookup"><span data-stu-id="f541e-348">Available if entityType is *Process*.</span></span> | <span data-ttu-id="f541e-349">2020-07-18T02:12:32.8616797 Z</span><span class="sxs-lookup"><span data-stu-id="f541e-349">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="f541e-350">ipAddress</span><span class="sxs-lookup"><span data-stu-id="f541e-350">ipAddress</span></span> | <span data-ttu-id="f541e-351">Disponible si entityType es *IP*.</span><span class="sxs-lookup"><span data-stu-id="f541e-351">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="f541e-352">Dirección IP de alertas asociadas con eventos de red, como *la comunicación a un destino de red malintencionado*.</span><span class="sxs-lookup"><span data-stu-id="f541e-352">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="f541e-353">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="f541e-353">62.216.203.204</span></span>
<span data-ttu-id="f541e-354">url</span><span class="sxs-lookup"><span data-stu-id="f541e-354">url</span></span> | <span data-ttu-id="f541e-355">Disponible si entityType es *URL*.</span><span class="sxs-lookup"><span data-stu-id="f541e-355">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="f541e-356">Dirección URL de las alertas asociadas a eventos de red, como *la comunicación a un destino de red malintencionado*.</span><span class="sxs-lookup"><span data-stu-id="f541e-356">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="f541e-357">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="f541e-357">down.esales360.cn</span></span>
<span data-ttu-id="f541e-358">accountName</span><span class="sxs-lookup"><span data-stu-id="f541e-358">accountName</span></span> | <span data-ttu-id="f541e-359">Disponible si entityType es *User*.</span><span class="sxs-lookup"><span data-stu-id="f541e-359">Available if entityType is *User*.</span></span> | <span data-ttu-id="f541e-360">testUser2</span><span class="sxs-lookup"><span data-stu-id="f541e-360">testUser2</span></span>
<span data-ttu-id="f541e-361">domainName</span><span class="sxs-lookup"><span data-stu-id="f541e-361">domainName</span></span> | <span data-ttu-id="f541e-362">Disponible si entityType es *User*.</span><span class="sxs-lookup"><span data-stu-id="f541e-362">Available if entityType is *User*.</span></span> | <span data-ttu-id="f541e-363">Europa. Corp. contoso</span><span class="sxs-lookup"><span data-stu-id="f541e-363">europe.corp.contoso</span></span>
<span data-ttu-id="f541e-364">userSid</span><span class="sxs-lookup"><span data-stu-id="f541e-364">userSid</span></span> | <span data-ttu-id="f541e-365">Disponible si entityType es *User*.</span><span class="sxs-lookup"><span data-stu-id="f541e-365">Available if entityType is *User*.</span></span> | <span data-ttu-id="f541e-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="f541e-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="f541e-367">aadUserId</span><span class="sxs-lookup"><span data-stu-id="f541e-367">aadUserId</span></span> | <span data-ttu-id="f541e-368">Disponible si entityType es *User*.</span><span class="sxs-lookup"><span data-stu-id="f541e-368">Available if entityType is *User*.</span></span> | <span data-ttu-id="f541e-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="f541e-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="f541e-370">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="f541e-370">userPrincipalName</span></span> | <span data-ttu-id="f541e-371">Disponible si entityType es  / MailMessage de *buzón* de usuario / .</span><span class="sxs-lookup"><span data-stu-id="f541e-371">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="f541e-372">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f541e-372">testUser2@contoso.com</span></span>
<span data-ttu-id="f541e-373">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="f541e-373">mailboxDisplayName</span></span> | <span data-ttu-id="f541e-374">Disponible si entityType es *MailBox*.</span><span class="sxs-lookup"><span data-stu-id="f541e-374">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="f541e-375">prueba user2</span><span class="sxs-lookup"><span data-stu-id="f541e-375">test User2</span></span>
<span data-ttu-id="f541e-376">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="f541e-376">mailboxAddress</span></span> | <span data-ttu-id="f541e-377">Disponible si entityType es  / MailMessage de *buzón* de usuario / .</span><span class="sxs-lookup"><span data-stu-id="f541e-377">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="f541e-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f541e-378">testUser2@contoso.com</span></span>
<span data-ttu-id="f541e-379">clusterBy</span><span class="sxs-lookup"><span data-stu-id="f541e-379">clusterBy</span></span> | <span data-ttu-id="f541e-380">Disponible si entityType es  *MailCluster*.</span><span class="sxs-lookup"><span data-stu-id="f541e-380">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="f541e-381">Titular P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="f541e-381">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="f541e-382">sender</span><span class="sxs-lookup"><span data-stu-id="f541e-382">sender</span></span> | <span data-ttu-id="f541e-383">Disponible si entityType es  / MailMessage de *buzón* de usuario / .</span><span class="sxs-lookup"><span data-stu-id="f541e-383">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="f541e-384">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="f541e-384">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="f541e-385">destinatario</span><span class="sxs-lookup"><span data-stu-id="f541e-385">recipient</span></span> | <span data-ttu-id="f541e-386">Disponible si entityType es *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="f541e-386">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="f541e-387">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f541e-387">testUser2@contoso.com</span></span>
<span data-ttu-id="f541e-388">subject</span><span class="sxs-lookup"><span data-stu-id="f541e-388">subject</span></span> | <span data-ttu-id="f541e-389">Disponible si entityType es *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="f541e-389">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="f541e-390">\[\]Atención externa</span><span class="sxs-lookup"><span data-stu-id="f541e-390">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="f541e-391">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="f541e-391">deliveryAction</span></span> | <span data-ttu-id="f541e-392">Disponible si entityType es *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="f541e-392">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="f541e-393">Pronuncia</span><span class="sxs-lookup"><span data-stu-id="f541e-393">Delivered</span></span>
<span data-ttu-id="f541e-394">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="f541e-394">securityGroupId</span></span> | <span data-ttu-id="f541e-395">Disponible si entityType es  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="f541e-395">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="f541e-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="f541e-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="f541e-397">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="f541e-397">securityGroupName</span></span> | <span data-ttu-id="f541e-398">Disponible si entityType es  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="f541e-398">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="f541e-399">Operadores de configuración de red</span><span class="sxs-lookup"><span data-stu-id="f541e-399">Network Configuration Operators</span></span>
<span data-ttu-id="f541e-400">registryHive</span><span class="sxs-lookup"><span data-stu-id="f541e-400">registryHive</span></span> | <span data-ttu-id="f541e-401">Disponible si entityType es  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="f541e-401">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="f541e-402">HKEY \_ local \_ Machine</span><span class="sxs-lookup"><span data-stu-id="f541e-402">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="f541e-403">Deleteinstance</span><span class="sxs-lookup"><span data-stu-id="f541e-403">registryKey</span></span> | <span data-ttu-id="f541e-404">Disponible si entityType es  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="f541e-404">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="f541e-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="f541e-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="f541e-406">registryValueType</span><span class="sxs-lookup"><span data-stu-id="f541e-406">registryValueType</span></span> | <span data-ttu-id="f541e-407">Disponible si entityType es  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="f541e-407">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="f541e-408">Cadena</span><span class="sxs-lookup"><span data-stu-id="f541e-408">String</span></span>
<span data-ttu-id="f541e-409">Deleteinstance</span><span class="sxs-lookup"><span data-stu-id="f541e-409">registryValue</span></span> | <span data-ttu-id="f541e-410">Disponible si entityType es  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="f541e-410">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="f541e-411">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="f541e-411">31-00-00-00</span></span>
<span data-ttu-id="f541e-412">deviceId</span><span class="sxs-lookup"><span data-stu-id="f541e-412">deviceId</span></span> | <span data-ttu-id="f541e-413">IDENTIFICADOR, si existe, del dispositivo relacionado con la entidad.</span><span class="sxs-lookup"><span data-stu-id="f541e-413">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="f541e-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="f541e-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="f541e-415">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f541e-415">Example</span></span>

<span data-ttu-id="f541e-416">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="f541e-416">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="f541e-417">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="f541e-417">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="f541e-418">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="f541e-418">Related articles</span></span>

- [<span data-ttu-id="f541e-419">Acceso a las API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="f541e-419">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="f541e-420">Obtenga información sobre los límites de API y las licencias</span><span class="sxs-lookup"><span data-stu-id="f541e-420">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="f541e-421">Descripción de los códigos de error</span><span class="sxs-lookup"><span data-stu-id="f541e-421">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="f541e-422">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="f541e-422">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="f541e-423">API de incidentes</span><span class="sxs-lookup"><span data-stu-id="f541e-423">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="f541e-424">Actualizar la API de incidentes</span><span class="sxs-lookup"><span data-stu-id="f541e-424">Update incident API</span></span>](api-update-incidents.md)
