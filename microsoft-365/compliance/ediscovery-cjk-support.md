---
title: Compatibilidad con CJK/Double Byte para eDiscovery avanzada
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
description: Obtenga información sobre cómo la exhibición de documentos electrónicos avanzada en Microsoft 365 admite los idiomas chino, japonés y coreano (CJK), que usan un juego de caracteres de doble byte.
ms.openlocfilehash: ee47c5cd7f1a378ccfff05b8f7712e91092907cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926606"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="1e23a-103">Compatibilidad con lenguaje CJK para exhibición de documentos electrónicos avanzada</span><span class="sxs-lookup"><span data-stu-id="1e23a-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="1e23a-104">La exhibición de documentos electrónicos avanzada admite idiomas de juego de caracteres de doble byte (entre los que se incluyen chino simplificado, chino tradicional, japonés y coreano, que se conocen colectivamente como idiomas *CJK)* para los siguientes escenarios avanzados de un conjunto de opiniones:</span><span class="sxs-lookup"><span data-stu-id="1e23a-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="1e23a-105">Al consultar [los datos de un conjunto de revisión](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="1e23a-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="1e23a-106">Al [etiquetar documentos en un conjunto de revisión](tagging-documents.md).</span><span class="sxs-lookup"><span data-stu-id="1e23a-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="1e23a-107">Al analizar [los datos de casos en un conjunto de revisión](analyzing-data-in-review-set.md) mediante la detección casi duplicada, el subproceso de correo electrónico y el análisis de temas.</span><span class="sxs-lookup"><span data-stu-id="1e23a-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="1e23a-108">Preguntas frecuentes</span><span class="sxs-lookup"><span data-stu-id="1e23a-108">Frequently asked questions</span></span>

<span data-ttu-id="1e23a-109">**¿Cómo puedo crear una búsqueda para recopilar elementos que contengan caracteres CJK?**</span><span class="sxs-lookup"><span data-stu-id="1e23a-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="1e23a-110">Puede usar caracteres CJK para [búsquedas](building-search-queries.md#keyword-searches)de palabras clave, consultas [de](keyword-queries-and-search-conditions.md) palabras clave y condiciones de búsqueda al buscar contenido en eDiscovery avanzada.</span><span class="sxs-lookup"><span data-stu-id="1e23a-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="1e23a-111">También se admite la búsqueda de caracteres CJK al buscar contenido en la exhibición de documentos electrónicos principal y la búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="1e23a-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="1e23a-112">Proporcionamos compatibilidad con CJK para todos [los](keyword-queries-and-search-conditions.md#search-operators) operadores de búsqueda y las condiciones de [búsqueda,](keyword-queries-and-search-conditions.md#search-conditions)incluidos los operadores **booleanos AND**, **OR**, **NOT** y **NEAR**.</span><span class="sxs-lookup"><span data-stu-id="1e23a-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="1e23a-113">Si está seguro de que las ubicaciones de contenido o los elementos contienen caracteres CJK, pero las búsquedas no devuelven ningún resultado, haga clic en el icono idioma-país o región de la consulta</span><span class="sxs-lookup"><span data-stu-id="1e23a-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![Icono de idioma-país/región de consulta en búsqueda de contenido](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="1e23a-115">y seleccione el valor de código de referencia cultural idioma-país correspondiente para la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1e23a-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="1e23a-116">Por defecto, la versión del idioma/región es la neutra.</span><span class="sxs-lookup"><span data-stu-id="1e23a-116">The default language/region is neutral.</span></span>

<span data-ttu-id="1e23a-117">**¿Puedo buscar varios idiomas a la vez?**</span><span class="sxs-lookup"><span data-stu-id="1e23a-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="1e23a-118">Depende del escenario de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1e23a-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="1e23a-119">Al consultar [datos en un conjunto de revisión](review-set-search.md) de eDiscovery avanzado, puede buscar varios idiomas.</span><span class="sxs-lookup"><span data-stu-id="1e23a-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="1e23a-120">Al crear [una búsqueda para recopilar datos,](create-search-to-collect-data.md)cree una búsqueda independiente para cada idioma de destino.</span><span class="sxs-lookup"><span data-stu-id="1e23a-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="1e23a-121">Por ejemplo, si está buscando un documento que contenga chino y coreano, seleccione Chino para la primera consulta y seleccione Coreano para la segunda consulta.</span><span class="sxs-lookup"><span data-stu-id="1e23a-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="1e23a-122">**No veo el icono de idioma-país o región de consulta para seleccionar un idioma para las consultas de un conjunto de revisión. ¿Cómo puedo especificar un idioma de consulta en una búsqueda de conjunto de revisión?**</span><span class="sxs-lookup"><span data-stu-id="1e23a-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="1e23a-123">Para las consultas de conjunto de revisión, no es necesario especificar un idioma del documento.</span><span class="sxs-lookup"><span data-stu-id="1e23a-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="1e23a-124">La exhibición de documentos electrónicos avanzada detecta automáticamente los idiomas de los documentos al agregar contenido a un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="1e23a-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="1e23a-125">Esto le ayuda a optimizar los resultados de la consulta en un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="1e23a-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="1e23a-126">**¿Puedo ver idiomas detectados en metadatos [de archivo?](view-documents-in-review-set.md#file-metadata)**</span><span class="sxs-lookup"><span data-stu-id="1e23a-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="1e23a-127">No, no puede ver los idiomas detectados en los metadatos de archivo.</span><span class="sxs-lookup"><span data-stu-id="1e23a-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="1e23a-128">**¿Puedo filtrar por idiomas de documento en un conjunto de revisión?**</span><span class="sxs-lookup"><span data-stu-id="1e23a-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="1e23a-129">No, no puede filtrar, ordenar o buscar por idiomas de documento en un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="1e23a-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="1e23a-130">**¿Afectará esta versión de CJK a los escenarios de conjunto de revisión alguno de mis conjuntos de búsquedas y revisión existentes?**</span><span class="sxs-lookup"><span data-stu-id="1e23a-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="1e23a-131">No, ninguna de las búsquedas y conjuntos de revisión existentes cambiará.</span><span class="sxs-lookup"><span data-stu-id="1e23a-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="1e23a-132">No es necesario volver a indizar los datos existentes y los resultados de la búsqueda del texto en inglés serán los mismos.</span><span class="sxs-lookup"><span data-stu-id="1e23a-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="1e23a-133">**¿Cómo puedo cambiar mi idioma de presentación a chino, japonés o coreano?**</span><span class="sxs-lookup"><span data-stu-id="1e23a-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="1e23a-134">Para obtener información sobre cómo cambiar el idioma para mostrar y la zona horaria, vea [How to set language and region settings for Office 365](/office365/troubleshoot/access-management/set-language-and-region).</span><span class="sxs-lookup"><span data-stu-id="1e23a-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="1e23a-135">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="1e23a-135">Known issues</span></span>

- <span data-ttu-id="1e23a-136">OCR no admite caracteres CJK de archivos de imagen</span><span class="sxs-lookup"><span data-stu-id="1e23a-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="1e23a-137">Los archivos de correo electrónico (como \*.eml y \*.msg) en la vista Anotación no son compatibles con los idiomas CJK. [](view-documents-in-review-set.md#annotate-view)</span><span class="sxs-lookup"><span data-stu-id="1e23a-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="1e23a-138">El resaltado de resultados de búsqueda en [la vista](view-documents-in-review-set.md#text-view) Texto no es compatible con los idiomas CJK.</span><span class="sxs-lookup"><span data-stu-id="1e23a-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="1e23a-139">El [módulo Relevancia](using-relevance.md) usado para analizar datos no admite idiomas CJK.</span><span class="sxs-lookup"><span data-stu-id="1e23a-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="1e23a-140">[Las retenciones basadas en](managing-holds.md#manage-non-custodial-holds) consultas no son compatibles con los idiomas CJK.</span><span class="sxs-lookup"><span data-stu-id="1e23a-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span>