---
title: Obtener una actividad de corrección por id.
description: Devuelve información sobre la actividad de corrección especificada.
keywords: apis, remediation, remediation api, get, remediation tasks, list
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 40a7102a8c7dbf63641daaf47bbd9aa9f2e54649
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061168"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="2124e-104">Obtener una actividad de corrección por id.</span><span class="sxs-lookup"><span data-stu-id="2124e-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2124e-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2124e-105">**Applies to:**</span></span>

- [<span data-ttu-id="2124e-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2124e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2124e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2124e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2124e-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="2124e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2124e-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="2124e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="2124e-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="2124e-110">API description</span></span>

<span data-ttu-id="2124e-111">Devuelve información sobre la actividad de corrección especificada.</span><span class="sxs-lookup"><span data-stu-id="2124e-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="2124e-112">Presenta las mismas columnas que [Obtener toda](get-remediation-all-activities.md)la actividad de corrección ", pero devuelve resultados solo para la actividad _de corrección especificada_.</span><span class="sxs-lookup"><span data-stu-id="2124e-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="2124e-113">[Obtenga más información sobre las actividades de corrección](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="2124e-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="2124e-114">Enumerar una actividad de corrección especificada para (id)</span><span class="sxs-lookup"><span data-stu-id="2124e-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="2124e-115">**DIRECCIÓN URL:** GET: /api/remediationTasks/ \{ id\}</span><span class="sxs-lookup"><span data-stu-id="2124e-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

<span data-ttu-id="2124e-116">**Detalles de** propiedades</span><span class="sxs-lookup"><span data-stu-id="2124e-116">**Properties** details</span></span>

<span data-ttu-id="2124e-117">Propiedad (id)</span><span class="sxs-lookup"><span data-stu-id="2124e-117">Property (id)</span></span> | <span data-ttu-id="2124e-118">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2124e-118">Data type</span></span> | <span data-ttu-id="2124e-119">Description</span><span class="sxs-lookup"><span data-stu-id="2124e-119">Description</span></span> | <span data-ttu-id="2124e-120">Ejemplo de un valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2124e-120">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="2124e-121">categoría</span><span class="sxs-lookup"><span data-stu-id="2124e-121">category</span></span> | <span data-ttu-id="2124e-122">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-122">String</span></span> | <span data-ttu-id="2124e-123">Categoría de la actividad de corrección (configuración software/seguridad)</span><span class="sxs-lookup"><span data-stu-id="2124e-123">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="2124e-124">Software</span><span class="sxs-lookup"><span data-stu-id="2124e-124">Software</span></span>
<span data-ttu-id="2124e-125">completerEmail</span><span class="sxs-lookup"><span data-stu-id="2124e-125">completerEmail</span></span> | <span data-ttu-id="2124e-126">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-126">String</span></span> | <span data-ttu-id="2124e-127">Si alguien completó manualmente la actividad de corrección, esta columna contiene su correo electrónico</span><span class="sxs-lookup"><span data-stu-id="2124e-127">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="2124e-128">nulo</span><span class="sxs-lookup"><span data-stu-id="2124e-128">null</span></span>
<span data-ttu-id="2124e-129">completerId</span><span class="sxs-lookup"><span data-stu-id="2124e-129">completerId</span></span> | <span data-ttu-id="2124e-130">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-130">String</span></span> | <span data-ttu-id="2124e-131">Si alguien completó la actividad de corrección manualmente, esta columna contiene su identificador de objeto</span><span class="sxs-lookup"><span data-stu-id="2124e-131">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="2124e-132">nulo</span><span class="sxs-lookup"><span data-stu-id="2124e-132">null</span></span>
<span data-ttu-id="2124e-133">completionMethod</span><span class="sxs-lookup"><span data-stu-id="2124e-133">completionMethod</span></span> | <span data-ttu-id="2124e-134">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-134">String</span></span> | <span data-ttu-id="2124e-135">Una actividad de corrección se puede completar "automáticamente" (si todos los dispositivos están parcheados) o "manualmente" por una persona que selecciona "marcar como completada"</span><span class="sxs-lookup"><span data-stu-id="2124e-135">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="2124e-136">Automático</span><span class="sxs-lookup"><span data-stu-id="2124e-136">Automatic</span></span>
<span data-ttu-id="2124e-137">createdOn</span><span class="sxs-lookup"><span data-stu-id="2124e-137">createdOn</span></span> | <span data-ttu-id="2124e-138">DateTime</span><span class="sxs-lookup"><span data-stu-id="2124e-138">DateTime</span></span> | <span data-ttu-id="2124e-139">Hora en que se creó esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="2124e-139">Time this remediation activity was created</span></span> | <span data-ttu-id="2124e-140">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="2124e-140">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="2124e-141">description</span><span class="sxs-lookup"><span data-stu-id="2124e-141">description</span></span> | <span data-ttu-id="2124e-142">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-142">String</span></span> | <span data-ttu-id="2124e-143">Descripción de esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="2124e-143">Description of this remediation activity</span></span> | <span data-ttu-id="2124e-144">Actualiza Chrome a una versión posterior para mitigar las 1248 vulnerabilidades conocidas que afectan a tus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2124e-144">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="2124e-145">dueOn</span><span class="sxs-lookup"><span data-stu-id="2124e-145">dueOn</span></span> | <span data-ttu-id="2124e-146">DateTime</span><span class="sxs-lookup"><span data-stu-id="2124e-146">DateTime</span></span> | <span data-ttu-id="2124e-147">Fecha de vencimiento que el creador estableció para esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="2124e-147">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="2124e-148">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="2124e-148">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="2124e-149">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="2124e-149">fixedDevices</span></span> |  | <span data-ttu-id="2124e-150">Número de dispositivos que se han corregido</span><span class="sxs-lookup"><span data-stu-id="2124e-150">The number of devices that have been fixed</span></span> | <span data-ttu-id="2124e-151">2</span><span class="sxs-lookup"><span data-stu-id="2124e-151">2</span></span>
<span data-ttu-id="2124e-152">id</span><span class="sxs-lookup"><span data-stu-id="2124e-152">id</span></span> | <span data-ttu-id="2124e-153">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-153">String</span></span> | <span data-ttu-id="2124e-154">Identificador de esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="2124e-154">ID of this remediation activity</span></span> | <span data-ttu-id="2124e-155">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="2124e-155">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="2124e-156">nameId</span><span class="sxs-lookup"><span data-stu-id="2124e-156">nameId</span></span> | <span data-ttu-id="2124e-157">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-157">String</span></span> | <span data-ttu-id="2124e-158">Nombre del producto relacionado</span><span class="sxs-lookup"><span data-stu-id="2124e-158">Related product name</span></span> | <span data-ttu-id="2124e-159">chrome</span><span class="sxs-lookup"><span data-stu-id="2124e-159">chrome</span></span>
<span data-ttu-id="2124e-160">priority</span><span class="sxs-lookup"><span data-stu-id="2124e-160">priority</span></span> | <span data-ttu-id="2124e-161">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-161">String</span></span> | <span data-ttu-id="2124e-162">Prioridad del conjunto de creadores para esta actividad de corrección (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="2124e-162">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="2124e-163">Alto</span><span class="sxs-lookup"><span data-stu-id="2124e-163">High</span></span>
<span data-ttu-id="2124e-164">productId</span><span class="sxs-lookup"><span data-stu-id="2124e-164">productId</span></span> | <span data-ttu-id="2124e-165">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-165">String</span></span> | <span data-ttu-id="2124e-166">Id. de producto relacionado</span><span class="sxs-lookup"><span data-stu-id="2124e-166">Related product ID</span></span> | <span data-ttu-id="2124e-167">google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="2124e-167">google-_-chrome</span></span>
<span data-ttu-id="2124e-168">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="2124e-168">productivityImpactRemediationType</span></span> | <span data-ttu-id="2124e-169">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-169">String</span></span> | <span data-ttu-id="2124e-170">Solo se podrían solicitar algunos cambios de configuración para dispositivos sin impacto del usuario.</span><span class="sxs-lookup"><span data-stu-id="2124e-170">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="2124e-171">Este valor indica la selección entre "todos los dispositivos expuestos" o "solo dispositivos sin impacto del usuario".</span><span class="sxs-lookup"><span data-stu-id="2124e-171">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="2124e-172">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="2124e-172">AllExposedAssets</span></span>
<span data-ttu-id="2124e-173">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="2124e-173">rbacGroupNames</span></span> | <span data-ttu-id="2124e-174">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-174">String</span></span> | <span data-ttu-id="2124e-175">Nombres de grupo de dispositivos relacionados</span><span class="sxs-lookup"><span data-stu-id="2124e-175">Related device group names</span></span> | <span data-ttu-id="2124e-176">[ "Servidores de Windows", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="2124e-176">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="2124e-177">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="2124e-177">recommendedProgram</span></span> | <span data-ttu-id="2124e-178">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-178">String</span></span> | <span data-ttu-id="2124e-179">Programa recomendado para actualizar a</span><span class="sxs-lookup"><span data-stu-id="2124e-179">Recommended program to upgrade to</span></span> | <span data-ttu-id="2124e-180">nulo</span><span class="sxs-lookup"><span data-stu-id="2124e-180">null</span></span>
<span data-ttu-id="2124e-181">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="2124e-181">recommendedVendor</span></span> | <span data-ttu-id="2124e-182">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-182">String</span></span> | <span data-ttu-id="2124e-183">Proveedor recomendado para actualizar a</span><span class="sxs-lookup"><span data-stu-id="2124e-183">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="2124e-184">nulo</span><span class="sxs-lookup"><span data-stu-id="2124e-184">null</span></span>
<span data-ttu-id="2124e-185">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="2124e-185">recommendedVersion</span></span> | <span data-ttu-id="2124e-186">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-186">String</span></span> | <span data-ttu-id="2124e-187">Versión recomendada para actualizar o actualizar a</span><span class="sxs-lookup"><span data-stu-id="2124e-187">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="2124e-188">nulo</span><span class="sxs-lookup"><span data-stu-id="2124e-188">null</span></span>
<span data-ttu-id="2124e-189">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="2124e-189">relatedComponent</span></span> | <span data-ttu-id="2124e-190">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-190">String</span></span> | <span data-ttu-id="2124e-191">Componente relacionado de esta actividad de corrección (similar al componente relacionado para una recomendación de seguridad)</span><span class="sxs-lookup"><span data-stu-id="2124e-191">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="2124e-192">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="2124e-192">Google Chrome</span></span>
<span data-ttu-id="2124e-193">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="2124e-193">requesterEmail</span></span> | <span data-ttu-id="2124e-194">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-194">String</span></span> | <span data-ttu-id="2124e-195">Dirección de correo electrónico del creador</span><span class="sxs-lookup"><span data-stu-id="2124e-195">Creator email address</span></span> | <span data-ttu-id="2124e-196">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2124e-196">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="2124e-197">requesterId</span><span class="sxs-lookup"><span data-stu-id="2124e-197">requesterId</span></span> | <span data-ttu-id="2124e-198">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-198">String</span></span> | <span data-ttu-id="2124e-199">Id. de objeto Creator</span><span class="sxs-lookup"><span data-stu-id="2124e-199">Creator object id</span></span> | <span data-ttu-id="2124e-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="2124e-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="2124e-201">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="2124e-201">requesterNotes</span></span> | <span data-ttu-id="2124e-202">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-202">String</span></span> | <span data-ttu-id="2124e-203">Las notas (texto libre) que el creador agregó para esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="2124e-203">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="2124e-204">nulo</span><span class="sxs-lookup"><span data-stu-id="2124e-204">null</span></span>
<span data-ttu-id="2124e-205">scid</span><span class="sxs-lookup"><span data-stu-id="2124e-205">scid</span></span> | <span data-ttu-id="2124e-206">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-206">String</span></span> | <span data-ttu-id="2124e-207">SCID de la recomendación de seguridad relacionada</span><span class="sxs-lookup"><span data-stu-id="2124e-207">SCID of the related security recommendation</span></span> | <span data-ttu-id="2124e-208">nulo</span><span class="sxs-lookup"><span data-stu-id="2124e-208">null</span></span>
<span data-ttu-id="2124e-209">status</span><span class="sxs-lookup"><span data-stu-id="2124e-209">status</span></span> | <span data-ttu-id="2124e-210">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-210">String</span></span> | <span data-ttu-id="2124e-211">Estado de la actividad de corrección (Activo/Completado)</span><span class="sxs-lookup"><span data-stu-id="2124e-211">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="2124e-212">Activo</span><span class="sxs-lookup"><span data-stu-id="2124e-212">Active</span></span>
<span data-ttu-id="2124e-213">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="2124e-213">statusLastModifiedOn</span></span> | <span data-ttu-id="2124e-214">DateTime</span><span class="sxs-lookup"><span data-stu-id="2124e-214">DateTime</span></span> | <span data-ttu-id="2124e-215">Fecha en la que se actualizó el campo de estado</span><span class="sxs-lookup"><span data-stu-id="2124e-215">Date when the status field was updated</span></span> | <span data-ttu-id="2124e-216">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="2124e-216">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="2124e-217">targetDevices</span><span class="sxs-lookup"><span data-stu-id="2124e-217">targetDevices</span></span> | <span data-ttu-id="2124e-218">Long</span><span class="sxs-lookup"><span data-stu-id="2124e-218">Long</span></span> | <span data-ttu-id="2124e-219">Número de dispositivos expuestos a los que se aplica esta corrección</span><span class="sxs-lookup"><span data-stu-id="2124e-219">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="2124e-220">43</span><span class="sxs-lookup"><span data-stu-id="2124e-220">43</span></span>
<span data-ttu-id="2124e-221">title</span><span class="sxs-lookup"><span data-stu-id="2124e-221">title</span></span> | <span data-ttu-id="2124e-222">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-222">String</span></span> | <span data-ttu-id="2124e-223">Título de esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="2124e-223">Title of this remediation activity</span></span> | <span data-ttu-id="2124e-224">Actualizar Google Chrome</span><span class="sxs-lookup"><span data-stu-id="2124e-224">Update Google Chrome</span></span>
<span data-ttu-id="2124e-225">type</span><span class="sxs-lookup"><span data-stu-id="2124e-225">type</span></span> | <span data-ttu-id="2124e-226">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-226">String</span></span> | <span data-ttu-id="2124e-227">Tipo de corrección</span><span class="sxs-lookup"><span data-stu-id="2124e-227">Remediation type</span></span> | <span data-ttu-id="2124e-228">Actualizar</span><span class="sxs-lookup"><span data-stu-id="2124e-228">Update</span></span>
<span data-ttu-id="2124e-229">vendorId</span><span class="sxs-lookup"><span data-stu-id="2124e-229">vendorId</span></span> | <span data-ttu-id="2124e-230">Cadena</span><span class="sxs-lookup"><span data-stu-id="2124e-230">String</span></span> | <span data-ttu-id="2124e-231">Nombre de proveedor relacionado</span><span class="sxs-lookup"><span data-stu-id="2124e-231">Related vendor name</span></span> | <span data-ttu-id="2124e-232">google</span><span class="sxs-lookup"><span data-stu-id="2124e-232">google</span></span>

## <a name="example"></a><span data-ttu-id="2124e-233">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2124e-233">Example</span></span>

<span data-ttu-id="2124e-234">**Ejemplo de** solicitud</span><span class="sxs-lookup"><span data-stu-id="2124e-234">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

<span data-ttu-id="2124e-235">**Ejemplo de** respuesta</span><span class="sxs-lookup"><span data-stu-id="2124e-235">**Response** example</span></span>

```json
{ 
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks/$entity", 
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c", 
    "title": "Update Microsoft Silverlight", 
    "createdOn": "2021-02-10T13:20:36.4718166Z", 
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4", 
    "requesterEmail": "user1@contoso.com", 
    "status": "Active", 
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z", 
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ", 
    "relatedComponent": "Microsoft Silverlight", 
    "targetDevices": 18511, 
    "rbacGroupNames": [ 
        "UnassignedGroup", 
        "hhh" 
    ], 
    "fixedDevices": 2866, 
    "requesterNotes": "test", 
    "dueOn": "2021-02-11T00:00:00Z", 
    "category": "Software", 
    "productivityImpactRemediationType": null, 
    "priority": "Medium", 
    "completionMethod": null, 
    "completerId": null, 
    "completerEmail": null, 
    "scid": null, 
    "type": "Update", 
    "productId": "microsoft-_-silverlight", 
    "vendorId": "microsoft", 
    "nameId": "silverlight", 
    "recommendedVersion": null, 
    "recommendedVendor": null, 
    "recommendedProgram": null 
} 
```

## <a name="see-also"></a><span data-ttu-id="2124e-236">Vea también</span><span class="sxs-lookup"><span data-stu-id="2124e-236">See also</span></span>

- [<span data-ttu-id="2124e-237">Propiedades y métodos de corrección</span><span class="sxs-lookup"><span data-stu-id="2124e-237">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="2124e-238">Enumerar todas las actividades de corrección</span><span class="sxs-lookup"><span data-stu-id="2124e-238">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="2124e-239">Enumerar dispositivos expuestos de una actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="2124e-239">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="2124e-240">Administración de vulnerabilidades & amenazas basadas en riesgos</span><span class="sxs-lookup"><span data-stu-id="2124e-240">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="2124e-241">Vulnerabilidades de la organización</span><span class="sxs-lookup"><span data-stu-id="2124e-241">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
