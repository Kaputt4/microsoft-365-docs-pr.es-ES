---
title: 'Detección casi duplicada: exhibición de documentos electrónicos'
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
description: Use la detección casi duplicada para agrupar documentos textualmente similares al analizar datos de casos en Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286026"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a><span data-ttu-id="ffaed-103">Casi detección de duplicados en Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ffaed-103">Near duplicate detection in Advanced eDiscovery</span></span>

<span data-ttu-id="ffaed-104">Considere la posibilidad de revisar un conjunto de documentos en el que un subconjunto se basa en la misma plantilla y tiene principalmente el mismo lenguaje reutilizable, con algunas diferencias aquí y allá.</span><span class="sxs-lookup"><span data-stu-id="ffaed-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="ffaed-105">Si un revisor pudiera identificar este subconjunto, revisar uno de ellos exhaustivamente y revisar las diferencias para el resto, no se habría perdido ninguna información única mientras se tardaba solo una fracción de tiempo en leer todos los documentos que se cubren.</span><span class="sxs-lookup"><span data-stu-id="ffaed-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="ffaed-106">La detección de casi duplicados agrupa documentos textualmente similares para ayudarlo a que su proceso de revisión sea más eficiente.</span><span class="sxs-lookup"><span data-stu-id="ffaed-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="ffaed-107">¿Cómo funciona?</span><span class="sxs-lookup"><span data-stu-id="ffaed-107">How does it work?</span></span>

<span data-ttu-id="ffaed-108">Cuando se ejecuta la detección de casi duplicados, el sistema analiza cada documento con texto.</span><span class="sxs-lookup"><span data-stu-id="ffaed-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="ffaed-109">Luego, compara cada documento entre sí para determinar si su similitud es mayor que el umbral establecido.</span><span class="sxs-lookup"><span data-stu-id="ffaed-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="ffaed-110">Si es así, los documentos se agrupan juntos.</span><span class="sxs-lookup"><span data-stu-id="ffaed-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="ffaed-111">Una vez que se han comparado y agrupado todos los documentos, se marca un documento de cada grupo como "documento principal"; Al revisar sus documentos, puede revisar un documento principal en primer lugar y revisar los otros documentos en el mismo conjunto casi duplicado, enfocándose en la diferencia entre el documento principal y el documento que está en revisión.</span><span class="sxs-lookup"><span data-stu-id="ffaed-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
