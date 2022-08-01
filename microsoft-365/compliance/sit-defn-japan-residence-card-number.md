---
title: Definición de entidad de número de tarjeta de residencia de Japón
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
description: Definición de entidad de tipo de información confidencial del número de tarjeta de residencia de Japón.
ms.openlocfilehash: 512a20f00dd2ff77d2f88950d83b227a717c309e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000268"
---
# <a name="japan-residence-card-number"></a>Número de tarjeta de residencia de Japón

## <a name="format"></a>Formato

12 letras y dígitos

## <a name="pattern"></a>Patrón

12 letras y dígitos:

- dos letras (no distinguen mayúsculas de minúsculas)
- ocho dígitos
- dos letras (no distinguen mayúsculas de minúsculas)

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_jp_residence_card_number` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_jp_residence_card_number`.

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_jp_residence_card_number"></a>Keyword_jp_residence_card_number

- Número de tarjeta de residencia
- Tarjeta de residencia no
- Tarjeta de residencia #
- 在留カード番号
- 在留カード
- 在留番号