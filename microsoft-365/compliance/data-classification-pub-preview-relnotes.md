---
title: Notas de la versión de clasificación de datos
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
description: Notas de la versión para clasificación de datos.
ms.openlocfilehash: 71d8e8e4fffddc4c9373a2bdd37d4509337ec231
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127145"
---
# <a name="data-classification-release-notes"></a><span data-ttu-id="ebea3-103">Notas de la versión de clasificación de datos</span><span class="sxs-lookup"><span data-stu-id="ebea3-103">Data classification release notes</span></span>

<span data-ttu-id="ebea3-104">Por favor, revise las notas de la versión para tener una mejor experiencia con la clasificación de datos.</span><span class="sxs-lookup"><span data-stu-id="ebea3-104">Please review these release notes so that you have the best experience with data classification.</span></span>

## <a name="exchange-mailbox-count"></a><span data-ttu-id="ebea3-105">Buzón de correo de Exchange</span><span class="sxs-lookup"><span data-stu-id="ebea3-105">Exchange mailbox count</span></span>

<span data-ttu-id="ebea3-106">Notará la aparición de información breve sobre herramientas cuando explore en los buzones de correo de Exchange.</span><span class="sxs-lookup"><span data-stu-id="ebea3-106">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="ebea3-107">Esto sirve para llamar la atención sobre el hecho de que el recuento total mostrado sobre el tipo de información confidencial, etiquetas de confidencialidad y retención puede no coincidir exactamente con el número de elementos que se encuentran en el interior del buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="ebea3-107">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="ebea3-108">Esto se debe a la exploración en profundo de la carpeta para obtener la vista en vivo del contenido, que es clasificado, mientras se calcula el conteo agregado.</span><span class="sxs-lookup"><span data-stu-id="ebea3-108">This is because the drill down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>


## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="ebea3-109">Representación de documentos codificados</span><span class="sxs-lookup"><span data-stu-id="ebea3-109">Rendering of encrypted documents</span></span>

<span data-ttu-id="ebea3-110">Los archivos cifrados de SharePoint, Exchange y OneDrive no serán representados en el explorador de contenido.</span><span class="sxs-lookup"><span data-stu-id="ebea3-110">SharePoint, Exchange, and OneDrive files that are encrypted will not render in the content explorer.</span></span> <span data-ttu-id="ebea3-111">Este es un problema de confidencialidad que requiere de un equilibrio entre la necesidad de ver el contenido del archivo en el explorador de contenido y la necesidad de mantener el contenido cifrado.</span><span class="sxs-lookup"><span data-stu-id="ebea3-111">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="ebea3-112">Con los permisos concedidos por los grupos de roles del **visor de listas del explorador de contenido** y el **visor del explorador de contenido**, obtendrá una vista de la lista de los archivos, los metadatos y un vínculo que puede usar para obtener acceso al contenido a través del cliente web.</span><span class="sxs-lookup"><span data-stu-id="ebea3-112">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="ebea3-113">Caracteres admitidos en los nombres de las etiquetas de retención en la búsqueda de SharePoint</span><span class="sxs-lookup"><span data-stu-id="ebea3-113">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="ebea3-114">La búsqueda de SharePoint no admite nombres de etiquetas de retención con `-`, o `_`en ellos.</span><span class="sxs-lookup"><span data-stu-id="ebea3-114">SharePoint search does not support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="ebea3-115">Por ejemplo `Label-MIP` y `Label_MIP` no son admitidos.</span><span class="sxs-lookup"><span data-stu-id="ebea3-115">For example `Label-MIP` and `Label_MIP` are not supported.</span></span> <span data-ttu-id="ebea3-116">La búsqueda en SharePoint admite el uso de esos caracteres en los nombres de las etiquetas de confidencialidad y en los nombres de los tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="ebea3-116">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="onedrive-remains-in-preview"></a><span data-ttu-id="ebea3-117">OneDrive permanece en versión preliminar</span><span class="sxs-lookup"><span data-stu-id="ebea3-117">OneDrive remains in preview</span></span>

<span data-ttu-id="ebea3-118">Hemos escuchado sus valiosos comentarios sobre la integración de OneDrive durante el programa de versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="ebea3-118">We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="ebea3-119">Mientras trabajamos en las especificaciones, es posible que se puedan producir datos/flujos incoherentes.</span><span class="sxs-lookup"><span data-stu-id="ebea3-119">As we work through the specifics, you may run into inconsistent data / flows.</span></span> <span data-ttu-id="ebea3-120">Seguiremos mostrando OneDrive en la versión preliminar hasta que todas las correcciones estén en su sitio.</span><span class="sxs-lookup"><span data-stu-id="ebea3-120">We will continue to showcase OneDrive in preview till all fixes are in place.</span></span> <span data-ttu-id="ebea3-121">Agradecemos su continuado soporte en este aspecto.</span><span class="sxs-lookup"><span data-stu-id="ebea3-121">We appreciate your continued support on this.</span></span>


## <a name="see-also"></a><span data-ttu-id="ebea3-122">Ver también</span><span class="sxs-lookup"><span data-stu-id="ebea3-122">See also</span></span>

- [<span data-ttu-id="ebea3-123">Introducción a la clasificación de datos (vista previa)</span><span class="sxs-lookup"><span data-stu-id="ebea3-123">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="ebea3-124">Ver actividad de la etiqueta (vista previa)</span><span class="sxs-lookup"><span data-stu-id="ebea3-124">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="ebea3-125">Ver contenido etiquetado (vista previa)</span><span class="sxs-lookup"><span data-stu-id="ebea3-125">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="ebea3-126">Información sobre las etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="ebea3-126">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="ebea3-127">Obtenga más información sobre las directivas de retención y las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="ebea3-127">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="ebea3-128">Definiciones de entidad de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="ebea3-128">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)