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
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a>Casi detección de duplicados en Advanced eDiscovery

Considere la posibilidad de revisar un conjunto de documentos en el que un subconjunto se basa en la misma plantilla y tiene principalmente el mismo lenguaje reutilizable, con algunas diferencias aquí y allá. Si un revisor pudiera identificar este subconjunto, revisar uno de ellos exhaustivamente y revisar las diferencias para el resto, no se habría perdido ninguna información única mientras se tardaba solo una fracción de tiempo en leer todos los documentos que se cubren. La detección de casi duplicados agrupa documentos textualmente similares para ayudarlo a que su proceso de revisión sea más eficiente.

## <a name="how-does-it-work"></a>¿Cómo funciona?

Cuando se ejecuta la detección de casi duplicados, el sistema analiza cada documento con texto. Luego, compara cada documento entre sí para determinar si su similitud es mayor que el umbral establecido. Si es así, los documentos se agrupan juntos. Una vez que se han comparado y agrupado todos los documentos, se marca un documento de cada grupo como "documento principal"; Al revisar sus documentos, puede revisar un documento principal en primer lugar y revisar los otros documentos en el mismo conjunto casi duplicado, enfocándose en la diferencia entre el documento principal y el documento que está en revisión.
