---
title: Enumerar todas las actividades de corrección
description: Devuelve información sobre todas las actividades de corrección.
keywords: apis, remediation, remediation api, get, remediation tasks, all remediation,
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 60f80e78a5f5c7da44a218c30f4b0173d4ecc829
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845143"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="481e6-104">Enumerar todas las actividades de corrección</span><span class="sxs-lookup"><span data-stu-id="481e6-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="481e6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="481e6-105">**Applies to:**</span></span>

- [<span data-ttu-id="481e6-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="481e6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="481e6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="481e6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="481e6-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="481e6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="481e6-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="481e6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="481e6-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="481e6-110">API description</span></span>

<span data-ttu-id="481e6-111">Devuelve información sobre todas las actividades de corrección.</span><span class="sxs-lookup"><span data-stu-id="481e6-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="481e6-112">[Obtenga más información sobre las actividades de corrección](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="481e6-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="481e6-113">**DIRECCIÓN URL:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="481e6-113">**URL:** GET: /api/remediationTasks</span></span>

## <a name="permissions"></a><span data-ttu-id="481e6-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="481e6-114">Permissions</span></span>

<span data-ttu-id="481e6-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="481e6-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="481e6-116">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="481e6-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="481e6-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="481e6-117">Permission type</span></span> | <span data-ttu-id="481e6-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="481e6-118">Permission</span></span> | <span data-ttu-id="481e6-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="481e6-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="481e6-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="481e6-120">Application</span></span> | <span data-ttu-id="481e6-121">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="481e6-121">RemediationTask.Read.All</span></span> | <span data-ttu-id="481e6-122">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="481e6-122">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="481e6-123">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="481e6-123">Delegated (work or school account)</span></span> | <span data-ttu-id="481e6-124">RemediationTask.Read</span><span class="sxs-lookup"><span data-stu-id="481e6-124">RemediationTask.Read</span></span> | <span data-ttu-id="481e6-125">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="481e6-125">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="481e6-126">Propiedades</span><span class="sxs-lookup"><span data-stu-id="481e6-126">Properties</span></span>

<span data-ttu-id="481e6-127">Propiedad (id)</span><span class="sxs-lookup"><span data-stu-id="481e6-127">Property (id)</span></span> | <span data-ttu-id="481e6-128">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="481e6-128">Data type</span></span> | <span data-ttu-id="481e6-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="481e6-129">Description</span></span> | <span data-ttu-id="481e6-130">Ejemplo de un valor devuelto</span><span class="sxs-lookup"><span data-stu-id="481e6-130">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="481e6-131">categoría</span><span class="sxs-lookup"><span data-stu-id="481e6-131">category</span></span> | <span data-ttu-id="481e6-132">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-132">String</span></span> | <span data-ttu-id="481e6-133">Categoría de la actividad de corrección (configuración software/seguridad)</span><span class="sxs-lookup"><span data-stu-id="481e6-133">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="481e6-134">Software</span><span class="sxs-lookup"><span data-stu-id="481e6-134">Software</span></span>
<span data-ttu-id="481e6-135">completerEmail</span><span class="sxs-lookup"><span data-stu-id="481e6-135">completerEmail</span></span> | <span data-ttu-id="481e6-136">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-136">String</span></span> | <span data-ttu-id="481e6-137">Si alguien completó manualmente la actividad de corrección, esta columna contiene su correo electrónico</span><span class="sxs-lookup"><span data-stu-id="481e6-137">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="481e6-138">nulo</span><span class="sxs-lookup"><span data-stu-id="481e6-138">null</span></span>
<span data-ttu-id="481e6-139">completerId</span><span class="sxs-lookup"><span data-stu-id="481e6-139">completerId</span></span> | <span data-ttu-id="481e6-140">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-140">String</span></span> | <span data-ttu-id="481e6-141">Si alguien completó la actividad de corrección manualmente, esta columna contiene su identificador de objeto</span><span class="sxs-lookup"><span data-stu-id="481e6-141">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="481e6-142">nulo</span><span class="sxs-lookup"><span data-stu-id="481e6-142">null</span></span>
<span data-ttu-id="481e6-143">completionMethod</span><span class="sxs-lookup"><span data-stu-id="481e6-143">completionMethod</span></span> | <span data-ttu-id="481e6-144">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-144">String</span></span> | <span data-ttu-id="481e6-145">Una actividad de corrección se puede completar "automáticamente" (si todos los dispositivos están parcheados) o "manualmente" por una persona que selecciona "marcar como completada"</span><span class="sxs-lookup"><span data-stu-id="481e6-145">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="481e6-146">Automático</span><span class="sxs-lookup"><span data-stu-id="481e6-146">Automatic</span></span>
<span data-ttu-id="481e6-147">createdOn</span><span class="sxs-lookup"><span data-stu-id="481e6-147">createdOn</span></span> | <span data-ttu-id="481e6-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="481e6-148">DateTime</span></span> | <span data-ttu-id="481e6-149">Hora en que se creó esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="481e6-149">Time this remediation activity was created</span></span> | <span data-ttu-id="481e6-150">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="481e6-150">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="481e6-151">descripción</span><span class="sxs-lookup"><span data-stu-id="481e6-151">description</span></span> | <span data-ttu-id="481e6-152">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-152">String</span></span> | <span data-ttu-id="481e6-153">Descripción de esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="481e6-153">Description of this remediation activity</span></span> | <span data-ttu-id="481e6-154">Actualiza Microsoft Silverlight a una versión posterior para mitigar las vulnerabilidades conocidas que afectan a los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="481e6-154">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="481e6-155">dueOn</span><span class="sxs-lookup"><span data-stu-id="481e6-155">dueOn</span></span> | <span data-ttu-id="481e6-156">DateTime</span><span class="sxs-lookup"><span data-stu-id="481e6-156">DateTime</span></span> | <span data-ttu-id="481e6-157">Fecha de vencimiento que el creador estableció para esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="481e6-157">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="481e6-158">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="481e6-158">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="481e6-159">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="481e6-159">fixedDevices</span></span> | <span data-ttu-id="481e6-160">.</span><span class="sxs-lookup"><span data-stu-id="481e6-160">.</span></span> | <span data-ttu-id="481e6-161">Número de dispositivos que se han corregido</span><span class="sxs-lookup"><span data-stu-id="481e6-161">The number of devices that have been fixed</span></span> | <span data-ttu-id="481e6-162">2</span><span class="sxs-lookup"><span data-stu-id="481e6-162">2</span></span>
<span data-ttu-id="481e6-163">id</span><span class="sxs-lookup"><span data-stu-id="481e6-163">id</span></span> | <span data-ttu-id="481e6-164">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-164">String</span></span> | <span data-ttu-id="481e6-165">Identificador de esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="481e6-165">ID of this remediation activity</span></span> | <span data-ttu-id="481e6-166">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="481e6-166">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="481e6-167">nameId</span><span class="sxs-lookup"><span data-stu-id="481e6-167">nameId</span></span> | <span data-ttu-id="481e6-168">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-168">String</span></span> | <span data-ttu-id="481e6-169">Nombre del producto relacionado</span><span class="sxs-lookup"><span data-stu-id="481e6-169">Related product name</span></span> | <span data-ttu-id="481e6-170">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="481e6-170">Microsoft Silverlight</span></span>
<span data-ttu-id="481e6-171">priority</span><span class="sxs-lookup"><span data-stu-id="481e6-171">priority</span></span> | <span data-ttu-id="481e6-172">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-172">String</span></span> | <span data-ttu-id="481e6-173">Prioridad del conjunto de creadores para esta actividad de corrección (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="481e6-173">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="481e6-174">Alto</span><span class="sxs-lookup"><span data-stu-id="481e6-174">High</span></span>
<span data-ttu-id="481e6-175">productId</span><span class="sxs-lookup"><span data-stu-id="481e6-175">productId</span></span> | <span data-ttu-id="481e6-176">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-176">String</span></span> | <span data-ttu-id="481e6-177">Id. de producto relacionado</span><span class="sxs-lookup"><span data-stu-id="481e6-177">Related product ID</span></span> | <span data-ttu-id="481e6-178">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="481e6-178">microsoft-_-silverlight</span></span>
<span data-ttu-id="481e6-179">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="481e6-179">productivityImpactRemediationType</span></span> | <span data-ttu-id="481e6-180">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-180">String</span></span> | <span data-ttu-id="481e6-181">Solo se podrían solicitar algunos cambios de configuración para dispositivos sin impacto del usuario.</span><span class="sxs-lookup"><span data-stu-id="481e6-181">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="481e6-182">Este valor indica la selección entre "todos los dispositivos expuestos" o "solo dispositivos sin impacto del usuario".</span><span class="sxs-lookup"><span data-stu-id="481e6-182">This value indicates the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="481e6-183">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="481e6-183">AllExposedAssets</span></span>
<span data-ttu-id="481e6-184">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="481e6-184">rbacGroupNames</span></span> | <span data-ttu-id="481e6-185">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-185">String</span></span> | <span data-ttu-id="481e6-186">Nombres de grupo de dispositivos relacionados</span><span class="sxs-lookup"><span data-stu-id="481e6-186">Related device group names</span></span> | <span data-ttu-id="481e6-187">[ "Windows servidores", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="481e6-187">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="481e6-188">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="481e6-188">recommendedProgram</span></span> | <span data-ttu-id="481e6-189">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-189">String</span></span> | <span data-ttu-id="481e6-190">Programa recomendado para actualizar a</span><span class="sxs-lookup"><span data-stu-id="481e6-190">Recommended program to upgrade to</span></span> | <span data-ttu-id="481e6-191">nulo</span><span class="sxs-lookup"><span data-stu-id="481e6-191">null</span></span>
<span data-ttu-id="481e6-192">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="481e6-192">recommendedVendor</span></span> | <span data-ttu-id="481e6-193">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-193">String</span></span> | <span data-ttu-id="481e6-194">Proveedor recomendado para actualizar a</span><span class="sxs-lookup"><span data-stu-id="481e6-194">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="481e6-195">nulo</span><span class="sxs-lookup"><span data-stu-id="481e6-195">null</span></span>
<span data-ttu-id="481e6-196">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="481e6-196">recommendedVersion</span></span> | <span data-ttu-id="481e6-197">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-197">String</span></span> | <span data-ttu-id="481e6-198">Versión recomendada para actualizar o actualizar a</span><span class="sxs-lookup"><span data-stu-id="481e6-198">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="481e6-199">nulo</span><span class="sxs-lookup"><span data-stu-id="481e6-199">null</span></span>
<span data-ttu-id="481e6-200">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="481e6-200">relatedComponent</span></span> | <span data-ttu-id="481e6-201">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-201">String</span></span> | <span data-ttu-id="481e6-202">Componente relacionado de esta actividad de corrección (similar al componente relacionado para una recomendación de seguridad)</span><span class="sxs-lookup"><span data-stu-id="481e6-202">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="481e6-203">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="481e6-203">Microsoft Silverlight</span></span>
<span data-ttu-id="481e6-204">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="481e6-204">requesterEmail</span></span> | <span data-ttu-id="481e6-205">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-205">String</span></span> | <span data-ttu-id="481e6-206">Dirección de correo electrónico del creador</span><span class="sxs-lookup"><span data-stu-id="481e6-206">Creator email address</span></span> | <span data-ttu-id="481e6-207">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="481e6-207">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="481e6-208">requesterId</span><span class="sxs-lookup"><span data-stu-id="481e6-208">requesterId</span></span> | <span data-ttu-id="481e6-209">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-209">String</span></span> | <span data-ttu-id="481e6-210">Id. de objeto Creator</span><span class="sxs-lookup"><span data-stu-id="481e6-210">Creator object id</span></span> | <span data-ttu-id="481e6-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="481e6-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="481e6-212">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="481e6-212">requesterNotes</span></span> | <span data-ttu-id="481e6-213">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-213">String</span></span> | <span data-ttu-id="481e6-214">Las notas (texto libre) que el creador agregó para esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="481e6-214">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="481e6-215">nulo</span><span class="sxs-lookup"><span data-stu-id="481e6-215">null</span></span>
<span data-ttu-id="481e6-216">scid</span><span class="sxs-lookup"><span data-stu-id="481e6-216">scid</span></span> | <span data-ttu-id="481e6-217">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-217">String</span></span> | <span data-ttu-id="481e6-218">SCID de la recomendación de seguridad relacionada</span><span class="sxs-lookup"><span data-stu-id="481e6-218">SCID of the related security recommendation</span></span> | <span data-ttu-id="481e6-219">nulo</span><span class="sxs-lookup"><span data-stu-id="481e6-219">null</span></span>
<span data-ttu-id="481e6-220">status</span><span class="sxs-lookup"><span data-stu-id="481e6-220">status</span></span> | <span data-ttu-id="481e6-221">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-221">String</span></span> | <span data-ttu-id="481e6-222">Estado de la actividad de corrección (Activo/Completado)</span><span class="sxs-lookup"><span data-stu-id="481e6-222">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="481e6-223">Activo</span><span class="sxs-lookup"><span data-stu-id="481e6-223">Active</span></span>
<span data-ttu-id="481e6-224">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="481e6-224">statusLastModifiedOn</span></span> | <span data-ttu-id="481e6-225">DateTime</span><span class="sxs-lookup"><span data-stu-id="481e6-225">DateTime</span></span> | <span data-ttu-id="481e6-226">Fecha en la que se actualizó el campo de estado</span><span class="sxs-lookup"><span data-stu-id="481e6-226">Date when the status field was updated</span></span> | <span data-ttu-id="481e6-227">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="481e6-227">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="481e6-228">targetDevices</span><span class="sxs-lookup"><span data-stu-id="481e6-228">targetDevices</span></span> | <span data-ttu-id="481e6-229">Long</span><span class="sxs-lookup"><span data-stu-id="481e6-229">Long</span></span> | <span data-ttu-id="481e6-230">Número de dispositivos expuestos a los que se aplica esta corrección</span><span class="sxs-lookup"><span data-stu-id="481e6-230">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="481e6-231">43</span><span class="sxs-lookup"><span data-stu-id="481e6-231">43</span></span>
<span data-ttu-id="481e6-232">title</span><span class="sxs-lookup"><span data-stu-id="481e6-232">title</span></span> | <span data-ttu-id="481e6-233">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-233">String</span></span> | <span data-ttu-id="481e6-234">Título de esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="481e6-234">Title of this remediation activity</span></span> | <span data-ttu-id="481e6-235">Actualizar Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="481e6-235">Update Microsoft Silverlight</span></span>
<span data-ttu-id="481e6-236">type</span><span class="sxs-lookup"><span data-stu-id="481e6-236">type</span></span> | <span data-ttu-id="481e6-237">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-237">String</span></span> | <span data-ttu-id="481e6-238">Tipo de corrección</span><span class="sxs-lookup"><span data-stu-id="481e6-238">Remediation type</span></span> | <span data-ttu-id="481e6-239">Actualizar</span><span class="sxs-lookup"><span data-stu-id="481e6-239">Update</span></span>
<span data-ttu-id="481e6-240">vendorId</span><span class="sxs-lookup"><span data-stu-id="481e6-240">vendorId</span></span> | <span data-ttu-id="481e6-241">Cadena</span><span class="sxs-lookup"><span data-stu-id="481e6-241">String</span></span> | <span data-ttu-id="481e6-242">Nombre de proveedor relacionado</span><span class="sxs-lookup"><span data-stu-id="481e6-242">Related vendor name</span></span> | <span data-ttu-id="481e6-243">Microsoft</span><span class="sxs-lookup"><span data-stu-id="481e6-243">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="481e6-244">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="481e6-244">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="481e6-245">Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="481e6-245">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a><span data-ttu-id="481e6-246">Ejemplo de respuesta</span><span class="sxs-lookup"><span data-stu-id="481e6-246">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="481e6-247">Consulte también</span><span class="sxs-lookup"><span data-stu-id="481e6-247">See also</span></span>

- [<span data-ttu-id="481e6-248">Propiedades y métodos de corrección</span><span class="sxs-lookup"><span data-stu-id="481e6-248">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="481e6-249">Obtener una actividad de corrección por id.</span><span class="sxs-lookup"><span data-stu-id="481e6-249">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="481e6-250">Lista de dispositivos expuestos de una actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="481e6-250">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="481e6-251">Amenazas basadas en riesgos & administración de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="481e6-251">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="481e6-252">Vulnerabilidades de la organización</span><span class="sxs-lookup"><span data-stu-id="481e6-252">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
