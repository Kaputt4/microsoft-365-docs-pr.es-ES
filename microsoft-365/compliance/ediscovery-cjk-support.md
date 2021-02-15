---
title: Compatibilidad con CJK/Doble byte para eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo eDiscovery avanzado en Microsoft 365 admite los idiomas chino, japonés y coreano (CJK), que usan un juego de caracteres de doble byte.
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626944"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="a6a19-103">Compatibilidad con lenguaje CJK para eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="a6a19-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="a6a19-104">EDiscovery avanzado admite idiomas de juego de caracteres de doble byte (incluidos chino simplificado, chino tradicional, japonés y coreano, que se conocen colectivamente como *idiomas CJK)* para los siguientes escenarios avanzados en un conjunto de revisión:</span><span class="sxs-lookup"><span data-stu-id="a6a19-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="a6a19-105">Cuando se [consultan los datos de un conjunto de revisión.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="a6a19-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="a6a19-106">Al [etiquetar documentos en un conjunto de revisión.](tagging-documents.md)</span><span class="sxs-lookup"><span data-stu-id="a6a19-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="a6a19-107">Al analizar [los datos de casos en un conjunto de revisión](analyzing-data-in-review-set.md) mediante detección casi duplicada, subprocesos de correo electrónico y análisis de temas.</span><span class="sxs-lookup"><span data-stu-id="a6a19-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="a6a19-108">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="a6a19-108">Frequently asked questions</span></span>

<span data-ttu-id="a6a19-109">**¿Cómo puedo crear una búsqueda para recopilar elementos que contengan caracteres CJK?**</span><span class="sxs-lookup"><span data-stu-id="a6a19-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="a6a19-110">Puede usar caracteres CJK para [búsquedas](building-search-queries.md#keyword-searches)de palabras clave, consultas de palabras [clave](keyword-queries-and-search-conditions.md) y condiciones de búsqueda al buscar contenido en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="a6a19-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="a6a19-111">También se admite la búsqueda de caracteres CJK al buscar contenido en la exhibición de documentos electrónicos principal y la búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="a6a19-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="a6a19-112">Proporcionamos compatibilidad con CJK para todos [los](keyword-queries-and-search-conditions.md#search-operators) operadores de búsqueda y condiciones de [búsqueda,](keyword-queries-and-search-conditions.md#search-conditions)incluidos los operadores booleanos **AND**, **OR**, **NOT** y **NEAR**.</span><span class="sxs-lookup"><span data-stu-id="a6a19-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="a6a19-113">Si está seguro de que las ubicaciones de contenido o los elementos contienen caracteres CJK, pero las búsquedas no devuelven ningún resultado, haga clic en el icono de idioma de consulta, país o región.</span><span class="sxs-lookup"><span data-stu-id="a6a19-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![Icono de idioma-país/región de consulta en la búsqueda de contenido](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="a6a19-115">y seleccione el valor de código de referencia cultural idioma-país correspondiente para la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a6a19-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="a6a19-116">Por defecto, la versión del idioma/región es la neutra.</span><span class="sxs-lookup"><span data-stu-id="a6a19-116">The default language/region is neutral.</span></span>

<span data-ttu-id="a6a19-117">**¿Puedo buscar varios idiomas a la vez?**</span><span class="sxs-lookup"><span data-stu-id="a6a19-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="a6a19-118">Depende del escenario de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a6a19-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="a6a19-119">Cuando consulta [datos en un conjunto de revisión](review-set-search.md) de eDiscovery avanzado, puede buscar varios idiomas.</span><span class="sxs-lookup"><span data-stu-id="a6a19-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="a6a19-120">Cuando cree [una búsqueda para recopilar datos,](create-search-to-collect-data.md)cree una búsqueda independiente para cada idioma de destino.</span><span class="sxs-lookup"><span data-stu-id="a6a19-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="a6a19-121">Por ejemplo, si busca un documento que contenga chino y coreano, seleccione chino para la primera consulta y coreano para la segunda consulta.</span><span class="sxs-lookup"><span data-stu-id="a6a19-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="a6a19-122">**No veo el icono de idioma de consulta, país o región para seleccionar un idioma para las consultas de un conjunto de revisión. ¿Cómo puedo especificar un idioma de consulta en una búsqueda de conjunto de revisión?**</span><span class="sxs-lookup"><span data-stu-id="a6a19-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="a6a19-123">Para las consultas de conjunto de revisión, no es necesario especificar un idioma del documento.</span><span class="sxs-lookup"><span data-stu-id="a6a19-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="a6a19-124">EDiscovery avanzado detecta automáticamente los idiomas de los documentos cuando agrega contenido a un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="a6a19-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="a6a19-125">Esto le ayuda a optimizar los resultados de la consulta en un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="a6a19-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="a6a19-126">**¿Puedo ver los idiomas detectados en los [metadatos de archivo?](view-documents-in-review-set.md#file-metadata)**</span><span class="sxs-lookup"><span data-stu-id="a6a19-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="a6a19-127">No, no puede ver los idiomas detectados en los metadatos de archivo.</span><span class="sxs-lookup"><span data-stu-id="a6a19-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="a6a19-128">**¿Puedo filtrar por idiomas de documento en un conjunto de revisión?**</span><span class="sxs-lookup"><span data-stu-id="a6a19-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="a6a19-129">No, no puede filtrar, ordenar ni buscar por idiomas de documento en un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="a6a19-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="a6a19-130">**¿Esta versión CJK para escenarios de conjunto de revisión afectará a cualquiera de mis búsquedas y conjuntos de revisión existentes?**</span><span class="sxs-lookup"><span data-stu-id="a6a19-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="a6a19-131">No, ninguna de las búsquedas y conjuntos de revisión existentes cambiará.</span><span class="sxs-lookup"><span data-stu-id="a6a19-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="a6a19-132">No es necesario volver a indexar los datos existentes y los resultados de la búsqueda para el texto en inglés serán los mismos.</span><span class="sxs-lookup"><span data-stu-id="a6a19-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="a6a19-133">**¿Cómo puedo cambiar el idioma para mostrar a chino, japonés o coreano?**</span><span class="sxs-lookup"><span data-stu-id="a6a19-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="a6a19-134">Para obtener información sobre cómo cambiar el idioma de visualización y la zona horaria, vea Cómo establecer la configuración de idioma y [región para Office 365.](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region)</span><span class="sxs-lookup"><span data-stu-id="a6a19-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="a6a19-135">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="a6a19-135">Known issues</span></span>

- <span data-ttu-id="a6a19-136">OCR no admite caracteres CJK de archivos de imagen</span><span class="sxs-lookup"><span data-stu-id="a6a19-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="a6a19-137">Los archivos de correo electrónico (como \*.eml y \*.msg) en la vista Anotación no son compatibles con los idiomas CJK. [](view-documents-in-review-set.md#annotate-view)</span><span class="sxs-lookup"><span data-stu-id="a6a19-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="a6a19-138">El resaltado de resultados de búsqueda en [la](view-documents-in-review-set.md#text-view) vista Texto no es compatible con los idiomas CJK.</span><span class="sxs-lookup"><span data-stu-id="a6a19-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="a6a19-139">El [módulo Relevancia](using-relevance.md) usado para analizar datos no admite lenguajes CJK.</span><span class="sxs-lookup"><span data-stu-id="a6a19-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="a6a19-140">[Las retenciones basadas en](managing-holds.md#manage-non-custodial-holds) consultas no son compatibles con los idiomas CJK.</span><span class="sxs-lookup"><span data-stu-id="a6a19-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span> 
