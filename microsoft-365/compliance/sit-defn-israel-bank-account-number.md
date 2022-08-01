---
title: Definición de entidad de número de cuenta bancaria de Israel
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
description: Definición de entidad de tipo de información confidencial de número de cuenta bancaria de Israel.
ms.openlocfilehash: a68f90cd92432778d89d3f8494522a5ab2822d07
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000400"
---
# <a name="israel-bank-account-number"></a>Número de cuenta bancaria de Israel

## <a name="format"></a>Formato

13 dígitos

## <a name="pattern"></a>Patrón

Formato:

- dos dígitos
- un guión
- tres dígitos
- un guión
- ocho dígitos

Sin formato:

- 	13 dígitos consecutivos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_israel_bank_account_number` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_israel_bank_account_number`.

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_israel_bank_account_number"></a>Keyword_israel_bank_account_number

- Número de cuenta bancaria
- Cuenta bancaria
- Account Number
- מספר חשבון בנק