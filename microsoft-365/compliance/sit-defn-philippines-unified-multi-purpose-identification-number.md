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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Definición de entidad de tipo de información confidencial de número de identificación multiuso unificado de Filipinas.
ms.openlocfilehash: d5e880ff8c021cdcee195077f419f3b7ab87ed36
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000319"
---
# <a name="philippines-unified-multi-purpose-identification-number"></a>Número de identidad universal unificado de Filipinas

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

- La expresión `Regex_philippines_unified_id` regular busca contenido que coincida con el patrón.
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