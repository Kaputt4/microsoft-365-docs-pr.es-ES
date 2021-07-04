---
title: OBTENER API de alertas
description: Obtenga información sobre los métodos y propiedades del tipo de recurso Alert en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: df1a032ffab0490c41edc7d282f0f2cc60608870
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289684"
---
# <a name="alert-resource-type"></a><span data-ttu-id="19cb0-104">Tipo de recurso Alert</span><span class="sxs-lookup"><span data-stu-id="19cb0-104">Alert resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="19cb0-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="19cb0-105">**Applies to:**</span></span>
- [<span data-ttu-id="19cb0-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="19cb0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="19cb0-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="19cb0-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="19cb0-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="19cb0-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a><span data-ttu-id="19cb0-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="19cb0-109">Methods</span></span>

<span data-ttu-id="19cb0-110">Método</span><span class="sxs-lookup"><span data-stu-id="19cb0-110">Method</span></span> |<span data-ttu-id="19cb0-111">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="19cb0-111">Return Type</span></span> |<span data-ttu-id="19cb0-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="19cb0-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="19cb0-113">Obtener alerta</span><span class="sxs-lookup"><span data-stu-id="19cb0-113">Get alert</span></span>](get-alert-info-by-id.md) | [<span data-ttu-id="19cb0-114">Alerta</span><span class="sxs-lookup"><span data-stu-id="19cb0-114">Alert</span></span>](alerts.md) | <span data-ttu-id="19cb0-115">Obtener un único [objeto de](alerts.md) alerta.</span><span class="sxs-lookup"><span data-stu-id="19cb0-115">Get a single [alert](alerts.md) object.</span></span>
[<span data-ttu-id="19cb0-116">Listar alertas</span><span class="sxs-lookup"><span data-stu-id="19cb0-116">List alerts</span></span>](get-alerts.md) | <span data-ttu-id="19cb0-117">[Colección Alert](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="19cb0-117">[Alert](alerts.md) collection</span></span> | <span data-ttu-id="19cb0-118">Enumerar [la colección de](alerts.md) alertas.</span><span class="sxs-lookup"><span data-stu-id="19cb0-118">List [alert](alerts.md) collection.</span></span>
[<span data-ttu-id="19cb0-119">Update alert</span><span class="sxs-lookup"><span data-stu-id="19cb0-119">Update alert</span></span>](update-alert.md) | [<span data-ttu-id="19cb0-120">Alerta</span><span class="sxs-lookup"><span data-stu-id="19cb0-120">Alert</span></span>](alerts.md) | <span data-ttu-id="19cb0-121">Actualizar alerta [específica](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="19cb0-121">Update specific [alert](alerts.md).</span></span>
[<span data-ttu-id="19cb0-122">Alertas de actualización por lotes</span><span class="sxs-lookup"><span data-stu-id="19cb0-122">Batch update alerts</span></span>](batch-update-alerts.md) | | <span data-ttu-id="19cb0-123">Actualizar un lote de [alertas](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="19cb0-123">Update a batch of [alerts](alerts.md).</span></span>
[<span data-ttu-id="19cb0-124">Crear alerta</span><span class="sxs-lookup"><span data-stu-id="19cb0-124">Create alert</span></span>](create-alert-by-reference.md)|[<span data-ttu-id="19cb0-125">Alerta</span><span class="sxs-lookup"><span data-stu-id="19cb0-125">Alert</span></span>](alerts.md)|<span data-ttu-id="19cb0-126">Crear una alerta basada en los datos de eventos obtenidos de [la búsqueda avanzada](run-advanced-query-api.md).</span><span class="sxs-lookup"><span data-stu-id="19cb0-126">Create an alert based on event data obtained from [Advanced Hunting](run-advanced-query-api.md).</span></span>
[<span data-ttu-id="19cb0-127">Enumerar dominios relacionados</span><span class="sxs-lookup"><span data-stu-id="19cb0-127">List related domains</span></span>](get-alert-related-domain-info.md)|<span data-ttu-id="19cb0-128">Colección domain</span><span class="sxs-lookup"><span data-stu-id="19cb0-128">Domain collection</span></span>| <span data-ttu-id="19cb0-129">Enumerar las direcciones URL asociadas con la alerta.</span><span class="sxs-lookup"><span data-stu-id="19cb0-129">List URLs associated with the alert.</span></span>
[<span data-ttu-id="19cb0-130">Enumerar archivos relacionados</span><span class="sxs-lookup"><span data-stu-id="19cb0-130">List related files</span></span>](get-alert-related-files-info.md) | <span data-ttu-id="19cb0-131">[Colección de](files.md) archivos</span><span class="sxs-lookup"><span data-stu-id="19cb0-131">[File](files.md) collection</span></span> |  <span data-ttu-id="19cb0-132">Enumerar [las entidades](files.md) de archivo asociadas a la [alerta](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="19cb0-132">List the [file](files.md) entities that are associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="19cb0-133">Enumerar direcciones IP relacionadas</span><span class="sxs-lookup"><span data-stu-id="19cb0-133">List related IPs</span></span>](get-alert-related-ip-info.md) | <span data-ttu-id="19cb0-134">Colección IP</span><span class="sxs-lookup"><span data-stu-id="19cb0-134">IP collection</span></span> | <span data-ttu-id="19cb0-135">Enumerar direcciones IP asociadas a la alerta.</span><span class="sxs-lookup"><span data-stu-id="19cb0-135">List IPs that are associated with the alert.</span></span>
[<span data-ttu-id="19cb0-136">Obtener máquinas relacionadas</span><span class="sxs-lookup"><span data-stu-id="19cb0-136">Get related machines</span></span>](get-alert-related-machine-info.md) | [<span data-ttu-id="19cb0-137">Máquina</span><span class="sxs-lookup"><span data-stu-id="19cb0-137">Machine</span></span>](machine.md) | <span data-ttu-id="19cb0-138">El [equipo](machine.md) asociado a la [alerta](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="19cb0-138">The [machine](machine.md) that is associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="19cb0-139">Obtener usuarios relacionados</span><span class="sxs-lookup"><span data-stu-id="19cb0-139">Get related users</span></span>](get-alert-related-user-info.md) | [<span data-ttu-id="19cb0-140">Usuario</span><span class="sxs-lookup"><span data-stu-id="19cb0-140">User</span></span>](user.md) | <span data-ttu-id="19cb0-141">El [usuario](user.md) asociado a la [alerta](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="19cb0-141">The [user](user.md) that is associated with the [alert](alerts.md).</span></span>

## <a name="properties"></a><span data-ttu-id="19cb0-142">Propiedades</span><span class="sxs-lookup"><span data-stu-id="19cb0-142">Properties</span></span>

<span data-ttu-id="19cb0-143">Propiedad</span><span class="sxs-lookup"><span data-stu-id="19cb0-143">Property</span></span> |    <span data-ttu-id="19cb0-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="19cb0-144">Type</span></span>    |    <span data-ttu-id="19cb0-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="19cb0-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="19cb0-146">id</span><span class="sxs-lookup"><span data-stu-id="19cb0-146">id</span></span> | <span data-ttu-id="19cb0-147">Cadena</span><span class="sxs-lookup"><span data-stu-id="19cb0-147">String</span></span> | <span data-ttu-id="19cb0-148">Id. de alerta.</span><span class="sxs-lookup"><span data-stu-id="19cb0-148">Alert ID.</span></span>
<span data-ttu-id="19cb0-149">title</span><span class="sxs-lookup"><span data-stu-id="19cb0-149">title</span></span> | <span data-ttu-id="19cb0-150">String</span><span class="sxs-lookup"><span data-stu-id="19cb0-150">String</span></span> | <span data-ttu-id="19cb0-151">Título de la alerta.</span><span class="sxs-lookup"><span data-stu-id="19cb0-151">Alert title.</span></span>
<span data-ttu-id="19cb0-152">description</span><span class="sxs-lookup"><span data-stu-id="19cb0-152">description</span></span> | <span data-ttu-id="19cb0-153">String</span><span class="sxs-lookup"><span data-stu-id="19cb0-153">String</span></span> | <span data-ttu-id="19cb0-154">Descripción de la alerta.</span><span class="sxs-lookup"><span data-stu-id="19cb0-154">Alert description.</span></span>
<span data-ttu-id="19cb0-155">alertCreationTime</span><span class="sxs-lookup"><span data-stu-id="19cb0-155">alertCreationTime</span></span> | <span data-ttu-id="19cb0-156">DateTimeOffset que admite valores NULL</span><span class="sxs-lookup"><span data-stu-id="19cb0-156">Nullable DateTimeOffset</span></span> | <span data-ttu-id="19cb0-157">La fecha y hora (en UTC) se creó la alerta.</span><span class="sxs-lookup"><span data-stu-id="19cb0-157">The date and time (in UTC) the alert was created.</span></span>
<span data-ttu-id="19cb0-158">lastEventTime</span><span class="sxs-lookup"><span data-stu-id="19cb0-158">lastEventTime</span></span> | <span data-ttu-id="19cb0-159">DateTimeOffset que admite valores NULL</span><span class="sxs-lookup"><span data-stu-id="19cb0-159">Nullable DateTimeOffset</span></span> | <span data-ttu-id="19cb0-160">La última aparición del evento que desencadenó la alerta en el mismo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="19cb0-160">The last occurrence of the event that triggered the alert on the same device.</span></span>
<span data-ttu-id="19cb0-161">firstEventTime</span><span class="sxs-lookup"><span data-stu-id="19cb0-161">firstEventTime</span></span> | <span data-ttu-id="19cb0-162">DateTimeOffset que admite valores NULL</span><span class="sxs-lookup"><span data-stu-id="19cb0-162">Nullable DateTimeOffset</span></span> | <span data-ttu-id="19cb0-163">La primera aparición del evento que desencadenó la alerta en ese dispositivo.</span><span class="sxs-lookup"><span data-stu-id="19cb0-163">The first occurrence of the event that triggered the alert on that device.</span></span>
<span data-ttu-id="19cb0-164">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="19cb0-164">lastUpdateTime</span></span> | <span data-ttu-id="19cb0-165">DateTimeOffset que admite valores NULL</span><span class="sxs-lookup"><span data-stu-id="19cb0-165">Nullable DateTimeOffset</span></span> | <span data-ttu-id="19cb0-166">La fecha y hora (en UTC) la alerta se actualizó por última vez.</span><span class="sxs-lookup"><span data-stu-id="19cb0-166">The date and time (in UTC) the alert was last updated.</span></span>
<span data-ttu-id="19cb0-167">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="19cb0-167">resolvedTime</span></span> | <span data-ttu-id="19cb0-168">DateTimeOffset que admite valores NULL</span><span class="sxs-lookup"><span data-stu-id="19cb0-168">Nullable DateTimeOffset</span></span> | <span data-ttu-id="19cb0-169">La fecha y hora en que se cambió el estado de la alerta a "Resuelto".</span><span class="sxs-lookup"><span data-stu-id="19cb0-169">The date and time in which the status of the alert was changed to 'Resolved'.</span></span>
<span data-ttu-id="19cb0-170">incidentId</span><span class="sxs-lookup"><span data-stu-id="19cb0-170">incidentId</span></span> | <span data-ttu-id="19cb0-171">Long que admite valores NULL</span><span class="sxs-lookup"><span data-stu-id="19cb0-171">Nullable Long</span></span> | <span data-ttu-id="19cb0-172">El [identificador de](view-incidents-queue.md) incidente de la alerta.</span><span class="sxs-lookup"><span data-stu-id="19cb0-172">The [Incident](view-incidents-queue.md) ID of the Alert.</span></span>
<span data-ttu-id="19cb0-173">investigationId</span><span class="sxs-lookup"><span data-stu-id="19cb0-173">investigationId</span></span> | <span data-ttu-id="19cb0-174">Long que admite valores NULL</span><span class="sxs-lookup"><span data-stu-id="19cb0-174">Nullable Long</span></span> | <span data-ttu-id="19cb0-175">El [identificador de](automated-investigations.md) investigación relacionado con la alerta.</span><span class="sxs-lookup"><span data-stu-id="19cb0-175">The [Investigation](automated-investigations.md) ID related to the Alert.</span></span>
<span data-ttu-id="19cb0-176">investigationState</span><span class="sxs-lookup"><span data-stu-id="19cb0-176">investigationState</span></span> | <span data-ttu-id="19cb0-177">Enumeración que admite valores null</span><span class="sxs-lookup"><span data-stu-id="19cb0-177">Nullable Enum</span></span> | <span data-ttu-id="19cb0-178">El estado actual de la [investigación](automated-investigations.md).</span><span class="sxs-lookup"><span data-stu-id="19cb0-178">The current state of the [Investigation](automated-investigations.md).</span></span> <span data-ttu-id="19cb0-179">Los valores posibles son: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span><span class="sxs-lookup"><span data-stu-id="19cb0-179">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="19cb0-180">assignedTo</span><span class="sxs-lookup"><span data-stu-id="19cb0-180">assignedTo</span></span> | <span data-ttu-id="19cb0-181">Cadena</span><span class="sxs-lookup"><span data-stu-id="19cb0-181">String</span></span> | <span data-ttu-id="19cb0-182">Propietario de la alerta.</span><span class="sxs-lookup"><span data-stu-id="19cb0-182">Owner of the alert.</span></span>
<span data-ttu-id="19cb0-183">severity</span><span class="sxs-lookup"><span data-stu-id="19cb0-183">severity</span></span> | <span data-ttu-id="19cb0-184">Enum</span><span class="sxs-lookup"><span data-stu-id="19cb0-184">Enum</span></span> | <span data-ttu-id="19cb0-185">Gravedad de la alerta.</span><span class="sxs-lookup"><span data-stu-id="19cb0-185">Severity of the alert.</span></span> <span data-ttu-id="19cb0-186">Los valores posibles son: 'UnSpecified', 'Informational', 'Low', 'Medium' y 'High'.</span><span class="sxs-lookup"><span data-stu-id="19cb0-186">Possible values are: 'UnSpecified', 'Informational', 'Low', 'Medium' and 'High'.</span></span>
<span data-ttu-id="19cb0-187">status</span><span class="sxs-lookup"><span data-stu-id="19cb0-187">status</span></span> | <span data-ttu-id="19cb0-188">Enum</span><span class="sxs-lookup"><span data-stu-id="19cb0-188">Enum</span></span> | <span data-ttu-id="19cb0-189">Especifica el estado actual de la alerta.</span><span class="sxs-lookup"><span data-stu-id="19cb0-189">Specifies the current status of the alert.</span></span> <span data-ttu-id="19cb0-190">Los valores posibles son: "Desconocido", "Nuevo", "InProgress" y "Resuelto".</span><span class="sxs-lookup"><span data-stu-id="19cb0-190">Possible values are: 'Unknown', 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="19cb0-191">classification</span><span class="sxs-lookup"><span data-stu-id="19cb0-191">classification</span></span> | <span data-ttu-id="19cb0-192">Enumeración que admite valores null</span><span class="sxs-lookup"><span data-stu-id="19cb0-192">Nullable Enum</span></span> | <span data-ttu-id="19cb0-193">Especificación de la alerta.</span><span class="sxs-lookup"><span data-stu-id="19cb0-193">Specification of the alert.</span></span> <span data-ttu-id="19cb0-194">Los valores posibles son: 'Unknown', 'FalsePositive', 'TruePositive'.</span><span class="sxs-lookup"><span data-stu-id="19cb0-194">Possible values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span>
<span data-ttu-id="19cb0-195">determinación</span><span class="sxs-lookup"><span data-stu-id="19cb0-195">determination</span></span> | <span data-ttu-id="19cb0-196">Enumeración que admite valores null</span><span class="sxs-lookup"><span data-stu-id="19cb0-196">Nullable Enum</span></span> | <span data-ttu-id="19cb0-197">Especifica la determinación de la alerta.</span><span class="sxs-lookup"><span data-stu-id="19cb0-197">Specifies the determination of the alert.</span></span> <span data-ttu-id="19cb0-198">Los valores posibles son: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.</span><span class="sxs-lookup"><span data-stu-id="19cb0-198">Possible values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.</span></span>
<span data-ttu-id="19cb0-199">categoría</span><span class="sxs-lookup"><span data-stu-id="19cb0-199">category</span></span>| <span data-ttu-id="19cb0-200">Cadena</span><span class="sxs-lookup"><span data-stu-id="19cb0-200">String</span></span> | <span data-ttu-id="19cb0-201">Categoría de la alerta.</span><span class="sxs-lookup"><span data-stu-id="19cb0-201">Category of the alert.</span></span>
<span data-ttu-id="19cb0-202">detectionSource</span><span class="sxs-lookup"><span data-stu-id="19cb0-202">detectionSource</span></span> | <span data-ttu-id="19cb0-203">Cadena</span><span class="sxs-lookup"><span data-stu-id="19cb0-203">String</span></span> | <span data-ttu-id="19cb0-204">Origen de detección.</span><span class="sxs-lookup"><span data-stu-id="19cb0-204">Detection source.</span></span>
<span data-ttu-id="19cb0-205">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="19cb0-205">threatFamilyName</span></span> | <span data-ttu-id="19cb0-206">Cadena</span><span class="sxs-lookup"><span data-stu-id="19cb0-206">String</span></span> | <span data-ttu-id="19cb0-207">Familia de amenazas.</span><span class="sxs-lookup"><span data-stu-id="19cb0-207">Threat family.</span></span>
<span data-ttu-id="19cb0-208">threatName</span><span class="sxs-lookup"><span data-stu-id="19cb0-208">threatName</span></span> | <span data-ttu-id="19cb0-209">Cadena</span><span class="sxs-lookup"><span data-stu-id="19cb0-209">String</span></span> | <span data-ttu-id="19cb0-210">Nombre de la amenaza.</span><span class="sxs-lookup"><span data-stu-id="19cb0-210">Threat name.</span></span>
<span data-ttu-id="19cb0-211">machineId</span><span class="sxs-lookup"><span data-stu-id="19cb0-211">machineId</span></span> | <span data-ttu-id="19cb0-212">Cadena</span><span class="sxs-lookup"><span data-stu-id="19cb0-212">String</span></span> | <span data-ttu-id="19cb0-213">Id. de una [entidad de](machine.md) máquina asociada a la alerta.</span><span class="sxs-lookup"><span data-stu-id="19cb0-213">ID of a [machine](machine.md) entity that is associated with the alert.</span></span>
<span data-ttu-id="19cb0-214">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="19cb0-214">computerDnsName</span></span> | <span data-ttu-id="19cb0-215">Cadena</span><span class="sxs-lookup"><span data-stu-id="19cb0-215">String</span></span> | <span data-ttu-id="19cb0-216">[nombre](machine.md) completo de la máquina.</span><span class="sxs-lookup"><span data-stu-id="19cb0-216">[machine](machine.md) fully qualified name.</span></span>
<span data-ttu-id="19cb0-217">aadTenantId</span><span class="sxs-lookup"><span data-stu-id="19cb0-217">aadTenantId</span></span> | <span data-ttu-id="19cb0-218">Cadena</span><span class="sxs-lookup"><span data-stu-id="19cb0-218">String</span></span> | <span data-ttu-id="19cb0-219">El Azure Active Directory de usuario.</span><span class="sxs-lookup"><span data-stu-id="19cb0-219">The Azure Active Directory ID.</span></span>
<span data-ttu-id="19cb0-220">detectorId</span><span class="sxs-lookup"><span data-stu-id="19cb0-220">detectorId</span></span> | <span data-ttu-id="19cb0-221">Cadena</span><span class="sxs-lookup"><span data-stu-id="19cb0-221">String</span></span> | <span data-ttu-id="19cb0-222">El identificador del detector que desencadenó la alerta.</span><span class="sxs-lookup"><span data-stu-id="19cb0-222">The ID of the detector that triggered the alert.</span></span>
<span data-ttu-id="19cb0-223">comments</span><span class="sxs-lookup"><span data-stu-id="19cb0-223">comments</span></span> | <span data-ttu-id="19cb0-224">Lista de comentarios de alerta</span><span class="sxs-lookup"><span data-stu-id="19cb0-224">List of Alert comments</span></span> | <span data-ttu-id="19cb0-225">El objeto Alert Comment contiene: cadena de comentario, createdBy string y createTime date time.</span><span class="sxs-lookup"><span data-stu-id="19cb0-225">Alert Comment object contains: comment string, createdBy string and createTime date time.</span></span>
<span data-ttu-id="19cb0-226">Evidencia</span><span class="sxs-lookup"><span data-stu-id="19cb0-226">Evidence</span></span> | <span data-ttu-id="19cb0-227">Lista de pruebas de alerta</span><span class="sxs-lookup"><span data-stu-id="19cb0-227">List of Alert evidence</span></span> | <span data-ttu-id="19cb0-228">Evidencia relacionada con la alerta.</span><span class="sxs-lookup"><span data-stu-id="19cb0-228">Evidence related to the alert.</span></span> <span data-ttu-id="19cb0-229">Vea el ejemplo abajo.</span><span class="sxs-lookup"><span data-stu-id="19cb0-229">See example below.</span></span>

### <a name="response-example-for-getting-single-alert"></a><span data-ttu-id="19cb0-230">Ejemplo de respuesta para obtener una sola alerta:</span><span class="sxs-lookup"><span data-stu-id="19cb0-230">Response example for getting single alert:</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
{
    "id": "da637472900382838869_1364969609",
    "incidentId": 1126093,
    "investigationId": null,
    "assignedTo": null,
    "severity": "Low",
    "status": "New",
    "classification": null,
    "determination": null,
    "investigationState": "Queued",
    "detectionSource": "WindowsDefenderAtp",
    "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
    "category": "Execution",
    "threatFamilyName": null,
    "title": "Low-reputation arbitrary code executed by signed executable",
    "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
    "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
    "firstEventTime": "2021-01-26T20:31:32.9562661Z",
    "lastEventTime": "2021-01-26T20:31:33.0577322Z",
    "lastUpdateTime": "2021-01-26T20:33:59.2Z",
    "resolvedTime": null,
    "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
    "computerDnsName": "temp123.middleeast.corp.microsoft.com",
    "rbacGroupName": "A",
    "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
    "threatName": null,
    "mitreTechniques": [
        "T1064",
        "T1085",
        "T1220"
    ],
    "relatedUser": {
        "userName": "temp123",
        "domainName": "MIDDLEEAST"
    },
    "comments": [
        {
            "comment": "test comment for docs",
            "createdBy": "secop123@contoso.com",
            "createdTime": "2021-01-26T01:00:37.8404534Z"
        }
    ],
    "evidence": [
        {
            "entityType": "User",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": null,
            "sha256": null,
            "fileName": null,
            "filePath": null,
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": "eranb",
            "domainName": "MIDDLEEAST",
            "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
            "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
            "userPrincipalName": "temp123@microsoft.com",
            "detectionStatus": null
        },
        {
            "entityType": "Process",
            "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
            "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
            "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
            "fileName": "rundll32.exe",
            "filePath": "C:\\Windows\\SysWOW64",
            "processId": 3276,
            "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
            "processCreationTime": "2021-01-26T20:31:32.9581596Z",
            "parentProcessId": 8420,
            "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
            "parentProcessFileName": "rundll32.exe",
            "parentProcessFilePath": "C:\\Windows\\System32",
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        },
        {
            "entityType": "File",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
            "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
            "fileName": "suspicious.dll",
            "filePath": "c:\\temp",
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        }
    ]
}
```
