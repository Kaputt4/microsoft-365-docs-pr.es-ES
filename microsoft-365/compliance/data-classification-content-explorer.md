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
ms.openlocfilehash: 9e9ad76d2bdd7f74368121346f7e04d1208803ff
ms.sourcegitcommit: 99d759d5c4e7d81266c3ebc087eaa37486cc0bc1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "39818862"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="ca5a0-103">Usar el explorador de contenido de clasificación de datos (vista previa)</span><span class="sxs-lookup"><span data-stu-id="ca5a0-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="ca5a0-104">El explorador de contenido de la clasificación de datos le permite ver de forma nativa los elementos que se resumiendo en la página información general.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="ca5a0-105">Explorador de contenido</span><span class="sxs-lookup"><span data-stu-id="ca5a0-105">Content explorer</span></span>

<span data-ttu-id="ca5a0-106">El explorador de contenido muestra una instantánea actual de los elementos que tienen una etiqueta de confidencial, una etiqueta de retención o que se han clasificado como un tipo de información confidencial en la organización.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-106">Content explorer is a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="ca5a0-107">Tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="ca5a0-107">Sensitive information types</span></span>

<span data-ttu-id="ca5a0-108">Una [directiva DLP](data-loss-prevention-policies.md) puede ayudar a proteger información confidencial, lo que se define como un **tipo de información confidencial**.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-108">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="ca5a0-109">Microsoft 365 incluye [definiciones para muchos tipos comunes de información confidencial, en muchas regiones diferentes y listas para su uso.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-109">Office 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> <span data-ttu-id="ca5a0-110">Por ejemplo, un número de tarjeta de crédito, números de cuenta bancaria, números de identificación nacionales y números de servicio de Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-110">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="ca5a0-111">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="ca5a0-111">Sensitivity labels</span></span>

<span data-ttu-id="ca5a0-112">Una [etiqueta de confidencialidad](sensitivity-labels.md) es simplemente una etiqueta que indica el valor que tiene el elemento para su organización.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-112">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="ca5a0-113">Se puede aplicar manualmente o automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-113">It can be applied manually, or automatically.</span></span> <span data-ttu-id="ca5a0-114">Una vez aplicada, se inserta en el documento y se adhiere a él dondequiera que vaya.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-114">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="ca5a0-115">Una etiqueta de confidencialidad habilita varios comportamientos de protección, como, por ejemplo, la marca de agua o el cifrado obligatorios.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-115">the presence of the tag enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="ca5a0-116">Con la protección del punto de conexión habilitada, podrá incluso evitar que un elemento abandone el control de la organización.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-116">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="ca5a0-117">Etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="ca5a0-117">Retention labels</span></span>

<span data-ttu-id="ca5a0-118">Una [etiqueta de retención le permite definir durante cuánto tiempo se conserva un elemento con una etiqueta y los pasos que se deben seguir antes de eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-118">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="ca5a0-119">Se puede aplicar manualmente o automáticamente mediante directivas.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-119">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="ca5a0-120">Puede ayudar a su organización a mantener el cumplimiento normativo y los requerimientos legales.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-120">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

![Captura de pantalla contraída de Content Explorer](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="ca5a0-122">Permisos</span><span class="sxs-lookup"><span data-stu-id="ca5a0-122">Permissions</span></span>

<span data-ttu-id="ca5a0-123">Hay dos roles que otorgan acceso al explorador de contenido:</span><span class="sxs-lookup"><span data-stu-id="ca5a0-123">There are two roles that grant access to Content explorer:</span></span>

- <span data-ttu-id="ca5a0-124">**Visor de listas del explorador de contenido**: la pertenencia a este rol permite ver cada elemento y su ubicación.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-124">**Content Explorer List viewer**: Membership in this role allows you to see each item and its location.</span></span>

- <span data-ttu-id="ca5a0-125">**Visor de contenido del explorador de contenido**: la pertenencia a este rol permite ver el contenido de cada elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-125">**Content Explorer Content viewer**: Membership in this role allows you to view the contents of each item in the list.</span></span>

<span data-ttu-id="ca5a0-126">La cuenta que use para tener acceso al explorador de contenido debe estar en uno de los roles o en ambos.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-126">The account you use to access Content explorer must be in one or both of the roles.</span></span> <span data-ttu-id="ca5a0-127">Este es un rol independiente y no es acumulativa.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-127">These are independent roles and are not cumulative.</span></span> <span data-ttu-id="ca5a0-128">Por ejemplo, si desea conceder a una cuenta la capacidad para ver los elementos y sus ubicaciones únicamente, conceda a los derechos de visores de listas de explorador de contenido.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-128">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="ca5a0-129">Si desea que esa misma cuenta también pueda ver el contenido de los elementos de la lista, conceda los derechos de visor de contenido de explorador de contenido.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-129">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="ca5a0-130">Cómo usar el explorador de contenido</span><span class="sxs-lookup"><span data-stu-id="ca5a0-130">How to use content explorer</span></span>

1. <span data-ttu-id="ca5a0-131">Abra \*\*Centro de cumplimiento de Microsoft 365 \*\*  > \*\*de la clasificación de datos \*\* > **El explorador de contenido**.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-131">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="ca5a0-132">Si sabe el nombre de la etiqueta o el tipo de información confidencial, puede escribirlo en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-132">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="ca5a0-133">De forma alternativa, puede buscar el elemento expandiendo el tipo de etiqueta y seleccionando la etiqueta de la lista; a continuación se muestra un elemento de la parte de la lista correspondiente a la etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-133">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="ca5a0-134">Seleccione una ubicación en **todas las ubicaciones** y profundice en la estructura de carpetas hasta el elemento.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-134">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="ca5a0-135">Haga doble clic para abrir el elemento de forma nativa en el explorador de contenido.</span><span class="sxs-lookup"><span data-stu-id="ca5a0-135">Double click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca5a0-136">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ca5a0-136">See also</span></span>

- [<span data-ttu-id="ca5a0-137">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="ca5a0-137">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="ca5a0-138">Etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="ca5a0-138">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="ca5a0-139">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="ca5a0-139">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="ca5a0-140">Información general sobre las directivas de retención</span><span class="sxs-lookup"><span data-stu-id="ca5a0-140">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="ca5a0-141">Información general sobre la prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="ca5a0-141">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
