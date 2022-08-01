---
title: Definición de entidad de número de pasaporte de Taiwán
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
description: Definición de entidad de tipo de información confidencial del número de pasaporte de Taiwán.
ms.openlocfilehash: b899fbe560ea6cba19c66bafea819c769ece2634
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999902"
---
# <a name="taiwan-passport-number"></a>Número de pasaporte de Taiwán

## <a name="format"></a>Formato

- número de pasaporte biométrico: nueve dígitos
- número de pasaporte no biométrico: nueve dígitos

## <a name="pattern"></a>Patrón

número de pasaporte biométrico:

- el carácter "3"
- ocho dígitos

número de pasaporte no biométrico:

- nueve dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_taiwan_passport` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_taiwan_passport`.

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_taiwan_passport"></a>Keyword_taiwan_passport

- Número de pasaporte ROC
- Número de pasaporte
- Núm. pasaporte

- N.ro pasaporte
- N.º de pasaporte
- 护照
- 中華民國護照
- Zhōnghuá Mínguó hùzhào