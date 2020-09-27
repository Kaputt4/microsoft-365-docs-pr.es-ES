---
title: Usar etiquetas de confidencialidad como condición en las directivas DLP (vista previa)
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
description: Obtenga más información sobre los servicios y los tipos de elementos en los que puede usar etiquetas de sensibilidad como condiciones en directivas DLP
ms.openlocfilehash: bb06ed6919a396bef1e5d1f1cb04731fa11267ae
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235727"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a><span data-ttu-id="30f83-103">Usar etiquetas de confidencialidad como condición en las directivas DLP (vista previa)</span><span class="sxs-lookup"><span data-stu-id="30f83-103">Use sensitivity labels as conditions in DLP policies (preview)</span></span>

<span data-ttu-id="30f83-104">Puede usar [etiquetas de confidencialidad](sensitivity-labels.md) como condiciones en las directivas DLP para estas ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="30f83-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="30f83-105">Mensajes de correo electrónico de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="30f83-105">Exchange Online email messages</span></span>
- <span data-ttu-id="30f83-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="30f83-106">SharePoint Online</span></span>
- <span data-ttu-id="30f83-107">Sitios de OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="30f83-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="30f83-108">Dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="30f83-108">Windows 10 devices</span></span>

<span data-ttu-id="30f83-109">Las etiquetas de confidencialidad aparecen como una opción en la lista de **Contenido**.</span><span class="sxs-lookup"><span data-stu-id="30f83-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

![etiqueta de confidencialidad como una condición](../media/dlp-sensitivity-label-as-a-condition.png)

## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="30f83-111">Elementos compatibles, escenarios y sugerencias de directiva</span><span class="sxs-lookup"><span data-stu-id="30f83-111">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="30f83-112">Puede usar etiquetas de confidencialidad como condiciones para estos elementos y en estos escenarios.</span><span class="sxs-lookup"><span data-stu-id="30f83-112">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="30f83-113">Elementos compatibles</span><span class="sxs-lookup"><span data-stu-id="30f83-113">Supported items</span></span>

|<span data-ttu-id="30f83-114">servicio</span><span class="sxs-lookup"><span data-stu-id="30f83-114">service</span></span>  |<span data-ttu-id="30f83-115">tipo de elemento</span><span class="sxs-lookup"><span data-stu-id="30f83-115">item type</span></span>  |<span data-ttu-id="30f83-116">disponible para sugerencia de directiva</span><span class="sxs-lookup"><span data-stu-id="30f83-116">available to policy tip</span></span>  |<span data-ttu-id="30f83-117">aplicable</span><span class="sxs-lookup"><span data-stu-id="30f83-117">enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="30f83-118">Exchange</span><span class="sxs-lookup"><span data-stu-id="30f83-118">Exchange</span></span>    |<span data-ttu-id="30f83-119">mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="30f83-119">email message</span></span>         |<span data-ttu-id="30f83-120">sí</span><span class="sxs-lookup"><span data-stu-id="30f83-120">yes</span></span>         |<span data-ttu-id="30f83-121">sí</span><span class="sxs-lookup"><span data-stu-id="30f83-121">yes</span></span>         |
|<span data-ttu-id="30f83-122">Exchange</span><span class="sxs-lookup"><span data-stu-id="30f83-122">Exchange</span></span>    |<span data-ttu-id="30f83-123">datos adjuntos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="30f83-123">email attachment</span></span>         |<span data-ttu-id="30f83-124">no \*</span><span class="sxs-lookup"><span data-stu-id="30f83-124">no \*</span></span>         |<span data-ttu-id="30f83-125">no \*</span><span class="sxs-lookup"><span data-stu-id="30f83-125">no \*</span></span>         |
|<span data-ttu-id="30f83-126">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="30f83-126">SharePoint Online</span></span>     |<span data-ttu-id="30f83-127">elementos en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="30f83-127">items in SharePoint Online</span></span>         |<span data-ttu-id="30f83-128">sí</span><span class="sxs-lookup"><span data-stu-id="30f83-128">yes</span></span>         |<span data-ttu-id="30f83-129">sí</span><span class="sxs-lookup"><span data-stu-id="30f83-129">yes</span></span>         |
|<span data-ttu-id="30f83-130">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="30f83-130">OneDrive for Business</span></span>     |<span data-ttu-id="30f83-131">elementos</span><span class="sxs-lookup"><span data-stu-id="30f83-131">items</span></span>         |<span data-ttu-id="30f83-132">sí</span><span class="sxs-lookup"><span data-stu-id="30f83-132">yes</span></span>         |<span data-ttu-id="30f83-133">sí</span><span class="sxs-lookup"><span data-stu-id="30f83-133">yes</span></span>         |
|<span data-ttu-id="30f83-134">Teams</span><span class="sxs-lookup"><span data-stu-id="30f83-134">Teams</span></span>     |<span data-ttu-id="30f83-135">Mensajes de canal y de Teams</span><span class="sxs-lookup"><span data-stu-id="30f83-135">Teams and channel messages</span></span>         |<span data-ttu-id="30f83-136">no aplicable</span><span class="sxs-lookup"><span data-stu-id="30f83-136">not applicable</span></span>         |<span data-ttu-id="30f83-137">no aplicable</span><span class="sxs-lookup"><span data-stu-id="30f83-137">not applicable</span></span>         |
|<span data-ttu-id="30f83-138">Teams</span><span class="sxs-lookup"><span data-stu-id="30f83-138">Teams</span></span>     |<span data-ttu-id="30f83-139">datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="30f83-139">attachements</span></span>         |<span data-ttu-id="30f83-140">sí \*\*</span><span class="sxs-lookup"><span data-stu-id="30f83-140">yes \*\*</span></span>         |<span data-ttu-id="30f83-141">sí \*\*</span><span class="sxs-lookup"><span data-stu-id="30f83-141">yes \*\*</span></span>         |
|<span data-ttu-id="30f83-142">Dispositivos de Windows 10 (vista previa)</span><span class="sxs-lookup"><span data-stu-id="30f83-142">Windows 10 devices (preview)</span></span>     |<span data-ttu-id="30f83-143">elementos</span><span class="sxs-lookup"><span data-stu-id="30f83-143">items</span></span>         |<span data-ttu-id="30f83-144">sí</span><span class="sxs-lookup"><span data-stu-id="30f83-144">yes</span></span>         |<span data-ttu-id="30f83-145">sí</span><span class="sxs-lookup"><span data-stu-id="30f83-145">yes</span></span>         |
|<span data-ttu-id="30f83-146">MCAS (vista previa)</span><span class="sxs-lookup"><span data-stu-id="30f83-146">MCAS (preview)</span></span> |<span data-ttu-id="30f83-147">elementos</span><span class="sxs-lookup"><span data-stu-id="30f83-147">items</span></span>         |<span data-ttu-id="30f83-148">sí</span><span class="sxs-lookup"><span data-stu-id="30f83-148">yes</span></span>         |<span data-ttu-id="30f83-149">sí</span><span class="sxs-lookup"><span data-stu-id="30f83-149">yes</span></span>         |

<span data-ttu-id="30f83-150">\* Se admite la detección DLP de etiquetas de confidencialidad en mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="30f83-150">\* DLP detection of sensitivity labels on emails are supported.</span></span> <span data-ttu-id="30f83-151">No se admite la detección DLP de etiquetas de confidencialidad en los datos adjuntos de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="30f83-151">DLP detection of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="30f83-152">\*\* Los datos adjuntos enviados en Teams sobre chats o canales 1:1 se cargan automáticamente en OneDrive para la empresa y SharePoint.</span><span class="sxs-lookup"><span data-stu-id="30f83-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to One drive for business and SharePoint.</span></span> <span data-ttu-id="30f83-153">Por lo tanto, si se incluyen SharePoint Online o OneDrive para la empresa como ubicaciones en su directiva DLP, los datos adjuntos etiquetados enviados en Teams se incluirán automáticamente en el ámbito de esta condición.</span><span class="sxs-lookup"><span data-stu-id="30f83-153">So if SharePoint Online or One Drive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="30f83-154">No es necesario seleccionar Teams como una ubicación en la Directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="30f83-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="30f83-155">Escenarios admitidos</span><span class="sxs-lookup"><span data-stu-id="30f83-155">Supported scenarios</span></span>

- <span data-ttu-id="30f83-156">El administrador de DLP podrá ver una lista de todas las etiquetas de confidencialidad en el espacio empresarial cuando decida incluir una o más etiquetas de confidencialidad como condición.</span><span class="sxs-lookup"><span data-stu-id="30f83-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>
- <span data-ttu-id="30f83-157">El uso de las etiquetas de confidencialidad como condición se admite en todas las cargas de trabajo, como se indica en la matriz de soporte más arriba</span><span class="sxs-lookup"><span data-stu-id="30f83-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above</span></span>
- <span data-ttu-id="30f83-158">Las sugerencias de directiva DLP se seguirán mostrando en las cargas de trabajo (excepto Outlook Win32) para las directivas DLP que contienen la etiqueta de confidencialidad como condición.</span><span class="sxs-lookup"><span data-stu-id="30f83-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>
- <span data-ttu-id="30f83-159">Las etiquetas de sensibilidad también aparecerán como parte del correo del informe de incidentes si se cumple una directiva DLP con la etiqueta de confidencialidad como condición.</span><span class="sxs-lookup"><span data-stu-id="30f83-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>
- <span data-ttu-id="30f83-160">Los detalles de la etiqueta de confidencialidad también se mostrarán en el registro de auditoría de coincidencia de regla DLP para una coincidencia de directiva DLP que contiene la etiqueta de confidencialidad como condición.</span><span class="sxs-lookup"><span data-stu-id="30f83-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="30f83-161">Sugerencias de directivas compatibles</span><span class="sxs-lookup"><span data-stu-id="30f83-161">Support policy tips</span></span>


|<span data-ttu-id="30f83-162">carga de trabajo</span><span class="sxs-lookup"><span data-stu-id="30f83-162">workload</span></span>  |<span data-ttu-id="30f83-163">Sugerencias sobre las directivas compatibles / no compatibles</span><span class="sxs-lookup"><span data-stu-id="30f83-163">policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="30f83-164">OWA</span><span class="sxs-lookup"><span data-stu-id="30f83-164">OWA</span></span> |    <span data-ttu-id="30f83-165">compatible</span><span class="sxs-lookup"><span data-stu-id="30f83-165">supported</span></span>     |
|<span data-ttu-id="30f83-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="30f83-166">Outlook Win 32</span></span>    |  <span data-ttu-id="30f83-167">no compatible</span><span class="sxs-lookup"><span data-stu-id="30f83-167">not supported</span></span>       |
|<span data-ttu-id="30f83-168">SharePoint</span><span class="sxs-lookup"><span data-stu-id="30f83-168">SharePoint</span></span>   |   <span data-ttu-id="30f83-169">compatible</span><span class="sxs-lookup"><span data-stu-id="30f83-169">supported</span></span>      |
|<span data-ttu-id="30f83-170">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="30f83-170">OneDrive for Business</span></span>    |    <span data-ttu-id="30f83-171">compatible</span><span class="sxs-lookup"><span data-stu-id="30f83-171">supported</span></span>     |
|<span data-ttu-id="30f83-172">dispositivos de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="30f83-172">endpoint devices</span></span>   |  <span data-ttu-id="30f83-173">no compatible</span><span class="sxs-lookup"><span data-stu-id="30f83-173">not supported</span></span>       |
