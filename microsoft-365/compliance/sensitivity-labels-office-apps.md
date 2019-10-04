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
ms.openlocfilehash: 1de7eadfcf95a54917c1d5e2cc0d42cc1ad486a5
ms.sourcegitcommit: c7f7ff463141f7d7f0970b64e5a04341db7e4fa8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2019
ms.locfileid: "37378661"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a><span data-ttu-id="31cbb-104">Cómo funcionan las etiquetas de confidencialidad en las aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="31cbb-104">How sensitivity labels work in Office apps</span></span>

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a><span data-ttu-id="31cbb-105">¿Cuáles son los requisitos previos para usar etiquetas de confidencialidad en las aplicaciones de Office?</span><span class="sxs-lookup"><span data-stu-id="31cbb-105">What prerequisites are there to use sensitivity labels in Office applications?</span></span>

### <a name="common-requirements"></a><span data-ttu-id="31cbb-106">Requisitos comunes</span><span class="sxs-lookup"><span data-stu-id="31cbb-106">Common requirements</span></span> 

- <span data-ttu-id="31cbb-107">Las etiquetas de confidencialidad unificadas deben ser [configuradas y publicadas en el Centro de Seguridad y Cumplimiento](https://aka.ms/managemip)</span><span class="sxs-lookup"><span data-stu-id="31cbb-107">Unified sensitivity labels must be [configured and published in the Security and Compliance Center](https://aka.ms/managemip)</span></span>
- <span data-ttu-id="31cbb-108">Los usuarios tienen que haber iniciado sesión en Office con su cuenta profesional.</span><span class="sxs-lookup"><span data-stu-id="31cbb-108">Users must be signed in to Office with their work account.</span></span>
- <span data-ttu-id="31cbb-109">Los usuarios deben tener asignada una licencia de Office 365 E3 o superior.</span><span class="sxs-lookup"><span data-stu-id="31cbb-109">Users must have an Office 365 E3 or above license assigned.</span></span>

### <a name="additional-requirements-for-office-for-windows"></a><span data-ttu-id="31cbb-110">Requisitos adicionales de Office para Windows</span><span class="sxs-lookup"><span data-stu-id="31cbb-110">Additional requirements for Office for Windows</span></span> 

- <span data-ttu-id="31cbb-111">El cliente de Azure Information Protection no debe estar ejecutándose en Office.</span><span class="sxs-lookup"><span data-stu-id="31cbb-111">The Azure Information Protection client must not be running in Office.</span></span> <span data-ttu-id="31cbb-112">Vea también: [¿Las etiquetas de confidencialidad pueden ejecutarse junto al cliente de Azure Information Protection en Office para Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).</span><span class="sxs-lookup"><span data-stu-id="31cbb-112">See also: [Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).</span></span>

### <a name="additional-requirements-for-outlook-on-all-platforms"></a><span data-ttu-id="31cbb-113">Requisitos adicionales para Outlook en todas las plataformas</span><span class="sxs-lookup"><span data-stu-id="31cbb-113">Additional requirements for Outlook on all platforms</span></span> 

- <span data-ttu-id="31cbb-114">En la configuración de la etiqueta, si activa la marca de contenido, debe usar Exchange Online para que la marca de contenido se inserte en tránsito.</span><span class="sxs-lookup"><span data-stu-id="31cbb-114">In your label configuration, if you turn on content marking, you must be using Exchange Online for that content marking to be inserted in transit.</span></span>

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a><span data-ttu-id="31cbb-115">¿Qué funcionalidades de etiqueta de confidencialidad admite Office en la actualidad?</span><span class="sxs-lookup"><span data-stu-id="31cbb-115">What sensitivity label capabilities are supported in Office today?</span></span> 

<table border="1" cellspacing="0" cellpadding="0">
<th><span data-ttu-id="31cbb-116"><font size="-1">Funcionalidad</span><span class="sxs-lookup"><span data-stu-id="31cbb-116"><font size="-1"></span></span><th><span data-ttu-id="31cbb-117"><font size="-1">Windows </span><span class="sxs-lookup"><span data-stu-id="31cbb-117"><font size="-1"></span></span><th><span data-ttu-id="31cbb-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span><span class="sxs-lookup"><span data-stu-id="31cbb-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span></span></tr>
<tr><td>

<td><span data-ttu-id="31cbb-119"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="31cbb-119"><font size="-1">Word</span></span><br>
<span data-ttu-id="31cbb-120">Excel</span><span class="sxs-lookup"><span data-stu-id="31cbb-120">Excel</span></span><br>
<span data-ttu-id="31cbb-121">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="31cbb-121">PowerPoint</span></span><br>
<span data-ttu-id="31cbb-122">Outlook</span><span class="sxs-lookup"><span data-stu-id="31cbb-122">Outlook</span></span>


<td><span data-ttu-id="31cbb-123"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="31cbb-123"><font size="-1">Word</span></span><br>
<span data-ttu-id="31cbb-124">Excel</span><span class="sxs-lookup"><span data-stu-id="31cbb-124">Excel</span></span><br>
<span data-ttu-id="31cbb-125">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="31cbb-125">PowerPoint</span></span><br>
<span data-ttu-id="31cbb-126">Outlook</span><span class="sxs-lookup"><span data-stu-id="31cbb-126">Outlook</span></span>

<td><span data-ttu-id="31cbb-127"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="31cbb-127"><font size="-1">Word</span></span><br>
<span data-ttu-id="31cbb-128">Excel</span><span class="sxs-lookup"><span data-stu-id="31cbb-128">Excel</span></span><br>
<span data-ttu-id="31cbb-129">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="31cbb-129">PowerPoint</span></span>
<td><span data-ttu-id="31cbb-130"><font size="-1">Outlook</span><span class="sxs-lookup"><span data-stu-id="31cbb-130"><font size="-1">Outlook</span></span>

<td><span data-ttu-id="31cbb-131"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="31cbb-131"><font size="-1">Word</span></span><br>
<span data-ttu-id="31cbb-132">Excel</span><span class="sxs-lookup"><span data-stu-id="31cbb-132">Excel</span></span><br>
<span data-ttu-id="31cbb-133">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="31cbb-133">PowerPoint</span></span>
<td><span data-ttu-id="31cbb-134"><font size="-1">Outlook</span><span class="sxs-lookup"><span data-stu-id="31cbb-134"><font size="-1">Outlook</span></span>

<td><span data-ttu-id="31cbb-135"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="31cbb-135"><font size="-1">Word</span></span><br>
<span data-ttu-id="31cbb-136">Excel</span><span class="sxs-lookup"><span data-stu-id="31cbb-136">Excel</span></span><br>
<span data-ttu-id="31cbb-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="31cbb-137">PowerPoint</span></span>
<td><span data-ttu-id="31cbb-138"><font size="-1">Outlook</b>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-138">Outlook</span></span></tr>

<tr>
<td><span data-ttu-id="31cbb-139"><font size="-1">Aplicar, cambiar o quitar manualmente la etiqueta</span><span class="sxs-lookup"><span data-stu-id="31cbb-139"><font size="-1">Manually apply, change, or remove label</span></span><td><span data-ttu-id="31cbb-140"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-140">Yes</span></span><br><span data-ttu-id="31cbb-141"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="31cbb-141"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="31cbb-142"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-142">Yes</span></span><br><span data-ttu-id="31cbb-143"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="31cbb-143"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="31cbb-144"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-144">Yes</span></span><br><span data-ttu-id="31cbb-145"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-145"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="31cbb-146"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-146"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="31cbb-147"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-147">Yes</span></span><br><span data-ttu-id="31cbb-148"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-148"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="31cbb-149"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-149"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="31cbb-150"><font size="-1">Próximamente...<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="31cbb-150"><font size="-1">Coming soon<sup>3</sup></span></span><td><span data-ttu-id="31cbb-151"><font size="-1">Próximamente<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="31cbb-151"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr>
<td><span data-ttu-id="31cbb-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Aplicar una etiqueta predeterminada</a>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Apply a default label</a>
</span></span><td><span data-ttu-id="31cbb-153"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-153">Yes</span></span><br><span data-ttu-id="31cbb-154"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="31cbb-154"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="31cbb-155"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-155">Yes</span></span><br><span data-ttu-id="31cbb-156"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="31cbb-156"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="31cbb-157"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-157">Yes</span></span><br><span data-ttu-id="31cbb-158"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-158"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="31cbb-159"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-159"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="31cbb-160"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-160">Yes</span></span><br><span data-ttu-id="31cbb-161"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-161"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="31cbb-162"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-162"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="31cbb-163"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-163"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="31cbb-164"><font size="-1">Próximamente...<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="31cbb-164"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="31cbb-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Requerir una justificación para cambiar un etiqueta</a><sup>1</sup>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Require a justification for changing a label</a><sup>1</sup>
</span></span><td><span data-ttu-id="31cbb-166"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-166">Yes</span></span><br><span data-ttu-id="31cbb-167"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="31cbb-167"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="31cbb-168"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-168">Yes</span></span><br><span data-ttu-id="31cbb-169"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="31cbb-169"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="31cbb-170"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-170">Yes</span></span><br><span data-ttu-id="31cbb-171"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-171"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="31cbb-172"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-172"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="31cbb-173"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-173">Yes</span></span><br><span data-ttu-id="31cbb-174"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-174"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="31cbb-175"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-175"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="31cbb-176"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-176"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="31cbb-177"><font size="-1">Próximamente...<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="31cbb-177"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="31cbb-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Proporcionar un vínculo de ayuda a una página de ayuda personalizada</a>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Provide help link to a custom help page</a>
</span></span><td><span data-ttu-id="31cbb-179"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-179">Yes</span></span><br><span data-ttu-id="31cbb-180"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="31cbb-180"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="31cbb-181"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-181">Yes</span></span><br><span data-ttu-id="31cbb-182"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="31cbb-182"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="31cbb-183"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-183">Yes</span></span><br><span data-ttu-id="31cbb-184"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-184"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="31cbb-185"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-185"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="31cbb-186"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-186">Yes</span></span><br><span data-ttu-id="31cbb-187"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-187"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="31cbb-188"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-188"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="31cbb-189"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-189"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="31cbb-190"><font size="-1">Próximamente...<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="31cbb-190"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="31cbb-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Marcar el contenido</a>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Mark the content</a>
</span></span><td><span data-ttu-id="31cbb-192"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-192">Yes</span></span><br><span data-ttu-id="31cbb-193"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="31cbb-193"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="31cbb-194"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-194">Yes</span></span><br><span data-ttu-id="31cbb-195"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="31cbb-195"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="31cbb-196"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-196">Yes</span></span><br><span data-ttu-id="31cbb-197"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-197"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="31cbb-198"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-198"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="31cbb-199"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-199">Yes</span></span><br><span data-ttu-id="31cbb-200"><font size="-1">16.0.11231+</font
</span><span class="sxs-lookup"><span data-stu-id="31cbb-200"><font size="-1">16.0.11231+</font
</span></span>><td><span data-ttu-id="31cbb-201"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-201"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="31cbb-202"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-202"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="31cbb-203"><font size="-1">Próximamente...<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="31cbb-203"><font size="-1">Coming soon<sup>3</sup></span></span>

<tr><td><span data-ttu-id="31cbb-204"><font size="-1">Asignar permisos predefinidos</span><span class="sxs-lookup"><span data-stu-id="31cbb-204"><font size="-1">Assign pre-defined permissions</span></span>
<td><span data-ttu-id="31cbb-205"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-205">Yes</span></span><br><span data-ttu-id="31cbb-206"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="31cbb-206"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="31cbb-207"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-207">Yes</span></span><br><span data-ttu-id="31cbb-208"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="31cbb-208"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="31cbb-209"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-209">Yes</span></span><br><span data-ttu-id="31cbb-210"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-210"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="31cbb-211"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-211"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="31cbb-212"><font size="-1"><b>Sí</b></span><span class="sxs-lookup"><span data-stu-id="31cbb-212">Yes</span></span><br><span data-ttu-id="31cbb-213"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-213"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="31cbb-214"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-214"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="31cbb-215"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-215"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="31cbb-216"><font size="-1">Próximamente...<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="31cbb-216"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="31cbb-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">Permitir a los usuarios asignar permisos</a>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-217">Let users assign permissions</span></span><td><span data-ttu-id="31cbb-218"><font size="-1"><b>Sí</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="31cbb-218"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="31cbb-219"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="31cbb-219"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="31cbb-220"><font size="-1"><b>Sí</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="31cbb-220"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="31cbb-221"><font size="-1">16.21.0+</font></span><span class="sxs-lookup"><span data-stu-id="31cbb-221"><font size="-1">16.21.0+</font></span></span>

<td><span data-ttu-id="31cbb-222"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-222"><font size="-1">TBD</span></span>
<td><span data-ttu-id="31cbb-223"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-223"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="31cbb-224"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-224"><font size="-1">TBD</span></span><td
><span data-ttu-id="31cbb-225"><font size="-1">Próximamente...<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-225"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="31cbb-226"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-226"><font size="-1">TBD</span></span>
<td><span data-ttu-id="31cbb-227"><font size="-1">Próximamente...<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="31cbb-227"><font size="-1">Coming soon<sup>3</sup></span></span>

<tr><td><span data-ttu-id="31cbb-228"><font size="-1">Enviar<a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">datos de análisis de etiquetas</a>para administradores</span><span class="sxs-lookup"><span data-stu-id="31cbb-228"><font size="-1">Send <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">label analytics</a> data for administrators</span></span>
<td><span data-ttu-id="31cbb-229"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-229"><font size="-1">TBD</span></span>

<td><span data-ttu-id="31cbb-230"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-230"><font size="-1">TBD</span></span>

<td><span data-ttu-id="31cbb-231"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-231"><font size="-1">TBD</span></span>
<td><span data-ttu-id="31cbb-232"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-232"><font size="-1">TBD</span></span>
<td><span data-ttu-id="31cbb-233"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-233"><font size="-1">TBD</span></span>
<td><span data-ttu-id="31cbb-234"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-234"><font size="-1">TBD</span></span>
<td><span data-ttu-id="31cbb-235"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-235"><font size="-1">TBD</span></span>
<td><span data-ttu-id="31cbb-236"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-236"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="31cbb-237"><font size="-1">Requerir que los usuarios apliquen una etiqueta al correo electrónico y a los documentos</span><span class="sxs-lookup"><span data-stu-id="31cbb-237"><font size="-1">Require users to apply a label to their email and documents</span></span>
<td><span data-ttu-id="31cbb-238"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-238"><font size="-1">TBD</span></span>

<td><span data-ttu-id="31cbb-239"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-239"><font size="-1">TBD</span></span>

<td><span data-ttu-id="31cbb-240"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-240"><font size="-1">TBD</span></span>
<td><span data-ttu-id="31cbb-241"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-241"><font size="-1">TBD</span></span>
<td><span data-ttu-id="31cbb-242"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-242"><font size="-1">TBD</span></span>
<td><span data-ttu-id="31cbb-243"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-243"><font size="-1">TBD</span></span>
<td><span data-ttu-id="31cbb-244"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-244"><font size="-1">TBD</span></span>
<td><span data-ttu-id="31cbb-245"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-245"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="31cbb-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">Aplicar automáticamente una etiqueta de confidencialidad al contenido</a>
</span><span class="sxs-lookup"><span data-stu-id="31cbb-246">Apply a sensitivity label to content automatically</span></span><td><span data-ttu-id="31cbb-247"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-247"><font size="-1">TBD</span></span>

<td><span data-ttu-id="31cbb-248"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-248"><font size="-1">TBD</span></span>

<td><span data-ttu-id="31cbb-249"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-249"><font size="-1">TBD</span></span>
<td><span data-ttu-id="31cbb-250"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-250"><font size="-1">TBD</span></span>
<td><span data-ttu-id="31cbb-251"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-251"><font size="-1">TBD</span></span>
<td><span data-ttu-id="31cbb-252"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-252"><font size="-1">TBD</span></span>
<td><span data-ttu-id="31cbb-253"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-253"><font size="-1">TBD</span></span>
<td><span data-ttu-id="31cbb-254"><font size="-1">Por determinar</span><span class="sxs-lookup"><span data-stu-id="31cbb-254"><font size="-1">TBD</span></span>
</table>

<br><span data-ttu-id="31cbb-255"><sup>1</sup>Si está configurada, se pide a los usuarios que justifiquen la degradación de las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="31cbb-255"><sup>1</sup>If configured, users are prompted to justify label downgrades.</span></span> <span data-ttu-id="31cbb-256">Sin embargo, los datos de justificación aún no están disponibles para los administradores.</span><span class="sxs-lookup"><span data-stu-id="31cbb-256">However, the justification data is not made available for administrators yet.</span></span> <span data-ttu-id="31cbb-257">Estarán disponibles cuando se admita la función de "enviar datos de análisis de etiqueta para administradores".</span><span class="sxs-lookup"><span data-stu-id="31cbb-257">It will become available when the “send label analytics data for administrators” capability is supported.</span></span>
<br><span data-ttu-id="31cbb-258"><sup>2</sup> Permitir a los usuarios asignar permisos está actualmente disponible solo en Outlook para Windows y Mac.</span><span class="sxs-lookup"><span data-stu-id="31cbb-258"><sup>2</sup>Let users assign permissions is currently only available in Outlook for Windows and Mac.</span></span> <span data-ttu-id="31cbb-259">La disponibilidad para Word, Excel y PowerPoint está por determinar.</span><span class="sxs-lookup"><span data-stu-id="31cbb-259">Availability for Word, Excel, and PowerPoint is TBD.</span></span>
<br><span data-ttu-id="31cbb-260"><sup>3</sup>Previsto para el cuarto trimestre del año calendario 2019.</span><span class="sxs-lookup"><span data-stu-id="31cbb-260"><sup>3</sup>Expected Q4 of calendar year 2019.</span></span>

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a><span data-ttu-id="31cbb-261">¿Cuándo se aplican las marcas de contenido o el cifrado después de que el contenido recibe una etiqueta de confidencialidad?</span><span class="sxs-lookup"><span data-stu-id="31cbb-261">When do content marks or encryption get applied after content is given a sensitivity label?</span></span>

| <span data-ttu-id="31cbb-262">Aplicación</span><span class="sxs-lookup"><span data-stu-id="31cbb-262">Application</span></span> | <span data-ttu-id="31cbb-263">Marcado de contenido</span><span class="sxs-lookup"><span data-stu-id="31cbb-263">Content marking</span></span> | <span data-ttu-id="31cbb-264">Cifrado</span><span class="sxs-lookup"><span data-stu-id="31cbb-264">Encryption</span></span>
| --- | --- | --- |
| <span data-ttu-id="31cbb-265">Word, Excel y PowerPoint en todas las plataformas</span><span class="sxs-lookup"><span data-stu-id="31cbb-265">Word, Excel, PowerPoint on all platforms</span></span> | <span data-ttu-id="31cbb-266">De forma inmediata</span><span class="sxs-lookup"><span data-stu-id="31cbb-266">Immediately</span></span> | <span data-ttu-id="31cbb-267">De forma inmediata</span><span class="sxs-lookup"><span data-stu-id="31cbb-267">Immediately</span></span> |
| <span data-ttu-id="31cbb-268">Outlook para PC y Mac</span><span class="sxs-lookup"><span data-stu-id="31cbb-268">Outlook for PC and Mac</span></span> | <span data-ttu-id="31cbb-269">Cuando Exchange Online envíe el correo electrónico</span><span class="sxs-lookup"><span data-stu-id="31cbb-269">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="31cbb-270">De forma inmediata</span><span class="sxs-lookup"><span data-stu-id="31cbb-270">Immediately</span></span> |
| <span data-ttu-id="31cbb-271">Word, Excel y PowerPoint en todas las plataformas</span><span class="sxs-lookup"><span data-stu-id="31cbb-271">Word, Excel, PowerPoint on all platforms</span></span> | <span data-ttu-id="31cbb-272">Cuando Exchange Online envíe el correo electrónico</span><span class="sxs-lookup"><span data-stu-id="31cbb-272">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="31cbb-273">Cuando Exchange Online envíe el correo electrónico</span><span class="sxs-lookup"><span data-stu-id="31cbb-273">After the email is sent by Exchange Online</span></span> |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a><span data-ttu-id="31cbb-274">¿Las etiquetas de confidencialidad pueden ejecutarse junto al cliente de Azure Information Protection en Office para Windows?</span><span class="sxs-lookup"><span data-stu-id="31cbb-274">Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?</span></span>

<span data-ttu-id="31cbb-275">No.</span><span class="sxs-lookup"><span data-stu-id="31cbb-275">No.</span></span> <span data-ttu-id="31cbb-276">Las etiquetas de confidencialidad se desactivan si el cliente de Azure Information Protection está cargado en Office para Windows.</span><span class="sxs-lookup"><span data-stu-id="31cbb-276">Sensitivity labels are turned off if the Azure Information Protection client is loaded in Office for Windows.</span></span>

<span data-ttu-id="31cbb-277">Si tiene el cliente de Azure Information Protection instalado, pero quiere usar las etiquetas de confidencialidad en su lugar, puede:</span><span class="sxs-lookup"><span data-stu-id="31cbb-277">If you have the Azure Information Protection client installed, but you want to use sensitivity labels instead, you can:</span></span>

1. <span data-ttu-id="31cbb-278">Configure la opción  **Use la función de Confidencialidad en Office para aplicar y ver las etiquetas de confidencialidad en la**Configuración de Directiva de grupo, que se encuentra en **Configuración de Usuario /Plantillas administrativas/ Microsoft Office 2016/Configuración de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="31cbb-278">Configure the **Use the Sensitivity feature in Office to apply and view sensitivity labels** Group Policy setting, which can be found under **User Configuration/Administrative Templates/Microsoft Office 2016/Security Settings**.</span></span>

  ><span data-ttu-id="31cbb-279">Nota: esta configuración puede implementarse mediante los mecanismos tradicionales de la Directiva de grupo, o bien mediante el [Servicio de directivas en la nube de Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).</span><span class="sxs-lookup"><span data-stu-id="31cbb-279">Note: this setting can be deployed via traditional group policy deployment mechanisms, or by the [Office cloud policy service](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).</span></span> 
 
  <span data-ttu-id="31cbb-280">Como alternativa, puede desinstalar o  [deshabilitar](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) el cliente de Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="31cbb-280">Alternatively, you can uninstall or [disable](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) the Azure Information Protection client.</span></span> 

2. <span data-ttu-id="31cbb-281">Reiniciar todas las aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="31cbb-281">Restart all Office applications.</span></span>

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a><span data-ttu-id="31cbb-282">¿Serán compatibles las etiquetas de confidencialidad en las versiones de Office que no sean de suscripción, como Office 2016 u Office 2019?</span><span class="sxs-lookup"><span data-stu-id="31cbb-282">Will sensitivity labels be supported in non-subscription versions of Office like Office 2016 or Office 2019?</span></span>

<span data-ttu-id="31cbb-283">No.</span><span class="sxs-lookup"><span data-stu-id="31cbb-283">No.</span></span> <span data-ttu-id="31cbb-284">Las etiquetas de confidencialidad solo serán compatibles con la suscripción de Office 365 y no se admitirán en ninguna versión que no sea de suscripción.</span><span class="sxs-lookup"><span data-stu-id="31cbb-284">Sensitivity labels will only be supported in the Office 365 subscription and will not be supported in any non-subscription version.</span></span> <span data-ttu-id="31cbb-285">Sin embargo, el cliente de etiquetado unificado de Azure Information Protection se puede usar en las versiones de Office que no sean de suscripción.</span><span class="sxs-lookup"><span data-stu-id="31cbb-285">However, the Azure Information Protection unified labeling client may be used in non-subscription versions of Office.</span></span> 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a><span data-ttu-id="31cbb-286">He implementado previamente plantillas de protección antes de configurar las etiquetas de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="31cbb-286">I previously deployed protection templates before setting up sensitivity labels.</span></span> <span data-ttu-id="31cbb-287">¿Dónde se encuentran?</span><span class="sxs-lookup"><span data-stu-id="31cbb-287">Where did they go?</span></span>

<span data-ttu-id="31cbb-288">Las [plantillas de protección](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) definidas por el administrados se ocultan de la experiencia de usuario de Office cuando las etiquetas de confidencialidad están habilitadas, ya que son redundantes con las etiquetas de confidencialidad que tienen el cifrado habilitado.</span><span class="sxs-lookup"><span data-stu-id="31cbb-288">Administrator-defined [protection templates](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) are hidden from the Office user experience when sensitivity labels are enabled because they are redundant with sensitivity labels that have encryption enabled.</span></span> 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a><span data-ttu-id="31cbb-289">¿Puede un archivo o correo electrónico tener más de una clasificación?</span><span class="sxs-lookup"><span data-stu-id="31cbb-289">Can a file or email have more than one classification?</span></span>

<span data-ttu-id="31cbb-290">Los usuarios pueden seleccionar una etiqueta de cada vez para cada documento o correo electrónico, lo que a menudo resulta en una sola clasificación.</span><span class="sxs-lookup"><span data-stu-id="31cbb-290">Users can select just one label at a time for each document or email, which often results in just one classification.</span></span> <span data-ttu-id="31cbb-291">Sin embargo, si los usuarios seleccionan una sub-etiqueta, en realidad se aplican dos etiquetas al mismo tiempo; una etiqueta principal y una etiqueta secundaria.</span><span class="sxs-lookup"><span data-stu-id="31cbb-291">However, if users select a sublabel, this actually applies two labels at the same time; a primary label and a secondary label.</span></span> <span data-ttu-id="31cbb-292">Al usar sub-etiquetas, un archivo puede tener dos clasificaciones que denotan una relación principal/secundaria para un nivel adicional de control.</span><span class="sxs-lookup"><span data-stu-id="31cbb-292">By using sublabels, a file can have two classifications that denote a parent/child relationship for an additional level of control.</span></span> 

<span data-ttu-id="31cbb-293">Por ejemplo, la etiqueta  **Confidencial**  podría contener sub-etiquetas como  **Legal ** y  **Finanzas**.</span><span class="sxs-lookup"><span data-stu-id="31cbb-293">For example, the label **Confidential** might contain sublabels such as **Legal** and **Finance**.</span></span> <span data-ttu-id="31cbb-294">Puede aplicar distintas marcas visuales de clasificación y distintas plantillas de Administración de Derechos a estas sub-etiquetas.</span><span class="sxs-lookup"><span data-stu-id="31cbb-294">You can apply different classification visual markings and different Rights Management templates to these sublabels.</span></span> <span data-ttu-id="31cbb-295">Un usuario no puede seleccionar la etiqueta  **Confidencial** por sí mismo; sino solo una de sus sub-etiquetas, como  **Legal**.</span><span class="sxs-lookup"><span data-stu-id="31cbb-295">A user cannot select the **Confidential** label by itself; only one of its sublabels, such as **Legal**.</span></span> <span data-ttu-id="31cbb-296">Por lo tanto, la etiqueta que se muestra en la definición es  **Confidencial** / **Legal**.</span><span class="sxs-lookup"><span data-stu-id="31cbb-296">As a result, the label that they see set is **Confidential** / **Legal**.</span></span> <span data-ttu-id="31cbb-297">Los metadatos de ese archivo contienen una propiedad de texto personalizada para  **Confidencial**, una propiedad de texto personalizada para  **Legal**, y otra que contiene ambos valores (**Confidencial Legal**).</span><span class="sxs-lookup"><span data-stu-id="31cbb-297">The metadata for that file includes one custom text property for **Confidential**, one custom text property for **Legal**, and another that contains both values (**Confidential Legal**).</span></span> 

<span data-ttu-id="31cbb-298">Cuando use sub-etiquetas, no configure las marcas visuales, la protección y las condiciones en la etiqueta principal.</span><span class="sxs-lookup"><span data-stu-id="31cbb-298">When you use sublabels, don't configure visual markings, protection, and conditions at the primary label.</span></span> <span data-ttu-id="31cbb-299">Cuando use subniveles, configure estos ajustes solo en la sub-etiqueta.</span><span class="sxs-lookup"><span data-stu-id="31cbb-299">When you use sublevels, configure these setting on the sublabel only.</span></span> <span data-ttu-id="31cbb-300">Si establece estas opciones de configuración en la etiqueta principal y en su sub-etiqueta, la configuración de la sub-etiqueta tendrá prioridad.</span><span class="sxs-lookup"><span data-stu-id="31cbb-300">If you configure these settings on the primary label and its sublabel, the settings at the sublabel take precedence.</span></span>

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a><span data-ttu-id="31cbb-301">Cuando se etiqueta un correo electrónico, ¿los datos adjuntos reciben automáticamente la misma etiqueta?</span><span class="sxs-lookup"><span data-stu-id="31cbb-301">When an email is labeled, do any attachments automatically get the same labeling?</span></span>

<span data-ttu-id="31cbb-302">No.</span><span class="sxs-lookup"><span data-stu-id="31cbb-302">No.</span></span> <span data-ttu-id="31cbb-303">Al etiquetar un mensaje de correo electrónico con datos adjuntos, estos no heredan la misma etiqueta.</span><span class="sxs-lookup"><span data-stu-id="31cbb-303">When you label an email message that has attachments, those attachments do not inherit the same label.</span></span> <span data-ttu-id="31cbb-304">Los datos adjuntos permanecen sin etiqueta o mantienen una etiqueta aplicada por separado.</span><span class="sxs-lookup"><span data-stu-id="31cbb-304">The attachments remain either without a label or retain a separately applied label.</span></span> <span data-ttu-id="31cbb-305">Sin embargo, si la etiqueta del correo electrónico aplica protección, esa protección se aplicará a los datos adjuntos de Office.</span><span class="sxs-lookup"><span data-stu-id="31cbb-305">However, if the label for the email applies protection, that protection is applied to Office attachments.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="31cbb-306">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="31cbb-306">Additional resources</span></span>

[<span data-ttu-id="31cbb-307">Preguntas más frecuentes sobre la clasificación y etiquetado en Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="31cbb-307">Frequently asked questions about classification and labeling in Azure Information Protection</span></span>](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[<span data-ttu-id="31cbb-308">Aplicar etiquetas de confidencialidad en sus documentos y correo electrónico en Office</span><span class="sxs-lookup"><span data-stu-id="31cbb-308">Apply sensitivity labels to your documents and email within Office</span></span>](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)