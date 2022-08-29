---
title: Definición de entidad de número de cuenta bancaria de Nueva Zelanda
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
description: Definición de entidad de tipo de información confidencial de número de cuenta bancaria de Nueva Zelanda.
ms.openlocfilehash: 3e682641abeee0c6e48fa1df70c767f029d0af4c
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2022
ms.locfileid: "67369720"
---
# <a name="new-zealand-bank-account-number"></a>Número de cuenta bancaria de Nueva Zelanda

## <a name="format"></a>Formato

Patrón de 14 a 16 dígitos con delimitador opcional

## <a name="pattern"></a>Patrón

Patrón de 14 a 16 dígitos con delimitador opcional:

- dos dígitos
- un guion o espacio opcional
- de tres a cuatro dígitos
- un guion o espacio opcional
- siete dígitos
- un guion o espacio opcional
- de dos a tres dígitos
- un guion o espacio de opciones

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_new_zealand_bank_account_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_new_zealand_bank_account_number`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_new_zealand_bank_account_number` encuentra contenido que coincide con el patrón.

```xml
      <!-- New Zealand Bank Account Number -->
      <Entity id="1a97fc2b-dd2f-48f1-bc4e-2ddf25813956" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
          <Match idRef="Keywords_new_zFealand_bank_account_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_new_zealand_bank_account_number"></a>Keyword_new_zealand_bank_account_number

- account number
- cuenta bancaria
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr