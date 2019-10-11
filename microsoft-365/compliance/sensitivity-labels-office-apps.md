---
title: Cómo funcionan las etiquetas de confidencialidad en las aplicaciones de Office
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Con las etiquetas de confidencialidad, puede clasificar y ayudar a proteger el contenido confidencial, sin poner impedimentos a la productividad y la capacidad de colaboración de los usuarios. Puede usar etiquetas de confidencialidad para aplicar opciones de protección como encriptación o marcas de agua en el contenido con la etiqueta.
ms.openlocfilehash: f702423f0b1074b5619ef1c321cc5e9f1daef1d7
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417569"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a><span data-ttu-id="65616-104">Cómo funcionan las etiquetas de confidencialidad en las aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="65616-104">How sensitivity labels work in Office apps</span></span>

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a><span data-ttu-id="65616-105">¿Cuáles son los requisitos previos para usar etiquetas de confidencialidad en las aplicaciones de Office?</span><span class="sxs-lookup"><span data-stu-id="65616-105">What prerequisites are there to use sensitivity labels in Office applications?</span></span>

### <a name="common-requirements"></a><span data-ttu-id="65616-106">Requisitos comunes</span><span class="sxs-lookup"><span data-stu-id="65616-106">Common requirements</span></span> 

- <span data-ttu-id="65616-107">Las etiquetas de confidencialidad unificadas deben ser [configuradas y publicadas en el Centro de Seguridad y Cumplimiento](https://aka.ms/managemip)</span><span class="sxs-lookup"><span data-stu-id="65616-107">Unified sensitivity labels must be [configured and published in the Security and Compliance Center](https://aka.ms/managemip)</span></span>
- <span data-ttu-id="65616-108">Los usuarios tienen que haber iniciado sesión en Office con su cuenta profesional.</span><span class="sxs-lookup"><span data-stu-id="65616-108">Users must be signed in to Office with their work account.</span></span>
- <span data-ttu-id="65616-109">Los usuarios deben tener asignada una licencia de Office 365 E3 o superior.</span><span class="sxs-lookup"><span data-stu-id="65616-109">Users must have an Office 365 E3 or above license assigned.</span></span>

### <a name="additional-requirements-for-office-for-windows"></a><span data-ttu-id="65616-110">Requisitos adicionales de Office para Windows</span><span class="sxs-lookup"><span data-stu-id="65616-110">Additional requirements for Office for Windows</span></span> 

- <span data-ttu-id="65616-111">El cliente de Azure Information Protection no debe estar ejecutándose en Office.</span><span class="sxs-lookup"><span data-stu-id="65616-111">The Azure Information Protection client must not be running in Office.</span></span> <span data-ttu-id="65616-112">Vea también: [¿Las etiquetas de confidencialidad pueden ejecutarse junto al cliente de Azure Information Protection en Office para Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).</span><span class="sxs-lookup"><span data-stu-id="65616-112">See also: [Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).</span></span>

### <a name="additional-requirements-for-outlook-on-all-platforms"></a><span data-ttu-id="65616-113">Requisitos adicionales para Outlook en todas las plataformas</span><span class="sxs-lookup"><span data-stu-id="65616-113">Additional requirements for Outlook on all platforms</span></span> 

- <span data-ttu-id="65616-114">En la configuración de la etiqueta, si activa la marca de contenido, debe usar Exchange Online para que la marca de contenido se inserte en tránsito.</span><span class="sxs-lookup"><span data-stu-id="65616-114">In your label configuration, if you turn on content marking, you must be using Exchange Online for that content marking to be inserted in transit.</span></span>

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a><span data-ttu-id="65616-115">¿Qué funcionalidades de etiqueta de confidencialidad admite Office en la actualidad?</span><span class="sxs-lookup"><span data-stu-id="65616-115">What sensitivity label capabilities are supported in Office today?</span></span> 

<table border="1" cellspacing="0" cellpadding="0">
<th><span data-ttu-id="65616-116"><font size="-1">Funcionalidad</span><span class="sxs-lookup"><span data-stu-id="65616-116"><font size="-1">Capability</span></span><th><span data-ttu-id="65616-117"><font size="-1">Windows </span><span class="sxs-lookup"><span data-stu-id="65616-117"><font size="-1">Windows</span></span><th><span data-ttu-id="65616-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span><span class="sxs-lookup"><span data-stu-id="65616-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span></span></tr>
<tr><td>

<td><span data-ttu-id="65616-119"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="65616-119"><font size="-1"> Word</span></span><br>
<span data-ttu-id="65616-120">Excel</span><span class="sxs-lookup"><span data-stu-id="65616-120">Excel</span></span><br>
<span data-ttu-id="65616-121">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="65616-121">PowerPoint</span></span><br>
<span data-ttu-id="65616-122">Outlook</span><span class="sxs-lookup"><span data-stu-id="65616-122">Outlook</span></span>


<td><span data-ttu-id="65616-123"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="65616-123"><font size="-1"> Word</span></span><br>
<span data-ttu-id="65616-124">Excel</span><span class="sxs-lookup"><span data-stu-id="65616-124">Excel</span></span><br>
<span data-ttu-id="65616-125">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="65616-125">PowerPoint</span></span><br>
<span data-ttu-id="65616-126">Outlook</span><span class="sxs-lookup"><span data-stu-id="65616-126">Outlook</span></span>

<td><span data-ttu-id="65616-127"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="65616-127"><font size="-1"> Word</span></span><br>
<span data-ttu-id="65616-128">Excel</span><span class="sxs-lookup"><span data-stu-id="65616-128">Excel</span></span><br>
<span data-ttu-id="65616-129">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="65616-129">PowerPoint</span></span>
<td><span data-ttu-id="65616-130"><font size="-1">Outlook</span><span class="sxs-lookup"><span data-stu-id="65616-130"><font size="-1"> Outlook</span></span>

<td><span data-ttu-id="65616-131"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="65616-131"><font size="-1"> Word</span></span><br>
<span data-ttu-id="65616-132">Excel</span><span class="sxs-lookup"><span data-stu-id="65616-132">Excel</span></span><br>
<span data-ttu-id="65616-133">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="65616-133">PowerPoint</span></span>
<td><span data-ttu-id="65616-134"><font size="-1">Outlook</span><span class="sxs-lookup"><span data-stu-id="65616-134"><font size="-1"> Outlook</span></span>

<td><span data-ttu-id="65616-135"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="65616-135"><font size="-1"> Word</span></span><br>
<span data-ttu-id="65616-136">Excel</span><span class="sxs-lookup"><span data-stu-id="65616-136">Excel</span></span><br>
<span data-ttu-id="65616-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="65616-137">PowerPoint</span></span>
<td><span data-ttu-id="65616-138"><font size="-1">Outlook</b>
</span><span class="sxs-lookup"><span data-stu-id="65616-138"><font size="-1"> Outlook </b>
</span></span></tr>

<tr>
<td><span data-ttu-id="65616-139"><font size="-1">Aplicar, cambiar o quitar manualmente la etiqueta</span><span class="sxs-lookup"><span data-stu-id="65616-139"><font size="-1">Manually apply, change, or remove label</span></span><td><span data-ttu-id="65616-140"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-140"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-141"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="65616-141"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="65616-142"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-142"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-143"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="65616-143"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="65616-144"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-144"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-145"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="65616-145"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="65616-146"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="65616-146"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="65616-147"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-147"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-148"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="65616-148"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="65616-149"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="65616-149"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="65616-150"><font size="-1">Próximamente...<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="65616-150"><font size="-1">Coming soon<sup>3</sup></span></span><td><span data-ttu-id="65616-151"><font size="-1">Próximamente<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="65616-151"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr>
<td><span data-ttu-id="65616-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Aplicar una etiqueta predeterminada</a>
</span><span class="sxs-lookup"><span data-stu-id="65616-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Apply a default label</a>
</span></span><td><span data-ttu-id="65616-153"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-153"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-154"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="65616-154"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="65616-155"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-155"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-156"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="65616-156"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="65616-157"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-157"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-158"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="65616-158"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="65616-159"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="65616-159"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="65616-160"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-160"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-161"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="65616-161"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="65616-162"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="65616-162"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="65616-163"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="65616-163"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="65616-164"><font size="-1">Próximamente...<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="65616-164"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="65616-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Requerir una justificación para cambiar un etiqueta</a><sup>1</sup>
</span><span class="sxs-lookup"><span data-stu-id="65616-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Require a justification for changing a label</a><sup>1</sup>
</span></span><td><span data-ttu-id="65616-166"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-166"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-167"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="65616-167"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="65616-168"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-168"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-169"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="65616-169"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="65616-170"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-170"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-171"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="65616-171"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="65616-172"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="65616-172"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="65616-173"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-173"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-174"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="65616-174"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="65616-175"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="65616-175"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="65616-176"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="65616-176"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="65616-177"><font size="-1">Próximamente...<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="65616-177"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="65616-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Proporcionar un vínculo de ayuda a una página de ayuda personalizada</a>
</span><span class="sxs-lookup"><span data-stu-id="65616-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Provide help link to a custom help page</a>
</span></span><td><span data-ttu-id="65616-179"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-179"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-180"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="65616-180"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="65616-181"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-181"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-182"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="65616-182"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="65616-183"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-183"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-184"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="65616-184"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="65616-185"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="65616-185"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="65616-186"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-186"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-187"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="65616-187"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="65616-188"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="65616-188"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="65616-189"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="65616-189"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="65616-190"><font size="-1">Próximamente...<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="65616-190"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="65616-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Marcar el contenido</a>
</span><span class="sxs-lookup"><span data-stu-id="65616-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Mark the content</a>
</span></span><td><span data-ttu-id="65616-192"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-192"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-193"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="65616-193"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="65616-194"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-194"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-195"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="65616-195"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="65616-196"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-196"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-197"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="65616-197"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="65616-198"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="65616-198"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="65616-199"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-199"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-200"><font size="-1">16.0.11231+</font
</span><span class="sxs-lookup"><span data-stu-id="65616-200"><font size="-1">16.0.11231+</font
</span></span>><td><span data-ttu-id="65616-201"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="65616-201"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="65616-202"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="65616-202"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="65616-203"><font size="-1">Próximamente...<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="65616-203"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="65616-204"><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/encryption-sensitivity-labels#assign-permissions-now">Asignar permisos definidos previamente</a>
</span><span class="sxs-lookup"><span data-stu-id="65616-204"><font size="-1">Assign pre-defined permissions</span></span><td><span data-ttu-id="65616-205"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-205"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-206"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="65616-206"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="65616-207"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-207"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-208"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="65616-208"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="65616-209"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-209"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-210"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="65616-210"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="65616-211"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="65616-211"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="65616-212"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="65616-212"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="65616-213"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="65616-213"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="65616-214"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="65616-214"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="65616-215"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="65616-215"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="65616-216"><font size="-1">Próximamente...<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="65616-216"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="65616-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">Permitir a los usuarios asignar permisos</a>
</span><span class="sxs-lookup"><span data-stu-id="65616-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">Let users assign permissions</a>
</span></span><td><span data-ttu-id="65616-218"><font size="-1"><b>Sí</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="65616-218"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="65616-219"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="65616-219"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="65616-220"><font size="-1"><b>Sí</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="65616-220"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="65616-221"><font size="-1">16.21.0+</font></span><span class="sxs-lookup"><span data-stu-id="65616-221"><font size="-1">16.21.0+</font></span></span>

<td><span data-ttu-id="65616-222"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-222"><font size="-1">TBD</span></span>
<td><span data-ttu-id="65616-223"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="65616-223"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="65616-224"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-224"><font size="-1">TBD</span></span><td
><span data-ttu-id="65616-225"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="65616-225"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="65616-226"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-226"><font size="-1">TBD</span></span>
<td><span data-ttu-id="65616-227"><font size="-1">Próximamente...<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="65616-227"><font size="-1">Coming soon<sup>3</sup></span></span>

<tr><td><span data-ttu-id="65616-228"><font size="-1">Enviar<a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">datos de análisis de etiquetas</a>para administradores</span><span class="sxs-lookup"><span data-stu-id="65616-228"><font size="-1">Send <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">label analytics</a> data for administrators</span></span>
<td><span data-ttu-id="65616-229"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-229"><font size="-1">TBD</span></span>

<td><span data-ttu-id="65616-230"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-230"><font size="-1">TBD</span></span>

<td><span data-ttu-id="65616-231"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-231"><font size="-1">TBD</span></span>
<td><span data-ttu-id="65616-232"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-232"><font size="-1">TBD</span></span>
<td><span data-ttu-id="65616-233"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-233"><font size="-1">TBD</span></span>
<td><span data-ttu-id="65616-234"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-234"><font size="-1">TBD</span></span>
<td><span data-ttu-id="65616-235"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-235"><font size="-1">TBD</span></span>
<td><span data-ttu-id="65616-236"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-236"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="65616-237"><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Requerir que los usuarios apliquen una etiqueta al correo electrónico y a los documentos</a>
</span><span class="sxs-lookup"><span data-stu-id="65616-237"><font size="-1">Require users to apply a label to their email and documents</span></span><td><span data-ttu-id="65616-238"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-238"><font size="-1">TBD</span></span>

<td><span data-ttu-id="65616-239"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-239"><font size="-1">TBD</span></span>

<td><span data-ttu-id="65616-240"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-240"><font size="-1">TBD</span></span>
<td><span data-ttu-id="65616-241"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-241"><font size="-1">TBD</span></span>
<td><span data-ttu-id="65616-242"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-242"><font size="-1">TBD</span></span>
<td><span data-ttu-id="65616-243"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-243"><font size="-1">TBD</span></span>
<td><span data-ttu-id="65616-244"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-244"><font size="-1">TBD</span></span>
<td><span data-ttu-id="65616-245"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-245"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="65616-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">Aplicar automáticamente una etiqueta de confidencialidad al contenido</a>
</span><span class="sxs-lookup"><span data-stu-id="65616-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">Apply a sensitivity label to content automatically</a>
</span></span><td><span data-ttu-id="65616-247"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-247"><font size="-1">TBD</span></span>

<td><span data-ttu-id="65616-248"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-248"><font size="-1">TBD</span></span>

<td><span data-ttu-id="65616-249"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-249"><font size="-1">TBD</span></span>
<td><span data-ttu-id="65616-250"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-250"><font size="-1">TBD</span></span>
<td><span data-ttu-id="65616-251"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-251"><font size="-1">TBD</span></span>
<td><span data-ttu-id="65616-252"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-252"><font size="-1">TBD</span></span>
<td><span data-ttu-id="65616-253"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-253"><font size="-1">TBD</span></span>
<td><span data-ttu-id="65616-254"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="65616-254"><font size="-1">TBD</span></span>
</table>

<br><span data-ttu-id="65616-255"><sup>1</sup>Si está configurada, se pide a los usuarios que justifiquen la degradación de las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="65616-255"><sup>1</sup>If configured, users are prompted to justify label downgrades.</span></span> <span data-ttu-id="65616-256">Sin embargo, los datos de justificación aún no están disponibles para los administradores.</span><span class="sxs-lookup"><span data-stu-id="65616-256">However, the justification data is not made available for administrators yet.</span></span> <span data-ttu-id="65616-257">Estarán disponibles cuando se admita la función de "enviar datos de análisis de etiqueta para administradores".</span><span class="sxs-lookup"><span data-stu-id="65616-257">It will become available when the “send label analytics data for administrators” capability is supported.</span></span>
<br><span data-ttu-id="65616-258"><sup>2</sup> Permitir a los usuarios asignar permisos está actualmente disponible solo en Outlook para Windows y Mac.</span><span class="sxs-lookup"><span data-stu-id="65616-258"><sup>2</sup>Let users assign permissions is currently only available in Outlook for Windows and Mac.</span></span> <span data-ttu-id="65616-259">La disponibilidad para Word, Excel y PowerPoint está por determinar.</span><span class="sxs-lookup"><span data-stu-id="65616-259">Availability for Word, Excel, and PowerPoint is TBD.</span></span>
<br><span data-ttu-id="65616-260"><sup>3</sup>Previsto para el cuarto trimestre del año calendario 2019.</span><span class="sxs-lookup"><span data-stu-id="65616-260"><sup>3</sup>Expected Q4 of calendar year 2019.</span></span>

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a><span data-ttu-id="65616-261">¿Cuándo se aplican las marcas de contenido o el cifrado después de que el contenido recibe una etiqueta de confidencialidad?</span><span class="sxs-lookup"><span data-stu-id="65616-261">When do content marks or encryption get applied after content is given a sensitivity label?</span></span>

| <span data-ttu-id="65616-262">Aplicación</span><span class="sxs-lookup"><span data-stu-id="65616-262">Application</span></span> | <span data-ttu-id="65616-263">Marcado de contenido</span><span class="sxs-lookup"><span data-stu-id="65616-263">Content marking</span></span> | <span data-ttu-id="65616-264">Cifrado</span><span class="sxs-lookup"><span data-stu-id="65616-264">Encryption</span></span>
| --- | --- | --- |
| <span data-ttu-id="65616-265">Word, Excel y PowerPoint en todas las plataformas</span><span class="sxs-lookup"><span data-stu-id="65616-265">Word, Excel, PowerPoint on all platforms</span></span> | <span data-ttu-id="65616-266">De forma inmediata</span><span class="sxs-lookup"><span data-stu-id="65616-266">Immediately</span></span> | <span data-ttu-id="65616-267">De forma inmediata</span><span class="sxs-lookup"><span data-stu-id="65616-267">Immediately</span></span> |
| <span data-ttu-id="65616-268">Outlook para PC y Mac</span><span class="sxs-lookup"><span data-stu-id="65616-268">Outlook for PC and Mac</span></span> | <span data-ttu-id="65616-269">Cuando Exchange Online envíe el correo electrónico</span><span class="sxs-lookup"><span data-stu-id="65616-269">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="65616-270">De forma inmediata</span><span class="sxs-lookup"><span data-stu-id="65616-270">Immediately</span></span> |
| <span data-ttu-id="65616-271">Outlook en la web, iOS, y Android</span><span class="sxs-lookup"><span data-stu-id="65616-271">Outlook on the web, iOS, and Android</span></span> | <span data-ttu-id="65616-272">Cuando Exchange Online envíe el correo electrónico</span><span class="sxs-lookup"><span data-stu-id="65616-272">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="65616-273">Cuando Exchange Online envíe el correo electrónico</span><span class="sxs-lookup"><span data-stu-id="65616-273">After the email is sent by Exchange Online</span></span> |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a><span data-ttu-id="65616-274">¿Las etiquetas de confidencialidad pueden ejecutarse junto al cliente de Azure Information Protection en Office para Windows?</span><span class="sxs-lookup"><span data-stu-id="65616-274">Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?</span></span>

<span data-ttu-id="65616-275">No.</span><span class="sxs-lookup"><span data-stu-id="65616-275">No.</span></span> <span data-ttu-id="65616-276">Las etiquetas de confidencialidad se desactivan si el cliente de Azure Information Protection está cargado en Office para Windows.</span><span class="sxs-lookup"><span data-stu-id="65616-276">Sensitivity labels are turned off if the Azure Information Protection client is loaded in Office for Windows.</span></span>

<span data-ttu-id="65616-277">Si tiene el cliente de Azure Information Protection instalado, pero quiere usar las etiquetas de confidencialidad en su lugar, puede:</span><span class="sxs-lookup"><span data-stu-id="65616-277">If you have the Azure Information Protection client installed, but you want to use sensitivity labels instead, you can:</span></span>

1. <span data-ttu-id="65616-278">Configure la opción  **Use la función de Confidencialidad en Office para aplicar y ver las etiquetas de confidencialidad en la**Configuración de Directiva de grupo, que se encuentra en **Configuración de Usuario /Plantillas administrativas/ Microsoft Office 2016/Configuración de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="65616-278">Configure the **Use the Sensitivity feature in Office to apply and view sensitivity labels** Group Policy setting, which can be found under **User Configuration/Administrative Templates/Microsoft Office 2016/Security Settings**.</span></span>

  ><span data-ttu-id="65616-279">Nota: esta configuración puede implementarse mediante los mecanismos tradicionales de la Directiva de grupo, o bien mediante el [Servicio de directivas en la nube de Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).</span><span class="sxs-lookup"><span data-stu-id="65616-279">Note: this setting can be deployed via traditional group policy deployment mechanisms, or by the [Office cloud policy service](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).</span></span> 
 
  <span data-ttu-id="65616-280">Como alternativa, puede desinstalar o  [deshabilitar](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) el cliente de Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="65616-280">Alternatively, you can uninstall or [disable](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) the Azure Information Protection client.</span></span> 

2. <span data-ttu-id="65616-281">Reiniciar todas las aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="65616-281">Restart all Office applications.</span></span>

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a><span data-ttu-id="65616-282">¿Serán compatibles las etiquetas de confidencialidad en las versiones de Office que no sean de suscripción, como Office 2016 u Office 2019?</span><span class="sxs-lookup"><span data-stu-id="65616-282">Will sensitivity labels be supported in non-subscription versions of Office like Office 2016 or Office 2019?</span></span>

<span data-ttu-id="65616-283">No.</span><span class="sxs-lookup"><span data-stu-id="65616-283">No.</span></span> <span data-ttu-id="65616-284">Las etiquetas de confidencialidad solo serán compatibles con la suscripción de Office 365 y no se admitirán en ninguna versión que no sea de suscripción.</span><span class="sxs-lookup"><span data-stu-id="65616-284">Sensitivity labels will only be supported in the Office 365 subscription and will not be supported in any non-subscription version.</span></span> <span data-ttu-id="65616-285">Sin embargo, el cliente de etiquetado unificado de Azure Information Protection se puede usar en las versiones de Office que no sean de suscripción.</span><span class="sxs-lookup"><span data-stu-id="65616-285">However, the Azure Information Protection unified labeling client may be used in non-subscription versions of Office.</span></span> 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a><span data-ttu-id="65616-286">He implementado previamente plantillas de protección antes de configurar las etiquetas de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="65616-286">I previously deployed protection templates before setting up sensitivity labels.</span></span> <span data-ttu-id="65616-287">¿Dónde se encuentran?</span><span class="sxs-lookup"><span data-stu-id="65616-287">Where did they go?</span></span>

<span data-ttu-id="65616-288">Las [plantillas de protección](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) definidas por el administrados se ocultan de la experiencia de usuario de Office cuando las etiquetas de confidencialidad están habilitadas, ya que son redundantes con las etiquetas de confidencialidad que tienen el cifrado habilitado.</span><span class="sxs-lookup"><span data-stu-id="65616-288">Administrator-defined [protection templates](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) are hidden from the Office user experience when sensitivity labels are enabled because they are redundant with sensitivity labels that have encryption enabled.</span></span> 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a><span data-ttu-id="65616-289">¿Puede un archivo o correo electrónico tener más de una clasificación?</span><span class="sxs-lookup"><span data-stu-id="65616-289">Can a file or email have more than one classification?</span></span>

<span data-ttu-id="65616-290">No.</span><span class="sxs-lookup"><span data-stu-id="65616-290">No.</span></span> <span data-ttu-id="65616-291">Los usuarios pueden hacer una selección de etiquetas para cada documento o correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="65616-291">Users can select just one label at a time for each document or email, which often results in just one classification.</span></span>

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a><span data-ttu-id="65616-292">Cuando se etiqueta un correo electrónico, ¿los datos adjuntos reciben automáticamente la misma etiqueta?</span><span class="sxs-lookup"><span data-stu-id="65616-292">When an email is labeled, do any attachments automatically get the same labeling?</span></span>

<span data-ttu-id="65616-293">No.</span><span class="sxs-lookup"><span data-stu-id="65616-293">No.</span></span> <span data-ttu-id="65616-294">Al etiquetar un mensaje de correo electrónico con datos adjuntos, estos no heredan la misma etiqueta.</span><span class="sxs-lookup"><span data-stu-id="65616-294">When you label an email message that has attachments, those attachments do not inherit the same label.</span></span> <span data-ttu-id="65616-295">Los datos adjuntos permanecen sin etiqueta o mantienen una etiqueta aplicada por separado.</span><span class="sxs-lookup"><span data-stu-id="65616-295">The attachments remain either without a label or retain a separately applied label.</span></span> <span data-ttu-id="65616-296">Sin embargo, si la etiqueta del correo electrónico aplica protección, esa protección se aplicará a los datos adjuntos de Office.</span><span class="sxs-lookup"><span data-stu-id="65616-296">However, if the label for the email applies protection, that protection is applied to Office attachments.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="65616-297">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="65616-297">Additional resources</span></span>

[<span data-ttu-id="65616-298">Preguntas más frecuentes sobre la clasificación y etiquetado en Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="65616-298">Frequently asked questions about classification and labeling in Azure Information Protection</span></span>](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[<span data-ttu-id="65616-299">Aplicar etiquetas de confidencialidad en sus documentos y correo electrónico en Office</span><span class="sxs-lookup"><span data-stu-id="65616-299">Apply sensitivity labels to your documents and email within Office</span></span>](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
