---
title: Obtener una actividad de corrección por id.
description: Devuelve información sobre la actividad de corrección especificada.
keywords: apis, remediation, remediation api, get, remediation tasks, remediation by ID,
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
ms.openlocfilehash: e0f68e8a28b302f0ae1ca06a2f892fea38a219b2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244448"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="40762-104">Obtener una actividad de corrección por id.</span><span class="sxs-lookup"><span data-stu-id="40762-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="40762-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="40762-105">**Applies to:**</span></span>

- [<span data-ttu-id="40762-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="40762-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="40762-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="40762-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="40762-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="40762-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="40762-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="40762-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="40762-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="40762-110">API description</span></span>

<span data-ttu-id="40762-111">Devuelve información sobre la actividad de corrección especificada.</span><span class="sxs-lookup"><span data-stu-id="40762-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="40762-112">Presenta las mismas columnas que [Obtener toda](get-remediation-all-activities.md)la actividad de corrección ", pero devuelve resultados solo para la actividad _de corrección especificada_.</span><span class="sxs-lookup"><span data-stu-id="40762-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="40762-113">[Obtenga más información sobre las actividades de corrección](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="40762-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="40762-114">Enumerar una actividad de corrección especificada para (id)</span><span class="sxs-lookup"><span data-stu-id="40762-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="40762-115">**DIRECCIÓN URL:** GET: /api/remediationTasks/ \{ id\}</span><span class="sxs-lookup"><span data-stu-id="40762-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

## <a name="permissions"></a><span data-ttu-id="40762-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="40762-116">Permissions</span></span>

<span data-ttu-id="40762-117">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="40762-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="40762-118">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="40762-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="40762-119">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="40762-119">Permission type</span></span> | <span data-ttu-id="40762-120">Permiso</span><span class="sxs-lookup"><span data-stu-id="40762-120">Permission</span></span> | <span data-ttu-id="40762-121">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="40762-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="40762-122">Aplicación</span><span class="sxs-lookup"><span data-stu-id="40762-122">Application</span></span> | <span data-ttu-id="40762-123">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="40762-123">RemediationTask.Read.All</span></span> | <span data-ttu-id="40762-124">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="40762-124">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="40762-125">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="40762-125">Delegated (work or school account)</span></span> | <span data-ttu-id="40762-126">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="40762-126">RemediationTask.Read.Read</span></span> | <span data-ttu-id="40762-127">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="40762-127">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="40762-128">Propiedades</span><span class="sxs-lookup"><span data-stu-id="40762-128">Properties</span></span>

<span data-ttu-id="40762-129">Propiedad (id)</span><span class="sxs-lookup"><span data-stu-id="40762-129">Property (id)</span></span> | <span data-ttu-id="40762-130">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="40762-130">Data type</span></span> | <span data-ttu-id="40762-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="40762-131">Description</span></span> | <span data-ttu-id="40762-132">Ejemplo de un valor devuelto</span><span class="sxs-lookup"><span data-stu-id="40762-132">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="40762-133">categoría</span><span class="sxs-lookup"><span data-stu-id="40762-133">category</span></span> | <span data-ttu-id="40762-134">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-134">String</span></span> | <span data-ttu-id="40762-135">Categoría de la actividad de corrección (configuración software/seguridad)</span><span class="sxs-lookup"><span data-stu-id="40762-135">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="40762-136">Software</span><span class="sxs-lookup"><span data-stu-id="40762-136">Software</span></span>
<span data-ttu-id="40762-137">completerEmail</span><span class="sxs-lookup"><span data-stu-id="40762-137">completerEmail</span></span> | <span data-ttu-id="40762-138">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-138">String</span></span> | <span data-ttu-id="40762-139">Si alguien completó manualmente la actividad de corrección, esta columna contiene su correo electrónico</span><span class="sxs-lookup"><span data-stu-id="40762-139">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="40762-140">nulo</span><span class="sxs-lookup"><span data-stu-id="40762-140">null</span></span>
<span data-ttu-id="40762-141">completerId</span><span class="sxs-lookup"><span data-stu-id="40762-141">completerId</span></span> | <span data-ttu-id="40762-142">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-142">String</span></span> | <span data-ttu-id="40762-143">Si alguien completó la actividad de corrección manualmente, esta columna contiene su identificador de objeto</span><span class="sxs-lookup"><span data-stu-id="40762-143">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="40762-144">nulo</span><span class="sxs-lookup"><span data-stu-id="40762-144">null</span></span>
<span data-ttu-id="40762-145">completionMethod</span><span class="sxs-lookup"><span data-stu-id="40762-145">completionMethod</span></span> | <span data-ttu-id="40762-146">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-146">String</span></span> | <span data-ttu-id="40762-147">Una actividad de corrección se puede completar "automáticamente" (si todos los dispositivos están parcheados) o "manualmente" por una persona que selecciona "marcar como completada"</span><span class="sxs-lookup"><span data-stu-id="40762-147">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="40762-148">Automático</span><span class="sxs-lookup"><span data-stu-id="40762-148">Automatic</span></span>
<span data-ttu-id="40762-149">createdOn</span><span class="sxs-lookup"><span data-stu-id="40762-149">createdOn</span></span> | <span data-ttu-id="40762-150">DateTime</span><span class="sxs-lookup"><span data-stu-id="40762-150">DateTime</span></span> | <span data-ttu-id="40762-151">Hora en que se creó esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="40762-151">Time this remediation activity was created</span></span> | <span data-ttu-id="40762-152">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="40762-152">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="40762-153">description</span><span class="sxs-lookup"><span data-stu-id="40762-153">description</span></span> | <span data-ttu-id="40762-154">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-154">String</span></span> | <span data-ttu-id="40762-155">Descripción de esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="40762-155">Description of this remediation activity</span></span> | <span data-ttu-id="40762-156">Actualiza Microsoft Silverlight a una versión posterior para mitigar las vulnerabilidades conocidas que afectan a los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="40762-156">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="40762-157">dueOn</span><span class="sxs-lookup"><span data-stu-id="40762-157">dueOn</span></span> | <span data-ttu-id="40762-158">DateTime</span><span class="sxs-lookup"><span data-stu-id="40762-158">DateTime</span></span> | <span data-ttu-id="40762-159">Fecha de vencimiento que el creador estableció para esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="40762-159">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="40762-160">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="40762-160">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="40762-161">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="40762-161">fixedDevices</span></span> |  | <span data-ttu-id="40762-162">Número de dispositivos que se han corregido</span><span class="sxs-lookup"><span data-stu-id="40762-162">The number of devices that have been fixed</span></span> | <span data-ttu-id="40762-163">2</span><span class="sxs-lookup"><span data-stu-id="40762-163">2</span></span>
<span data-ttu-id="40762-164">id</span><span class="sxs-lookup"><span data-stu-id="40762-164">id</span></span> | <span data-ttu-id="40762-165">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-165">String</span></span> | <span data-ttu-id="40762-166">Identificador de esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="40762-166">ID of this remediation activity</span></span> | <span data-ttu-id="40762-167">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="40762-167">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="40762-168">nameId</span><span class="sxs-lookup"><span data-stu-id="40762-168">nameId</span></span> | <span data-ttu-id="40762-169">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-169">String</span></span> | <span data-ttu-id="40762-170">Nombre del producto relacionado</span><span class="sxs-lookup"><span data-stu-id="40762-170">Related product name</span></span> | <span data-ttu-id="40762-171">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="40762-171">Microsoft Silverlight</span></span>
<span data-ttu-id="40762-172">priority</span><span class="sxs-lookup"><span data-stu-id="40762-172">priority</span></span> | <span data-ttu-id="40762-173">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-173">String</span></span> | <span data-ttu-id="40762-174">Prioridad del conjunto de creadores para esta actividad de corrección (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="40762-174">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="40762-175">Alto</span><span class="sxs-lookup"><span data-stu-id="40762-175">High</span></span>
<span data-ttu-id="40762-176">productId</span><span class="sxs-lookup"><span data-stu-id="40762-176">productId</span></span> | <span data-ttu-id="40762-177">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-177">String</span></span> | <span data-ttu-id="40762-178">Id. de producto relacionado</span><span class="sxs-lookup"><span data-stu-id="40762-178">Related product ID</span></span> | <span data-ttu-id="40762-179">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="40762-179">microsoft-_-silverlight</span></span>
<span data-ttu-id="40762-180">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="40762-180">productivityImpactRemediationType</span></span> | <span data-ttu-id="40762-181">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-181">String</span></span> | <span data-ttu-id="40762-182">Solo se podrían solicitar algunos cambios de configuración para dispositivos sin impacto del usuario.</span><span class="sxs-lookup"><span data-stu-id="40762-182">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="40762-183">Este valor indica la selección entre "todos los dispositivos expuestos" o "solo dispositivos sin impacto del usuario".</span><span class="sxs-lookup"><span data-stu-id="40762-183">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="40762-184">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="40762-184">AllExposedAssets</span></span>
<span data-ttu-id="40762-185">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="40762-185">rbacGroupNames</span></span> | <span data-ttu-id="40762-186">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-186">String</span></span> | <span data-ttu-id="40762-187">Nombres de grupo de dispositivos relacionados</span><span class="sxs-lookup"><span data-stu-id="40762-187">Related device group names</span></span> | <span data-ttu-id="40762-188">[ "Windows servidores", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="40762-188">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="40762-189">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="40762-189">recommendedProgram</span></span> | <span data-ttu-id="40762-190">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-190">String</span></span> | <span data-ttu-id="40762-191">Programa recomendado para actualizar a</span><span class="sxs-lookup"><span data-stu-id="40762-191">Recommended program to upgrade to</span></span> | <span data-ttu-id="40762-192">nulo</span><span class="sxs-lookup"><span data-stu-id="40762-192">null</span></span>
<span data-ttu-id="40762-193">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="40762-193">recommendedVendor</span></span> | <span data-ttu-id="40762-194">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-194">String</span></span> | <span data-ttu-id="40762-195">Proveedor recomendado para actualizar a</span><span class="sxs-lookup"><span data-stu-id="40762-195">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="40762-196">nulo</span><span class="sxs-lookup"><span data-stu-id="40762-196">null</span></span>
<span data-ttu-id="40762-197">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="40762-197">recommendedVersion</span></span> | <span data-ttu-id="40762-198">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-198">String</span></span> | <span data-ttu-id="40762-199">Versión recomendada para actualizar o actualizar a</span><span class="sxs-lookup"><span data-stu-id="40762-199">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="40762-200">nulo</span><span class="sxs-lookup"><span data-stu-id="40762-200">null</span></span>
<span data-ttu-id="40762-201">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="40762-201">relatedComponent</span></span> | <span data-ttu-id="40762-202">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-202">String</span></span> | <span data-ttu-id="40762-203">Componente relacionado de esta actividad de corrección (similar al componente relacionado para una recomendación de seguridad)</span><span class="sxs-lookup"><span data-stu-id="40762-203">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="40762-204">Microsoft Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="40762-204">Microsoft Microsoft Silverlight</span></span>
<span data-ttu-id="40762-205">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="40762-205">requesterEmail</span></span> | <span data-ttu-id="40762-206">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-206">String</span></span> | <span data-ttu-id="40762-207">Dirección de correo electrónico del creador</span><span class="sxs-lookup"><span data-stu-id="40762-207">Creator email address</span></span> | <span data-ttu-id="40762-208">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="40762-208">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="40762-209">requesterId</span><span class="sxs-lookup"><span data-stu-id="40762-209">requesterId</span></span> | <span data-ttu-id="40762-210">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-210">String</span></span> | <span data-ttu-id="40762-211">Id. de objeto Creator</span><span class="sxs-lookup"><span data-stu-id="40762-211">Creator object id</span></span> | <span data-ttu-id="40762-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="40762-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="40762-213">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="40762-213">requesterNotes</span></span> | <span data-ttu-id="40762-214">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-214">String</span></span> | <span data-ttu-id="40762-215">Las notas (texto libre) que el creador agregó para esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="40762-215">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="40762-216">nulo</span><span class="sxs-lookup"><span data-stu-id="40762-216">null</span></span>
<span data-ttu-id="40762-217">scid</span><span class="sxs-lookup"><span data-stu-id="40762-217">scid</span></span> | <span data-ttu-id="40762-218">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-218">String</span></span> | <span data-ttu-id="40762-219">SCID de la recomendación de seguridad relacionada</span><span class="sxs-lookup"><span data-stu-id="40762-219">SCID of the related security recommendation</span></span> | <span data-ttu-id="40762-220">nulo</span><span class="sxs-lookup"><span data-stu-id="40762-220">null</span></span>
<span data-ttu-id="40762-221">status</span><span class="sxs-lookup"><span data-stu-id="40762-221">status</span></span> | <span data-ttu-id="40762-222">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-222">String</span></span> | <span data-ttu-id="40762-223">Estado de la actividad de corrección (Activo/Completado)</span><span class="sxs-lookup"><span data-stu-id="40762-223">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="40762-224">Activo</span><span class="sxs-lookup"><span data-stu-id="40762-224">Active</span></span>
<span data-ttu-id="40762-225">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="40762-225">statusLastModifiedOn</span></span> | <span data-ttu-id="40762-226">DateTime</span><span class="sxs-lookup"><span data-stu-id="40762-226">DateTime</span></span> | <span data-ttu-id="40762-227">Fecha en la que se actualizó el campo de estado</span><span class="sxs-lookup"><span data-stu-id="40762-227">Date when the status field was updated</span></span> | <span data-ttu-id="40762-228">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="40762-228">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="40762-229">targetDevices</span><span class="sxs-lookup"><span data-stu-id="40762-229">targetDevices</span></span> | <span data-ttu-id="40762-230">Long</span><span class="sxs-lookup"><span data-stu-id="40762-230">Long</span></span> | <span data-ttu-id="40762-231">Número de dispositivos expuestos a los que se aplica esta corrección</span><span class="sxs-lookup"><span data-stu-id="40762-231">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="40762-232">43</span><span class="sxs-lookup"><span data-stu-id="40762-232">43</span></span>
<span data-ttu-id="40762-233">title</span><span class="sxs-lookup"><span data-stu-id="40762-233">title</span></span> | <span data-ttu-id="40762-234">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-234">String</span></span> | <span data-ttu-id="40762-235">Título de esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="40762-235">Title of this remediation activity</span></span> | <span data-ttu-id="40762-236">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="40762-236">Microsoft Silverlight</span></span>
<span data-ttu-id="40762-237">type</span><span class="sxs-lookup"><span data-stu-id="40762-237">type</span></span> | <span data-ttu-id="40762-238">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-238">String</span></span> | <span data-ttu-id="40762-239">Tipo de corrección</span><span class="sxs-lookup"><span data-stu-id="40762-239">Remediation type</span></span> | <span data-ttu-id="40762-240">Update</span><span class="sxs-lookup"><span data-stu-id="40762-240">Update</span></span>
<span data-ttu-id="40762-241">vendorId</span><span class="sxs-lookup"><span data-stu-id="40762-241">vendorId</span></span> | <span data-ttu-id="40762-242">Cadena</span><span class="sxs-lookup"><span data-stu-id="40762-242">String</span></span> | <span data-ttu-id="40762-243">Nombre de proveedor relacionado</span><span class="sxs-lookup"><span data-stu-id="40762-243">Related vendor name</span></span> | <span data-ttu-id="40762-244">Microsoft</span><span class="sxs-lookup"><span data-stu-id="40762-244">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="40762-245">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="40762-245">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="40762-246">Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="40762-246">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a><span data-ttu-id="40762-247">Ejemplo de respuesta</span><span class="sxs-lookup"><span data-stu-id="40762-247">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="40762-248">Vea también</span><span class="sxs-lookup"><span data-stu-id="40762-248">See also</span></span>

- [<span data-ttu-id="40762-249">Propiedades y métodos de corrección</span><span class="sxs-lookup"><span data-stu-id="40762-249">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="40762-250">Enumerar todas las actividades de corrección</span><span class="sxs-lookup"><span data-stu-id="40762-250">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="40762-251">Lista de dispositivos expuestos de una actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="40762-251">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="40762-252">Amenazas basadas en riesgos & administración de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="40762-252">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="40762-253">Vulnerabilidades de la organización</span><span class="sxs-lookup"><span data-stu-id="40762-253">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
