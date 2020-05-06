---
title: Aplicar o quitar una directiva de eliminación de documentos de un sitio
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3e92668-f9b2-46ee-8e5e-c623870588b6
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo crear, eliminar y administrar una directiva de eliminación de documentos en una colección de sitios de Office 365.
ms.openlocfilehash: 7a9cbec25349de02da35f0aaf0cc206774a9b59a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034344"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="6572c-103">Aplicar o quitar una directiva de eliminación de documentos de un sitio</span><span class="sxs-lookup"><span data-stu-id="6572c-103">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="6572c-104">Las organizaciones suelen estar sujetas a normas de cumplimiento, leyes u otras regulaciones que las obligan a conservar sus documentos durante un período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="6572c-104">Organizations are often subject to compliance, legal, or other regulations that require them to retain documents for a certain period of time.</span></span> <span data-ttu-id="6572c-105">Sin embargo, conservar los documentos durante más tiempo de lo necesario puede exponer a la organización a riesgos de carácter legal.</span><span class="sxs-lookup"><span data-stu-id="6572c-105">However, retaining documents for longer than required can expose the organization to legal risk.</span></span> <span data-ttu-id="6572c-106">Por este motivo, es posible que su organización haya creado una directiva de eliminación de&mdash;documentos para el sitio, por ejemplo, puede que sea necesario que los documentos generales de negocio se eliminen cinco años después de su creación.</span><span class="sxs-lookup"><span data-stu-id="6572c-106">For this reason, your organization may have created a document deletion policy for your site&mdash;for example, general business documents might be required to be deleted five years after they were created.</span></span>
  
<span data-ttu-id="6572c-107">Dependiendo de la organización, una directiva de eliminación de documentos puede ser:</span><span class="sxs-lookup"><span data-stu-id="6572c-107">Depending on your organization, a document deletion policy might be:</span></span>
  
- <span data-ttu-id="6572c-108">**Obligatorio** El propietario de un sitio no puede optar por una directiva obligatoria, que se aplica automáticamente al sitio.</span><span class="sxs-lookup"><span data-stu-id="6572c-108">**Mandatory** A site owner can't opt out of a mandatory policy, which is automatically applied to the site.</span></span> 
    
- <span data-ttu-id="6572c-109">**Predeterminada** Una directiva predeterminada se aplica automáticamente a un sitio, pero el propietario de dicho sitio puede:</span><span class="sxs-lookup"><span data-stu-id="6572c-109">**Default** A default policy is automatically applied to a site, but a site owner can:</span></span> 
    
  - <span data-ttu-id="6572c-110">Elegir otra directiva, si la hay.</span><span class="sxs-lookup"><span data-stu-id="6572c-110">Choose another policy if available.</span></span>
    
  - <span data-ttu-id="6572c-111">No participar en la Directiva en su totalidad si no es relevante para el contenido del sitio.</span><span class="sxs-lookup"><span data-stu-id="6572c-111">Opt out of the policy entirely if it isn't relevant to the content in the site.</span></span>
    
- <span data-ttu-id="6572c-112">**Ni obligatoria ni predeterminada** En este caso, no se aplica ninguna directiva al sitio automáticamente, y el propietario debe aplicarla de forma manual.</span><span class="sxs-lookup"><span data-stu-id="6572c-112">**Neither mandatory nor default** In this case, no policy is automatically applied to the site, and the site owner needs to take action to apply one.</span></span> 
    
<span data-ttu-id="6572c-113">Una directiva de eliminación de documentos puede contener más de&mdash;una regla por ejemplo, una regla puede decir eliminar documentos un año después de su creación, pero otra regla puede decir eliminar documentos un año después de que se modificaron por última vez.</span><span class="sxs-lookup"><span data-stu-id="6572c-113">A document deletion policy may contain more than one rule&mdash;for example, one rule might say delete documents one year after they were created, but another rule might say delete documents one year after they were last modified.</span></span> <span data-ttu-id="6572c-114">Si una directiva contiene más de una regla, puede seleccionar la que se ajuste mejor al sitio.</span><span class="sxs-lookup"><span data-stu-id="6572c-114">If a policy contains more than one rule, you can select the rule that best applies to your site.</span></span> <span data-ttu-id="6572c-115">La regla de eliminación se aplicará a todas las bibliotecas del sitio.</span><span class="sxs-lookup"><span data-stu-id="6572c-115">The delete rule will be applied to all libraries within the site.</span></span> <span data-ttu-id="6572c-116">Solo puede haber una directiva y una regla activas en un sitio al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="6572c-116">Only one policy and one rule can be active in a site at one time.</span></span> <span data-ttu-id="6572c-117">Al igual que una directiva, una regla se puede establecer como predeterminada para que se aplique automáticamente cuando se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="6572c-117">Like a policy, a rule can be set as default, so that it's applied automatically when the policy is applied.</span></span>
  
<span data-ttu-id="6572c-p103">Por último, las directivas de eliminación de documentos son heredadas. Cuando se selecciona una directiva o regla para un sitio, todos los subsitios heredan esa selección, a menos que el propietario de un subsitio interrumpa la herencia seleccionando una directiva o regla distinta. Cuando seleccione una directiva o regla, tenga en cuenta el contenido de los subsitios del sitio.</span><span class="sxs-lookup"><span data-stu-id="6572c-p103">Finally, document deletion policies are inherited. When you select a policy or rule for your site, that selection is inherited by all subsites, although an owner of a subsite can break inheritance by selecting a different policy or rule. When you select a policy or rule, consider the content of any subsites below your site.</span></span>
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a><span data-ttu-id="6572c-121">Ver las directivas de eliminación de documentos disponibles en una colección de sitios</span><span class="sxs-lookup"><span data-stu-id="6572c-121">View the document deletion policies available in a site collection</span></span>

<span data-ttu-id="6572c-p104">Su organización puede asignar distintas directivas a colecciones de sitios diferentes. En el nivel de colección de sitios, el propietario de una colección de sitios puede ver todas las directivas de eliminación de documentos disponibles para esa colección concreta. Las directivas pueden estar disponibles para la plantilla de la colección de sitios (y, por tanto, para todas las colecciones de sitios creadas a partir de esta plantilla) o para esta colección de sitios específica.</span><span class="sxs-lookup"><span data-stu-id="6572c-p104">Your organization may assign different policies to different site collections. At the site collection level, an owner of a site collection can view all of the document deletion policies that are available to that site collection. The policies may have been made available to the site collection template (and therefore all site collections created from this template) or to this specific site collection.</span></span>
  
1. <span data-ttu-id="6572c-125">En el sitio de nivel superior de la colección de sitios, en la esquina superior derecha, elija **configuración** del \> **sitio**[icono de engranaje].</span><span class="sxs-lookup"><span data-stu-id="6572c-125">In the top-level site in the site collection, in the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="6572c-126">En **directivas de eliminación de documentos**de administración \> de la colección de **sitios** .</span><span class="sxs-lookup"><span data-stu-id="6572c-126">Under **Site Collection Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6572c-127">El vínculo **directivas de eliminación de documentos** no aparecerá a menos que se hayan asignado directivas a la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="6572c-127">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="6572c-128">Además, el vínculo no aparece inmediatamente después de que las directivas se hayan asignado al sitio: puede tardar hasta 24 horas desde el momento en que se asignan las directivas cuando aparece el vínculo **directivas de eliminación de documentos** .</span><span class="sxs-lookup"><span data-stu-id="6572c-128">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="6572c-129">En esta página, puede ver lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6572c-129">On this page you can view:</span></span>
    
  - <span data-ttu-id="6572c-p106">Las directivas asignadas actualmente y las reglas asociadas. Seleccione una directiva para ver las reglas en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="6572c-p106">The currently assigned policies and the associated rules. Select a policy to view the rules in the right pane.</span></span>
    
  - <span data-ttu-id="6572c-132">Si existe una directiva predeterminada, se muestra **Sí** en la columna **Predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="6572c-132">The default policy, if any, displays **Yes** in the **Default** column.</span></span> 
    
  - <span data-ttu-id="6572c-133">Si la directiva se ha asignado como **Obligatoria**, se muestra un mensaje debajo de la lista.</span><span class="sxs-lookup"><span data-stu-id="6572c-133">A message is displayed below the list if the policy has been assigned as **Mandatory**.</span></span>
    
<span data-ttu-id="6572c-p107">Esta lista es solo para consulta, para que el propietario de la colección de sitios pueda ver todas las directivas y reglas disponibles. Para aplicar una directiva, consulte la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="6572c-p107">This list is view only, for the site collection owner to see all of the available policies and rules. To apply a policy, see the next section.</span></span>
  
![Ver las directivas de eliminación de documentos asignadas a una colección de sitios](../media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="6572c-137">Aplicar o quitar una directiva de eliminación de documentos de un sitio</span><span class="sxs-lookup"><span data-stu-id="6572c-137">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="6572c-138">Como propietario del sitio o propietario de la colección de sitios, su organización puede haber creado directivas que puede aplicar al sitio o anular por completo.</span><span class="sxs-lookup"><span data-stu-id="6572c-138">As a site owner or site collection owner, your organization may have created policies that you can either apply to your site or opt out of entirely.</span></span>
  
1. <span data-ttu-id="6572c-139">En la esquina superior derecha, elija **configuración** del \> **sitio**[icono de engranaje].</span><span class="sxs-lookup"><span data-stu-id="6572c-139">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="6572c-140">En **directivas de eliminación de documentos**de administración \> del **sitio** .</span><span class="sxs-lookup"><span data-stu-id="6572c-140">Under **Site Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6572c-141">El vínculo **directivas de eliminación de documentos** no aparecerá a menos que se hayan asignado directivas a la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="6572c-141">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="6572c-142">Además, el vínculo no aparece inmediatamente después de que las directivas se hayan asignado al sitio: puede tardar hasta 24 horas desde el momento en que se asignan las directivas cuando aparece el vínculo **directivas de eliminación de documentos** .</span><span class="sxs-lookup"><span data-stu-id="6572c-142">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="6572c-143">Realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="6572c-143">Do one of the following:</span></span>
    
  - <span data-ttu-id="6572c-144">**Para aplicar una directiva** Seleccione una directiva \> Seleccione una regla en esa directiva \> **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6572c-144">**To apply a policy** Select a policy \> select a rule in that policy \> **Save**.</span></span>
    
    <span data-ttu-id="6572c-p109">Solo puede haber una directiva y una regla activas en un sitio al mismo tiempo. Su organización puede proporcionar varias directivas y reglas para elegir o solo una directiva o regla.</span><span class="sxs-lookup"><span data-stu-id="6572c-p109">Only one policy and one rule can be active in a site at one time. Your organization may provide several policies and rules to choose from, or only one policy or rule.</span></span>
    
    ![Selección de la opción de Directiva](../media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - <span data-ttu-id="6572c-148">**Para dejar de participar en una directiva** Elija **no participar: Nota eliminar** \> **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6572c-148">**To opt out of a policy** Choose **Opt-Out: Do Note Delete** \> **Save**.</span></span>
    
    <span data-ttu-id="6572c-149">Como propietario de un sitio, puede rechazar una directiva de eliminación de documentos si determina que la Directiva no se aplica al contenido de su sitio.</span><span class="sxs-lookup"><span data-stu-id="6572c-149">As a site owner, you can opt out of a document deletion policy if you determine that the policy isn't applicable to the content in your site.</span></span> <span data-ttu-id="6572c-150">Sin embargo, no puede optar por no participar en una directiva que se haya marcado como **obligatoria**.</span><span class="sxs-lookup"><span data-stu-id="6572c-150">However, you can't opt out of a policy that has been marked as **Mandatory**.</span></span>
    
    ![Opción de cancelación](../media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a><span data-ttu-id="6572c-152">Las directivas de eliminación de documentos invalidan otras directivas</span><span class="sxs-lookup"><span data-stu-id="6572c-152">Document deletion policies override other policies</span></span>

<span data-ttu-id="6572c-153">Un sitio puede usar otras directivas para la retención y eliminación de contenido:</span><span class="sxs-lookup"><span data-stu-id="6572c-153">A site may use other policies for retaining and deleting content:</span></span>
  
- <span data-ttu-id="6572c-154">Directivas de tipo de contenido para la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="6572c-154">Content type policies for the site collection.</span></span>
    
- <span data-ttu-id="6572c-155">Directivas de administración de la información para una lista o biblioteca.</span><span class="sxs-lookup"><span data-stu-id="6572c-155">Information management policies for a list or library.</span></span>
    
<span data-ttu-id="6572c-156">Si aplica una directiva de eliminación de documentos a un sitio que ya usa directivas de tipo de contenido o directivas de administración de información para una lista o biblioteca, dichas directivas se ignorarán mientras la directiva de eliminación de documentos esté activa.</span><span class="sxs-lookup"><span data-stu-id="6572c-156">If you apply a document deletion policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the document deletion policy is in effect.</span></span> <span data-ttu-id="6572c-157">Si se omiten otras directivas, verá el mensaje "el contenido de este sitio usa directivas de eliminación de documentos".</span><span class="sxs-lookup"><span data-stu-id="6572c-157">If other policies are ignored, you'll see the message "Content on this site uses Document Deletion Policies".</span></span>
  
<span data-ttu-id="6572c-158">Esto quiere decir que debe configurar un sitio de forma que solo utilice directivas creadas para contenido estructurado (directivas de administración de información y directivas de tipo de contenido) o contenido no estructurado (directivas de eliminación de documentos), pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="6572c-158">This means you should plan for a site to use only policies meant for structured content (information management policies and content type policies) or unstructured content (document deletion policies), not both.</span></span> <span data-ttu-id="6572c-159">Si opta por no usar una directiva de eliminación de documentos, la advertencia no se mostrará y otros tipos de directivas seguirán funcionando.</span><span class="sxs-lookup"><span data-stu-id="6572c-159">If you opt out of a document deletion policy, the warning won't be displayed and other types of policies will continue to work.</span></span>
  
<span data-ttu-id="6572c-160">Las directivas del sitio no se verán afectadas por las directivas de eliminación de documentos.</span><span class="sxs-lookup"><span data-stu-id="6572c-160">Site policies are not affected by document deletion policies.</span></span>
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a><span data-ttu-id="6572c-161">Determinar si se están ignorando las directivas de tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="6572c-161">Determine if content type policies are being ignored</span></span>

<span data-ttu-id="6572c-162">Si el sitio estaba usando directivas de tipo de contenido y ahora ve este mensaje, esas directivas ya no se aplicarán.</span><span class="sxs-lookup"><span data-stu-id="6572c-162">If your site was using content type policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="6572c-163">Para restaurar las directivas de tipo de contenido, puede quitar la Directiva de eliminación de documentos del sitio, tal como se ha descrito anteriormente, si hay una opción de cancelación disponible.</span><span class="sxs-lookup"><span data-stu-id="6572c-163">To restore the content type policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="6572c-164">Si no existe la opción de no participar, la Directiva de eliminación de documentos es obligatoria y deberá ponerse en contacto con el responsable de cumplimiento de su organización.</span><span class="sxs-lookup"><span data-stu-id="6572c-164">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
1. <span data-ttu-id="6572c-165">En la esquina superior derecha, elija **configuración** del \> **sitio**[icono de engranaje].</span><span class="sxs-lookup"><span data-stu-id="6572c-165">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="6572c-166">En **plantillas de directiva de tipo de contenido**de administración \> de **sitio** .</span><span class="sxs-lookup"><span data-stu-id="6572c-166">Under **Site Administration** \> **Content Type Policy Templates**.</span></span>
    
    ![ADVERTENCIA en el sitio de que se están usando directivas de eliminación de documentos](../media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a><span data-ttu-id="6572c-168">Determinar si se están ignorando las directivas de administración de información</span><span class="sxs-lookup"><span data-stu-id="6572c-168">Determine if information management policies are being ignored</span></span>

<span data-ttu-id="6572c-169">Si el sitio estaba usando directivas de administración de la información y ahora ve este mensaje, esas directivas ya no se aplicarán.</span><span class="sxs-lookup"><span data-stu-id="6572c-169">If your site was using information management policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="6572c-170">Para restaurar las directivas de administración de la información, puede quitar la Directiva de eliminación de documentos del sitio, como se ha descrito anteriormente, si hay una opción de cancelación disponible.</span><span class="sxs-lookup"><span data-stu-id="6572c-170">To restore the information management policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="6572c-171">Si no existe la opción de no participar, la Directiva de eliminación de documentos es obligatoria y deberá ponerse en contacto con el responsable de cumplimiento de su organización.</span><span class="sxs-lookup"><span data-stu-id="6572c-171">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
- <span data-ttu-id="6572c-172">Para una lista o biblioteca, en la biblioteca \> de la \> ficha **biblioteca** de la cinta de **Opciones Configuración** \> de la **Directiva** **permisos y** \> administración de información de administración.</span><span class="sxs-lookup"><span data-stu-id="6572c-172">For a list or library, on the Ribbon \> **Library** tab \> **Library Settings** \> under **Permissions and Management** \> **Information Management Policy Settings**.</span></span>
    
    ![ADVERTENCIA en el sitio de que se están usando directivas de eliminación de documentos](../media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a><span data-ttu-id="6572c-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="6572c-174">See also</span></span>

<span data-ttu-id="6572c-175">[Overview of document deletion policies](document-deletion-policies.md) (Información general sobre las directivas de eliminación de documentos)</span><span class="sxs-lookup"><span data-stu-id="6572c-175">[Overview of document deletion policies](document-deletion-policies.md)</span></span>
  
[<span data-ttu-id="6572c-176">Crear una directiva de eliminación de documentos</span><span class="sxs-lookup"><span data-stu-id="6572c-176">Create a document deletion policy</span></span>](create-a-document-deletion-policy.md)

