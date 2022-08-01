---
title: Definición de entidad de número de cuenta bancaria de Australia
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
description: Definición de entidad de tipo de información confidencial del número de cuenta bancaria de Australia.
ms.openlocfilehash: df46075da0b85f306a52b1971db7b15c6a13028b
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999212"
---
# <a name="australia-bank-account-number"></a>Número de cuenta bancaria de Australia

## <a name="format"></a>Formato

de seis a 10 dígitos con o sin un número de sucursal estatal bancaria

## <a name="pattern"></a>Patrón

El número de cuenta es de 6 a 10 dígitos.

Número de sucursal bancaria de Australia:

- tres dígitos
- un guion
- tres dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular Regex_australia_bank_account_number busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de Keyword_australia_bank_account_number.
- La expresión regular Regex_australia_bank_account_number_bsb encuentra contenido que coincide con el patrón.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular Regex_australia_bank_account_number busca contenido que coincida con el patrón.

- Se encuentra una palabra clave de Keyword_australia_bank_account_number.

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_australia_bank_account_number"></a>Keyword_australia_bank_account_number

- swift bank code
- correspondent bank
- base currency
- usa account
- holder address
- bank address
- information account
- fund transfers
- bank charges
- bank details
- banking information
- full names
- Oiea