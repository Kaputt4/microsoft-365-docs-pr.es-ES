---
title: Definición de entidad de número de cuenta bancaria de Canadá
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
description: Definición de entidad de tipo de información confidencial de número de cuenta bancaria de Canadá.
ms.openlocfilehash: c7008b17ff532a55dfefc079a07fc8e95f789b04
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999839"
---
# <a name="canada-bank-account-number"></a>Número de cuenta bancaria de Canadá

## <a name="format"></a>Formato

7 o 12 dígitos

## <a name="pattern"></a>Patrón

Un número de cuenta bancaria de Canadá es de 7 o 12 dígitos.

Un número de tránsito de cuenta bancaria de Canadá es:

- cinco dígitos
- un guion
- OR de tres dígitos
- un cero "0"
- ocho dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_canada_bank_account_number` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_canada_bank_account_number`.
- La expresión `Regex_canada_bank_account_transit_number` regular busca contenido que coincida con el patrón.

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_canada_bank_account_number` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_canada_bank_account_number`.

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_canada_bank_account_number"></a>Keyword_canada_bank_account_number

- canada savings bonds
- canada revenue agency
- canadian financial institution
- direct deposit form
- canadian citizen
- legal representative
- notary public
- commissioner for oaths
- child care benefit
- universal child care
- canada child tax benefit
- income tax benefit
- harmonized sales tax
- social insurance number
- income tax refund
- child tax benefit
- territorial payments
- institution number
- deposit request
- banking information
- direct deposit