---
title: Soporte de bytes CJK o doble para eDiscovery avanzado
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
description: Obtenga información sobre cómo la exhibición avanzada de documentos electrónicos en Microsoft 365 admite idiomas de chino, Japonés y Coreano (CJK), que usan un juego de caracteres de doble byte.
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626944"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="3983a-103">Compatibilidad con el idioma CJK para eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="3983a-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="3983a-104">EDiscovery avanzado admite idiomas de juegos de caracteres de doble byte (incluidos el chino simplificado, el chino tradicional, el japonés y el coreano, que se denominan en conjunto idiomas *CJK* ) para los siguientes escenarios avanzados en un conjunto de revisión:</span><span class="sxs-lookup"><span data-stu-id="3983a-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="3983a-105">Cuando se [consultan los datos de un conjunto de revisión](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="3983a-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="3983a-106">Al [etiquetar documentos en un conjunto de revisión](tagging-documents.md).</span><span class="sxs-lookup"><span data-stu-id="3983a-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="3983a-107">Al [analizar datos de casos en un conjunto de revisiones mediante la](analyzing-data-in-review-set.md) detección de duplicados, el procesamiento de correo electrónico y los análisis de temas.</span><span class="sxs-lookup"><span data-stu-id="3983a-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="3983a-108">Preguntas frecuentes</span><span class="sxs-lookup"><span data-stu-id="3983a-108">Frequently asked questions</span></span>

<span data-ttu-id="3983a-109">**¿Cómo se crea una búsqueda para recopilar elementos que contienen caracteres CJK?**</span><span class="sxs-lookup"><span data-stu-id="3983a-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="3983a-110">Puede usar caracteres CJK para [búsquedas de palabras clave](building-search-queries.md#keyword-searches), [consultas de palabras clave y condiciones de búsqueda](keyword-queries-and-search-conditions.md) al buscar contenido en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="3983a-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="3983a-111">La búsqueda de caracteres CJK también se admite al buscar contenido en la exhibición de documentos electrónicos y la búsqueda de contenido principales.</span><span class="sxs-lookup"><span data-stu-id="3983a-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="3983a-112">Se proporciona compatibilidad con CJK para todos los [operadores de búsqueda](keyword-queries-and-search-conditions.md#search-operators) y [condiciones de búsqueda](keyword-queries-and-search-conditions.md#search-conditions), incluidos los operadores booleanos **and**, **or**, **Not**y **Near**.</span><span class="sxs-lookup"><span data-stu-id="3983a-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="3983a-113">Si está seguro de que las ubicaciones de contenido o los elementos contienen caracteres CJK, pero las búsquedas no devuelven ningún resultado, haga clic en el icono de idioma de la consulta-país o región</span><span class="sxs-lookup"><span data-stu-id="3983a-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![Idioma de consulta: icono de país o región en la búsqueda de contenido](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="3983a-115">y seleccione el valor de código de referencia cultural correspondiente al país de idioma para la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3983a-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="3983a-116">Por defecto, la versión del idioma/región es la neutra.</span><span class="sxs-lookup"><span data-stu-id="3983a-116">The default language/region is neutral.</span></span>

<span data-ttu-id="3983a-117">**¿Puedo buscar varios idiomas a la vez?**</span><span class="sxs-lookup"><span data-stu-id="3983a-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="3983a-118">Depende del escenario de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3983a-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="3983a-119">Cuando [consulta datos en un conjunto de revisión en la](review-set-search.md) exhibición avanzada de documentos electrónicos, puede buscar en varios idiomas.</span><span class="sxs-lookup"><span data-stu-id="3983a-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="3983a-120">Al [crear una búsqueda para recopilar datos](create-search-to-collect-data.md), cree una búsqueda independiente para cada idioma al que esté destinado.</span><span class="sxs-lookup"><span data-stu-id="3983a-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="3983a-121">Por ejemplo, si está buscando un documento que contenga tanto chino como coreano, seleccione chino para la primera consulta y seleccione Coreano para la segunda consulta.</span><span class="sxs-lookup"><span data-stu-id="3983a-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="3983a-122">**No veo el icono de idioma de la consulta, país o región, para seleccionar un idioma para las consultas de un conjunto de revisión. ¿Cómo puedo especificar un idioma de consulta en una búsqueda de conjunto de revisión?**</span><span class="sxs-lookup"><span data-stu-id="3983a-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="3983a-123">Para las consultas de set de revisión, no es necesario especificar un idioma de documento.</span><span class="sxs-lookup"><span data-stu-id="3983a-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="3983a-124">EDiscovery avanzado detecta automáticamente los idiomas del documento cuando se agrega contenido a un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="3983a-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="3983a-125">Esto le ayudará a optimizar los resultados de la consulta en un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="3983a-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="3983a-126">**¿Puedo ver los idiomas detectados en los [metadatos del archivo](view-documents-in-review-set.md#file-metadata)?**</span><span class="sxs-lookup"><span data-stu-id="3983a-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="3983a-127">No, no puede ver los idiomas detectados en los metadatos del archivo.</span><span class="sxs-lookup"><span data-stu-id="3983a-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="3983a-128">**¿Puedo filtrar por idiomas de documentos en un conjunto de revisión**?</span><span class="sxs-lookup"><span data-stu-id="3983a-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="3983a-129">No, no puede filtrar, ordenar o buscar por idiomas del documento en un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="3983a-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="3983a-130">**¿Esta versión CJK para los escenarios de revisión de revisión afecta a mis conjuntos de revisión y búsquedas existentes?**</span><span class="sxs-lookup"><span data-stu-id="3983a-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="3983a-131">No, se cambiará ninguna de las búsquedas y los conjuntos de revisión existentes.</span><span class="sxs-lookup"><span data-stu-id="3983a-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="3983a-132">No es necesario reindizar los datos existentes y los resultados de búsqueda de texto en inglés serán los mismos.</span><span class="sxs-lookup"><span data-stu-id="3983a-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="3983a-133">**¿Cómo cambio el idioma para mostrar a chino, Japonés o Coreano?**</span><span class="sxs-lookup"><span data-stu-id="3983a-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="3983a-134">Para obtener información acerca de cómo cambiar la zona horaria y el idioma para mostrar, vea [el procedimiento para establecer la configuración de idioma y región para Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span><span class="sxs-lookup"><span data-stu-id="3983a-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="3983a-135">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="3983a-135">Known issues</span></span>

- <span data-ttu-id="3983a-136">OCR no admite caracteres CJK de archivos de imagen</span><span class="sxs-lookup"><span data-stu-id="3983a-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="3983a-137">Los archivos de correo electrónico (como \*. eml y \*. msg) en la [vista anotar](view-documents-in-review-set.md#annotate-view) no son compatibles con los idiomas CJK.</span><span class="sxs-lookup"><span data-stu-id="3983a-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="3983a-138">El resaltado de referencias de búsqueda en la [vista de texto](view-documents-in-review-set.md#text-view) no es compatible con los idiomas CJK.</span><span class="sxs-lookup"><span data-stu-id="3983a-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="3983a-139">El [módulo de relevancia](using-relevance.md) usado para analizar datos no admite idiomas CJK.</span><span class="sxs-lookup"><span data-stu-id="3983a-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="3983a-140">Las [retenciones basadas en consultas](managing-holds.md#manage-non-custodial-holds) no son compatibles con los idiomas CJK.</span><span class="sxs-lookup"><span data-stu-id="3983a-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span> 
