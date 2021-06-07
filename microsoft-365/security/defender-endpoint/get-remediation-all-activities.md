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
ms.openlocfilehash: b95fa2da177a3ecb93bcf3e2085be6111c2c641e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770522"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="1489f-104">Enumerar todas las actividades de corrección</span><span class="sxs-lookup"><span data-stu-id="1489f-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1489f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="1489f-105">**Applies to:**</span></span>

- [<span data-ttu-id="1489f-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="1489f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1489f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1489f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1489f-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="1489f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1489f-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="1489f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="1489f-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="1489f-110">API description</span></span>

<span data-ttu-id="1489f-111">Devuelve información sobre todas las actividades de corrección.</span><span class="sxs-lookup"><span data-stu-id="1489f-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="1489f-112">[Obtenga más información sobre las actividades de corrección](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="1489f-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="1489f-113">**DIRECCIÓN URL:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="1489f-113">**URL:** GET: /api/remediationTasks</span></span>

## <a name="permissions"></a><span data-ttu-id="1489f-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="1489f-114">Permissions</span></span>

<span data-ttu-id="1489f-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="1489f-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1489f-116">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1489f-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="1489f-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="1489f-117">Permission type</span></span> | <span data-ttu-id="1489f-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="1489f-118">Permission</span></span> | <span data-ttu-id="1489f-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="1489f-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1489f-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="1489f-120">Application</span></span> | <span data-ttu-id="1489f-121">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="1489f-121">RemediationTask.Read.All</span></span> | <span data-ttu-id="1489f-122">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="1489f-122">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="1489f-123">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="1489f-123">Delegated (work or school account)</span></span> | <span data-ttu-id="1489f-124">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="1489f-124">RemediationTask.Read.Read</span></span> | <span data-ttu-id="1489f-125">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="1489f-125">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="1489f-126">Propiedades</span><span class="sxs-lookup"><span data-stu-id="1489f-126">Properties</span></span>

<span data-ttu-id="1489f-127">Propiedad (id)</span><span class="sxs-lookup"><span data-stu-id="1489f-127">Property (id)</span></span> | <span data-ttu-id="1489f-128">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1489f-128">Data type</span></span> | <span data-ttu-id="1489f-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="1489f-129">Description</span></span> | <span data-ttu-id="1489f-130">Ejemplo de un valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1489f-130">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="1489f-131">categoría</span><span class="sxs-lookup"><span data-stu-id="1489f-131">category</span></span> | <span data-ttu-id="1489f-132">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-132">String</span></span> | <span data-ttu-id="1489f-133">Categoría de la actividad de corrección (configuración software/seguridad)</span><span class="sxs-lookup"><span data-stu-id="1489f-133">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="1489f-134">Software</span><span class="sxs-lookup"><span data-stu-id="1489f-134">Software</span></span>
<span data-ttu-id="1489f-135">completerEmail</span><span class="sxs-lookup"><span data-stu-id="1489f-135">completerEmail</span></span> | <span data-ttu-id="1489f-136">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-136">String</span></span> | <span data-ttu-id="1489f-137">Si alguien completó manualmente la actividad de corrección, esta columna contiene su correo electrónico</span><span class="sxs-lookup"><span data-stu-id="1489f-137">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="1489f-138">nulo</span><span class="sxs-lookup"><span data-stu-id="1489f-138">null</span></span>
<span data-ttu-id="1489f-139">completerId</span><span class="sxs-lookup"><span data-stu-id="1489f-139">completerId</span></span> | <span data-ttu-id="1489f-140">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-140">String</span></span> | <span data-ttu-id="1489f-141">Si alguien completó la actividad de corrección manualmente, esta columna contiene su identificador de objeto</span><span class="sxs-lookup"><span data-stu-id="1489f-141">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="1489f-142">nulo</span><span class="sxs-lookup"><span data-stu-id="1489f-142">null</span></span>
<span data-ttu-id="1489f-143">completionMethod</span><span class="sxs-lookup"><span data-stu-id="1489f-143">completionMethod</span></span> | <span data-ttu-id="1489f-144">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-144">String</span></span> | <span data-ttu-id="1489f-145">Una actividad de corrección se puede completar "automáticamente" (si todos los dispositivos están parcheados) o "manualmente" por una persona que selecciona "marcar como completada"</span><span class="sxs-lookup"><span data-stu-id="1489f-145">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="1489f-146">Automático</span><span class="sxs-lookup"><span data-stu-id="1489f-146">Automatic</span></span>
<span data-ttu-id="1489f-147">createdOn</span><span class="sxs-lookup"><span data-stu-id="1489f-147">createdOn</span></span> | <span data-ttu-id="1489f-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="1489f-148">DateTime</span></span> | <span data-ttu-id="1489f-149">Hora en que se creó esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="1489f-149">Time this remediation activity was created</span></span> | <span data-ttu-id="1489f-150">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="1489f-150">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="1489f-151">description</span><span class="sxs-lookup"><span data-stu-id="1489f-151">description</span></span> | <span data-ttu-id="1489f-152">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-152">String</span></span> | <span data-ttu-id="1489f-153">Descripción de esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="1489f-153">Description of this remediation activity</span></span> | <span data-ttu-id="1489f-154">Actualiza Microsoft Silverlight a una versión posterior para mitigar las vulnerabilidades conocidas que afectan a los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1489f-154">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="1489f-155">dueOn</span><span class="sxs-lookup"><span data-stu-id="1489f-155">dueOn</span></span> | <span data-ttu-id="1489f-156">DateTime</span><span class="sxs-lookup"><span data-stu-id="1489f-156">DateTime</span></span> | <span data-ttu-id="1489f-157">Fecha de vencimiento que el creador estableció para esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="1489f-157">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="1489f-158">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="1489f-158">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="1489f-159">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="1489f-159">fixedDevices</span></span> | <span data-ttu-id="1489f-160">.</span><span class="sxs-lookup"><span data-stu-id="1489f-160">.</span></span> | <span data-ttu-id="1489f-161">Número de dispositivos que se han corregido</span><span class="sxs-lookup"><span data-stu-id="1489f-161">The number of devices that have been fixed</span></span> | <span data-ttu-id="1489f-162">2</span><span class="sxs-lookup"><span data-stu-id="1489f-162">2</span></span>
<span data-ttu-id="1489f-163">id</span><span class="sxs-lookup"><span data-stu-id="1489f-163">id</span></span> | <span data-ttu-id="1489f-164">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-164">String</span></span> | <span data-ttu-id="1489f-165">Identificador de esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="1489f-165">ID of this remediation activity</span></span> | <span data-ttu-id="1489f-166">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="1489f-166">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="1489f-167">nameId</span><span class="sxs-lookup"><span data-stu-id="1489f-167">nameId</span></span> | <span data-ttu-id="1489f-168">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-168">String</span></span> | <span data-ttu-id="1489f-169">Nombre del producto relacionado</span><span class="sxs-lookup"><span data-stu-id="1489f-169">Related product name</span></span> | <span data-ttu-id="1489f-170">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="1489f-170">Microsoft Silverlight</span></span>
<span data-ttu-id="1489f-171">priority</span><span class="sxs-lookup"><span data-stu-id="1489f-171">priority</span></span> | <span data-ttu-id="1489f-172">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-172">String</span></span> | <span data-ttu-id="1489f-173">Prioridad del conjunto de creadores para esta actividad de corrección (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="1489f-173">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="1489f-174">Alto</span><span class="sxs-lookup"><span data-stu-id="1489f-174">High</span></span>
<span data-ttu-id="1489f-175">productId</span><span class="sxs-lookup"><span data-stu-id="1489f-175">productId</span></span> | <span data-ttu-id="1489f-176">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-176">String</span></span> | <span data-ttu-id="1489f-177">Id. de producto relacionado</span><span class="sxs-lookup"><span data-stu-id="1489f-177">Related product ID</span></span> | <span data-ttu-id="1489f-178">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="1489f-178">microsoft-_-silverlight</span></span>
<span data-ttu-id="1489f-179">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="1489f-179">productivityImpactRemediationType</span></span> | <span data-ttu-id="1489f-180">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-180">String</span></span> | <span data-ttu-id="1489f-181">Solo se podrían solicitar algunos cambios de configuración para dispositivos sin impacto del usuario.</span><span class="sxs-lookup"><span data-stu-id="1489f-181">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="1489f-182">Este valor indica la selección entre "todos los dispositivos expuestos" o "solo dispositivos sin impacto del usuario".</span><span class="sxs-lookup"><span data-stu-id="1489f-182">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="1489f-183">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="1489f-183">AllExposedAssets</span></span>
<span data-ttu-id="1489f-184">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="1489f-184">rbacGroupNames</span></span> | <span data-ttu-id="1489f-185">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-185">String</span></span> | <span data-ttu-id="1489f-186">Nombres de grupo de dispositivos relacionados</span><span class="sxs-lookup"><span data-stu-id="1489f-186">Related device group names</span></span> | <span data-ttu-id="1489f-187">[ "Windows servidores", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="1489f-187">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="1489f-188">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="1489f-188">recommendedProgram</span></span> | <span data-ttu-id="1489f-189">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-189">String</span></span> | <span data-ttu-id="1489f-190">Programa recomendado para actualizar a</span><span class="sxs-lookup"><span data-stu-id="1489f-190">Recommended program to upgrade to</span></span> | <span data-ttu-id="1489f-191">nulo</span><span class="sxs-lookup"><span data-stu-id="1489f-191">null</span></span>
<span data-ttu-id="1489f-192">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="1489f-192">recommendedVendor</span></span> | <span data-ttu-id="1489f-193">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-193">String</span></span> | <span data-ttu-id="1489f-194">Proveedor recomendado para actualizar a</span><span class="sxs-lookup"><span data-stu-id="1489f-194">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="1489f-195">nulo</span><span class="sxs-lookup"><span data-stu-id="1489f-195">null</span></span>
<span data-ttu-id="1489f-196">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="1489f-196">recommendedVersion</span></span> | <span data-ttu-id="1489f-197">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-197">String</span></span> | <span data-ttu-id="1489f-198">Versión recomendada para actualizar o actualizar a</span><span class="sxs-lookup"><span data-stu-id="1489f-198">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="1489f-199">nulo</span><span class="sxs-lookup"><span data-stu-id="1489f-199">null</span></span>
<span data-ttu-id="1489f-200">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="1489f-200">relatedComponent</span></span> | <span data-ttu-id="1489f-201">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-201">String</span></span> | <span data-ttu-id="1489f-202">Componente relacionado de esta actividad de corrección (similar al componente relacionado para una recomendación de seguridad)</span><span class="sxs-lookup"><span data-stu-id="1489f-202">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="1489f-203">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="1489f-203">Microsoft Silverlight</span></span>
<span data-ttu-id="1489f-204">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="1489f-204">requesterEmail</span></span> | <span data-ttu-id="1489f-205">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-205">String</span></span> | <span data-ttu-id="1489f-206">Dirección de correo electrónico del creador</span><span class="sxs-lookup"><span data-stu-id="1489f-206">Creator email address</span></span> | <span data-ttu-id="1489f-207">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1489f-207">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="1489f-208">requesterId</span><span class="sxs-lookup"><span data-stu-id="1489f-208">requesterId</span></span> | <span data-ttu-id="1489f-209">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-209">String</span></span> | <span data-ttu-id="1489f-210">Id. de objeto Creator</span><span class="sxs-lookup"><span data-stu-id="1489f-210">Creator object id</span></span> | <span data-ttu-id="1489f-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="1489f-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="1489f-212">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="1489f-212">requesterNotes</span></span> | <span data-ttu-id="1489f-213">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-213">String</span></span> | <span data-ttu-id="1489f-214">Las notas (texto libre) que el creador agregó para esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="1489f-214">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="1489f-215">nulo</span><span class="sxs-lookup"><span data-stu-id="1489f-215">null</span></span>
<span data-ttu-id="1489f-216">scid</span><span class="sxs-lookup"><span data-stu-id="1489f-216">scid</span></span> | <span data-ttu-id="1489f-217">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-217">String</span></span> | <span data-ttu-id="1489f-218">SCID de la recomendación de seguridad relacionada</span><span class="sxs-lookup"><span data-stu-id="1489f-218">SCID of the related security recommendation</span></span> | <span data-ttu-id="1489f-219">nulo</span><span class="sxs-lookup"><span data-stu-id="1489f-219">null</span></span>
<span data-ttu-id="1489f-220">status</span><span class="sxs-lookup"><span data-stu-id="1489f-220">status</span></span> | <span data-ttu-id="1489f-221">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-221">String</span></span> | <span data-ttu-id="1489f-222">Estado de la actividad de corrección (Activo/Completado)</span><span class="sxs-lookup"><span data-stu-id="1489f-222">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="1489f-223">Activa</span><span class="sxs-lookup"><span data-stu-id="1489f-223">Active</span></span>
<span data-ttu-id="1489f-224">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="1489f-224">statusLastModifiedOn</span></span> | <span data-ttu-id="1489f-225">DateTime</span><span class="sxs-lookup"><span data-stu-id="1489f-225">DateTime</span></span> | <span data-ttu-id="1489f-226">Fecha en la que se actualizó el campo de estado</span><span class="sxs-lookup"><span data-stu-id="1489f-226">Date when the status field was updated</span></span> | <span data-ttu-id="1489f-227">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="1489f-227">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="1489f-228">targetDevices</span><span class="sxs-lookup"><span data-stu-id="1489f-228">targetDevices</span></span> | <span data-ttu-id="1489f-229">Long</span><span class="sxs-lookup"><span data-stu-id="1489f-229">Long</span></span> | <span data-ttu-id="1489f-230">Número de dispositivos expuestos a los que se aplica esta corrección</span><span class="sxs-lookup"><span data-stu-id="1489f-230">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="1489f-231">43</span><span class="sxs-lookup"><span data-stu-id="1489f-231">43</span></span>
<span data-ttu-id="1489f-232">title</span><span class="sxs-lookup"><span data-stu-id="1489f-232">title</span></span> | <span data-ttu-id="1489f-233">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-233">String</span></span> | <span data-ttu-id="1489f-234">Título de esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="1489f-234">Title of this remediation activity</span></span> | <span data-ttu-id="1489f-235">Actualizar Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="1489f-235">Update Microsoft Silverlight</span></span>
<span data-ttu-id="1489f-236">type</span><span class="sxs-lookup"><span data-stu-id="1489f-236">type</span></span> | <span data-ttu-id="1489f-237">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-237">String</span></span> | <span data-ttu-id="1489f-238">Tipo de corrección</span><span class="sxs-lookup"><span data-stu-id="1489f-238">Remediation type</span></span> | <span data-ttu-id="1489f-239">Actualizar</span><span class="sxs-lookup"><span data-stu-id="1489f-239">Update</span></span>
<span data-ttu-id="1489f-240">vendorId</span><span class="sxs-lookup"><span data-stu-id="1489f-240">vendorId</span></span> | <span data-ttu-id="1489f-241">Cadena</span><span class="sxs-lookup"><span data-stu-id="1489f-241">String</span></span> | <span data-ttu-id="1489f-242">Nombre de proveedor relacionado</span><span class="sxs-lookup"><span data-stu-id="1489f-242">Related vendor name</span></span> | <span data-ttu-id="1489f-243">Microsoft</span><span class="sxs-lookup"><span data-stu-id="1489f-243">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="1489f-244">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1489f-244">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="1489f-245">Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="1489f-245">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a><span data-ttu-id="1489f-246">Ejemplo de respuesta</span><span class="sxs-lookup"><span data-stu-id="1489f-246">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1489f-247">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1489f-247">See also</span></span>

- [<span data-ttu-id="1489f-248">Propiedades y métodos de corrección</span><span class="sxs-lookup"><span data-stu-id="1489f-248">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="1489f-249">Obtener una actividad de corrección por id.</span><span class="sxs-lookup"><span data-stu-id="1489f-249">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="1489f-250">Lista de dispositivos expuestos de una actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="1489f-250">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="1489f-251">Amenazas basadas en riesgos & administración de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="1489f-251">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="1489f-252">Vulnerabilidades de la organización</span><span class="sxs-lookup"><span data-stu-id="1489f-252">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
