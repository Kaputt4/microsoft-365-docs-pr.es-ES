---
title: 'Temas: eDiscovery'
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use los temas de la exhibición avanzada de documentos electrónicos para organizar los conjuntos de revisiones buscando el tema dominante en cada documento.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: eb008e091cd8c8330d1cdd5b388e252af70922da
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034524"
---
# <a name="themes"></a><span data-ttu-id="6a9b8-103">Temas</span><span class="sxs-lookup"><span data-stu-id="6a9b8-103">Themes</span></span>

<span data-ttu-id="6a9b8-104">¿Cómo escribe un documento un usuario?</span><span class="sxs-lookup"><span data-stu-id="6a9b8-104">How does a person write a document?</span></span> <span data-ttu-id="6a9b8-105">Por lo general, comienzan con una o más ideas que quieren transmitir en el documento y se redactan con palabras que se alinean con las ideas.</span><span class="sxs-lookup"><span data-stu-id="6a9b8-105">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="6a9b8-106">Cuanto más frecuente sea la idea, más frecuentes serán las palabras relacionadas con dicha idea.</span><span class="sxs-lookup"><span data-stu-id="6a9b8-106">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="6a9b8-107">Esto informa de cómo los usuarios también usan los documentos.</span><span class="sxs-lookup"><span data-stu-id="6a9b8-107">This informs how people consume documents as well.</span></span> <span data-ttu-id="6a9b8-108">Lo más importante que debe comprender a partir de la lectura de un documento son las ideas que el documento está tratando de transmitir, las ideas que aparecen en dónde y cuáles son las relaciones entre las ideas.</span><span class="sxs-lookup"><span data-stu-id="6a9b8-108">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="6a9b8-109">Esto puede ampliarse a cómo una persona desea consumir un conjunto de documentos.</span><span class="sxs-lookup"><span data-stu-id="6a9b8-109">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="6a9b8-110">Quieren ver qué ideas están presentes en los conjuntos y qué documentos están hablando sobre esas ideas.</span><span class="sxs-lookup"><span data-stu-id="6a9b8-110">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="6a9b8-111">Además, si encuentran un documento concreto de interés, quieren poder ver documentos que discutan ideas similares.</span><span class="sxs-lookup"><span data-stu-id="6a9b8-111">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="6a9b8-112">La funcionalidad de temas en eDiscovery avanzado intenta imitar la razón de los documentos de los usuarios mediante el análisis de los *temas* que se tratan en un conjunto de revisiones y la asignación de un tema a los documentos en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="6a9b8-112">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="6a9b8-113">En la exhibición avanzada de documentos electrónicos, los temas van un paso más allá e identifican el *tema dominante* en cada documento.</span><span class="sxs-lookup"><span data-stu-id="6a9b8-113">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="6a9b8-114">El tema dominante es el que aparece con más frecuencia en un documento.</span><span class="sxs-lookup"><span data-stu-id="6a9b8-114">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="6a9b8-115">¿Cómo funciona los temas?</span><span class="sxs-lookup"><span data-stu-id="6a9b8-115">How does Themes work?</span></span>

<span data-ttu-id="6a9b8-116">La funcionalidad temas analiza los documentos con texto en una revisión establecida para analizar los temas comunes que aparecen en todos los documentos del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="6a9b8-116">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="6a9b8-117">EDiscovery avanzado asigna los temas a los documentos en los que aparecen.</span><span class="sxs-lookup"><span data-stu-id="6a9b8-117">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="6a9b8-118">También etiqueta cada tema con las palabras que se usan en los documentos representativos del tema.</span><span class="sxs-lookup"><span data-stu-id="6a9b8-118">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="6a9b8-119">Debido a que un documento puede contener varios tipos de asunto, eDiscovery avanzado suele asignar varios temas a los documentos.</span><span class="sxs-lookup"><span data-stu-id="6a9b8-119">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="6a9b8-120">El tema que aparece más visiblemente en un documento se designa como su tema dominante.</span><span class="sxs-lookup"><span data-stu-id="6a9b8-120">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>
