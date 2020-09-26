---
title: Detección de duplicados Near-investigación de datos
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
description: Al administrar investigaciones de datos, use la detección de duplicados Near para agrupar documentos similares textualmente al analizar pruebas en investigaciones de datos (versión preliminar).
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 37ce968016e674ec83da536c65361d2075cf9bbb
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285956"
---
# <a name="near-duplicate-detection"></a><span data-ttu-id="3a82c-103">Detección de semiduplicados</span><span class="sxs-lookup"><span data-stu-id="3a82c-103">Near duplicate detection</span></span>

<span data-ttu-id="3a82c-104">Considere un conjunto de documentos que se deben revisar en los que un subconjunto se basa en la misma plantilla y que tiene principalmente el mismo lenguaje reutilizable, con unas pocas diferencias aquí y allí.</span><span class="sxs-lookup"><span data-stu-id="3a82c-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="3a82c-105">Si un revisor puede identificar este subconjunto, revise una de ellas minuciosamente y revise las diferencias para el resto, no habría perdido ninguna información única y solo tardó una pequeña parte del tiempo que habría llevado a leer todos los documentos que abarcaban.</span><span class="sxs-lookup"><span data-stu-id="3a82c-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="3a82c-106">La detección de duplicados de casi todos los documentos con texto similar que le ayudarán a mejorar el eficacia del proceso de revisión.</span><span class="sxs-lookup"><span data-stu-id="3a82c-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="3a82c-107">¿Cómo funciona?</span><span class="sxs-lookup"><span data-stu-id="3a82c-107">How does it work?</span></span>

<span data-ttu-id="3a82c-108">Cuando se ejecuta la detección cerca de duplicados, el sistema analiza todos los documentos con texto.</span><span class="sxs-lookup"><span data-stu-id="3a82c-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="3a82c-109">A continuación, compara cada documento entre sí para determinar si su similitud es mayor que el umbral establecido.</span><span class="sxs-lookup"><span data-stu-id="3a82c-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="3a82c-110">Si es así, los documentos se agrupan.</span><span class="sxs-lookup"><span data-stu-id="3a82c-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="3a82c-111">Una vez que se han comparado y agrupado todos los documentos, un documento de cada grupo se marca como "pivot"; al revisar los documentos, puede revisar primero un pivote y revisar los demás documentos en el mismo conjunto Near duplicado, centrándose en la diferencia entre el pivote y el documento que se está revisando.</span><span class="sxs-lookup"><span data-stu-id="3a82c-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
