---
title: Introducción al explorador de contenido
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: El explorador de contenido le permite ver elementos etiquetados de forma nativa.
ms.openlocfilehash: 7977d30881a4229f99f4c5976d4c41377573a6ca
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379217"
---
# <a name="get-started-with-content-explorer"></a><span data-ttu-id="e5db2-103">Introducción al explorador de contenido</span><span class="sxs-lookup"><span data-stu-id="e5db2-103">Get started with content explorer</span></span>

<span data-ttu-id="e5db2-104">El explorador de contenido de la clasificación de datos le permite ver de forma nativa los elementos que se resumiendo en la página información general.</span><span class="sxs-lookup"><span data-stu-id="e5db2-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

![captura de pantalla contraída del explorador de contenido](../media/data-classification-content-explorer-1.png)

## <a name="prerequisites"></a><span data-ttu-id="e5db2-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e5db2-106">Prerequisites</span></span>

<span data-ttu-id="e5db2-107">Todas las cuentas que tengan acceso a la clasificación de datos y la usen deben tener una licencia asignada de una de estas suscripciones:</span><span class="sxs-lookup"><span data-stu-id="e5db2-107">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="e5db2-108">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="e5db2-108">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="e5db2-109">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="e5db2-109">Office 365 (E5)</span></span>
- <span data-ttu-id="e5db2-110">Complemento de cumplimiento avanzado (E5)</span><span class="sxs-lookup"><span data-stu-id="e5db2-110">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="e5db2-111">Complemento de inteligencia de amenazas avanzado (E5)</span><span class="sxs-lookup"><span data-stu-id="e5db2-111">Advanced Threat Intelligence (E5) add-on</span></span>

### <a name="permissions"></a><span data-ttu-id="e5db2-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="e5db2-112">Permissions</span></span>

<span data-ttu-id="e5db2-113">Para obtener acceso a la pestaña del explorador de contenido, una cuenta debe tener asignada una suscripción en uno de estos roles o grupos de roles.</span><span class="sxs-lookup"><span data-stu-id="e5db2-113">In order to get access to the content explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span> 

<span data-ttu-id="e5db2-114">Una [directiva DLP](data-loss-prevention-policies.md) puede ayudar a proteger información confidencial, lo que se define como un **tipo de información confidencial**.</span><span class="sxs-lookup"><span data-stu-id="e5db2-114">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="e5db2-115">Microsoft 365 incluye [definiciones para muchos tipos comunes de información confidencial](sensitive-information-type-entity-definitions.md), en muchas regiones diferentes y listas para su uso.</span><span class="sxs-lookup"><span data-stu-id="e5db2-115">Microsoft 365 includes [definitions for many common sensitive information types](sensitive-information-type-entity-definitions.md) across many different regions that are ready for you to use.</span></span> <span data-ttu-id="e5db2-116">Por ejemplo, un número de tarjeta de crédito, números de cuenta bancaria, números de identificación nacionales y números de servicio de Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="e5db2-116">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

<span data-ttu-id="e5db2-117">**Grupos de roles de Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="e5db2-117">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="e5db2-118">Administrador global</span><span class="sxs-lookup"><span data-stu-id="e5db2-118">Global administrator</span></span>
- <span data-ttu-id="e5db2-119">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="e5db2-119">Compliance administrator</span></span>
- <span data-ttu-id="e5db2-120">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="e5db2-120">Security administrator</span></span>
- <span data-ttu-id="e5db2-121">Administrador de datos de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="e5db2-121">Compliance data administrator</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5db2-122">La pertenencia a estos grupos de roles no le permite ver la lista de elementos en el explorador de contenido o ver el contenido de los elementos en el explorador de contenido.</span><span class="sxs-lookup"><span data-stu-id="e5db2-122">Membership in these role groups does not allow you to view the list of items in content explorer or to view the contents of the items in content explorer.</span></span>

### <a name="required-permissions-to-access-items-in-content-explorer"></a><span data-ttu-id="e5db2-123">Permisos necesarios para acceder a elementos en el explorador de contenido</span><span class="sxs-lookup"><span data-stu-id="e5db2-123">Required permissions to access items in content explorer</span></span>

<span data-ttu-id="e5db2-124">El acceso al explorador de contenidos está altamente restringido porque permite leer el contenido de los archivos digitalizados.</span><span class="sxs-lookup"><span data-stu-id="e5db2-124">Access to content explorer is highly restricted because it lets you read the contents of scanned files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5db2-125">Estos permisos reemplazan los permisos que se asignan a los elementos de forma local, lo que permite ver el contenido.</span><span class="sxs-lookup"><span data-stu-id="e5db2-125">These permissions supercede permissions that are locally assigned to the items, which allows viewing of the content.</span></span> 

<span data-ttu-id="e5db2-126">Hay dos roles que otorgan acceso al explorador de contenido:</span><span class="sxs-lookup"><span data-stu-id="e5db2-126">There are two roles that grant access to content explorer:</span></span>

- <span data-ttu-id="e5db2-127">**Visor de listas del explorador de contenido**: la pertenencia a este grupo de roles permite ver cada elemento y su ubicación en la vista de lista.</span><span class="sxs-lookup"><span data-stu-id="e5db2-127">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location in list view.</span></span> <span data-ttu-id="e5db2-128">El rol `data classification list viewer` se ha asignado previamente a este grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="e5db2-128">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="e5db2-129">**Visor de contenido del explorador de contenido**: la pertenencia a este grupo de roles permite ver el contenido de cada elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="e5db2-129">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="e5db2-130">El rol `data classification content viewer` se ha asignado previamente a este grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="e5db2-130">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="e5db2-131">La cuenta que use para tener acceso al explorador de contenido debe estar en uno de los grupos de roles o en ambos.</span><span class="sxs-lookup"><span data-stu-id="e5db2-131">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="e5db2-132">Estos son grupos de roles independientes y no son acumulativos.</span><span class="sxs-lookup"><span data-stu-id="e5db2-132">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="e5db2-133">Por ejemplo, si desea conceder a una cuenta la capacidad para ver los elementos y sus ubicaciones únicamente, conceda a los derechos de visores de listas de explorador de contenido.</span><span class="sxs-lookup"><span data-stu-id="e5db2-133">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="e5db2-134">Si desea que esa misma cuenta también pueda ver el contenido de los elementos de la lista, conceda los derechos de visor de contenido de explorador de contenido.</span><span class="sxs-lookup"><span data-stu-id="e5db2-134">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="e5db2-135">También puede asignar uno o ambos roles a un grupo de roles personalizado para ajustar el acceso a Content Explorer.</span><span class="sxs-lookup"><span data-stu-id="e5db2-135">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

<span data-ttu-id="e5db2-136">Un administrador global, un administrador de cumplimiento o un administrador de datos pueden asignar el visor de listas del explorador de contenido cuando sea necesario y la pertenencia al grupo de funciones del visor del explorador de contenido.</span><span class="sxs-lookup"><span data-stu-id="e5db2-136">A Global admin, Compliance admin, or Data admin can assign the necessary Content Explorer List Viewer, and Content Explorer Content Viewer role group membership.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="e5db2-137">Explorador de contenido</span><span class="sxs-lookup"><span data-stu-id="e5db2-137">Content explorer</span></span>

<span data-ttu-id="e5db2-138">El explorador de contenido muestra una instantánea actual de los elementos que tienen una etiqueta de confidencial, una etiqueta de retención o que se han clasificado como un tipo de información confidencial en la organización.</span><span class="sxs-lookup"><span data-stu-id="e5db2-138">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="e5db2-139">Tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="e5db2-139">Sensitive information types</span></span>

<span data-ttu-id="e5db2-140">Una [directiva DLP](data-loss-prevention-policies.md) puede ayudar a proteger información confidencial, lo que se define como un **tipo de información confidencial**.</span><span class="sxs-lookup"><span data-stu-id="e5db2-140">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="e5db2-141">Microsoft 365 incluye [definiciones para muchos tipos comunes de información confidencial](sensitive-information-type-entity-definitions.md) de muchas regiones diferentes y listas para su uso.</span><span class="sxs-lookup"><span data-stu-id="e5db2-141">Microsoft 365 includes [definitions for many common sensitive information types](sensitive-information-type-entity-definitions.md) from across many different regions that are ready for you to use.</span></span> <span data-ttu-id="e5db2-142">Por ejemplo, un número de tarjeta de crédito, números de cuenta bancaria, números de identificación nacionales y números de servicio de Windows Live Id.  </span><span class="sxs-lookup"><span data-stu-id="e5db2-142">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

> [!NOTE]
> <span data-ttu-id="e5db2-143">Actualmente, el explorador de contenido no busca ningún tipo de información confidencial en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e5db2-143">Content explorer doesn't currently scan for sensitive information types in Exchange Online.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="e5db2-144">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="e5db2-144">Sensitivity labels</span></span>

<span data-ttu-id="e5db2-145">Una [etiqueta de confidencialidad](sensitivity-labels.md) es simplemente una etiqueta que indica el valor que tiene el elemento para su organización.</span><span class="sxs-lookup"><span data-stu-id="e5db2-145">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="e5db2-146">Se puede aplicar manualmente o automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e5db2-146">It can be applied manually, or automatically.</span></span> <span data-ttu-id="e5db2-147">Una vez aplicada, se inserta en el documento y se adhiere a él dondequiera que vaya.</span><span class="sxs-lookup"><span data-stu-id="e5db2-147">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="e5db2-148">Una etiqueta de confidencialidad habilita varios comportamientos de protección, como, por ejemplo, la marca de agua o el cifrado obligatorios.</span><span class="sxs-lookup"><span data-stu-id="e5db2-148">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span>

<span data-ttu-id="e5db2-149">Las etiquetas de confidencialidad deben habilitarse para los archivos de SharePoint y OneDrive para que los datos correspondientes aparezcan en la página de clasificación de datos.</span><span class="sxs-lookup"><span data-stu-id="e5db2-149">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="e5db2-150">Para más información, vea [Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="e5db2-150">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="e5db2-151">Etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="e5db2-151">Retention labels</span></span>

<span data-ttu-id="e5db2-152">Una [etiqueta de retención](retention.md) le permite definir durante cuánto tiempo se conserva un elemento con una etiqueta y los pasos que se deben seguir antes de eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="e5db2-152">A [retention label](retention.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="e5db2-153">Se puede aplicar manualmente o automáticamente mediante directivas.</span><span class="sxs-lookup"><span data-stu-id="e5db2-153">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="e5db2-154">Puede ayudar a su organización a mantener el cumplimiento normativo y los requerimientos legales.</span><span class="sxs-lookup"><span data-stu-id="e5db2-154">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="e5db2-155">Cómo usar el explorador de contenido</span><span class="sxs-lookup"><span data-stu-id="e5db2-155">How to use content explorer</span></span>

1. <span data-ttu-id="e5db2-156">Abra \*\*Centro de cumplimiento de Microsoft 365 \*\*  > \*\*de la clasificación de datos \*\* > **El explorador de contenido**.</span><span class="sxs-lookup"><span data-stu-id="e5db2-156">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="e5db2-157">Si sabe el nombre de la etiqueta o el tipo de información confidencial, puede escribirlo en el cuadro de filtro.</span><span class="sxs-lookup"><span data-stu-id="e5db2-157">If you know the name of the label, or the sensitive information type, you can type that into the filter box.</span></span>
3. <span data-ttu-id="e5db2-158">De forma alternativa, puede buscar el elemento expandiendo el tipo de etiqueta y seleccionando la etiqueta de la lista.</span><span class="sxs-lookup"><span data-stu-id="e5db2-158">Alternately, you can browse for the item by expanding the label type and selecting the label from the list.</span></span>
4. <span data-ttu-id="e5db2-159">Seleccione una ubicación en **todas las ubicaciones** y profundice en la estructura de carpetas hasta el elemento.</span><span class="sxs-lookup"><span data-stu-id="e5db2-159">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="e5db2-160">Haga doble clic para abrir el elemento de forma nativa en el explorador de contenido.</span><span class="sxs-lookup"><span data-stu-id="e5db2-160">Double-click to open the item natively in content explorer.</span></span>

### <a name="export"></a><span data-ttu-id="e5db2-161">Exportar</span><span class="sxs-lookup"><span data-stu-id="e5db2-161">Export</span></span>
<span data-ttu-id="e5db2-162">El control de **Exportación** creará un archivo .csv que contiene una lista de lo que se muestra en el panel **Todas las ubicaciones**.</span><span class="sxs-lookup"><span data-stu-id="e5db2-162">The **export** control will create a .csv file that contains a listing of whatever is showing in the **All locations** pane.</span></span>

![control de exportación de clasificación de datos](../media/data_classification_export_control.png)


### <a name="search"></a><span data-ttu-id="e5db2-164">Búsqueda</span><span class="sxs-lookup"><span data-stu-id="e5db2-164">Search</span></span>

<span data-ttu-id="e5db2-165">Cuando profundiza en una ubicación, como una carpeta de Exchange o un sitio de SharePoint o de OneDrive, aparece la herramienta de **búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="e5db2-165">When you drill down into a location, such as an Exchange folder, or a SharePoint or OneDrive site, the **search** tool appears.</span></span>

![herramienta de búsqueda del explorador de contenido](../media/data_classification_search_tool.png)


<span data-ttu-id="e5db2-167">El ámbito de la herramienta de búsqueda es lo que se muestra en el panel **Todas las ubicaciones** y lo que puede buscar varía en función de la ubicación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e5db2-167">The scope of the search tool is what is displaying in the **All locations** pane and what you can search on varies depending on the selected location.</span></span> 

<span data-ttu-id="e5db2-168">Cuando **Exchange** es la ubicación seleccionada, puede buscar en la dirección de correo completa del buzón, por ejemplo `user@domainname.com`.</span><span class="sxs-lookup"><span data-stu-id="e5db2-168">When **Exchange** is the selected location, you can search on the full email address of the mailbox, for example `user@domainname.com`.</span></span>

<span data-ttu-id="e5db2-169">Cuando **SharePoint** o **OneDrive** están seleccionados, la herramienta de búsqueda aparecerá cuando profundice en nombres de sitio, carpetas y archivos.</span><span class="sxs-lookup"><span data-stu-id="e5db2-169">When either **SharePoint** or **OneDrive** are selected location, the search tool will appear when you drill down to site names, folders and files.</span></span> 

> [!NOTE]
> <span data-ttu-id="e5db2-170">**OneDrive** Hemos escuchado sus valiosos comentarios sobre la integración de OneDrive durante nuestro programa de versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="e5db2-170">**OneDrive** We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="e5db2-171">En base a los comentarios, la funcionalidad de OneDrive permanecerá en la versión preliminar hasta que todas las correcciones estén instaladas.</span><span class="sxs-lookup"><span data-stu-id="e5db2-171">Based on that feedback, the OneDrive functionality will remain in preview till all fixes are in place.</span></span> <span data-ttu-id="e5db2-172">Según el espacio empresarial, es posible que algunos clientes no vean OneDrive como una ubicación.</span><span class="sxs-lookup"><span data-stu-id="e5db2-172">Depending on your tenant, some customers may not see OneDrive as a location.</span></span> <span data-ttu-id="e5db2-173">Agradecemos su continuo apoyo en esto.</span><span class="sxs-lookup"><span data-stu-id="e5db2-173">We appreciate your continued support on this.</span></span>

<span data-ttu-id="e5db2-174">Puede buscar en:</span><span class="sxs-lookup"><span data-stu-id="e5db2-174">You can search on:</span></span>


|<span data-ttu-id="e5db2-175">valor</span><span class="sxs-lookup"><span data-stu-id="e5db2-175">value</span></span>|<span data-ttu-id="e5db2-176">ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5db2-176">example</span></span>  |
|---------|---------|
|<span data-ttu-id="e5db2-177">nombre completo del sitio</span><span class="sxs-lookup"><span data-stu-id="e5db2-177">full site name</span></span>    |`https://contoso.onmicrosoft.com/sites/sitename`    |
|<span data-ttu-id="e5db2-178">nombre de carpeta raíz (obtiene todas las subcarpetas)</span><span class="sxs-lookup"><span data-stu-id="e5db2-178">root folder name - gets all subfolders</span></span>    | `/sites`        |
|<span data-ttu-id="e5db2-179">nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="e5db2-179">file name</span></span>    |    `RES_Resume_1234.txt`     |
|<span data-ttu-id="e5db2-180">texto al principio del nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="e5db2-180">text at the beginning of file name</span></span>| `RES`|
|<span data-ttu-id="e5db2-181">texto después de un carácter de subrayado (_) en el nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="e5db2-181">text after an underscore character ( _ ) in file name</span></span>|<span data-ttu-id="e5db2-182">`Resume` o `1234`</span><span class="sxs-lookup"><span data-stu-id="e5db2-182">`Resume` or `1234`</span></span>| 
|<span data-ttu-id="e5db2-183">extensión de archivo</span><span class="sxs-lookup"><span data-stu-id="e5db2-183">file extension</span></span>|`txt`|


## <a name="see-also"></a><span data-ttu-id="e5db2-184">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e5db2-184">See also</span></span>

- [<span data-ttu-id="e5db2-185">Más información sobre las etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="e5db2-185">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="e5db2-186">Información sobre las directivas de retención y las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="e5db2-186">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="e5db2-187">Definiciones de entidad de tipos de información confidencial.md</span><span class="sxs-lookup"><span data-stu-id="e5db2-187">Sensitive information type entity definitions.md</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="e5db2-188">Información general sobre la prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="e5db2-188">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
