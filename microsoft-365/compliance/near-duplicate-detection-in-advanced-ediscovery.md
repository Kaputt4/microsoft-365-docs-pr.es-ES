---
title: Detección casi duplicada en eDiscovery
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
ms.openlocfilehash: 985374558189b2001c6f11e09581f7cb3ed6d11b
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66622577"
---
# <a name="near-duplicate-detection-in-ediscovery-premium"></a>Detección de duplicados casi en eDiscovery (Premium)

Considere la posibilidad de revisar un conjunto de documentos en el que un subconjunto se basa en la misma plantilla y tiene principalmente el mismo lenguaje reutilizable, con algunas diferencias aquí y allí. Si un revisor pudiera identificar este subconjunto, revisar uno de ellos exhaustivamente y revisar las diferencias del resto, no habrían perdido ninguna información única mientras tardaban solo una fracción de tiempo que les habría llevado a leer todos los documentos que cubrir. La detección de casi duplicados agrupa documentos textualmente similares para ayudarlo a que su proceso de revisión sea más eficiente.

## <a name="how-does-it-work"></a>¿Cómo funciona?

Cuando se ejecuta la detección de casi duplicados, el sistema analiza cada documento con texto. Luego, compara cada documento entre sí para determinar si su similitud es mayor que el umbral establecido. Si es así, los documentos se agrupan juntos. Una vez que se han comparado y agrupado todos los documentos, se marca un documento de cada grupo como "documento principal"; Al revisar sus documentos, puede revisar un documento principal en primer lugar y revisar los otros documentos en el mismo conjunto casi duplicado, enfocándose en la diferencia entre el documento principal y el documento que está en revisión.
