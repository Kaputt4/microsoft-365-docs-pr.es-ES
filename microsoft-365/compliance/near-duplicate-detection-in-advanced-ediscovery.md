---
title: 'Detección de duplicados cercanos: exhibición de documentos electrónicos'
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
description: Use la detección de casi duplicados para agrupar documentos similares textualmente al analizar datos de casos en eDiscovery avanzado.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286026"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a><span data-ttu-id="a86c4-103">Detección de duplicados cercanos en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="a86c4-103">Near duplicate detection in Advanced eDiscovery</span></span>

<span data-ttu-id="a86c4-104">Considere la posibilidad de revisar un conjunto de documentos en el que un subconjunto se basa en la misma plantilla y tiene principalmente el mismo lenguaje reutilizable, con algunas diferencias aquí y allí.</span><span class="sxs-lookup"><span data-stu-id="a86c4-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="a86c4-105">Si un revisor pudiera identificar este subconjunto, revisar uno de ellos exhaustivamente y revisar las diferencias para el resto, no se habría perdido ninguna información única mientras tardaba solo una fracción de tiempo en leer todos los documentos que se cubren.</span><span class="sxs-lookup"><span data-stu-id="a86c4-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="a86c4-106">Casi los grupos de detección duplicados reúnen documentos similares textualmente para ayudarle a hacer que el proceso de revisión sea más eficaz.</span><span class="sxs-lookup"><span data-stu-id="a86c4-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="a86c4-107">¿Cómo funciona?</span><span class="sxs-lookup"><span data-stu-id="a86c4-107">How does it work?</span></span>

<span data-ttu-id="a86c4-108">Cuando se ejecuta la detección de duplicados cercanos, el sistema analiza cada documento con texto.</span><span class="sxs-lookup"><span data-stu-id="a86c4-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="a86c4-109">A continuación, compara cada documento entre sí para determinar si su similitud es mayor que el umbral establecido.</span><span class="sxs-lookup"><span data-stu-id="a86c4-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="a86c4-110">Si es así, los documentos se agrupan.</span><span class="sxs-lookup"><span data-stu-id="a86c4-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="a86c4-111">Una vez que todos los documentos se han comparado y agrupado, un documento de cada grupo se marca como "dinámico"; en la revisión de los documentos, puede revisar primero una tabla dinámica y revisar los demás documentos del mismo conjunto casi duplicado, centrándose en la diferencia entre la tabla dinámica y el documento que está en revisión.</span><span class="sxs-lookup"><span data-stu-id="a86c4-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
