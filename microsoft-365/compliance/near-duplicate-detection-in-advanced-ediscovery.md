---
title: Detección casi duplicada en eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use la detección casi duplicada para agrupar documentos textualmente similares al analizar datos de casos en eDiscovery (Premium).
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f7976f5fdf023c30f7f96264ecc2b744656e9091
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64949419"
---
# <a name="near-duplicate-detection-in-ediscovery-premium"></a>Detección de duplicados casi en eDiscovery (Premium)

Considere la posibilidad de revisar un conjunto de documentos en el que un subconjunto se basa en la misma plantilla y tiene principalmente el mismo lenguaje reutilizable, con algunas diferencias aquí y allí. Si un revisor pudiera identificar este subconjunto, revisar uno de ellos exhaustivamente y revisar las diferencias del resto, no habrían perdido ninguna información única mientras tardaban solo una fracción de tiempo que les habría llevado a leer todos los documentos que cubrir. La detección de casi duplicados agrupa documentos textualmente similares para ayudarlo a que su proceso de revisión sea más eficiente.

## <a name="how-does-it-work"></a>¿Cómo funciona?

Cuando se ejecuta la detección de casi duplicados, el sistema analiza cada documento con texto. Luego, compara cada documento entre sí para determinar si su similitud es mayor que el umbral establecido. Si es así, los documentos se agrupan juntos. Una vez que se han comparado y agrupado todos los documentos, se marca un documento de cada grupo como "documento principal"; Al revisar sus documentos, puede revisar un documento principal en primer lugar y revisar los otros documentos en el mismo conjunto casi duplicado, enfocándose en la diferencia entre el documento principal y el documento que está en revisión.
