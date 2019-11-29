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
ms.openlocfilehash: 6f062901acbf149f6fc56c266d10b370ed0c1112
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "39268658"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="5730a-103">Usar el explorador de contenido de clasificación de datos (vista previa)</span><span class="sxs-lookup"><span data-stu-id="5730a-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="5730a-104">El explorador de contenido de la clasificación de datos le permite ver de forma nativa los elementos que se resumiendo en la página información general.</span><span class="sxs-lookup"><span data-stu-id="5730a-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="5730a-105">Explorador de contenido</span><span class="sxs-lookup"><span data-stu-id="5730a-105">Content explorer</span></span>

<span data-ttu-id="5730a-106">El explorador de contenido es una instantánea actual de los elementos que tienen una etiqueta de sensibilidad, una etiqueta de retención o que se han clasificado como un tipo de información confidencial en la organización.</span><span class="sxs-lookup"><span data-stu-id="5730a-106">Content explorer is a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

![Captura de pantalla contraída de Content Explorer](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="5730a-108">Permisos</span><span class="sxs-lookup"><span data-stu-id="5730a-108">Permissions</span></span>

<span data-ttu-id="5730a-109">Hay dos roles que otorgan acceso al explorador de contenido:</span><span class="sxs-lookup"><span data-stu-id="5730a-109">There are two roles that grant access to Content explorer:</span></span>

- <span data-ttu-id="5730a-110">**Visor de listas del explorador de contenido**: la pertenencia a este rol permite ver cada elemento y su ubicación.</span><span class="sxs-lookup"><span data-stu-id="5730a-110">**Content Explorer List viewer**: Membership in this role allows you to see each item and its location.</span></span>

- <span data-ttu-id="5730a-111">**Visor de contenido del explorador de contenido**: la pertenencia a este rol permite ver el contenido de cada elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="5730a-111">**Content Explorer Content viewer**: Membership in this role allows you to view the contents of each item in the list.</span></span>

<span data-ttu-id="5730a-112">La cuenta que use para tener acceso al explorador de contenido debe estar en uno de los roles o en ambos.</span><span class="sxs-lookup"><span data-stu-id="5730a-112">The account you use to access Content explorer must be in one or both of the roles.</span></span> <span data-ttu-id="5730a-113">Este es un rol independiente y no es acumulativa.</span><span class="sxs-lookup"><span data-stu-id="5730a-113">These are independent roles and are not cumulative.</span></span> <span data-ttu-id="5730a-114">Por ejemplo, si desea conceder a una cuenta la capacidad para ver los elementos y sus ubicaciones únicamente, conceda a los derechos de visores de listas de explorador de contenido.</span><span class="sxs-lookup"><span data-stu-id="5730a-114">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="5730a-115">Si desea que esa misma cuenta también pueda ver el contenido de los elementos de la lista, conceda los derechos de visor de contenido de explorador de contenido.</span><span class="sxs-lookup"><span data-stu-id="5730a-115">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="5730a-116">Cómo usar el explorador de contenido</span><span class="sxs-lookup"><span data-stu-id="5730a-116">How to use content explorer</span></span>

1. <span data-ttu-id="5730a-117">Abra \*\*Centro de cumplimiento de Microsoft 365 \*\*  > \*\*de la clasificación de datos \*\* > **El explorador de contenido**.</span><span class="sxs-lookup"><span data-stu-id="5730a-117">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="5730a-118">Si sabe el nombre de la etiqueta o el tipo de información confidencial, puede escribirlo en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5730a-118">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="5730a-119">De forma alternativa, puede buscar el elemento expandiendo el tipo de etiqueta y seleccionando la etiqueta de la lista; a continuación se muestra un elemento de la parte de la lista correspondiente a la etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="5730a-119">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="5730a-120">Seleccione una ubicación en **todas las ubicaciones** y profundice en la estructura de carpetas hasta el elemento.</span><span class="sxs-lookup"><span data-stu-id="5730a-120">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="5730a-121">Haga doble clic para abrir el elemento de forma nativa en el explorador de contenido.</span><span class="sxs-lookup"><span data-stu-id="5730a-121">Double click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="5730a-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5730a-122">See also</span></span>

- [<span data-ttu-id="5730a-123">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="5730a-123">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="5730a-124">Etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="5730a-124">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="5730a-125">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="5730a-125">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="5730a-126">Información general sobre las directivas de retención</span><span class="sxs-lookup"><span data-stu-id="5730a-126">Overview of retention policies</span></span>](retention-policies.md)
