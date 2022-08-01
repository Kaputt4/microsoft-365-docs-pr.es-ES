---
title: Reino Unido definición de entidad de número de lista electoral
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
description: Reino Unido definición de entidad de tipo de información confidencial de número de lista electoral.
ms.openlocfilehash: d821878a155ec6c2393150265ddac1dc18fc5f10
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999251"
---
# <a name="uk-electoral-roll-number"></a>Reino Unido número de la tarjeta electoral

## <a name="format"></a>Formato

dos letras seguidas de 1-4 dígitos

## <a name="pattern"></a>Patrón

dos letras (no distinguen mayúsculas de minúsculas) seguidas de números de 1 a 4

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_uk_electoral` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_uk_electoral`.

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_uk_electoral"></a>Keyword_uk_electoral

- council nomination
- nomination form
- electoral register
- electoral roll