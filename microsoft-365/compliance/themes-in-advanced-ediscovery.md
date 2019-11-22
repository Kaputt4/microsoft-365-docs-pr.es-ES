---
title: Temas
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
description: ''
ms.openlocfilehash: ba57a89365c2a76dec215f56d7ed0755f27be12d
ms.sourcegitcommit: caa3f681a68daf5e463093a922c3d6f378143d91
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "39191215"
---
# <a name="themes"></a><span data-ttu-id="f78a0-102">Temas</span><span class="sxs-lookup"><span data-stu-id="f78a0-102">Themes</span></span>

<span data-ttu-id="f78a0-103">¿Cómo escribe un documento un usuario?</span><span class="sxs-lookup"><span data-stu-id="f78a0-103">How does a person write a document?</span></span> <span data-ttu-id="f78a0-104">Por lo general, comienzan con una o más ideas que quieren transmitir en el documento y se redactan con palabras que se alinean con las ideas.</span><span class="sxs-lookup"><span data-stu-id="f78a0-104">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="f78a0-105">Cuanto más frecuente sea la idea, más frecuentes serán las palabras relacionadas con dicha idea.</span><span class="sxs-lookup"><span data-stu-id="f78a0-105">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="f78a0-106">Esto informa de cómo los usuarios también usan los documentos.</span><span class="sxs-lookup"><span data-stu-id="f78a0-106">This informs how people consume documents as well.</span></span> <span data-ttu-id="f78a0-107">Lo más importante que debe comprender a partir de la lectura de un documento son las ideas que el documento está tratando de transmitir, las ideas que aparecen en dónde y cuáles son las relaciones entre las ideas.</span><span class="sxs-lookup"><span data-stu-id="f78a0-107">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="f78a0-108">Esto puede ampliarse a cómo una persona desea consumir un conjunto de documentos.</span><span class="sxs-lookup"><span data-stu-id="f78a0-108">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="f78a0-109">Quieren ver qué ideas están presentes en los conjuntos y qué documentos están hablando sobre esas ideas.</span><span class="sxs-lookup"><span data-stu-id="f78a0-109">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="f78a0-110">Además, si encuentran un documento concreto de interés, quieren poder ver documentos que discutan ideas similares.</span><span class="sxs-lookup"><span data-stu-id="f78a0-110">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="f78a0-111">La funcionalidad de temas en eDiscovery avanzado intenta imitar la razón de los documentos de los usuarios mediante el análisis de los *temas* que se tratan en un conjunto de revisiones y la asignación de un tema a los documentos en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="f78a0-111">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="f78a0-112">En la exhibición avanzada de documentos electrónicos, los temas van un paso más allá e identifican el *tema dominante* en cada documento.</span><span class="sxs-lookup"><span data-stu-id="f78a0-112">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="f78a0-113">El tema dominante es el que aparece con más frecuencia en un documento.</span><span class="sxs-lookup"><span data-stu-id="f78a0-113">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="f78a0-114">¿Cómo funciona los temas?</span><span class="sxs-lookup"><span data-stu-id="f78a0-114">How does Themes work?</span></span>

<span data-ttu-id="f78a0-115">La funcionalidad temas analiza los documentos con texto en una revisión establecida para analizar los temas comunes que aparecen en todos los documentos del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="f78a0-115">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="f78a0-116">EDiscovery avanzado asigna los temas a los documentos en los que aparecen.</span><span class="sxs-lookup"><span data-stu-id="f78a0-116">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="f78a0-117">También etiqueta cada tema con las palabras que se usan en los documentos representativos del tema.</span><span class="sxs-lookup"><span data-stu-id="f78a0-117">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="f78a0-118">Debido a que un documento puede contener varios tipos de asunto, eDiscovery avanzado suele asignar varios temas a los documentos.</span><span class="sxs-lookup"><span data-stu-id="f78a0-118">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="f78a0-119">El tema que aparece más visiblemente en un documento se designa como su tema dominante.</span><span class="sxs-lookup"><span data-stu-id="f78a0-119">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>