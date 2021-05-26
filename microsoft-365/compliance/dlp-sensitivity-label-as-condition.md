---
title: Usar etiquetas de confidencialidad como condiciones en las directivas de DLP
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga más información sobre los servicios y los tipos de elementos en los que puede usar etiquetas de confidencialidad como condiciones en directivas DLP
ms.openlocfilehash: b33e6704a3311740c1e386f77f1c751382ee6958
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651097"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a><span data-ttu-id="3cc5c-103">Usar etiquetas de confidencialidad como condiciones en las directivas de DLP</span><span class="sxs-lookup"><span data-stu-id="3cc5c-103">Use sensitivity labels as conditions in DLP policies</span></span>

<span data-ttu-id="3cc5c-104">Puede usar [etiquetas de confidencialidad](sensitivity-labels.md) como condiciones en las directivas DLP para estas ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="3cc5c-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="3cc5c-105">Mensajes de correo electrónico de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3cc5c-105">Exchange Online email messages</span></span>
- <span data-ttu-id="3cc5c-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3cc5c-106">SharePoint Online</span></span>
- <span data-ttu-id="3cc5c-107">Sitios de OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="3cc5c-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="3cc5c-108">Dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="3cc5c-108">Windows 10 devices</span></span>

<span data-ttu-id="3cc5c-109">Las etiquetas de confidencialidad aparecen como una opción en la lista de **Contenido**.</span><span class="sxs-lookup"><span data-stu-id="3cc5c-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3cc5c-110">![etiqueta de confidencialidad como una condición](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="3cc5c-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3cc5c-111">**Las etiquetas de confidencialidad** como una condición no estarán disponibles si ha seleccionado **mensajes de canal y de chat de Teams** como una ubicación para aplicar la directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="3cc5c-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="3cc5c-112">Elementos compatibles, escenarios y sugerencias de directiva</span><span class="sxs-lookup"><span data-stu-id="3cc5c-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="3cc5c-113">Puede usar etiquetas de confidencialidad como condiciones para estos elementos y en estos escenarios.</span><span class="sxs-lookup"><span data-stu-id="3cc5c-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="3cc5c-114">Elementos compatibles</span><span class="sxs-lookup"><span data-stu-id="3cc5c-114">Supported items</span></span>

|<span data-ttu-id="3cc5c-115">Servicio</span><span class="sxs-lookup"><span data-stu-id="3cc5c-115">Service</span></span>  |<span data-ttu-id="3cc5c-116">Tipo de elemento</span><span class="sxs-lookup"><span data-stu-id="3cc5c-116">Item type</span></span>  |<span data-ttu-id="3cc5c-117">Disponible para sugerencia de directiva</span><span class="sxs-lookup"><span data-stu-id="3cc5c-117">Available to policy tip</span></span>  |<span data-ttu-id="3cc5c-118">Aplicable</span><span class="sxs-lookup"><span data-stu-id="3cc5c-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="3cc5c-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="3cc5c-119">Exchange</span></span>    |<span data-ttu-id="3cc5c-120">mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="3cc5c-120">email message</span></span>         |<span data-ttu-id="3cc5c-121">sí</span><span class="sxs-lookup"><span data-stu-id="3cc5c-121">yes</span></span>         |<span data-ttu-id="3cc5c-122">sí</span><span class="sxs-lookup"><span data-stu-id="3cc5c-122">yes</span></span>         |
|<span data-ttu-id="3cc5c-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="3cc5c-123">Exchange</span></span>    |<span data-ttu-id="3cc5c-124">datos adjuntos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="3cc5c-124">email attachment</span></span>         |<span data-ttu-id="3cc5c-125">no</span><span class="sxs-lookup"><span data-stu-id="3cc5c-125">no</span></span>         |<span data-ttu-id="3cc5c-126">sí \*</span><span class="sxs-lookup"><span data-stu-id="3cc5c-126">yes \*</span></span>         |
|<span data-ttu-id="3cc5c-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3cc5c-127">SharePoint Online</span></span>     |<span data-ttu-id="3cc5c-128">elementos en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3cc5c-128">items in SharePoint Online</span></span>         |<span data-ttu-id="3cc5c-129">sí</span><span class="sxs-lookup"><span data-stu-id="3cc5c-129">yes</span></span>         |<span data-ttu-id="3cc5c-130">sí</span><span class="sxs-lookup"><span data-stu-id="3cc5c-130">yes</span></span>         |
|<span data-ttu-id="3cc5c-131">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="3cc5c-131">OneDrive for Business</span></span>     |<span data-ttu-id="3cc5c-132">elementos</span><span class="sxs-lookup"><span data-stu-id="3cc5c-132">items</span></span>         |<span data-ttu-id="3cc5c-133">sí</span><span class="sxs-lookup"><span data-stu-id="3cc5c-133">yes</span></span>         |<span data-ttu-id="3cc5c-134">sí</span><span class="sxs-lookup"><span data-stu-id="3cc5c-134">yes</span></span>         |
|<span data-ttu-id="3cc5c-135">Teams</span><span class="sxs-lookup"><span data-stu-id="3cc5c-135">Teams</span></span>     |<span data-ttu-id="3cc5c-136">Mensajes de canal y de Teams</span><span class="sxs-lookup"><span data-stu-id="3cc5c-136">Teams and channel messages</span></span>         |<span data-ttu-id="3cc5c-137">no aplicable</span><span class="sxs-lookup"><span data-stu-id="3cc5c-137">not applicable</span></span>         |<span data-ttu-id="3cc5c-138">no aplicable</span><span class="sxs-lookup"><span data-stu-id="3cc5c-138">not applicable</span></span>         |
|<span data-ttu-id="3cc5c-139">Teams</span><span class="sxs-lookup"><span data-stu-id="3cc5c-139">Teams</span></span>     |<span data-ttu-id="3cc5c-140">datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="3cc5c-140">attachments</span></span>         |<span data-ttu-id="3cc5c-141">sí \*\*</span><span class="sxs-lookup"><span data-stu-id="3cc5c-141">yes \*\*</span></span>         |<span data-ttu-id="3cc5c-142">sí \*\*</span><span class="sxs-lookup"><span data-stu-id="3cc5c-142">yes \*\*</span></span>         |
|<span data-ttu-id="3cc5c-143">Dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="3cc5c-143">Windows 10 devices</span></span>     |<span data-ttu-id="3cc5c-144">elementos</span><span class="sxs-lookup"><span data-stu-id="3cc5c-144">items</span></span>         |<span data-ttu-id="3cc5c-145">sí</span><span class="sxs-lookup"><span data-stu-id="3cc5c-145">yes</span></span>         |<span data-ttu-id="3cc5c-146">sí</span><span class="sxs-lookup"><span data-stu-id="3cc5c-146">yes</span></span>         |
|<span data-ttu-id="3cc5c-147">MCAS (vista previa)</span><span class="sxs-lookup"><span data-stu-id="3cc5c-147">MCAS (preview)</span></span> |<span data-ttu-id="3cc5c-148">elementos</span><span class="sxs-lookup"><span data-stu-id="3cc5c-148">items</span></span>         |<span data-ttu-id="3cc5c-149">sí</span><span class="sxs-lookup"><span data-stu-id="3cc5c-149">yes</span></span>         |<span data-ttu-id="3cc5c-150">sí</span><span class="sxs-lookup"><span data-stu-id="3cc5c-150">yes</span></span>         |

<span data-ttu-id="3cc5c-151">\* La detección DLP de etiquetas de confidencialidad en los datos adjuntos de correo electrónico solo es compatible con tipos de archivo de Office.</span><span class="sxs-lookup"><span data-stu-id="3cc5c-151">\* DLP detection of sensitivity labeled email attachments are supported for Office file types only.</span></span>

<span data-ttu-id="3cc5c-152">\*\* Los datos adjuntos enviados en Teams sobre chats o canales 1:1 son cargados automáticamente en OneDrive para la Empresa y SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3cc5c-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="3cc5c-153">De modo que si SharePoint Online o OneDrive para la Empresa están incluidos como ubicaciones en su directiva de DLP, entonces los adjuntos etiquetados enviados en Teams serán incluidos de forma automática en el alcance de esta condición.</span><span class="sxs-lookup"><span data-stu-id="3cc5c-153">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="3cc5c-154">No es necesario seleccionar Teams como una ubicación en la Directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="3cc5c-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="3cc5c-155">Escenarios admitidos</span><span class="sxs-lookup"><span data-stu-id="3cc5c-155">Supported scenarios</span></span>

- <span data-ttu-id="3cc5c-156">El administrador de DLP podrá ver una lista de todas las etiquetas de confidencialidad en el espacio empresarial cuando decida incluir una o más etiquetas de confidencialidad como condición.</span><span class="sxs-lookup"><span data-stu-id="3cc5c-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="3cc5c-157">El uso de las etiquetas de confidencialidad como condición se admite en todas las cargas de trabajo, como se indica en la matriz de soporte más arriba.</span><span class="sxs-lookup"><span data-stu-id="3cc5c-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="3cc5c-158">Las sugerencias de directiva DLP se seguirán mostrando en las cargas de trabajo (excepto Outlook Win32) para las directivas DLP que contienen la etiqueta de confidencialidad como condición.</span><span class="sxs-lookup"><span data-stu-id="3cc5c-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="3cc5c-159">Las etiquetas de sensibilidad también aparecerán como parte del correo del informe de incidentes si se cumple una directiva DLP con la etiqueta de confidencialidad como condición.</span><span class="sxs-lookup"><span data-stu-id="3cc5c-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="3cc5c-160">Los detalles de la etiqueta de confidencialidad también se mostrarán en el registro de auditoría de coincidencia de regla DLP para una coincidencia de directiva DLP que contiene la etiqueta de confidencialidad como condición.</span><span class="sxs-lookup"><span data-stu-id="3cc5c-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="3cc5c-161">Sugerencias de directivas compatibles</span><span class="sxs-lookup"><span data-stu-id="3cc5c-161">Support policy tips</span></span>


|<span data-ttu-id="3cc5c-162">Carga de trabajo</span><span class="sxs-lookup"><span data-stu-id="3cc5c-162">Workload</span></span>  |<span data-ttu-id="3cc5c-163">Sugerencias sobre las directivas compatibles / no compatibles</span><span class="sxs-lookup"><span data-stu-id="3cc5c-163">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="3cc5c-164">OWA</span><span class="sxs-lookup"><span data-stu-id="3cc5c-164">OWA</span></span> |    <span data-ttu-id="3cc5c-165">compatible</span><span class="sxs-lookup"><span data-stu-id="3cc5c-165">supported</span></span>     |
|<span data-ttu-id="3cc5c-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="3cc5c-166">Outlook Win 32</span></span>    |  <span data-ttu-id="3cc5c-167">no compatible</span><span class="sxs-lookup"><span data-stu-id="3cc5c-167">not supported</span></span>       |
|<span data-ttu-id="3cc5c-168">SharePoint</span><span class="sxs-lookup"><span data-stu-id="3cc5c-168">SharePoint</span></span>   |   <span data-ttu-id="3cc5c-169">compatible</span><span class="sxs-lookup"><span data-stu-id="3cc5c-169">supported</span></span>      |
|<span data-ttu-id="3cc5c-170">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="3cc5c-170">OneDrive for Business</span></span>    |    <span data-ttu-id="3cc5c-171">compatible</span><span class="sxs-lookup"><span data-stu-id="3cc5c-171">supported</span></span>     |
|<span data-ttu-id="3cc5c-172">dispositivos de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="3cc5c-172">endpoint devices</span></span>   |  <span data-ttu-id="3cc5c-173">no compatible</span><span class="sxs-lookup"><span data-stu-id="3cc5c-173">not supported</span></span>       |
