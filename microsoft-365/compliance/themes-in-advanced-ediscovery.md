---
title: 'Temas: exhibición de documentos electrónicos'
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use temas en eDiscovery avanzado para organizar conjuntos de revisión mediante la búsqueda del tema dominante en cada documento.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285536"
---
# <a name="themes-in-advanced-ediscovery"></a><span data-ttu-id="d3b6d-103">Temas en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="d3b6d-103">Themes in Advanced eDiscovery</span></span>

<span data-ttu-id="d3b6d-104">¿Cómo escribe un documento una persona?</span><span class="sxs-lookup"><span data-stu-id="d3b6d-104">How does a person write a document?</span></span> <span data-ttu-id="d3b6d-105">Por lo general, empiezan con una o más ideas que quieren transmitir en el documento y redactan con palabras que se alinean con las ideas.</span><span class="sxs-lookup"><span data-stu-id="d3b6d-105">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="d3b6d-106">Cuando más frecuente sea una idea, más frecuentes serán las palabras relacionadas con esa idea.</span><span class="sxs-lookup"><span data-stu-id="d3b6d-106">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="d3b6d-107">Esto informa de cómo los usuarios consumen documentos también.</span><span class="sxs-lookup"><span data-stu-id="d3b6d-107">This informs how people consume documents as well.</span></span> <span data-ttu-id="d3b6d-108">Lo importante que se debe comprender al leer un documento son las ideas que el documento intenta transmitir, qué ideas aparecen en qué lugar y cuáles son las relaciones entre las ideas.</span><span class="sxs-lookup"><span data-stu-id="d3b6d-108">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="d3b6d-109">Esto puede extenderse a la forma en que una persona desea consumir un conjunto de documentos.</span><span class="sxs-lookup"><span data-stu-id="d3b6d-109">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="d3b6d-110">Quieren ver qué ideas están presentes en los conjuntos y qué documentos están hablando de esas ideas.</span><span class="sxs-lookup"><span data-stu-id="d3b6d-110">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="d3b6d-111">Además, si encuentran un documento de interés concreto, desean poder ver documentos que analizan ideas similares.</span><span class="sxs-lookup"><span data-stu-id="d3b6d-111">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="d3b6d-112">La funcionalidad De temas de eDiscovery avanzado intenta imitar  la razón de los usuarios sobre los documentos, analizando los temas que se analizan en un conjunto de revisión y asignando un tema a los documentos del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="d3b6d-112">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="d3b6d-113">En eDiscovery avanzado, los temas van un paso más allá e identifican el *tema dominante* en cada documento.</span><span class="sxs-lookup"><span data-stu-id="d3b6d-113">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="d3b6d-114">El tema dominante es el que aparece con más frecuencia en un documento.</span><span class="sxs-lookup"><span data-stu-id="d3b6d-114">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="d3b6d-115">¿Cómo funcionan los temas?</span><span class="sxs-lookup"><span data-stu-id="d3b6d-115">How does Themes work?</span></span>

<span data-ttu-id="d3b6d-116">La funcionalidad Temas analiza los documentos con texto en un conjunto de revisión para analizar los temas comunes que aparecen en todos los documentos del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="d3b6d-116">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="d3b6d-117">EDiscovery avanzado asigna esos temas a los documentos en los que aparecen.</span><span class="sxs-lookup"><span data-stu-id="d3b6d-117">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="d3b6d-118">También etiqueta cada tema con las palabras usadas en los documentos que son representativos del tema.</span><span class="sxs-lookup"><span data-stu-id="d3b6d-118">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="d3b6d-119">Dado que un documento puede contener varios tipos de temas, eDiscovery avanzado suele asignar varios temas a los documentos.</span><span class="sxs-lookup"><span data-stu-id="d3b6d-119">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="d3b6d-120">El tema que aparece más destacado en un documento se designa como su tema dominante.</span><span class="sxs-lookup"><span data-stu-id="d3b6d-120">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>
