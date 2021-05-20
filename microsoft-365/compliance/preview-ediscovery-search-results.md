---
title: Vista previa de los resultados de una búsqueda de eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga una vista previa de un ejemplo de los resultados devueltos por una búsqueda de contenido o una búsqueda de eDiscovery Core en el Centro de cumplimiento de Microsoft 365.
ms.openlocfilehash: a89c8c9ed2500b4e2a859c75be3da177203d1406
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538596"
---
# <a name="preview-ediscovery-search-results"></a><span data-ttu-id="16d94-103">Vista previa de los resultados de búsqueda de eDiscovery</span><span class="sxs-lookup"><span data-stu-id="16d94-103">Preview eDiscovery search results</span></span>

<span data-ttu-id="16d94-104">Después de ejecutar una búsqueda de contenido o una búsqueda asociada a un caso de eDiscovery Core, puede obtener una vista previa de un ejemplo de los resultados devueltos por la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="16d94-104">After you run a Content search or a search associated with a Core eDiscovery case, you can preview a sample of the results returned by the search.</span></span> <span data-ttu-id="16d94-105">La vista previa de elementos devueltos por la consulta de búsqueda puede ayudarle a determinar si la búsqueda devuelve los resultados que espera o si necesita cambiar la consulta de búsqueda y volver a ejecutar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="16d94-105">Previewing items returned by the search query can help you determine if the search is returning the results you hope for or if you need to change the search query and rerun the search.</span></span>

<span data-ttu-id="16d94-106">Para obtener una vista previa de un ejemplo de resultados devuelto por una búsqueda:</span><span class="sxs-lookup"><span data-stu-id="16d94-106">To preview a sample of results returned by a search:</span></span>

1. <span data-ttu-id="16d94-107">En el Centro de cumplimiento de Microsoft 365, vaya a la página Búsqueda de contenido o a un caso de eDiscovery Core.</span><span class="sxs-lookup"><span data-stu-id="16d94-107">In the Microsoft 365 compliance center, go to the Content search page or a Core eDiscovery case.</span></span>

2. <span data-ttu-id="16d94-108">Seleccione la búsqueda para mostrar la página de controles flotantes.</span><span class="sxs-lookup"><span data-stu-id="16d94-108">Select search to display the flyout page.</span></span>

3. <span data-ttu-id="16d94-109">En la parte inferior de la página de controles flotantes, haga clic en **Revisar muestra**.</span><span class="sxs-lookup"><span data-stu-id="16d94-109">On the bottom of the flyout page, click **Review sample**.</span></span>

   ![Haga clic en Revisar muestra en la página de control flotante para previsualizar los resultados](../media/PreviewSearchResults1.png)

   <span data-ttu-id="16d94-111">Se muestra una página que contiene un ejemplo de los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="16d94-111">A page is displayed containing a sample of the search results.</span></span>

4. <span data-ttu-id="16d94-112">Seleccione un elemento para ver su contenido en el panel de lectura.</span><span class="sxs-lookup"><span data-stu-id="16d94-112">Select an item to view its contents in the reading pane.</span></span>

   ![Previsualizar elementos en el panel de lectura](../media/PreviewSearchResults2.png)

   <span data-ttu-id="16d94-114">En el recorte de pantalla anterior, observe que las palabras clave de búsqueda están resaltadas al previsualizar los elementos.</span><span class="sxs-lookup"><span data-stu-id="16d94-114">In the previous screenshot, notice that keywords from the search query are highlighted when you preview items.</span></span>

## <a name="how-the-search-result-samples-are-selected"></a><span data-ttu-id="16d94-115">Cómo se seleccionan las muestras de resultados</span><span class="sxs-lookup"><span data-stu-id="16d94-115">How the search result samples are selected</span></span>

<span data-ttu-id="16d94-116">Hay un máximo de 1 000 elementos seleccionados aleatoriamente disponibles para previsualizar.</span><span class="sxs-lookup"><span data-stu-id="16d94-116">A maximum of 1,000 randomly selected items are available to preview.</span></span> <span data-ttu-id="16d94-117">Además de seleccionarse aleatoriamente, los elementos disponibles para la vista previa deben cumplir los siguientes criterios:</span><span class="sxs-lookup"><span data-stu-id="16d94-117">In addition to being randomly selected, items available for preview must also meet the following criteria:</span></span>

- <span data-ttu-id="16d94-118">Se puede previsualizar un máximo de 100 elementos de una sola ubicación de contenido (un buzón o un sitio).</span><span class="sxs-lookup"><span data-stu-id="16d94-118">A maximum of 100 items from a single content location (a mailbox or a site) can be previewed.</span></span> <span data-ttu-id="16d94-119">Esto significa que es posible que menos de 1 000 elementos estén disponibles para previsualizar.</span><span class="sxs-lookup"><span data-stu-id="16d94-119">This means that it's possible that less than 1,000 items might be available for preview.</span></span> <span data-ttu-id="16d94-120">Por ejemplo, si busca cuatro buzones y la búsqueda obtiene 1 500 elementos estimados, solo 400 estarán disponibles para la vista previa, ya que solo se pueden previsualizar 100 elementos de cada buzón.</span><span class="sxs-lookup"><span data-stu-id="16d94-120">For example, if you search four mailboxes and the search returns 1,500 estimated items, only 400 will be available for preview because only 100 items from each mailbox can be previewed.</span></span>

- <span data-ttu-id="16d94-121">Para los elementos del buzón, solo se pueden previsualizar los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="16d94-121">For mailbox items, only email messages are available to preview.</span></span> <span data-ttu-id="16d94-122">No se pueden previsualizar elementos como tareas, elementos de calendario y contactos.</span><span class="sxs-lookup"><span data-stu-id="16d94-122">Items like tasks, calendar items, and contacts can't be previewed.</span></span>

- <span data-ttu-id="16d94-123">Para los elementos del sitio, solo los documentos están disponibles para previsualizar.</span><span class="sxs-lookup"><span data-stu-id="16d94-123">For site items, only documents are available to preview.</span></span> <span data-ttu-id="16d94-124">No se pueden previsualizar elementos como carpetas, listas o archivos adjuntos de listas.</span><span class="sxs-lookup"><span data-stu-id="16d94-124">Items like folders, lists, or list attachments can't be previewed.</span></span>

## <a name="file-types-supported-when-previewing-search-results"></a><span data-ttu-id="16d94-125">Los tipos de archivos se admiten al obtener una vista previa de los resultados de la búsqueda</span><span class="sxs-lookup"><span data-stu-id="16d94-125">File types supported when previewing search results</span></span>

<span data-ttu-id="16d94-126">Puede obtener una vista previa de los tipos de archivo compatibles en el panel de vista previa.</span><span class="sxs-lookup"><span data-stu-id="16d94-126">You can preview supported file types in the preview pane.</span></span> <span data-ttu-id="16d94-127">Si un tipo de archivo no es compatible, necesitará descargar una copia en el equipo local (haciendo clic en **Descargar artículo original**).</span><span class="sxs-lookup"><span data-stu-id="16d94-127">If a file type isn't supported, you have to download a copy of the file to your local computer (by clicking **Download original item**).</span></span> <span data-ttu-id="16d94-128">Para las páginas web .aspx se incluye la dirección URL de la página, aunque es posible que no tenga permiso para acceder a ella.</span><span class="sxs-lookup"><span data-stu-id="16d94-128">For .aspx Web pages, the URL for the page is included though you may not have permissions to access the page.</span></span> <span data-ttu-id="16d94-129">No se puede obtener una vista previa de los elementos sin indexar.</span><span class="sxs-lookup"><span data-stu-id="16d94-129">Unindexed items aren't available for previewing.</span></span>

<span data-ttu-id="16d94-130">Se admiten los siguientes tipos de archivo y se puede obtener una vista previa en el panel Resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="16d94-130">The following file types are supported and can be previewed in the search results pane.</span></span>
  
- <span data-ttu-id="16d94-131">.txt, .html, .mhtml</span><span class="sxs-lookup"><span data-stu-id="16d94-131">.txt, .html, .mhtml</span></span>

- <span data-ttu-id="16d94-132">.eml</span><span class="sxs-lookup"><span data-stu-id="16d94-132">.eml</span></span>

- <span data-ttu-id="16d94-133">.doc, .docx, .docm</span><span class="sxs-lookup"><span data-stu-id="16d94-133">.doc, .docx, .docm</span></span>

- <span data-ttu-id="16d94-134">.pptm, .pptx</span><span class="sxs-lookup"><span data-stu-id="16d94-134">.pptm, .pptx</span></span>

- <span data-ttu-id="16d94-135">.pdf</span><span class="sxs-lookup"><span data-stu-id="16d94-135">.pdf</span></span>

<span data-ttu-id="16d94-136">Asimismo, se admiten los siguientes tipos de contenedor de archivo.</span><span class="sxs-lookup"><span data-stu-id="16d94-136">Also, the following file container types are supported.</span></span> <span data-ttu-id="16d94-137">Puede ver la lista de archivos del contenedor en el panel de vista previa.</span><span class="sxs-lookup"><span data-stu-id="16d94-137">You can view the list of files in the container in the preview pane.</span></span>
  
- <span data-ttu-id="16d94-138">.zip</span><span class="sxs-lookup"><span data-stu-id="16d94-138">.zip</span></span>

- <span data-ttu-id="16d94-139">.gzip</span><span class="sxs-lookup"><span data-stu-id="16d94-139">.gzip</span></span>