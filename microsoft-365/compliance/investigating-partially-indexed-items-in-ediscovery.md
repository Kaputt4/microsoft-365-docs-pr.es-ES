---
title: Investigación de elementos parcialmente indizados en eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo administrar elementos parcialmente indizados (o desindizados) de Exchange, SharePoint y OneDrive para la empresa en su organización.
ms.openlocfilehash: 94dc568aa889e76241ef7bd48e3dedaba9b92f2f
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602067"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a><span data-ttu-id="2d0f3-103">Investigación de elementos parcialmente indizados en eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2d0f3-103">Investigating partially indexed items in eDiscovery</span></span>

<span data-ttu-id="2d0f3-104">Una búsqueda de exhibición de documentos electrónicos que se ejecuta desde el centro de cumplimiento de Microsoft 365 incluye automáticamente elementos parcialmente indizados en los resultados de búsqueda estimados al ejecutar una búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-104">An eDiscovery search that you run from the Microsoft 365 compliance center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="2d0f3-105">Los elementos indexados parcialmente son elementos de buzones de Exchange y documentos de sitios de SharePoint y OneDrive para la empresa que, por algún motivo, no se han indizado completamente para la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-105">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="2d0f3-106">La mayoría de los mensajes de correo electrónico y documentos de sitio se indizan correctamente porque entran dentro de los [límites de indización de los mensajes de correo electrónico](limits-for-content-search.md#indexing-limits-for-email-messages).</span><span class="sxs-lookup"><span data-stu-id="2d0f3-106">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="2d0f3-107">Sin embargo, algunos elementos pueden superar estos límites de indización y se indizarán parcialmente.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-107">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="2d0f3-108">Estas son otras razones por las que los elementos no se pueden indizar para la búsqueda y se devuelven como elementos parcialmente indizados al ejecutar una búsqueda de exhibición de documentos electrónicos:</span><span class="sxs-lookup"><span data-stu-id="2d0f3-108">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run an eDiscovery search:</span></span>
  
- <span data-ttu-id="2d0f3-109">Los mensajes de correo electrónico tienen un archivo adjunto sin un controlador válido, como archivos de imagen; Esta es la causa más común de los elementos de correo electrónico parcialmente indizados.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-109">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items.</span></span>

- <span data-ttu-id="2d0f3-110">Se han adjuntado demasiados archivos a un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-110">Too many files attached to an email message.</span></span>

- <span data-ttu-id="2d0f3-111">Un archivo adjuntado a un mensaje de correo electrónico es demasiado grande.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-111">A file attached to an email message is too large.</span></span>

- <span data-ttu-id="2d0f3-112">El tipo de archivo se admite para indización pero se produjo un error de indización en un archivo específico.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-112">The file type is supported for indexing but an indexing error occurred for a specific file.</span></span>

<span data-ttu-id="2d0f3-113">Aunque varía, la mayoría de los clientes de organizaciones tienen menos del 1% de contenido en volumen y menos del 12% de contenido en el tamaño que se indexa parcialmente.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-113">Although it varies, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="2d0f3-114">El motivo de la diferencia entre el volumen y el tamaño es que los archivos más grandes tienen una probabilidad mayor de contenido que no se puede indizar completamente.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-114">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="2d0f3-115">¿Por qué cambia el número de elementos parcialmente indizados para una búsqueda?</span><span class="sxs-lookup"><span data-stu-id="2d0f3-115">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="2d0f3-116">Después de ejecutar una búsqueda de exhibición de documentos electrónicos, el número total y el tamaño de los elementos parcialmente indizados en las ubicaciones en las que se realizó la búsqueda se muestran en las estadísticas de resultados de búsqueda que se muestran en las estadísticas detalladas de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-116">After you run an eDiscovery search, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="2d0f3-117">Nota Estos se denominan  *elementos sin indexar*  en las estadísticas de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-117">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="2d0f3-118">Estas son algunas de las cosas que afectarán al número de elementos parcialmente indizados que se devuelven en los resultados de la búsqueda:</span><span class="sxs-lookup"><span data-stu-id="2d0f3-118">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span>
  
- <span data-ttu-id="2d0f3-119">Si un elemento se indiza parcialmente y coincide con la consulta de búsqueda, se incluye tanto en el recuento como en el tamaño de los elementos de resultados de búsqueda y en los elementos parcialmente indizados.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-119">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="2d0f3-120">Sin embargo, cuando se exportan los resultados de esa misma búsqueda, el elemento solo se incluye con un conjunto de resultados de búsqueda; no se incluye como elemento parcialmente indizado.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-120">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>

- <span data-ttu-id="2d0f3-121">Si especifica un intervalo de fechas para una consulta de búsqueda (al incluirla en la consulta de palabras clave o mediante una condición), los elementos parcialmente indizados que no coinciden con el intervalo de fechas no se incluyen en el recuento de elementos parcialmente indizados.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-121">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items.</span></span> <span data-ttu-id="2d0f3-122">Solo los elementos parcialmente indizados que se encuentran en el intervalo de fechas se incluyen en el recuento de elementos indizados.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-122">Only the partially indexed items that fall within date range are included in the count of indexed items.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2d0f3-123">Los elementos parcialmente indizados ubicados en los sitios de SharePoint y OneDrive *no se* incluyen en la estimación de los elementos parcialmente indizados que se muestran en las estadísticas detalladas de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-123">Partially indexed items located in SharePoint and OneDrive sites *are not* included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="2d0f3-124">Sin embargo, los elementos parcialmente indizados se pueden exportar al exportar los resultados de una búsqueda de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-124">However, partially indexed items can be exported when you export the results of an eDiscovery search.</span></span> <span data-ttu-id="2d0f3-125">Por ejemplo, si solo busca sitios, el número estimado de elementos parcialmente indizados será cero.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-125">For example, if you only search sites, the estimated number partially indexed items will be zero.</span></span>
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="2d0f3-126">Cálculo de la proporción de elementos parcialmente indizados en la organización</span><span class="sxs-lookup"><span data-stu-id="2d0f3-126">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="2d0f3-127">Para comprender la exposición de la organización a los elementos parcialmente indizados, puede ejecutar una búsqueda de todo el contenido de todos los buzones (mediante una consulta de palabras clave en blanco).</span><span class="sxs-lookup"><span data-stu-id="2d0f3-127">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="2d0f3-128">En el siguiente ejemplo, hay 56.208 (4.830 MB) de elementos completamente indizados y 470 (316 MB) de elementos parcialmente indizados.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-128">In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![Ejemplo de estadísticas de búsqueda que muestran elementos parcialmente indizados](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="2d0f3-130">Puede determinar el porcentaje de elementos parcialmente indizados mediante los siguientes cálculos.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-130">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="2d0f3-131">**Para calcular la proporción de elementos parcialmente indizados en la organización:**</span><span class="sxs-lookup"><span data-stu-id="2d0f3-131">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`

`(470/56,208) x 100 = 0.84%`

<span data-ttu-id="2d0f3-132">Mediante el uso de los resultados de la búsqueda del ejemplo anterior, el 84% de todos los elementos de los buzones se indiza parcialmente.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-132">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="2d0f3-133">**Para calcular el porcentaje del tamaño de los elementos parcialmente indizados de la organización:**</span><span class="sxs-lookup"><span data-stu-id="2d0f3-133">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="2d0f3-134">Por lo tanto, en el ejemplo anterior, 6,54% del tamaño total de los elementos del buzón de correo son de elementos parcialmente indizados.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-134">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="2d0f3-135">Como se mencionó anteriormente, la mayoría de las organizaciones tienen menos del 1% de contenido en volumen y menos del 12% de contenido en el tamaño que se indexa parcialmente.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-135">As previously stated, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="2d0f3-136">Trabajar con elementos parcialmente indizados</span><span class="sxs-lookup"><span data-stu-id="2d0f3-136">Working with partially indexed items</span></span>

<span data-ttu-id="2d0f3-137">En los casos en los que necesite examinar elementos parciales para validar que no contienen información relevante, puede [exportar un informe de búsqueda de contenido](export-a-content-search-report.md) que contenga información sobre los elementos parcialmente indizados.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-137">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="2d0f3-138">Cuando exporte un informe de búsqueda de contenido, asegúrese de elegir una de las opciones de exportación que incluya elementos parcialmente indizados.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-138">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span>
  
![Elija la segunda o la tercera opción para exportar elementos parcialmente indizados](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="2d0f3-140">Cuando se exportan resultados de la búsqueda de eDiscovery o un informe de búsqueda mediante una de estas opciones, la exportación incluye un informe denominado Items.csv no indizado.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-140">When you export eDiscovery search results or a search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="2d0f3-141">Este informe incluye la mayor parte de la información que el archivo de ResultsLog.csv; sin embargo, el archivo Items.csv no indizado también incluye dos campos relacionados con elementos parcialmente indizados: **etiquetas de error** y **propiedades de error**.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-141">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="2d0f3-142">Estos campos contienen información sobre el error de indización para cada elemento parcialmente indizado.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-142">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="2d0f3-143">El uso de la información de estos dos campos puede ayudarle a determinar si el error de indización de un determinado impacto en la investigación.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-143">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="2d0f3-144">Si es así, puede realizar una búsqueda dirigida y recuperar y exportar mensajes de correo electrónico específicos y documentos de SharePoint o de OneDrive para poder examinarlos y determinar si son relevantes para la investigación.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-144">If it does, you can perform a targeted search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="2d0f3-145">Para obtener instrucciones paso a paso, vea [preparar un archivo CSV para una búsqueda dirigida en Office 365](csv-file-for-an-id-list-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="2d0f3-145">For step-by-step instructions, see [Prepare a CSV file for a targeted search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2d0f3-146">El archivo Items.csv no indizado también contiene campos denominados **tipo de error** y **mensaje de error**.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-146">The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="2d0f3-147">Estos son campos heredados que contienen información similar a la información de los campos de **propiedades** de error y **etiquetas de error** , pero con información menos detallada.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-147">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="2d0f3-148">Puede omitir estos campos heredados sin problemas.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-148">You can safely ignore these legacy fields.</span></span>
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="2d0f3-149">Errores relacionados con elementos parcialmente indizados</span><span class="sxs-lookup"><span data-stu-id="2d0f3-149">Errors related to partially indexed items</span></span>

<span data-ttu-id="2d0f3-150">Las etiquetas de error constan de dos fragmentos de información, el error y el tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-150">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="2d0f3-151">Por ejemplo, en este par error/tipo de archivo:</span><span class="sxs-lookup"><span data-stu-id="2d0f3-151">For example, in this error/file-type pair:</span></span>

```text
 parseroutputsize_xls
```

 <span data-ttu-id="2d0f3-152">`parseroutputsize` es el error y `xls` es el tipo de archivo del archivo en el que se produjo el error.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-152">`parseroutputsize` is the error and `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="2d0f3-153">En los casos en que no se haya reconocido el tipo de archivo o no se haya aplicado el tipo de archivo al error, verá el valor `noformat` en lugar del tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-153">In cases where the file type wasn't recognized or the file type didn't apply to the error, you will see the value `noformat` in place of the file type.</span></span>
  
<span data-ttu-id="2d0f3-154">A continuación se muestra una lista de errores de indización y una descripción de la posible causa del error.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-154">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
| <span data-ttu-id="2d0f3-155">Etiqueta error</span><span class="sxs-lookup"><span data-stu-id="2d0f3-155">Error tag</span></span> | <span data-ttu-id="2d0f3-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d0f3-156">Description</span></span> |
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="2d0f3-157">Un mensaje de correo electrónico tenía demasiados datos adjuntos y algunos de estos datos adjuntos no se procesaron.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-157">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="2d0f3-158">El analizador de contenido y el analizador de documentos encontraron demasiados niveles de datos adjuntos anidados dentro de otros datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-158">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="2d0f3-159">Algunos de estos datos adjuntos no se procesaron.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-159">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="2d0f3-160">Un archivo adjunto produjo un error al descodificar porque estaba protegido con RMS.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-160">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="2d0f3-161">Un archivo adjunto a un mensaje de correo electrónico era demasiado grande y no se pudo procesar.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-161">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="2d0f3-162">Al escribir el mensaje de correo electrónico procesado en el índice, una de las propiedades indizables es demasiado grande y se ha truncado.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-162">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="2d0f3-163">Las propiedades truncadas se muestran en el campo propiedades de error.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-163">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="2d0f3-164">Un mensaje de correo electrónico contenía texto que no se pudo procesar como Unicode válido.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-164">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="2d0f3-165">La indización para este elemento puede estar incompleta.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-165">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="2d0f3-166">El contenido de los datos adjuntos o del mensaje de correo electrónico se cifra y Microsoft 365 no pudo descodificar el contenido.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-166">The content of attachment or email message is encrypted, and Microsoft 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="2d0f3-167">Se ha producido un error desconocido durante el análisis.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-167">An unknown error occurred during parsing.</span></span> <span data-ttu-id="2d0f3-168">Esto suele deberse a un error de software o a un bloqueo del servicio.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-168">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="2d0f3-169">Los datos adjuntos son demasiado grandes para que el analizador los controle y el análisis de los datos adjuntos no se ha realizado o no se ha completado.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-169">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="2d0f3-170">Un archivo adjunto tenía un formato incorrecto y el analizador no pudo administrarlo.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-170">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="2d0f3-171">Este resultado puede deberse a formatos de archivo antiguos, a archivos creados por software incompatible o a virus que pretenden ser algo que no sea reclamar.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-171">This result can be due to old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="2d0f3-172">El resultado del análisis de datos adjuntos era demasiado grande y tuvo que truncarse.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-172">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="2d0f3-173">Los datos adjuntos tenían un tipo de archivo que Microsoft 365 no pudo detectar.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-173">An attachment had a file type that Microsoft 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="2d0f3-174">Los datos adjuntos tenían un tipo de archivo que Office 365 podría detectar, pero el análisis de ese tipo de archivo no es compatible.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-174">An attachment had a file type that Office 365 could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="2d0f3-175">El valor de una propiedad de correo electrónico en el almacén de Exchange era demasiado grande para recuperarse y no se pudo procesar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-175">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="2d0f3-176">Normalmente, esto sólo ocurre con la propiedad Body de un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-176">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="2d0f3-177">El recuperador de contenido no pudo descodificar un mensaje protegido con RMS.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-177">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="2d0f3-178">Se identificaron demasiadas palabras en el documento durante la indización.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-178">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="2d0f3-179">El procesamiento de la propiedad se detuvo al alcanzar el límite y la propiedad se trunca.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-179">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |

<span data-ttu-id="2d0f3-180">Los campos de error describen qué campos se ven afectados por el error de procesamiento que aparece en el campo etiquetas de error.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-180">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="2d0f3-181">Si está buscando una propiedad como  `subject` o, los  `participants` errores en el cuerpo del mensaje no afectarán a los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-181">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="2d0f3-182">Esto puede ser útil para determinar exactamente qué elementos parcialmente indizados podría necesitar investigar.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-182">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="2d0f3-183">Uso de un script de PowerShell para determinar la exposición de la organización a elementos de correo electrónico parcialmente indizados</span><span class="sxs-lookup"><span data-stu-id="2d0f3-183">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="2d0f3-184">Los pasos siguientes muestran cómo ejecutar un script de PowerShell que busca todos los elementos de todos los buzones de Exchange y, a continuación, genera un informe sobre la relación de la organización con los elementos de correo electrónico parcialmente indizados (por número y por tamaño) y muestra el número de elementos (y su tipo de archivo) para cada error de indización que se produce.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-184">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="2d0f3-185">Use las descripciones de las etiquetas de error de la sección anterior para identificar el error de indización.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-185">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="2d0f3-186">Guarde el siguiente texto en un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de. ps1; por ejemplo, `PartiallyIndexedItems.ps1` .</span><span class="sxs-lookup"><span data-stu-id="2d0f3-186">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

   ```powershell
     write-host "**************************************************"
     write-host "     Security & Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
     write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
     write-host "**************************************************"
     " " 
     # Create a search with Error Tags Refinders enabled
     Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
     New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
     Start-ComplianceSearch "RefinerTest"
     # Loop while search is in progress
     do{
         Write-host "Waiting for search to complete..."
         Start-Sleep -s 5
         $complianceSearch = Get-ComplianceSearch "RefinerTest"
     }while ($complianceSearch.Status -ne 'Completed')
     $refiners = $complianceSearch.Refiners | ConvertFrom-Json
     $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
     $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
     $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
     " "
     "===== Partially indexed items ====="
     "         Total          Ratio"
     "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
     "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
     " "
     Write-Host ===== Reasons for partially indexed items =====
     foreach($errorTagProperty in $errorTagProperties)
     {
         $name = $refiners.Entries.($errorTagProperty.Name).Name
         $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
         $frag = $name.Split("{_}")
         $errorTag = $frag[0]
         $fileType = $frag[1]
         if ($errorTag -ne $lastErrorTag)
         {
             $errorTag
         }
         "    " + $fileType + " => " + $count
         $lastErrorTag = $errorTag
     }
   ```

2. <span data-ttu-id="2d0f3-187">[Conectarse al Centro de seguridad y cumplimiento PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span><span class="sxs-lookup"><span data-stu-id="2d0f3-187">[Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span></span>

3. <span data-ttu-id="2d0f3-188">En el PowerShell del centro de cumplimiento de & de seguridad, vaya a la carpeta en la que guardó el script en el paso 1 y, a continuación, ejecute el script. por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2d0f3-188">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

   ```powershell
   .\PartiallyIndexedItems.ps1
   ```

<span data-ttu-id="2d0f3-189">Este es un ejemplo del resultado que devuelve el script.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-189">Here's an example fo the output returned by the script.</span></span>
  
![Ejemplo de salida de script que genera un informe sobre la exposición de su organización a elementos de correo electrónico parcialmente indizados](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)

> [!NOTE]
> <span data-ttu-id="2d0f3-191">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d0f3-191">Note the following:</span></span>
>  
> - <span data-ttu-id="2d0f3-192">El número total y el tamaño de los elementos de correo electrónico, y la relación de los elementos de correo electrónico parcialmente indizados (por número y por tamaño).</span><span class="sxs-lookup"><span data-stu-id="2d0f3-192">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size).</span></span>
> 
> - <span data-ttu-id="2d0f3-193">Una lista de etiquetas de error y los tipos de archivo correspondientes en los que se produjo el error.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-193">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2d0f3-194">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2d0f3-194">See also</span></span>

[<span data-ttu-id="2d0f3-195">Elementos parcialmente indizados en eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2d0f3-195">Partially indexed items in eDiscovery</span></span>](partially-indexed-items-in-content-search.md)
