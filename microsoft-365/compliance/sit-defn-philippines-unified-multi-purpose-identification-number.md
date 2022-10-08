---
title: Definición de entidad de número de identificación multiuso unificado de Filipinas
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Definición de entidad de tipo de información confidencial de número de identificación multiuso unificado de Filipinas.
ms.openlocfilehash: d3d19524e8eefa5549ea5a461a5dee7c9fe0d59c
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68471703"
---
# <a name="philippines-unified-multi-purpose-identification-number"></a>Número de identidad universal unificado de Filipinas

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

12 dígitos separados por guiones

## <a name="pattern"></a>Patrón

12 dígitos:

- cuatro dígitos
- un guion
- siete dígitos
- un guion
- un dígito

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular `Regex_philippines_unified_id` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_philippines_id`.

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_philippines_id"></a>Keyword_philippines_id

- Id. universal unificado

- UMID
- Tarjeta de identidad
- Pinag-isang Multi-Layunin ID
