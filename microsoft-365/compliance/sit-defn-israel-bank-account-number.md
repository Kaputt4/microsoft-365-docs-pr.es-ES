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
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Definición de entidad de tipo de información confidencial de número de cuenta bancaria de Israel.
ms.openlocfilehash: d29a328cc53a76ad86cc0c7cee51457b0cfa2c26
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68382470"
---
# <a name="israel-bank-account-number"></a>Número de cuenta bancaria de Israel

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

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

- La expresión regular `Regex_israel_bank_account_number` encuentra contenido que coincide con el patrón.
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
