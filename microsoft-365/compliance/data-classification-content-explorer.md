---
title: Usar el explorador de contenido de clasificación de datos (vista previa)
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
search.appverid:
- MOE150
- MET150
description: El explorador de contenido le permite ver elementos etiquetados de forma nativa.
ms.openlocfilehash: 8a795e0582599dc3160f896a6361b773caa6c4e4
ms.sourcegitcommit: 6ae69c40bafa6aef633789c3df0fa20590bdcf40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "40823802"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="a71de-103">Usar el explorador de contenido de clasificación de datos (vista previa)</span><span class="sxs-lookup"><span data-stu-id="a71de-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="a71de-104">El explorador de contenido de la clasificación de datos le permite ver de forma nativa los elementos que se resumiendo en la página información general.</span><span class="sxs-lookup"><span data-stu-id="a71de-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="a71de-105">Explorador de contenido</span><span class="sxs-lookup"><span data-stu-id="a71de-105">Content explorer</span></span>

<span data-ttu-id="a71de-106">El explorador de contenido muestra una instantánea actual de los elementos que tienen una etiqueta de confidencial, una etiqueta de retención o que se han clasificado como un tipo de información confidencial en la organización.</span><span class="sxs-lookup"><span data-stu-id="a71de-106">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="a71de-107">Tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="a71de-107">Sensitive information types</span></span>

<span data-ttu-id="a71de-108">Una [directiva DLP](data-loss-prevention-policies.md) puede ayudar a proteger información confidencial, lo que se define como un **tipo de información confidencial**.</span><span class="sxs-lookup"><span data-stu-id="a71de-108">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="a71de-109">Microsoft 365 incluye [definiciones para muchos tipos comunes de información confidencial](what-the-sensitive-information-types-look-for.md), en muchas regiones diferentes y listas para su uso.</span><span class="sxs-lookup"><span data-stu-id="a71de-109">Microsoft 365 includes [definitions for many common sensitive information types](what-the-sensitive-information-types-look-for.md) across many different regions that are ready for you to use.</span></span> <span data-ttu-id="a71de-110">Por ejemplo, un número de tarjeta de crédito, números de cuenta bancaria, números de identificación nacionales y números de servicio de Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="a71de-110">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="a71de-111">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="a71de-111">Sensitivity labels</span></span>

<span data-ttu-id="a71de-112">Una [etiqueta de confidencialidad](sensitivity-labels.md) es simplemente una etiqueta que indica el valor que tiene el elemento para su organización.</span><span class="sxs-lookup"><span data-stu-id="a71de-112">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="a71de-113">Se puede aplicar manualmente o automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a71de-113">It can be applied manually, or automatically.</span></span> <span data-ttu-id="a71de-114">Una vez aplicada, se inserta en el documento y se adhiere a él dondequiera que vaya.</span><span class="sxs-lookup"><span data-stu-id="a71de-114">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="a71de-115">Una etiqueta de confidencialidad habilita varios comportamientos de protección, como, por ejemplo, la marca de agua o el cifrado obligatorios.</span><span class="sxs-lookup"><span data-stu-id="a71de-115">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="a71de-116">Con la protección del punto de conexión habilitada, podrá incluso evitar que un elemento abandone el control de la organización.</span><span class="sxs-lookup"><span data-stu-id="a71de-116">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="a71de-117">Las etiquetas de confidencialidad deben habilitarse para los archivos de SharePoint y OneDrive para que los datos correspondientes aparezcan en la página de clasificación de datos.</span><span class="sxs-lookup"><span data-stu-id="a71de-117">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="a71de-118">Para más información, vea[ habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive (vista previa)](sensitivity-labels-sharepoint-onedrive-files.md)</span><span class="sxs-lookup"><span data-stu-id="a71de-118">[Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md)</span></span>

### <a name="retention-labels"></a><span data-ttu-id="a71de-119">Etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="a71de-119">Retention labels</span></span>

<span data-ttu-id="a71de-120">Una [etiqueta de retención](labels.md) le permite definir durante cuánto tiempo se conserva un elemento con una etiqueta y los pasos que se deben seguir antes de eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="a71de-120">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="a71de-121">Se puede aplicar manualmente o automáticamente mediante directivas.</span><span class="sxs-lookup"><span data-stu-id="a71de-121">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="a71de-122">Puede ayudar a su organización a mantener el cumplimiento normativo y los requerimientos legales.</span><span class="sxs-lookup"><span data-stu-id="a71de-122">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

![Captura de pantalla contraída de Content Explorer](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="a71de-124">Permisos</span><span class="sxs-lookup"><span data-stu-id="a71de-124">Permissions</span></span>

<span data-ttu-id="a71de-125">Hay dos roles que otorgan acceso al explorador de contenido:</span><span class="sxs-lookup"><span data-stu-id="a71de-125">There are two roles that grant access to Content explorer:</span></span>

- <span data-ttu-id="a71de-126">**Visor de listas del explorador de contenido**: la pertenencia a este rol permite ver cada elemento y su ubicación.</span><span class="sxs-lookup"><span data-stu-id="a71de-126">**Content Explorer List viewer**: Membership in this role allows you to see each item and its location.</span></span>

- <span data-ttu-id="a71de-127">**Visor de contenido del explorador de contenido**: la pertenencia a este rol permite ver el contenido de cada elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="a71de-127">**Content Explorer Content viewer**: Membership in this role allows you to view the contents of each item in the list.</span></span>

<span data-ttu-id="a71de-128">La cuenta que use para tener acceso al explorador de contenido debe estar en uno de los roles o en ambos.</span><span class="sxs-lookup"><span data-stu-id="a71de-128">The account you use to access Content explorer must be in one or both of the roles.</span></span> <span data-ttu-id="a71de-129">Este es un rol independiente y no es acumulativa.</span><span class="sxs-lookup"><span data-stu-id="a71de-129">These are independent roles and are not cumulative.</span></span> <span data-ttu-id="a71de-130">Por ejemplo, si desea conceder a una cuenta la capacidad para ver los elementos y sus ubicaciones únicamente, conceda a los derechos de visores de listas de explorador de contenido.</span><span class="sxs-lookup"><span data-stu-id="a71de-130">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="a71de-131">Si desea que esa misma cuenta también pueda ver el contenido de los elementos de la lista, conceda los derechos de visor de contenido de explorador de contenido.</span><span class="sxs-lookup"><span data-stu-id="a71de-131">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="a71de-132">Cómo usar el explorador de contenido</span><span class="sxs-lookup"><span data-stu-id="a71de-132">How to use content explorer</span></span>

1. <span data-ttu-id="a71de-133">Abra \*\*Centro de cumplimiento de Microsoft 365 \*\*  > \*\*de la clasificación de datos \*\* > **El explorador de contenido**.</span><span class="sxs-lookup"><span data-stu-id="a71de-133">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="a71de-134">Si sabe el nombre de la etiqueta o el tipo de información confidencial, puede escribirlo en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a71de-134">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="a71de-135">De forma alternativa, puede buscar el elemento expandiendo el tipo de etiqueta y seleccionando la etiqueta de la lista; a continuación se muestra un elemento de la parte de la lista correspondiente a la etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="a71de-135">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="a71de-136">Seleccione una ubicación en **todas las ubicaciones** y profundice en la estructura de carpetas hasta el elemento.</span><span class="sxs-lookup"><span data-stu-id="a71de-136">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="a71de-137">Haga doble clic para abrir el elemento de forma nativa en el explorador de contenido.</span><span class="sxs-lookup"><span data-stu-id="a71de-137">Double-click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="a71de-138">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a71de-138">See also</span></span>

- [<span data-ttu-id="a71de-139">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="a71de-139">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="a71de-140">Etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="a71de-140">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="a71de-141">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="a71de-141">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="a71de-142">Información general sobre las directivas de retención</span><span class="sxs-lookup"><span data-stu-id="a71de-142">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="a71de-143">Información general sobre la prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="a71de-143">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
