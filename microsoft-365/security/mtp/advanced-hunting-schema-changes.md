---
title: Cambios de nomenclatura en el esquema de búsqueda avanzada de Microsoft 365 Defender
description: Realizar un seguimiento y revisar las tablas y columnas de cambios de nomenclatura en el esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, datos, cambios de nomenclatura, cambiar el nombre, Protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3f03543b03dca5fe426700ffff4f5c6edb8fa3c7
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066874"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="87bf5-104">Esquema de búsqueda avanzada: cambios de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="87bf5-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="87bf5-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="87bf5-105">**Applies to:**</span></span>
- <span data-ttu-id="87bf5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87bf5-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="87bf5-107">El [esquema de búsqueda avanzada se](advanced-hunting-schema-tables.md) actualiza periódicamente para agregar nuevas tablas y columnas.</span><span class="sxs-lookup"><span data-stu-id="87bf5-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="87bf5-108">En algunos casos, se cambia el nombre de los nombres de las columnas existentes o se reemplazan para mejorar la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="87bf5-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="87bf5-109">Consulte este artículo para revisar los cambios de nomenclatura que podrían afectar a las consultas.</span><span class="sxs-lookup"><span data-stu-id="87bf5-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="87bf5-110">Los cambios de nomenclatura se aplican automáticamente a las consultas que se guardan en el centro de seguridad, incluidas las consultas usadas por reglas de detección personalizadas.</span><span class="sxs-lookup"><span data-stu-id="87bf5-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="87bf5-111">No es necesario actualizar estas consultas manualmente.</span><span class="sxs-lookup"><span data-stu-id="87bf5-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="87bf5-112">Sin embargo, tendrá que actualizar las siguientes consultas:</span><span class="sxs-lookup"><span data-stu-id="87bf5-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="87bf5-113">Consultas que se ejecutan con la API</span><span class="sxs-lookup"><span data-stu-id="87bf5-113">Queries that are run using the API</span></span>
- <span data-ttu-id="87bf5-114">Consultas que se guardan en otro lugar fuera del centro de seguridad</span><span class="sxs-lookup"><span data-stu-id="87bf5-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="87bf5-115">Diciembre de 2020</span><span class="sxs-lookup"><span data-stu-id="87bf5-115">December 2020</span></span>

| <span data-ttu-id="87bf5-116">Nombre de tabla</span><span class="sxs-lookup"><span data-stu-id="87bf5-116">Table name</span></span> | <span data-ttu-id="87bf5-117">Nombre de columna original</span><span class="sxs-lookup"><span data-stu-id="87bf5-117">Original column name</span></span> | <span data-ttu-id="87bf5-118">Nombre de columna nueva</span><span class="sxs-lookup"><span data-stu-id="87bf5-118">New column name</span></span> | <span data-ttu-id="87bf5-119">Motivo de la modificación</span><span class="sxs-lookup"><span data-stu-id="87bf5-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="87bf5-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="87bf5-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="87bf5-121">Comentarios del cliente</span><span class="sxs-lookup"><span data-stu-id="87bf5-121">Customer feedback</span></span> |
| [<span data-ttu-id="87bf5-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="87bf5-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="87bf5-123">Comentarios del cliente</span><span class="sxs-lookup"><span data-stu-id="87bf5-123">Customer feedback</span></span> |
| [<span data-ttu-id="87bf5-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="87bf5-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="87bf5-125">Comentarios del cliente</span><span class="sxs-lookup"><span data-stu-id="87bf5-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="87bf5-126">Enero de 2021</span><span class="sxs-lookup"><span data-stu-id="87bf5-126">January 2021</span></span>

| <span data-ttu-id="87bf5-127">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="87bf5-127">Column name</span></span> | <span data-ttu-id="87bf5-128">Nombre del valor original</span><span class="sxs-lookup"><span data-stu-id="87bf5-128">Original value name</span></span> | <span data-ttu-id="87bf5-129">Nuevo nombre de valor</span><span class="sxs-lookup"><span data-stu-id="87bf5-129">New value name</span></span> | <span data-ttu-id="87bf5-130">Motivo de la modificación</span><span class="sxs-lookup"><span data-stu-id="87bf5-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="87bf5-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="87bf5-131">MCAS</span></span> |    <span data-ttu-id="87bf5-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="87bf5-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="87bf5-133">Cambio de marca</span><span class="sxs-lookup"><span data-stu-id="87bf5-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="87bf5-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="87bf5-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="87bf5-135">EDR</span><span class="sxs-lookup"><span data-stu-id="87bf5-135">EDR</span></span>| <span data-ttu-id="87bf5-136">Cambio de marca</span><span class="sxs-lookup"><span data-stu-id="87bf5-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="87bf5-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="87bf5-137">WindowsDefenderAv</span></span> | <span data-ttu-id="87bf5-138">Antivirus</span><span class="sxs-lookup"><span data-stu-id="87bf5-138">Antivirus</span></span> | <span data-ttu-id="87bf5-139">Cambio de marca</span><span class="sxs-lookup"><span data-stu-id="87bf5-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="87bf5-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="87bf5-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="87bf5-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="87bf5-141">SmartScreen</span></span> | <span data-ttu-id="87bf5-142">Cambio de marca</span><span class="sxs-lookup"><span data-stu-id="87bf5-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="87bf5-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="87bf5-143">CustomerTI</span></span> |  <span data-ttu-id="87bf5-144">TI personalizada</span><span class="sxs-lookup"><span data-stu-id="87bf5-144">Custom TI</span></span> | <span data-ttu-id="87bf5-145">Cambio de marca</span><span class="sxs-lookup"><span data-stu-id="87bf5-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="87bf5-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="87bf5-146">OfficeATP</span></span> | <span data-ttu-id="87bf5-147">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="87bf5-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="87bf5-148">Cambio de marca</span><span class="sxs-lookup"><span data-stu-id="87bf5-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="87bf5-149">MTP</span><span class="sxs-lookup"><span data-stu-id="87bf5-149">MTP</span></span>   | <span data-ttu-id="87bf5-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87bf5-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="87bf5-151">Cambio de marca</span><span class="sxs-lookup"><span data-stu-id="87bf5-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="87bf5-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="87bf5-152">AzureATP</span></span> |    <span data-ttu-id="87bf5-153">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="87bf5-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="87bf5-154">Cambio de marca</span><span class="sxs-lookup"><span data-stu-id="87bf5-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="87bf5-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="87bf5-155">CustomDetection</span></span>   | <span data-ttu-id="87bf5-156">Detección personalizada</span><span class="sxs-lookup"><span data-stu-id="87bf5-156">Custom detection</span></span> | <span data-ttu-id="87bf5-157">Cambio de marca</span><span class="sxs-lookup"><span data-stu-id="87bf5-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="87bf5-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="87bf5-158">AutomatedInvestigation</span></span> |<span data-ttu-id="87bf5-159">Investigación automatizada</span><span class="sxs-lookup"><span data-stu-id="87bf5-159">Automated investigation</span></span> | <span data-ttu-id="87bf5-160">Cambio de marca</span><span class="sxs-lookup"><span data-stu-id="87bf5-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="87bf5-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="87bf5-161">ThreatExperts</span></span> | <span data-ttu-id="87bf5-162">Expertos en amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="87bf5-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="87bf5-163">Cambio de marca</span><span class="sxs-lookup"><span data-stu-id="87bf5-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="87bf5-164">TI de terceros</span><span class="sxs-lookup"><span data-stu-id="87bf5-164">3rd party TI</span></span> | <span data-ttu-id="87bf5-165">Sensores de terceros</span><span class="sxs-lookup"><span data-stu-id="87bf5-165">3rd Party sensors</span></span> | <span data-ttu-id="87bf5-166">Cambio de marca</span><span class="sxs-lookup"><span data-stu-id="87bf5-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="87bf5-167">inquilino dedicado</span><span class="sxs-lookup"><span data-stu-id="87bf5-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="87bf5-168">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="87bf5-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="87bf5-169">Cambio de marca</span><span class="sxs-lookup"><span data-stu-id="87bf5-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="87bf5-170">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="87bf5-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="87bf5-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87bf5-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="87bf5-172">Cambio de marca</span><span class="sxs-lookup"><span data-stu-id="87bf5-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="87bf5-173">ATP de Office 365</span><span class="sxs-lookup"><span data-stu-id="87bf5-173">Office 365 ATP</span></span>  |<span data-ttu-id="87bf5-174">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="87bf5-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="87bf5-175">Cambio de marca</span><span class="sxs-lookup"><span data-stu-id="87bf5-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="87bf5-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="87bf5-176">Azure ATP</span></span>    |<span data-ttu-id="87bf5-177">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="87bf5-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="87bf5-178">Cambio de marca</span><span class="sxs-lookup"><span data-stu-id="87bf5-178">Rebranding</span></span> |

<span data-ttu-id="87bf5-179">`DetectionSource`está disponible en la [tabla AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="87bf5-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="87bf5-180">`ServiceSource`está disponible en las [tablas AlertEvidence](advanced-hunting-alertevidence-table.md) [y AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="87bf5-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 
## <a name="related-topics"></a><span data-ttu-id="87bf5-181">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="87bf5-181">Related topics</span></span>
- [<span data-ttu-id="87bf5-182">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="87bf5-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="87bf5-183">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="87bf5-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)