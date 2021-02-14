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
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a>Detección de duplicados cercanos en eDiscovery avanzado

Considere la posibilidad de revisar un conjunto de documentos en el que un subconjunto se basa en la misma plantilla y tiene principalmente el mismo lenguaje reutilizable, con algunas diferencias aquí y allí. Si un revisor pudiera identificar este subconjunto, revisar uno de ellos exhaustivamente y revisar las diferencias para el resto, no se habría perdido ninguna información única mientras tardaba solo una fracción de tiempo en leer todos los documentos que se cubren. Casi los grupos de detección duplicados reúnen documentos similares textualmente para ayudarle a hacer que el proceso de revisión sea más eficaz.

## <a name="how-does-it-work"></a>¿Cómo funciona?

Cuando se ejecuta la detección de duplicados cercanos, el sistema analiza cada documento con texto. A continuación, compara cada documento entre sí para determinar si su similitud es mayor que el umbral establecido. Si es así, los documentos se agrupan. Una vez que todos los documentos se han comparado y agrupado, un documento de cada grupo se marca como "dinámico"; en la revisión de los documentos, puede revisar primero una tabla dinámica y revisar los demás documentos del mismo conjunto casi duplicado, centrándose en la diferencia entre la tabla dinámica y el documento que está en revisión.
