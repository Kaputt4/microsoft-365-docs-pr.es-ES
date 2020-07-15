---
title: Aplicación de etiquetas a datos personales
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Aprenda a utilizar las etiquetas de Office como parte de su plan de protección de la Normativa general de protección de datos (GDPR).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a7bea2abeaec7a858b3cfc693603c46c0f2a416a
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126821"
---
# <a name="apply-labels-to-personal-data"></a><span data-ttu-id="d6c5e-103">Aplicación de etiquetas a datos personales</span><span class="sxs-lookup"><span data-stu-id="d6c5e-103">Apply labels to personal data</span></span>

 <span data-ttu-id="d6c5e-104">Use este tema si utiliza las etiquetas de clasificación como parte de su plan de protección de RGPD.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-104">Use this topic if you're using classification labels as part of your GDPR protection plan.</span></span> 

<span data-ttu-id="d6c5e-105">Si utiliza etiquetas para la protección de datos personales de Microsoft 365, Microsoft recomienda que empiece con las [etiquetas de retención](retention.md#retention-labels).</span><span class="sxs-lookup"><span data-stu-id="d6c5e-105">If you're using labels for protection of personal data in Microsoft 365, Microsoft recommends you start with [retention labels](retention.md#retention-labels).</span></span> <span data-ttu-id="d6c5e-106">Con las etiquetas de retención, puede:</span><span class="sxs-lookup"><span data-stu-id="d6c5e-106">With retention labels, you can:</span></span>
- <span data-ttu-id="d6c5e-107">Usar el Gobierno de datos avanzado para aplicar automáticamente etiquetas con tipos de información confidencial u otros criterios.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-107">Use Advanced Data Governance to automatically apply labels based on sensitive information types or other criteria.</span></span>
- <span data-ttu-id="d6c5e-108">Usar etiquetas de retención con la prevención de pérdida de datos para aplicar la protección.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-108">Use retention labels with data loss prevention to apply protection.</span></span> 
- <span data-ttu-id="d6c5e-109">Usar etiquetas con eDiscovery y Búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-109">Use labels with eDiscovery and Content Search.</span></span> 

<span data-ttu-id="d6c5e-110">Cloud App Security actualmente no admite etiquetas de retención, pero puede usar tipos de información confidencial de Microsoft 365 con Cloud App Security para supervisar los datos personales que residen en otras aplicaciones SaaS.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-110">Cloud App Security doesn't currently support retention labels, but you can use Microsoft 365 sensitive information types with Cloud App Security to monitor personal data that resides in other SaaS apps.</span></span>

<span data-ttu-id="d6c5e-111">Actualmente se recomiendan las [etiquetas de confidencialidad](sensitivity-labels.md) para la aplicación de etiquetas a archivos locales y en otros proveedores y servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-111">[Sensitivity labels](sensitivity-labels.md) are currently recommended for applying labels to files on premises and in other cloud services and providers.</span></span> <span data-ttu-id="d6c5e-112">Estas también se recomiendan para los archivos de Microsoft 365 que requieren el cifrado de Azure Information Protection (AIP) para la protección de datos, como archivos de secreto comercial.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-112">These are also recommended for files in Microsoft 365 that require Azure Information Protection encryption for data protection, such as trade secret files.</span></span>

<span data-ttu-id="d6c5e-113">En este momento, no se recomienda usar Azure Information Protection para aplicar el cifrado a archivos en Microsoft 365 con datos que están sujetos al RGPD.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-113">At this time, using Azure Information Protection to apply encryption is not recommended for files in Microsoft 365 with data that is subject to the GDPR.</span></span> <span data-ttu-id="d6c5e-114">Los servicios de Microsoft 365 actualmente no pueden leer archivos cifrados AIP.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-114">Microsoft 365 services currently cannot read into AIP-encrypted files.</span></span> <span data-ttu-id="d6c5e-115">Por ello, el servicio no puede encontrar datos confidenciales en dichos archivos.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-115">Therefore, the service can't find sensitive data in these files.</span></span>

<span data-ttu-id="d6c5e-116">Pueden aplicarse etiquetas de confidencialidad a correo en Exchange Online que funcionan con la prevención de pérdida de datos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-116">Retention labels can be applied to mail in Exchange Online and these labels work with Microsoft 365 data loss prevention.</span></span> 

![Etiquetas de Microsoft 365 y de Azure Information Protection](../media/Apply-labels-to-personal-data-in-Office-365-image1.png)


<span data-ttu-id="d6c5e-118">En la ilustración:</span><span class="sxs-lookup"><span data-stu-id="d6c5e-118">In the illustration:</span></span>

-   <span data-ttu-id="d6c5e-119">Use las etiquetas de retención para los datos personales y archivos secretos empresariales muy regulados en SharePoint Online y OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-119">Use retention labels for personal data and for highly regulated and trade secret files in SharePoint Online and OneDrive for Business.</span></span>
-   <span data-ttu-id="d6c5e-120">Los tipos de información confidencial de Microsoft 365 pueden usarse en Microsoft 365 y con Cloud App Security para supervisar datos personales que residen en otras aplicaciones SaaS.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-120">Microsoft 365 sensitive information types can be used within Microsoft 365 and with Cloud App Security to monitor personal data that resides in other SaaS apps.</span></span>
-   <span data-ttu-id="d6c5e-121">Use las etiquetas de confidencialidad para archivos secretos empresariales muy regulados, correo electrónico de Exchange Online, archivos en otros servicios SaaS, archivos en centros de datos locales y archivos de otros proveedores en la nube.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-121">Use sensitivity labels for highly regulated and trade secret files, Exchange Online email, files in other SaaS services, files in on-premises datacenters, and files in other cloud providers.</span></span>


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a><span data-ttu-id="d6c5e-122">Uso de etiquetas de retención y tipos de información confidencial en Microsoft 365 para la protección de información</span><span class="sxs-lookup"><span data-stu-id="d6c5e-122">Use retention labels and sensitive information types across Microsoft 365 for information protection</span></span>

<span data-ttu-id="d6c5e-123">En la ilustración siguiente se muestra cómo pueden aprovecharse las etiquetas de retención y los tipos de información confidencial en las directivas de etiquetas, de prevención de pérdida de datos y de Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-123">The following illustration shows how retention labels and sensitive information types can be used in label policies, data loss prevention policies, and with Cloud App Security policies.</span></span>

![Etiquetas y tipos de información confidencial de Office](../media/Apply-labels-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="d6c5e-125">Por motivos de accesibilidad, en la tabla siguiente se incluyen los mismos ejemplos que en la ilustración.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-125">For accessibility, the following table provides the same examples in the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d6c5e-126"><strong>Elementos de clasificación</strong></span><span class="sxs-lookup"><span data-stu-id="d6c5e-126"><strong>Classification elements</strong></span></span></th>
<th align="left"><span data-ttu-id="d6c5e-127"><strong>Directivas de etiqueta: 2 ejemplos</strong></span><span class="sxs-lookup"><span data-stu-id="d6c5e-127"><strong>Label policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="d6c5e-128"><strong>Directivas de prevención de pérdida de datos: 2 ejemplos</strong></span><span class="sxs-lookup"><span data-stu-id="d6c5e-128"><strong>Data loss prevention policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="d6c5e-129"><strong>Directivas de Cloud App Security para todas las aplicaciones SaaS: 1 ejemplo</strong></span><span class="sxs-lookup"><span data-stu-id="d6c5e-129"><strong>Cloud App Security policies for all SaaS apps — 1 example</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="d6c5e-130">Etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-130">Retention labels.</span></span> <span data-ttu-id="d6c5e-131">Ejemplos: personal, público, datos de clientes, datos de recursos humanos, confidencial, extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="d6c5e-131">Examples: Personal, Public, Customer data, HR data, Confidential, Highly confidential</span></span></td>
<td align="left"><p><span data-ttu-id="d6c5e-132">Auto apply this label .</span><span class="sxs-lookup"><span data-stu-id="d6c5e-132">Auto apply this label .</span></span> <span data-ttu-id="d6c5e-133">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-133">.</span></span> <span data-ttu-id="d6c5e-134">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-134">.</span></span></p>
<p><span data-ttu-id="d6c5e-135">Datos de cliente</span><span class="sxs-lookup"><span data-stu-id="d6c5e-135">Customer data</span></span></p>
<p><span data-ttu-id="d6c5e-136">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-136">.</span></span> <span data-ttu-id="d6c5e-137">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-137">.</span></span> <span data-ttu-id="d6c5e-138">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-138">.</span></span> <span data-ttu-id="d6c5e-139">to documents that match these sensitive information types .</span><span class="sxs-lookup"><span data-stu-id="d6c5e-139">to documents that match these sensitive information types .</span></span> <span data-ttu-id="d6c5e-140">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-140">.</span></span> <span data-ttu-id="d6c5e-141">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-141">.</span></span></p>
<p><span data-ttu-id="d6c5e-142">&lt;lista de ejemplos de información confidencial disponibles&gt;</span><span class="sxs-lookup"><span data-stu-id="d6c5e-142">&lt;list of example sensitive information types&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="d6c5e-143">Apply this protection .</span><span class="sxs-lookup"><span data-stu-id="d6c5e-143">Apply this protection .</span></span> <span data-ttu-id="d6c5e-144">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-144">.</span></span> <span data-ttu-id="d6c5e-145">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-145">.</span></span></p>
<p><span data-ttu-id="d6c5e-146">&lt;definir la protección&gt;</span><span class="sxs-lookup"><span data-stu-id="d6c5e-146">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="d6c5e-147">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-147">.</span></span> <span data-ttu-id="d6c5e-148">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-148">.</span></span> <span data-ttu-id="d6c5e-149">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-149">.</span></span> <span data-ttu-id="d6c5e-150">to documents with this label .</span><span class="sxs-lookup"><span data-stu-id="d6c5e-150">to documents with this label .</span></span> <span data-ttu-id="d6c5e-151">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-151">.</span></span> <span data-ttu-id="d6c5e-152">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-152">.</span></span></p>
<p><span data-ttu-id="d6c5e-153">Datos de cliente</span><span class="sxs-lookup"><span data-stu-id="d6c5e-153">Customer data</span></span></p></td>
<td align="left"><p><span data-ttu-id="d6c5e-154">Alert when files with these attributes .</span><span class="sxs-lookup"><span data-stu-id="d6c5e-154">Alert when files with these attributes .</span></span> <span data-ttu-id="d6c5e-155">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-155">.</span></span> <span data-ttu-id="d6c5e-156">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-156">.</span></span></p>
<p><span data-ttu-id="d6c5e-157">Elija uno o varios atributos: atributo PII predefinido, tipo de información confidencial de Microsoft 365, etiqueta de confidencialidad (AIP), expresión personalizada.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-157">Choose one or more attributes: predefined PII attribute, Microsoft 365 sensitive information type, sensitivity label (AIP), custom expression</span></span></p>
<p><span data-ttu-id="d6c5e-158">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-158">.</span></span> <span data-ttu-id="d6c5e-159">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-159">.</span></span> <span data-ttu-id="d6c5e-160">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-160">.</span></span> <span data-ttu-id="d6c5e-161">en cualquier aplicación de SaaS autorizada se comparten fuera de la organización</span><span class="sxs-lookup"><span data-stu-id="d6c5e-161">in any sanctioned SaaS app are shared outside the organization</span></span></p><p><span data-ttu-id="d6c5e-162">Nota: las etiquetas de retención actualmente no se admiten en Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-162">Note: Retention labels are currently not supported in Cloud App Security.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d6c5e-163">Sensitive information types.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-163">Sensitive information types.</span></span> <span data-ttu-id="d6c5e-164">Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</span><span class="sxs-lookup"><span data-stu-id="d6c5e-164">Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</span></span></td>
<td align="left"><p><span data-ttu-id="d6c5e-165">Publish these labels for users to manually apply .</span><span class="sxs-lookup"><span data-stu-id="d6c5e-165">Publish these labels for users to manually apply .</span></span> <span data-ttu-id="d6c5e-166">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-166">.</span></span> <span data-ttu-id="d6c5e-167">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-167">.</span></span></p>
<p><span data-ttu-id="d6c5e-168">&lt;seleccionar etiquetas&gt;</span><span class="sxs-lookup"><span data-stu-id="d6c5e-168">&lt;select labels&gt;</span></span></p>
<p><span data-ttu-id="d6c5e-169">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-169">.</span></span> <span data-ttu-id="d6c5e-170">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-170">.</span></span> <span data-ttu-id="d6c5e-171">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-171">.</span></span> <span data-ttu-id="d6c5e-172">to these locations .</span><span class="sxs-lookup"><span data-stu-id="d6c5e-172">to these locations .</span></span> <span data-ttu-id="d6c5e-173">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-173">.</span></span> <span data-ttu-id="d6c5e-174">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-174">.</span></span></p>
<p><span data-ttu-id="d6c5e-175">&lt;todas las ubicaciones o elegir ubicaciones específicas&gt;</span><span class="sxs-lookup"><span data-stu-id="d6c5e-175">&lt;all locations or choose specific locations&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="d6c5e-176">Apply this protection .</span><span class="sxs-lookup"><span data-stu-id="d6c5e-176">Apply this protection .</span></span> <span data-ttu-id="d6c5e-177">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-177">.</span></span> <span data-ttu-id="d6c5e-178">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-178">.</span></span></p>
<p><span data-ttu-id="d6c5e-179">&lt;definir la protección&gt;</span><span class="sxs-lookup"><span data-stu-id="d6c5e-179">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="d6c5e-180">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-180">.</span></span> <span data-ttu-id="d6c5e-181">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-181">.</span></span> <span data-ttu-id="d6c5e-182">.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-182">.</span></span> <span data-ttu-id="d6c5e-183">to documents that match these sensitive information types&gt;</span><span class="sxs-lookup"><span data-stu-id="d6c5e-183">to documents that match these sensitive information types&gt;</span></span></p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a><span data-ttu-id="d6c5e-184">Asignar prioridades a las directivas de etiqueta de aplicación automática</span><span class="sxs-lookup"><span data-stu-id="d6c5e-184">Prioritize auto-apply label policies</span></span>

<span data-ttu-id="d6c5e-185">For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-185">For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment.</span></span> <span data-ttu-id="d6c5e-186">It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-186">It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.</span></span>

<span data-ttu-id="d6c5e-187">The order that auto-apply policies are created and whether users are also applying these labels affect the result.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-187">The order that auto-apply policies are created and whether users are also applying these labels affect the result.</span></span> <span data-ttu-id="d6c5e-188">So, it's important to carefully plan the roll-out. Here's what you need to know.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-188">So, it's important to carefully plan the roll-out. Here's what you need to know.</span></span>

### <a name="one-label-at-a-time"></a><span data-ttu-id="d6c5e-189">Una etiqueta de cada vez</span><span class="sxs-lookup"><span data-stu-id="d6c5e-189">One label at a time</span></span>

<span data-ttu-id="d6c5e-190">Solo puede aplicar una etiqueta a un documento.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-190">You can only assign one label to a document.</span></span>

### <a name="older-auto-apply-policies-win"></a><span data-ttu-id="d6c5e-191">Las directivas de aplicación automática antiguas tienen prioridad</span><span class="sxs-lookup"><span data-stu-id="d6c5e-191">Older auto-apply policies win</span></span>

<span data-ttu-id="d6c5e-192">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-192">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned.</span></span> <span data-ttu-id="d6c5e-193">For this reason, it's important to plan the label policies carefully before configuring them.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-193">For this reason, it's important to plan the label policies carefully before configuring them.</span></span> <span data-ttu-id="d6c5e-194">If an organization requires a change to the priority of the label policies, they'll need to delete and recreate them.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-194">If an organization requires a change to the priority of the label policies, they'll need to delete and recreate them.</span></span>

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a><span data-ttu-id="d6c5e-195">Las etiquetas de usuario aplicadas manualmente tienen prioridad sobre las etiquetas aplicadas automáticamente</span><span class="sxs-lookup"><span data-stu-id="d6c5e-195">Manual user-applied labels trump auto-applied labels</span></span>

<span data-ttu-id="d6c5e-196">Manual user applied labels trump auto-applied labels.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-196">Manual user applied labels trump auto-applied labels.</span></span> <span data-ttu-id="d6c5e-197">Auto-apply policies can't replace a label that is already applied by a user.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-197">Auto-apply policies can't replace a label that is already applied by a user.</span></span> <span data-ttu-id="d6c5e-198">Users can replace labels that are auto-applied.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-198">Users can replace labels that are auto-applied.</span></span>

### <a name="auto-assigned-labels-can-be-updated"></a><span data-ttu-id="d6c5e-199">Las etiquetas asignadas automáticamente pueden actualizarse</span><span class="sxs-lookup"><span data-stu-id="d6c5e-199">Auto-assigned labels can be updated</span></span>

<span data-ttu-id="d6c5e-200">Las directivas de etiqueta más recientes o las actualizaciones de directivas existentes pueden actualizar etiquetas asignadas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-200">Auto-assigned labels can be updated by either newer label policies or by updates to existing policies.</span></span>

<span data-ttu-id="d6c5e-201">Asegúrese de que su plan para implementar etiquetas incluye:</span><span class="sxs-lookup"><span data-stu-id="d6c5e-201">Be sure your plan for implementing labels includes:</span></span>

- <span data-ttu-id="d6c5e-202">Dar prioridad al orden en que se crean las directivas de aplicación automática.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-202">Prioritizing the order that auto-apply policies are created.</span></span>

- <span data-ttu-id="d6c5e-203">Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-203">Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply.</span></span> <span data-ttu-id="d6c5e-204">It can take up to seven days for the labels to be applied to all content that matches the conditions.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-204">It can take up to seven days for the labels to be applied to all content that matches the conditions.</span></span>

### <a name="example-priority-for-creating-the-auto-apply-policies"></a><span data-ttu-id="d6c5e-205">Prioridad de ejemplo para crear directivas de aplicación automática</span><span class="sxs-lookup"><span data-stu-id="d6c5e-205">Example priority for creating the auto-apply policies</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d6c5e-206"><strong>Etiquetas</strong></span><span class="sxs-lookup"><span data-stu-id="d6c5e-206"><strong>Labels</strong></span></span></th>
<th align="left"><span data-ttu-id="d6c5e-207"><strong>Orden de prioridad para crear directivas de aplicación automática</strong></span><span class="sxs-lookup"><span data-stu-id="d6c5e-207"><strong>Priority order to create auto-apply policies</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="d6c5e-208">Recursos humanos: datos de empleado</span><span class="sxs-lookup"><span data-stu-id="d6c5e-208">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="d6c5e-209">1</span><span class="sxs-lookup"><span data-stu-id="d6c5e-209">1</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d6c5e-210">Datos de cliente</span><span class="sxs-lookup"><span data-stu-id="d6c5e-210">Customer Data</span></span></td>
<td align="left"><span data-ttu-id="d6c5e-211">2</span><span class="sxs-lookup"><span data-stu-id="d6c5e-211">2</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="d6c5e-212">Extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="d6c5e-212">Highly Confidential</span></span></td>
<td align="left"><span data-ttu-id="d6c5e-213">3</span><span class="sxs-lookup"><span data-stu-id="d6c5e-213">3</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d6c5e-214">Recursos humanos: datos de sueldo</span><span class="sxs-lookup"><span data-stu-id="d6c5e-214">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="d6c5e-215">4</span><span class="sxs-lookup"><span data-stu-id="d6c5e-215">4</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="d6c5e-216">Confidencial</span><span class="sxs-lookup"><span data-stu-id="d6c5e-216">Confidential</span></span></td>
<td align="left"><span data-ttu-id="d6c5e-217">5</span><span class="sxs-lookup"><span data-stu-id="d6c5e-217">5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d6c5e-218">Público</span><span class="sxs-lookup"><span data-stu-id="d6c5e-218">Public</span></span></td>
<td align="left"><span data-ttu-id="d6c5e-219">6</span><span class="sxs-lookup"><span data-stu-id="d6c5e-219">6</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="d6c5e-220">Personal</span><span class="sxs-lookup"><span data-stu-id="d6c5e-220">Personal</span></span></td>
<td align="left"><span data-ttu-id="d6c5e-221">Directiva que no es de aplicación automática</span><span class="sxs-lookup"><span data-stu-id="d6c5e-221">No auto-apply policy</span></span></td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a><span data-ttu-id="d6c5e-222">Crear etiquetas y aplicar directivas de etiqueta automáticamente</span><span class="sxs-lookup"><span data-stu-id="d6c5e-222">Create labels and auto-apply label policies</span></span>

<span data-ttu-id="d6c5e-223">Cree etiquetas y directivas en el centro de seguridad o el centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-223">Create labels and policies in the security center or the compliance center.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d6c5e-224"><strong>Paso</strong></span><span class="sxs-lookup"><span data-stu-id="d6c5e-224"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="d6c5e-225"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="d6c5e-225"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d6c5e-226">Conceda permisos a los miembros de su equipo de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-226">Give permissions to members of your compliance team.</span></span></p></td>
<td align="left"><p><span data-ttu-id="d6c5e-227">Members of your compliance team who will create labels need permissions to use the security center and/or the compliance center.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-227">Members of your compliance team who will create labels need permissions to use the security center and/or the compliance center.</span></span> <span data-ttu-id="d6c5e-228">Go to Permissions in the security center or the compliance center and modify the members of the Compliance Administrator group.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-228">Go to Permissions in the security center or the compliance center and modify the members of the Compliance Administrator group.</span></span></p>
<p><span data-ttu-id="d6c5e-229">Vea <a href="https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center">Proporcionar acceso a los usuarios al centro de seguridad y/o el centro de cumplimiento</a>.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-229">See <a href="https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center">Give users access to the security center and/or the compliance center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d6c5e-230">Crear etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-230">Create retention labels.</span></span></p></td>
<td align="left"><span data-ttu-id="d6c5e-231">Vaya a Clasificaciones en el centro de seguridad o el centro de cumplimiento, elija Etiquetas de retención y cree las etiquetas para su entorno.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-231">Go to Classifications in the Security center or the Compliance center, choose Retention labels, and create the labels for your environment.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d6c5e-232">Cree directivas de aplicación automática para etiquetas.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-232">Create auto-apply policies for labels.</span></span></p></td>
<td align="left"><span data-ttu-id="d6c5e-233">Go to Classification in security center or the compliance center, choose Label policies, and create the policies for auto-applying labels.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-233">Go to Classification in security center or the compliance center, choose Label policies, and create the policies for auto-applying labels.</span></span> <span data-ttu-id="d6c5e-234">Be sure to create these policies in the prioritized order.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-234">Be sure to create these policies in the prioritized order.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6c5e-235">La siguiente ilustración muestra cómo crear una etiqueta de aplicación automática para la etiqueta Datos de cliente.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-235">The following illustration shows how to create an auto-apply label for the Customer data label.</span></span>

![Crear y aplicar una etiqueta de datos de cliente](../media/Apply-labels-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="d6c5e-237">En la ilustración:</span><span class="sxs-lookup"><span data-stu-id="d6c5e-237">In the illustration:</span></span>

- <span data-ttu-id="d6c5e-238">Se crea la etiqueta "Datos de cliente".</span><span class="sxs-lookup"><span data-stu-id="d6c5e-238">The "Customer data" label is created.</span></span>

- <span data-ttu-id="d6c5e-239">Se listan los tipos de información confidencial deseados para RGPD: número nacional de Bélgica, número de tarjeta de crédito, número de carnet de identidad de Croacia, documento de identidad nacional de Finlandia</span><span class="sxs-lookup"><span data-stu-id="d6c5e-239">The desired sensitive information types for GDPR are listed: Belgium National Number, Credit Card Number, Croatia Identity Card Number, Finland National ID.</span></span>

- <span data-ttu-id="d6c5e-240">Crear una directiva de aplicación automática asigna la etiqueta "Datos de cliente" a cualquier archivo que contenga uno de los tipos de información confidencial que añada a la directiva.</span><span class="sxs-lookup"><span data-stu-id="d6c5e-240">Create an auto-apply policy assigns the label "Customer data" to any file that includes one of the sensitive information types that you add to the policy.</span></span>
