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
ms.openlocfilehash: 2b9302cfa49f9445d3cbeb5109aef70e0c8d8f7f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663045"
---
# <a name="data-classification-release-notes"></a><span data-ttu-id="df5e8-103">Notas de la versión de clasificación de datos</span><span class="sxs-lookup"><span data-stu-id="df5e8-103">Data classification release notes</span></span>


## <a name="exchange-mailbox-count"></a><span data-ttu-id="df5e8-104">Buzón de correo de Exchange</span><span class="sxs-lookup"><span data-stu-id="df5e8-104">Exchange mailbox count</span></span>

<span data-ttu-id="df5e8-105">Notará la aparición de información breve sobre herramientas cuando explore en los buzones de correo de Exchange.</span><span class="sxs-lookup"><span data-stu-id="df5e8-105">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="df5e8-106">Esto sirve para llamar la atención sobre el hecho de que el recuento total mostrado sobre el tipo de información confidencial, etiquetas de confidencialidad y retención puede no coincidir exactamente con el número de elementos que se encuentran en el interior del buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="df5e8-106">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="df5e8-107">Esto se debe a la exploración en profundo de la carpeta para obtener la vista en vivo del contenido, que es clasificado, mientras se calcula el recuento agregado.</span><span class="sxs-lookup"><span data-stu-id="df5e8-107">This is because the drill-down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>


## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="df5e8-108">Representación de documentos cifrados</span><span class="sxs-lookup"><span data-stu-id="df5e8-108">Rendering of encrypted documents</span></span>

<span data-ttu-id="df5e8-109">Los archivos cifrados de SharePoint, Exchange y OneDrive no se representan en el explorador de contenido.</span><span class="sxs-lookup"><span data-stu-id="df5e8-109">SharePoint, Exchange, and OneDrive files that are encrypted don't render in the content explorer.</span></span> <span data-ttu-id="df5e8-110">Este es un problema de confidencialidad que requiere de un equilibrio entre la necesidad de ver el contenido del archivo en el explorador de contenido y la necesidad de mantener el contenido cifrado.</span><span class="sxs-lookup"><span data-stu-id="df5e8-110">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="df5e8-111">Con los permisos concedidos por los grupos de roles del **visor de listas del explorador de contenido** y el **visor del explorador de contenido**, obtendrá una vista de la lista de los archivos, los metadatos y un vínculo que puede usar para obtener acceso al contenido a través del cliente web.</span><span class="sxs-lookup"><span data-stu-id="df5e8-111">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="df5e8-112">Caracteres admitidos en los nombres de las etiquetas de retención en la búsqueda de SharePoint</span><span class="sxs-lookup"><span data-stu-id="df5e8-112">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="df5e8-113">La búsqueda de SharePoint no admite nombres de etiquetas de retención con `-` o `_` en ellos.</span><span class="sxs-lookup"><span data-stu-id="df5e8-113">SharePoint search doesn't support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="df5e8-114">Por ejemplo, `Label-MIP` y `Label_MIP` no son admitidos.</span><span class="sxs-lookup"><span data-stu-id="df5e8-114">For example, `Label-MIP` and `Label_MIP` aren't supported.</span></span> <span data-ttu-id="df5e8-115">La búsqueda en SharePoint admite el uso de esos caracteres en los nombres de las etiquetas de confidencialidad y en los nombres de los tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="df5e8-115">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="onedrive-remains-in-preview"></a><span data-ttu-id="df5e8-116">OneDrive permanece en versión preliminar</span><span class="sxs-lookup"><span data-stu-id="df5e8-116">OneDrive remains in preview</span></span>

<span data-ttu-id="df5e8-117">Agradecemos sus valiosos comentarios sobre la integración de OneDrive durante el programa de versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="df5e8-117">Thanks for your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="df5e8-118">Mientras trabajamos en las especificaciones, es posible que se puedan producir datos/flujos incoherentes.</span><span class="sxs-lookup"><span data-stu-id="df5e8-118">As we work through the specifics, you may run into inconsistent data / flows.</span></span> <span data-ttu-id="df5e8-119">Seguiremos mostrando OneDrive en la versión preliminar hasta que todas las correcciones estén en su sitio.</span><span class="sxs-lookup"><span data-stu-id="df5e8-119">We'll continue to showcase OneDrive in preview until all fixes are in place.</span></span> <span data-ttu-id="df5e8-120">Agradecemos su apoyo continuo.</span><span class="sxs-lookup"><span data-stu-id="df5e8-120">We appreciate your continued support.</span></span>


## <a name="see-also"></a><span data-ttu-id="df5e8-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="df5e8-121">See also</span></span>

- [<span data-ttu-id="df5e8-122">Introducción a la clasificación de datos (vista previa)</span><span class="sxs-lookup"><span data-stu-id="df5e8-122">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="df5e8-123">Ver actividad de la etiqueta (vista previa)</span><span class="sxs-lookup"><span data-stu-id="df5e8-123">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="df5e8-124">Ver contenido etiquetado (vista previa)</span><span class="sxs-lookup"><span data-stu-id="df5e8-124">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="df5e8-125">Información sobre las etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="df5e8-125">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="df5e8-126">Más información sobre las directivas y las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="df5e8-126">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="df5e8-127">Definiciones de entidad de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="df5e8-127">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)