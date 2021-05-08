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
ms.technology: mde
ms.openlocfilehash: cf7c79cb6cc76af88ce0293a013ba6edbf435d8c
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245497"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="6a1a4-104">Enumerar todas las actividades de corrección</span><span class="sxs-lookup"><span data-stu-id="6a1a4-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6a1a4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6a1a4-105">**Applies to:**</span></span>

- [<span data-ttu-id="6a1a4-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="6a1a4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6a1a4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a1a4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6a1a4-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="6a1a4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6a1a4-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="6a1a4-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="6a1a4-110">API description</span></span>

<span data-ttu-id="6a1a4-111">Devuelve información sobre todas las actividades de corrección.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="6a1a4-112">[Obtenga más información sobre las actividades de corrección](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="6a1a4-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="6a1a4-113">**DIRECCIÓN URL:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="6a1a4-113">**URL:** GET: /api/remediationTasks</span></span>

## <a name="permissions"></a><span data-ttu-id="6a1a4-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="6a1a4-114">Permissions</span></span>

<span data-ttu-id="6a1a4-115">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6a1a4-116">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6a1a4-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="6a1a4-117">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="6a1a4-117">Permission type</span></span> | <span data-ttu-id="6a1a4-118">Permiso</span><span class="sxs-lookup"><span data-stu-id="6a1a4-118">Permission</span></span> | <span data-ttu-id="6a1a4-119">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="6a1a4-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6a1a4-120">Aplicación</span><span class="sxs-lookup"><span data-stu-id="6a1a4-120">Application</span></span> | <span data-ttu-id="6a1a4-121">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="6a1a4-121">RemediationTask.Read.All</span></span> | <span data-ttu-id="6a1a4-122">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="6a1a4-122">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="6a1a4-123">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="6a1a4-123">Delegated (work or school account)</span></span> | <span data-ttu-id="6a1a4-124">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="6a1a4-124">RemediationTask.Read.Read</span></span> | <span data-ttu-id="6a1a4-125">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="6a1a4-125">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="6a1a4-126">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6a1a4-126">Properties</span></span>

<span data-ttu-id="6a1a4-127">Propiedad (id)</span><span class="sxs-lookup"><span data-stu-id="6a1a4-127">Property (id)</span></span> | <span data-ttu-id="6a1a4-128">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="6a1a4-128">Data type</span></span> | <span data-ttu-id="6a1a4-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a1a4-129">Description</span></span> | <span data-ttu-id="6a1a4-130">Ejemplo de un valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6a1a4-130">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="6a1a4-131">categoría</span><span class="sxs-lookup"><span data-stu-id="6a1a4-131">category</span></span> | <span data-ttu-id="6a1a4-132">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-132">String</span></span> | <span data-ttu-id="6a1a4-133">Categoría de la actividad de corrección (configuración software/seguridad)</span><span class="sxs-lookup"><span data-stu-id="6a1a4-133">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="6a1a4-134">Software</span><span class="sxs-lookup"><span data-stu-id="6a1a4-134">Software</span></span>
<span data-ttu-id="6a1a4-135">completerEmail</span><span class="sxs-lookup"><span data-stu-id="6a1a4-135">completerEmail</span></span> | <span data-ttu-id="6a1a4-136">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-136">String</span></span> | <span data-ttu-id="6a1a4-137">Si alguien completó manualmente la actividad de corrección, esta columna contiene su correo electrónico</span><span class="sxs-lookup"><span data-stu-id="6a1a4-137">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="6a1a4-138">nulo</span><span class="sxs-lookup"><span data-stu-id="6a1a4-138">null</span></span>
<span data-ttu-id="6a1a4-139">completerId</span><span class="sxs-lookup"><span data-stu-id="6a1a4-139">completerId</span></span> | <span data-ttu-id="6a1a4-140">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-140">String</span></span> | <span data-ttu-id="6a1a4-141">Si alguien completó la actividad de corrección manualmente, esta columna contiene su identificador de objeto</span><span class="sxs-lookup"><span data-stu-id="6a1a4-141">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="6a1a4-142">nulo</span><span class="sxs-lookup"><span data-stu-id="6a1a4-142">null</span></span>
<span data-ttu-id="6a1a4-143">completionMethod</span><span class="sxs-lookup"><span data-stu-id="6a1a4-143">completionMethod</span></span> | <span data-ttu-id="6a1a4-144">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-144">String</span></span> | <span data-ttu-id="6a1a4-145">Una actividad de corrección se puede completar "automáticamente" (si todos los dispositivos están parcheados) o "manualmente" por una persona que selecciona "marcar como completada"</span><span class="sxs-lookup"><span data-stu-id="6a1a4-145">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="6a1a4-146">Automático</span><span class="sxs-lookup"><span data-stu-id="6a1a4-146">Automatic</span></span>
<span data-ttu-id="6a1a4-147">createdOn</span><span class="sxs-lookup"><span data-stu-id="6a1a4-147">createdOn</span></span> | <span data-ttu-id="6a1a4-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="6a1a4-148">DateTime</span></span> | <span data-ttu-id="6a1a4-149">Hora en que se creó esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="6a1a4-149">Time this remediation activity was created</span></span> | <span data-ttu-id="6a1a4-150">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="6a1a4-150">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="6a1a4-151">description</span><span class="sxs-lookup"><span data-stu-id="6a1a4-151">description</span></span> | <span data-ttu-id="6a1a4-152">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-152">String</span></span> | <span data-ttu-id="6a1a4-153">Descripción de esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="6a1a4-153">Description of this remediation activity</span></span> | <span data-ttu-id="6a1a4-154">Actualiza Microsoft Silverlight a una versión posterior para mitigar las vulnerabilidades conocidas que afectan a los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-154">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="6a1a4-155">dueOn</span><span class="sxs-lookup"><span data-stu-id="6a1a4-155">dueOn</span></span> | <span data-ttu-id="6a1a4-156">DateTime</span><span class="sxs-lookup"><span data-stu-id="6a1a4-156">DateTime</span></span> | <span data-ttu-id="6a1a4-157">Fecha de vencimiento que el creador estableció para esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="6a1a4-157">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="6a1a4-158">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="6a1a4-158">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="6a1a4-159">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="6a1a4-159">fixedDevices</span></span> | <span data-ttu-id="6a1a4-160">.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-160">.</span></span> | <span data-ttu-id="6a1a4-161">Número de dispositivos que se han corregido</span><span class="sxs-lookup"><span data-stu-id="6a1a4-161">The number of devices that have been fixed</span></span> | <span data-ttu-id="6a1a4-162">2</span><span class="sxs-lookup"><span data-stu-id="6a1a4-162">2</span></span>
<span data-ttu-id="6a1a4-163">id</span><span class="sxs-lookup"><span data-stu-id="6a1a4-163">id</span></span> | <span data-ttu-id="6a1a4-164">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-164">String</span></span> | <span data-ttu-id="6a1a4-165">Identificador de esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="6a1a4-165">ID of this remediation activity</span></span> | <span data-ttu-id="6a1a4-166">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="6a1a4-166">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="6a1a4-167">nameId</span><span class="sxs-lookup"><span data-stu-id="6a1a4-167">nameId</span></span> | <span data-ttu-id="6a1a4-168">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-168">String</span></span> | <span data-ttu-id="6a1a4-169">Nombre del producto relacionado</span><span class="sxs-lookup"><span data-stu-id="6a1a4-169">Related product name</span></span> | <span data-ttu-id="6a1a4-170">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="6a1a4-170">Microsoft Silverlight</span></span>
<span data-ttu-id="6a1a4-171">priority</span><span class="sxs-lookup"><span data-stu-id="6a1a4-171">priority</span></span> | <span data-ttu-id="6a1a4-172">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-172">String</span></span> | <span data-ttu-id="6a1a4-173">Prioridad del conjunto de creadores para esta actividad de corrección (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="6a1a4-173">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="6a1a4-174">Alto</span><span class="sxs-lookup"><span data-stu-id="6a1a4-174">High</span></span>
<span data-ttu-id="6a1a4-175">productId</span><span class="sxs-lookup"><span data-stu-id="6a1a4-175">productId</span></span> | <span data-ttu-id="6a1a4-176">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-176">String</span></span> | <span data-ttu-id="6a1a4-177">Id. de producto relacionado</span><span class="sxs-lookup"><span data-stu-id="6a1a4-177">Related product ID</span></span> | <span data-ttu-id="6a1a4-178">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="6a1a4-178">microsoft-_-silverlight</span></span>
<span data-ttu-id="6a1a4-179">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="6a1a4-179">productivityImpactRemediationType</span></span> | <span data-ttu-id="6a1a4-180">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-180">String</span></span> | <span data-ttu-id="6a1a4-181">Solo se podrían solicitar algunos cambios de configuración para dispositivos sin impacto del usuario.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-181">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="6a1a4-182">Este valor indica la selección entre "todos los dispositivos expuestos" o "solo dispositivos sin impacto del usuario".</span><span class="sxs-lookup"><span data-stu-id="6a1a4-182">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="6a1a4-183">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="6a1a4-183">AllExposedAssets</span></span>
<span data-ttu-id="6a1a4-184">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="6a1a4-184">rbacGroupNames</span></span> | <span data-ttu-id="6a1a4-185">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-185">String</span></span> | <span data-ttu-id="6a1a4-186">Nombres de grupo de dispositivos relacionados</span><span class="sxs-lookup"><span data-stu-id="6a1a4-186">Related device group names</span></span> | <span data-ttu-id="6a1a4-187">[ "Windows servidores", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="6a1a4-187">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="6a1a4-188">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="6a1a4-188">recommendedProgram</span></span> | <span data-ttu-id="6a1a4-189">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-189">String</span></span> | <span data-ttu-id="6a1a4-190">Programa recomendado para actualizar a</span><span class="sxs-lookup"><span data-stu-id="6a1a4-190">Recommended program to upgrade to</span></span> | <span data-ttu-id="6a1a4-191">nulo</span><span class="sxs-lookup"><span data-stu-id="6a1a4-191">null</span></span>
<span data-ttu-id="6a1a4-192">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="6a1a4-192">recommendedVendor</span></span> | <span data-ttu-id="6a1a4-193">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-193">String</span></span> | <span data-ttu-id="6a1a4-194">Proveedor recomendado para actualizar a</span><span class="sxs-lookup"><span data-stu-id="6a1a4-194">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="6a1a4-195">nulo</span><span class="sxs-lookup"><span data-stu-id="6a1a4-195">null</span></span>
<span data-ttu-id="6a1a4-196">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="6a1a4-196">recommendedVersion</span></span> | <span data-ttu-id="6a1a4-197">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-197">String</span></span> | <span data-ttu-id="6a1a4-198">Versión recomendada para actualizar o actualizar a</span><span class="sxs-lookup"><span data-stu-id="6a1a4-198">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="6a1a4-199">nulo</span><span class="sxs-lookup"><span data-stu-id="6a1a4-199">null</span></span>
<span data-ttu-id="6a1a4-200">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="6a1a4-200">relatedComponent</span></span> | <span data-ttu-id="6a1a4-201">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-201">String</span></span> | <span data-ttu-id="6a1a4-202">Componente relacionado de esta actividad de corrección (similar al componente relacionado para una recomendación de seguridad)</span><span class="sxs-lookup"><span data-stu-id="6a1a4-202">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="6a1a4-203">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="6a1a4-203">Microsoft Silverlight</span></span>
<span data-ttu-id="6a1a4-204">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="6a1a4-204">requesterEmail</span></span> | <span data-ttu-id="6a1a4-205">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-205">String</span></span> | <span data-ttu-id="6a1a4-206">Dirección de correo electrónico del creador</span><span class="sxs-lookup"><span data-stu-id="6a1a4-206">Creator email address</span></span> | <span data-ttu-id="6a1a4-207">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6a1a4-207">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="6a1a4-208">requesterId</span><span class="sxs-lookup"><span data-stu-id="6a1a4-208">requesterId</span></span> | <span data-ttu-id="6a1a4-209">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-209">String</span></span> | <span data-ttu-id="6a1a4-210">Id. de objeto Creator</span><span class="sxs-lookup"><span data-stu-id="6a1a4-210">Creator object id</span></span> | <span data-ttu-id="6a1a4-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="6a1a4-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="6a1a4-212">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="6a1a4-212">requesterNotes</span></span> | <span data-ttu-id="6a1a4-213">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-213">String</span></span> | <span data-ttu-id="6a1a4-214">Las notas (texto libre) que el creador agregó para esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="6a1a4-214">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="6a1a4-215">nulo</span><span class="sxs-lookup"><span data-stu-id="6a1a4-215">null</span></span>
<span data-ttu-id="6a1a4-216">scid</span><span class="sxs-lookup"><span data-stu-id="6a1a4-216">scid</span></span> | <span data-ttu-id="6a1a4-217">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-217">String</span></span> | <span data-ttu-id="6a1a4-218">SCID de la recomendación de seguridad relacionada</span><span class="sxs-lookup"><span data-stu-id="6a1a4-218">SCID of the related security recommendation</span></span> | <span data-ttu-id="6a1a4-219">nulo</span><span class="sxs-lookup"><span data-stu-id="6a1a4-219">null</span></span>
<span data-ttu-id="6a1a4-220">status</span><span class="sxs-lookup"><span data-stu-id="6a1a4-220">status</span></span> | <span data-ttu-id="6a1a4-221">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-221">String</span></span> | <span data-ttu-id="6a1a4-222">Estado de la actividad de corrección (Activo/Completado)</span><span class="sxs-lookup"><span data-stu-id="6a1a4-222">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="6a1a4-223">Activo</span><span class="sxs-lookup"><span data-stu-id="6a1a4-223">Active</span></span>
<span data-ttu-id="6a1a4-224">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="6a1a4-224">statusLastModifiedOn</span></span> | <span data-ttu-id="6a1a4-225">DateTime</span><span class="sxs-lookup"><span data-stu-id="6a1a4-225">DateTime</span></span> | <span data-ttu-id="6a1a4-226">Fecha en la que se actualizó el campo de estado</span><span class="sxs-lookup"><span data-stu-id="6a1a4-226">Date when the status field was updated</span></span> | <span data-ttu-id="6a1a4-227">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="6a1a4-227">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="6a1a4-228">targetDevices</span><span class="sxs-lookup"><span data-stu-id="6a1a4-228">targetDevices</span></span> | <span data-ttu-id="6a1a4-229">Long</span><span class="sxs-lookup"><span data-stu-id="6a1a4-229">Long</span></span> | <span data-ttu-id="6a1a4-230">Número de dispositivos expuestos a los que se aplica esta corrección</span><span class="sxs-lookup"><span data-stu-id="6a1a4-230">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="6a1a4-231">43</span><span class="sxs-lookup"><span data-stu-id="6a1a4-231">43</span></span>
<span data-ttu-id="6a1a4-232">title</span><span class="sxs-lookup"><span data-stu-id="6a1a4-232">title</span></span> | <span data-ttu-id="6a1a4-233">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-233">String</span></span> | <span data-ttu-id="6a1a4-234">Título de esta actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="6a1a4-234">Title of this remediation activity</span></span> | <span data-ttu-id="6a1a4-235">Actualizar Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="6a1a4-235">Update Microsoft Silverlight</span></span>
<span data-ttu-id="6a1a4-236">type</span><span class="sxs-lookup"><span data-stu-id="6a1a4-236">type</span></span> | <span data-ttu-id="6a1a4-237">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-237">String</span></span> | <span data-ttu-id="6a1a4-238">Tipo de corrección</span><span class="sxs-lookup"><span data-stu-id="6a1a4-238">Remediation type</span></span> | <span data-ttu-id="6a1a4-239">Update</span><span class="sxs-lookup"><span data-stu-id="6a1a4-239">Update</span></span>
<span data-ttu-id="6a1a4-240">vendorId</span><span class="sxs-lookup"><span data-stu-id="6a1a4-240">vendorId</span></span> | <span data-ttu-id="6a1a4-241">Cadena</span><span class="sxs-lookup"><span data-stu-id="6a1a4-241">String</span></span> | <span data-ttu-id="6a1a4-242">Nombre de proveedor relacionado</span><span class="sxs-lookup"><span data-stu-id="6a1a4-242">Related vendor name</span></span> | <span data-ttu-id="6a1a4-243">Microsoft</span><span class="sxs-lookup"><span data-stu-id="6a1a4-243">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="6a1a4-244">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a1a4-244">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="6a1a4-245">Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="6a1a4-245">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a><span data-ttu-id="6a1a4-246">Ejemplo de respuesta</span><span class="sxs-lookup"><span data-stu-id="6a1a4-246">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6a1a4-247">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a1a4-247">See also</span></span>

- [<span data-ttu-id="6a1a4-248">Propiedades y métodos de corrección</span><span class="sxs-lookup"><span data-stu-id="6a1a4-248">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="6a1a4-249">Obtener una actividad de corrección por id.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-249">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="6a1a4-250">Lista de dispositivos expuestos de una actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="6a1a4-250">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="6a1a4-251">Amenazas basadas en riesgos & administración de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="6a1a4-251">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="6a1a4-252">Vulnerabilidades de la organización</span><span class="sxs-lookup"><span data-stu-id="6a1a4-252">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
