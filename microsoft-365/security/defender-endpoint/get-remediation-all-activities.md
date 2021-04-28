---
title: Enumerar todas las actividades de corrección
description: Devuelve información sobre todas las actividades de corrección.
keywords: apis, remediation, remediation api, get, remediation tasks,
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
ms.openlocfilehash: ac4a777136dcdfc5d7ab61ddc8d496b7452f69e2
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061160"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="71b6d-104">Enumerar todas las actividades de corrección</span><span class="sxs-lookup"><span data-stu-id="71b6d-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="71b6d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="71b6d-105">**Applies to:**</span></span>

- [<span data-ttu-id="71b6d-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="71b6d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="71b6d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71b6d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="71b6d-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="71b6d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="71b6d-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="71b6d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="71b6d-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="71b6d-110">API description</span></span>

<span data-ttu-id="71b6d-111">Devuelve información sobre todas las actividades de corrección.</span><span class="sxs-lookup"><span data-stu-id="71b6d-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="71b6d-112">[Obtenga más información sobre las actividades de corrección](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="71b6d-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="71b6d-113">**DIRECCIÓN URL:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="71b6d-113">**URL:** GET: /api/remediationTasks</span></span>

<span data-ttu-id="71b6d-114">**Detalles de** propiedades</span><span class="sxs-lookup"><span data-stu-id="71b6d-114">**Properties** details</span></span>

<span data-ttu-id="71b6d-115">Propiedad (id)</span><span class="sxs-lookup"><span data-stu-id="71b6d-115">Property (id)</span></span> | <span data-ttu-id="71b6d-116">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="71b6d-116">Data type</span></span> | <span data-ttu-id="71b6d-117">Description</span><span class="sxs-lookup"><span data-stu-id="71b6d-117">Description</span></span> | <span data-ttu-id="71b6d-118">Ejemplo de un valor devuelto</span><span class="sxs-lookup"><span data-stu-id="71b6d-118">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="71b6d-119">categoría</span><span class="sxs-lookup"><span data-stu-id="71b6d-119">category</span></span> | <span data-ttu-id="71b6d-120">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-120">String</span></span> | <span data-ttu-id="71b6d-121">Categoría de la actividad de corrección (configuración software/seguridad)</span><span class="sxs-lookup"><span data-stu-id="71b6d-121">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="71b6d-122">Software</span><span class="sxs-lookup"><span data-stu-id="71b6d-122">Software</span></span>
<span data-ttu-id="71b6d-123">completerEmail</span><span class="sxs-lookup"><span data-stu-id="71b6d-123">completerEmail</span></span> | <span data-ttu-id="71b6d-124">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-124">String</span></span> | <span data-ttu-id="71b6d-125">Si alguien completó manualmente la actividad de corrección, esta columna contiene su correo electrónico</span><span class="sxs-lookup"><span data-stu-id="71b6d-125">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="71b6d-126">nulo</span><span class="sxs-lookup"><span data-stu-id="71b6d-126">null</span></span>
<span data-ttu-id="71b6d-127">completerId</span><span class="sxs-lookup"><span data-stu-id="71b6d-127">completerId</span></span> | <span data-ttu-id="71b6d-128">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-128">String</span></span> | <span data-ttu-id="71b6d-129">Si alguien completó la actividad de corrección manualmente, esta columna contiene su identificador de objeto</span><span class="sxs-lookup"><span data-stu-id="71b6d-129">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="71b6d-130">nulo</span><span class="sxs-lookup"><span data-stu-id="71b6d-130">null</span></span>
<span data-ttu-id="71b6d-131">completionMethod</span><span class="sxs-lookup"><span data-stu-id="71b6d-131">completionMethod</span></span> | <span data-ttu-id="71b6d-132">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-132">String</span></span> | <span data-ttu-id="71b6d-133">Una actividad de corrección se puede completar "automáticamente" (si todos los dispositivos están parcheados) o "manualmente" por una persona que selecciona "marcar como completada"</span><span class="sxs-lookup"><span data-stu-id="71b6d-133">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="71b6d-134">Automático</span><span class="sxs-lookup"><span data-stu-id="71b6d-134">Automatic</span></span>
<span data-ttu-id="71b6d-135">createdOn</span><span class="sxs-lookup"><span data-stu-id="71b6d-135">createdOn</span></span> | <span data-ttu-id="71b6d-136">DateTime</span><span class="sxs-lookup"><span data-stu-id="71b6d-136">DateTime</span></span> | <span data-ttu-id="71b6d-137">Hora en que se creó esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="71b6d-137">Time this remediation activity was created</span></span> | <span data-ttu-id="71b6d-138">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="71b6d-138">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="71b6d-139">description</span><span class="sxs-lookup"><span data-stu-id="71b6d-139">description</span></span> | <span data-ttu-id="71b6d-140">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-140">String</span></span> | <span data-ttu-id="71b6d-141">Descripción de esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="71b6d-141">Description of this remediation activity</span></span> | <span data-ttu-id="71b6d-142">Actualiza Chrome a una versión posterior para mitigar las 1248 vulnerabilidades conocidas que afectan a tus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="71b6d-142">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="71b6d-143">dueOn</span><span class="sxs-lookup"><span data-stu-id="71b6d-143">dueOn</span></span> | <span data-ttu-id="71b6d-144">DateTime</span><span class="sxs-lookup"><span data-stu-id="71b6d-144">DateTime</span></span> | <span data-ttu-id="71b6d-145">Fecha de vencimiento que el creador estableció para esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="71b6d-145">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="71b6d-146">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="71b6d-146">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="71b6d-147">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="71b6d-147">fixedDevices</span></span> | <span data-ttu-id="71b6d-148">.</span><span class="sxs-lookup"><span data-stu-id="71b6d-148">.</span></span> | <span data-ttu-id="71b6d-149">Número de dispositivos que se han corregido</span><span class="sxs-lookup"><span data-stu-id="71b6d-149">The number of devices that have been fixed</span></span> | <span data-ttu-id="71b6d-150">2</span><span class="sxs-lookup"><span data-stu-id="71b6d-150">2</span></span>
<span data-ttu-id="71b6d-151">id</span><span class="sxs-lookup"><span data-stu-id="71b6d-151">id</span></span> | <span data-ttu-id="71b6d-152">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-152">String</span></span> | <span data-ttu-id="71b6d-153">Identificador de esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="71b6d-153">ID of this remediation activity</span></span> | <span data-ttu-id="71b6d-154">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="71b6d-154">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="71b6d-155">nameId</span><span class="sxs-lookup"><span data-stu-id="71b6d-155">nameId</span></span> | <span data-ttu-id="71b6d-156">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-156">String</span></span> | <span data-ttu-id="71b6d-157">Nombre del producto relacionado</span><span class="sxs-lookup"><span data-stu-id="71b6d-157">Related product name</span></span> | <span data-ttu-id="71b6d-158">chrome</span><span class="sxs-lookup"><span data-stu-id="71b6d-158">chrome</span></span>
<span data-ttu-id="71b6d-159">priority</span><span class="sxs-lookup"><span data-stu-id="71b6d-159">priority</span></span> | <span data-ttu-id="71b6d-160">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-160">String</span></span> | <span data-ttu-id="71b6d-161">Prioridad del conjunto de creadores para esta actividad de corrección (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="71b6d-161">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="71b6d-162">Alto</span><span class="sxs-lookup"><span data-stu-id="71b6d-162">High</span></span>
<span data-ttu-id="71b6d-163">productId</span><span class="sxs-lookup"><span data-stu-id="71b6d-163">productId</span></span> | <span data-ttu-id="71b6d-164">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-164">String</span></span> | <span data-ttu-id="71b6d-165">Id. de producto relacionado</span><span class="sxs-lookup"><span data-stu-id="71b6d-165">Related product ID</span></span> | <span data-ttu-id="71b6d-166">google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="71b6d-166">google-_-chrome</span></span>
<span data-ttu-id="71b6d-167">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="71b6d-167">productivityImpactRemediationType</span></span> | <span data-ttu-id="71b6d-168">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-168">String</span></span> | <span data-ttu-id="71b6d-169">Solo se podrían solicitar algunos cambios de configuración para dispositivos sin impacto del usuario.</span><span class="sxs-lookup"><span data-stu-id="71b6d-169">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="71b6d-170">Este valor indica la selección entre "todos los dispositivos expuestos" o "solo dispositivos sin impacto del usuario".</span><span class="sxs-lookup"><span data-stu-id="71b6d-170">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="71b6d-171">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="71b6d-171">AllExposedAssets</span></span>
<span data-ttu-id="71b6d-172">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="71b6d-172">rbacGroupNames</span></span> | <span data-ttu-id="71b6d-173">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-173">String</span></span> | <span data-ttu-id="71b6d-174">Nombres de grupo de dispositivos relacionados</span><span class="sxs-lookup"><span data-stu-id="71b6d-174">Related device group names</span></span> | <span data-ttu-id="71b6d-175">[ "Servidores de Windows", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="71b6d-175">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="71b6d-176">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="71b6d-176">recommendedProgram</span></span> | <span data-ttu-id="71b6d-177">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-177">String</span></span> | <span data-ttu-id="71b6d-178">Programa recomendado para actualizar a</span><span class="sxs-lookup"><span data-stu-id="71b6d-178">Recommended program to upgrade to</span></span> | <span data-ttu-id="71b6d-179">nulo</span><span class="sxs-lookup"><span data-stu-id="71b6d-179">null</span></span>
<span data-ttu-id="71b6d-180">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="71b6d-180">recommendedVendor</span></span> | <span data-ttu-id="71b6d-181">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-181">String</span></span> | <span data-ttu-id="71b6d-182">Proveedor recomendado para actualizar a</span><span class="sxs-lookup"><span data-stu-id="71b6d-182">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="71b6d-183">nulo</span><span class="sxs-lookup"><span data-stu-id="71b6d-183">null</span></span>
<span data-ttu-id="71b6d-184">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="71b6d-184">recommendedVersion</span></span> | <span data-ttu-id="71b6d-185">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-185">String</span></span> | <span data-ttu-id="71b6d-186">Versión recomendada para actualizar o actualizar a</span><span class="sxs-lookup"><span data-stu-id="71b6d-186">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="71b6d-187">nulo</span><span class="sxs-lookup"><span data-stu-id="71b6d-187">null</span></span>
<span data-ttu-id="71b6d-188">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="71b6d-188">relatedComponent</span></span> | <span data-ttu-id="71b6d-189">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-189">String</span></span> | <span data-ttu-id="71b6d-190">Componente relacionado de esta actividad de corrección (similar al componente relacionado para una recomendación de seguridad)</span><span class="sxs-lookup"><span data-stu-id="71b6d-190">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="71b6d-191">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="71b6d-191">Google Chrome</span></span>
<span data-ttu-id="71b6d-192">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="71b6d-192">requesterEmail</span></span> | <span data-ttu-id="71b6d-193">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-193">String</span></span> | <span data-ttu-id="71b6d-194">Dirección de correo electrónico del creador</span><span class="sxs-lookup"><span data-stu-id="71b6d-194">Creator email address</span></span> | <span data-ttu-id="71b6d-195">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="71b6d-195">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="71b6d-196">requesterId</span><span class="sxs-lookup"><span data-stu-id="71b6d-196">requesterId</span></span> | <span data-ttu-id="71b6d-197">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-197">String</span></span> | <span data-ttu-id="71b6d-198">Id. de objeto Creator</span><span class="sxs-lookup"><span data-stu-id="71b6d-198">Creator object id</span></span> | <span data-ttu-id="71b6d-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="71b6d-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="71b6d-200">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="71b6d-200">requesterNotes</span></span> | <span data-ttu-id="71b6d-201">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-201">String</span></span> | <span data-ttu-id="71b6d-202">Las notas (texto libre) que el creador agregó para esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="71b6d-202">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="71b6d-203">nulo</span><span class="sxs-lookup"><span data-stu-id="71b6d-203">null</span></span>
<span data-ttu-id="71b6d-204">scid</span><span class="sxs-lookup"><span data-stu-id="71b6d-204">scid</span></span> | <span data-ttu-id="71b6d-205">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-205">String</span></span> | <span data-ttu-id="71b6d-206">SCID de la recomendación de seguridad relacionada</span><span class="sxs-lookup"><span data-stu-id="71b6d-206">SCID of the related security recommendation</span></span> | <span data-ttu-id="71b6d-207">nulo</span><span class="sxs-lookup"><span data-stu-id="71b6d-207">null</span></span>
<span data-ttu-id="71b6d-208">status</span><span class="sxs-lookup"><span data-stu-id="71b6d-208">status</span></span> | <span data-ttu-id="71b6d-209">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-209">String</span></span> | <span data-ttu-id="71b6d-210">Estado de la actividad de corrección (Activo/Completado)</span><span class="sxs-lookup"><span data-stu-id="71b6d-210">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="71b6d-211">Activo</span><span class="sxs-lookup"><span data-stu-id="71b6d-211">Active</span></span>
<span data-ttu-id="71b6d-212">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="71b6d-212">statusLastModifiedOn</span></span> | <span data-ttu-id="71b6d-213">DateTime</span><span class="sxs-lookup"><span data-stu-id="71b6d-213">DateTime</span></span> | <span data-ttu-id="71b6d-214">Fecha en la que se actualizó el campo de estado</span><span class="sxs-lookup"><span data-stu-id="71b6d-214">Date when the status field was updated</span></span> | <span data-ttu-id="71b6d-215">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="71b6d-215">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="71b6d-216">targetDevices</span><span class="sxs-lookup"><span data-stu-id="71b6d-216">targetDevices</span></span> | <span data-ttu-id="71b6d-217">Long</span><span class="sxs-lookup"><span data-stu-id="71b6d-217">Long</span></span> | <span data-ttu-id="71b6d-218">Número de dispositivos expuestos a los que se aplica esta corrección</span><span class="sxs-lookup"><span data-stu-id="71b6d-218">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="71b6d-219">43</span><span class="sxs-lookup"><span data-stu-id="71b6d-219">43</span></span>
<span data-ttu-id="71b6d-220">title</span><span class="sxs-lookup"><span data-stu-id="71b6d-220">title</span></span> | <span data-ttu-id="71b6d-221">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-221">String</span></span> | <span data-ttu-id="71b6d-222">Título de esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="71b6d-222">Title of this remediation activity</span></span> | <span data-ttu-id="71b6d-223">Actualizar Google Chrome</span><span class="sxs-lookup"><span data-stu-id="71b6d-223">Update Google Chrome</span></span>
<span data-ttu-id="71b6d-224">type</span><span class="sxs-lookup"><span data-stu-id="71b6d-224">type</span></span> | <span data-ttu-id="71b6d-225">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-225">String</span></span> | <span data-ttu-id="71b6d-226">Tipo de corrección</span><span class="sxs-lookup"><span data-stu-id="71b6d-226">Remediation type</span></span> | <span data-ttu-id="71b6d-227">Actualizar</span><span class="sxs-lookup"><span data-stu-id="71b6d-227">Update</span></span>
<span data-ttu-id="71b6d-228">vendorId</span><span class="sxs-lookup"><span data-stu-id="71b6d-228">vendorId</span></span> | <span data-ttu-id="71b6d-229">Cadena</span><span class="sxs-lookup"><span data-stu-id="71b6d-229">String</span></span> | <span data-ttu-id="71b6d-230">Nombre de proveedor relacionado</span><span class="sxs-lookup"><span data-stu-id="71b6d-230">Related vendor name</span></span> | <span data-ttu-id="71b6d-231">google</span><span class="sxs-lookup"><span data-stu-id="71b6d-231">google</span></span>

## <a name="example"></a><span data-ttu-id="71b6d-232">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="71b6d-232">Example</span></span>

<span data-ttu-id="71b6d-233">**Ejemplo de** solicitud</span><span class="sxs-lookup"><span data-stu-id="71b6d-233">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

<span data-ttu-id="71b6d-234">**Ejemplo de** respuesta</span><span class="sxs-lookup"><span data-stu-id="71b6d-234">**Response** example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks",
    "value": [
        {
            "id": "03942ef5-aewb-4w6e-b555-d6a97013844w",
            "title": "Update Microsoft Silverlight",
            "createdOn": "2021-02-10T13:20:36.4718166Z",
            "requesterId": "65548a1d-ef00-4a7a-8d19-1b967b5c36f4",
            "requesterEmail": "user1@contoso.com",
            "status": "Active",
            "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
            "description": "Update Silverlight to a later version  to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ",
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
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="71b6d-235">Vea también</span><span class="sxs-lookup"><span data-stu-id="71b6d-235">See also</span></span>

- [<span data-ttu-id="71b6d-236">Propiedades y métodos de corrección</span><span class="sxs-lookup"><span data-stu-id="71b6d-236">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="71b6d-237">Obtener una actividad de corrección por id.</span><span class="sxs-lookup"><span data-stu-id="71b6d-237">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="71b6d-238">Enumerar dispositivos expuestos de una actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="71b6d-238">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="71b6d-239">Administración de vulnerabilidades & amenazas basadas en riesgos</span><span class="sxs-lookup"><span data-stu-id="71b6d-239">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="71b6d-240">Vulnerabilidades de la organización</span><span class="sxs-lookup"><span data-stu-id="71b6d-240">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
