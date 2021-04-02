---
title: Cambios de nomenclatura en el esquema de búsqueda avanzada de Microsoft 365 Defender
description: Seguimiento y revisión de cambios de nomenclatura en tablas y columnas en el esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, datos, cambios de nomenclatura, cambio de nombre, Protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ab6bdefb457fb31df98d829ee801b72f4c8ae70a
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499699"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="776f3-104">Esquema de búsqueda avanzada: cambios de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="776f3-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="776f3-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="776f3-105">**Applies to:**</span></span>
- <span data-ttu-id="776f3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="776f3-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="776f3-107">El [esquema de búsqueda avanzada](advanced-hunting-schema-tables.md) se actualiza regularmente para agregar nuevas tablas y columnas.</span><span class="sxs-lookup"><span data-stu-id="776f3-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="776f3-108">En algunos casos, los nombres de columnas existentes se renombran o reemplazan para mejorar la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="776f3-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="776f3-109">Consulte este artículo para revisar los cambios de nomenclatura que podrían afectar a las consultas.</span><span class="sxs-lookup"><span data-stu-id="776f3-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="776f3-110">Los cambios de nomenclatura se aplican automáticamente a las consultas que se guardan en el centro de seguridad, incluidas las consultas usadas por las reglas de detección personalizadas.</span><span class="sxs-lookup"><span data-stu-id="776f3-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="776f3-111">No es necesario actualizar estas consultas manualmente.</span><span class="sxs-lookup"><span data-stu-id="776f3-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="776f3-112">Sin embargo, deberá actualizar las siguientes consultas:</span><span class="sxs-lookup"><span data-stu-id="776f3-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="776f3-113">Consultas que se ejecutan con la API</span><span class="sxs-lookup"><span data-stu-id="776f3-113">Queries that are run using the API</span></span>
- <span data-ttu-id="776f3-114">Consultas que se guardan en otro lugar fuera del centro de seguridad</span><span class="sxs-lookup"><span data-stu-id="776f3-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="776f3-115">Diciembre de 2020</span><span class="sxs-lookup"><span data-stu-id="776f3-115">December 2020</span></span>

| <span data-ttu-id="776f3-116">Nombre de tabla</span><span class="sxs-lookup"><span data-stu-id="776f3-116">Table name</span></span> | <span data-ttu-id="776f3-117">Nombre de columna original</span><span class="sxs-lookup"><span data-stu-id="776f3-117">Original column name</span></span> | <span data-ttu-id="776f3-118">Nuevo nombre de columna</span><span class="sxs-lookup"><span data-stu-id="776f3-118">New column name</span></span> | <span data-ttu-id="776f3-119">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="776f3-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="776f3-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="776f3-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="776f3-121">Comentarios del cliente</span><span class="sxs-lookup"><span data-stu-id="776f3-121">Customer feedback</span></span> |
| [<span data-ttu-id="776f3-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="776f3-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="776f3-123">Comentarios del cliente</span><span class="sxs-lookup"><span data-stu-id="776f3-123">Customer feedback</span></span> |
| [<span data-ttu-id="776f3-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="776f3-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="776f3-125">Comentarios del cliente</span><span class="sxs-lookup"><span data-stu-id="776f3-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="776f3-126">Enero de 2021</span><span class="sxs-lookup"><span data-stu-id="776f3-126">January 2021</span></span>

| <span data-ttu-id="776f3-127">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="776f3-127">Column name</span></span> | <span data-ttu-id="776f3-128">Nombre del valor original</span><span class="sxs-lookup"><span data-stu-id="776f3-128">Original value name</span></span> | <span data-ttu-id="776f3-129">Nuevo nombre de valor</span><span class="sxs-lookup"><span data-stu-id="776f3-129">New value name</span></span> | <span data-ttu-id="776f3-130">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="776f3-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="776f3-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="776f3-131">MCAS</span></span> |    <span data-ttu-id="776f3-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="776f3-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="776f3-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="776f3-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="776f3-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="776f3-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="776f3-135">EDR</span><span class="sxs-lookup"><span data-stu-id="776f3-135">EDR</span></span>| <span data-ttu-id="776f3-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="776f3-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="776f3-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="776f3-137">WindowsDefenderAv</span></span> | <span data-ttu-id="776f3-138">Antivirus</span><span class="sxs-lookup"><span data-stu-id="776f3-138">Antivirus</span></span> | <span data-ttu-id="776f3-139">Rebranding</span><span class="sxs-lookup"><span data-stu-id="776f3-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="776f3-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="776f3-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="776f3-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="776f3-141">SmartScreen</span></span> | <span data-ttu-id="776f3-142">Rebranding</span><span class="sxs-lookup"><span data-stu-id="776f3-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="776f3-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="776f3-143">CustomerTI</span></span> |  <span data-ttu-id="776f3-144">TI personalizada</span><span class="sxs-lookup"><span data-stu-id="776f3-144">Custom TI</span></span> | <span data-ttu-id="776f3-145">Rebranding</span><span class="sxs-lookup"><span data-stu-id="776f3-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="776f3-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="776f3-146">OfficeATP</span></span> | <span data-ttu-id="776f3-147">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="776f3-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="776f3-148">Rebranding</span><span class="sxs-lookup"><span data-stu-id="776f3-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="776f3-149">MTP</span><span class="sxs-lookup"><span data-stu-id="776f3-149">MTP</span></span>   | <span data-ttu-id="776f3-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="776f3-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="776f3-151">Rebranding</span><span class="sxs-lookup"><span data-stu-id="776f3-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="776f3-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="776f3-152">AzureATP</span></span> |    <span data-ttu-id="776f3-153">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="776f3-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="776f3-154">Rebranding</span><span class="sxs-lookup"><span data-stu-id="776f3-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="776f3-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="776f3-155">CustomDetection</span></span>   | <span data-ttu-id="776f3-156">Detección personalizada</span><span class="sxs-lookup"><span data-stu-id="776f3-156">Custom detection</span></span> | <span data-ttu-id="776f3-157">Rebranding</span><span class="sxs-lookup"><span data-stu-id="776f3-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="776f3-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="776f3-158">AutomatedInvestigation</span></span> |<span data-ttu-id="776f3-159">Investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="776f3-159">Automated investigation</span></span> | <span data-ttu-id="776f3-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="776f3-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="776f3-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="776f3-161">ThreatExperts</span></span> | <span data-ttu-id="776f3-162">Expertos en amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="776f3-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="776f3-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="776f3-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="776f3-164">TI de terceros</span><span class="sxs-lookup"><span data-stu-id="776f3-164">3rd party TI</span></span> | <span data-ttu-id="776f3-165">Sensores de terceros</span><span class="sxs-lookup"><span data-stu-id="776f3-165">3rd Party sensors</span></span> | <span data-ttu-id="776f3-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="776f3-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="776f3-167">inquilino dedicado</span><span class="sxs-lookup"><span data-stu-id="776f3-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="776f3-168">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="776f3-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="776f3-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="776f3-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="776f3-170">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="776f3-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="776f3-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="776f3-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="776f3-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="776f3-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="776f3-173">ATP de Office 365</span><span class="sxs-lookup"><span data-stu-id="776f3-173">Office 365 ATP</span></span>  |<span data-ttu-id="776f3-174">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="776f3-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="776f3-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="776f3-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="776f3-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="776f3-176">Azure ATP</span></span>    |<span data-ttu-id="776f3-177">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="776f3-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="776f3-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="776f3-178">Rebranding</span></span> |

<span data-ttu-id="776f3-179">`DetectionSource`está disponible en la [tabla AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="776f3-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="776f3-180">`ServiceSource`está disponible en las [tablas AlertEvidence](advanced-hunting-alertevidence-table.md) [y AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="776f3-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="776f3-181">Febrero de 2021</span><span class="sxs-lookup"><span data-stu-id="776f3-181">February 2021</span></span>

1. <span data-ttu-id="776f3-182">En las [tablas EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) y [EmailEvents,](advanced-hunting-emailevents-table.md) las columnas y se han `MalwareFilterVerdict` reemplazado por la `PhishFilterVerdict` `ThreatTypes` columna.</span><span class="sxs-lookup"><span data-stu-id="776f3-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, the `MalwareFilterVerdict`and `PhishFilterVerdict` columns have been replaced by the `ThreatTypes` column.</span></span> <span data-ttu-id="776f3-183">Las `MalwareDetectionMethod` columnas y también se `PhishDetectionMethod` reemplazaron por la `DetectionMethods` columna.</span><span class="sxs-lookup"><span data-stu-id="776f3-183">The `MalwareDetectionMethod` and `PhishDetectionMethod` columns were also replaced by the `DetectionMethods` column.</span></span> <span data-ttu-id="776f3-184">Esta racionalización nos permite proporcionar más información debajo de las nuevas columnas.</span><span class="sxs-lookup"><span data-stu-id="776f3-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="776f3-185">La asignación se proporciona a continuación.</span><span class="sxs-lookup"><span data-stu-id="776f3-185">The mapping is provided below.</span></span>

| <span data-ttu-id="776f3-186">Nombre de tabla</span><span class="sxs-lookup"><span data-stu-id="776f3-186">Table name</span></span> | <span data-ttu-id="776f3-187">Nombre de columna original</span><span class="sxs-lookup"><span data-stu-id="776f3-187">Original column name</span></span> | <span data-ttu-id="776f3-188">Nuevo nombre de columna</span><span class="sxs-lookup"><span data-stu-id="776f3-188">New column name</span></span> | <span data-ttu-id="776f3-189">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="776f3-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="776f3-190">Incluir más métodos de detección</span><span class="sxs-lookup"><span data-stu-id="776f3-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="776f3-191">Incluir más tipos de amenazas</span><span class="sxs-lookup"><span data-stu-id="776f3-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="776f3-192">Incluir más métodos de detección</span><span class="sxs-lookup"><span data-stu-id="776f3-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="776f3-193">Incluir más tipos de amenazas</span><span class="sxs-lookup"><span data-stu-id="776f3-193">Include more threat types</span></span> |


2. <span data-ttu-id="776f3-194">En las `EmailAttachmentInfo` tablas `EmailEvents` y, la `ThreatNames` columna se agregó para proporcionar más información sobre la amenaza de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="776f3-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, the `ThreatNames` column was added to give more information about the email threat.</span></span> <span data-ttu-id="776f3-195">Esta columna contiene valores como Correo no deseado o Phish.</span><span class="sxs-lookup"><span data-stu-id="776f3-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="776f3-196">En la [tabla DeviceInfo,](advanced-hunting-deviceinfo-table.md) la `DeviceObjectId` columna se reemplazó por la `AadDeviceId` columna en función de los comentarios de los clientes.</span><span class="sxs-lookup"><span data-stu-id="776f3-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, the `DeviceObjectId` column was replaced by the `AadDeviceId` column based on customer feedback.</span></span>

4. <span data-ttu-id="776f3-197">En la [tabla DeviceEvents,](advanced-hunting-deviceevents-table.md) se modificaron varios nombres ActionType para reflejar mejor la descripción de la acción.</span><span class="sxs-lookup"><span data-stu-id="776f3-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, several ActionType names were modified to better reflect the description of the action.</span></span> <span data-ttu-id="776f3-198">Los detalles de los cambios se pueden encontrar a continuación.</span><span class="sxs-lookup"><span data-stu-id="776f3-198">Details of the changes can be found below.</span></span>

| <span data-ttu-id="776f3-199">Nombre de tabla</span><span class="sxs-lookup"><span data-stu-id="776f3-199">Table name</span></span> | <span data-ttu-id="776f3-200">Nombre ActionType original</span><span class="sxs-lookup"><span data-stu-id="776f3-200">Original ActionType name</span></span> | <span data-ttu-id="776f3-201">Nuevo nombre actionType</span><span class="sxs-lookup"><span data-stu-id="776f3-201">New ActionType name</span></span> | <span data-ttu-id="776f3-202">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="776f3-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="776f3-203">Comentarios del cliente</span><span class="sxs-lookup"><span data-stu-id="776f3-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="776f3-204">Comentarios del cliente</span><span class="sxs-lookup"><span data-stu-id="776f3-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="776f3-205">Comentarios del cliente</span><span class="sxs-lookup"><span data-stu-id="776f3-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="776f3-206">Comentarios del cliente</span><span class="sxs-lookup"><span data-stu-id="776f3-206">Customer feedback</span></span> |






## <a name="related-topics"></a><span data-ttu-id="776f3-207">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="776f3-207">Related topics</span></span>
- [<span data-ttu-id="776f3-208">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="776f3-208">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="776f3-209">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="776f3-209">Understand the schema</span></span>](advanced-hunting-schema-tables.md)