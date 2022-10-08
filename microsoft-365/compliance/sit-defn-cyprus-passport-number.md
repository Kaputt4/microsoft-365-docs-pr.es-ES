---
title: Definición de entidad de número de pasaporte de Chipre
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
description: Definición de entidad de tipo de información confidencial del número de pasaporte de Chipre.
ms.openlocfilehash: 8c45d9988cf56a0add6e12c1e58aa2bfe2469c53
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68361790"
---
# <a name="cyprus-passport-number"></a>Número de pasaporte de Chipre

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

una letra seguida de 6-8 dígitos sin espacios ni delimitadores

## <a name="pattern"></a>Patrón

una letra seguida de seis a ocho dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular `Regex_cyprus_eu_passport_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_eu_passport_number` o `Keywords_cyprus_eu_passport_number`.
- La expresión `Regex_cyprus_eu_passport_date` regular busca la fecha con el formato DD/MM/AAAA o se encuentra una palabra clave de `Keywords_cyprus_eu_passport_date`

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular `Regex_cyprus_eu_passport_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_eu_passport_number` o `Keywords_cyprus_eu_passport_number`.

```xml
      <!-- Cyprus Passport Number -->
      <Entity id="9193e2e8-7f8c-43c1-a274-ac40d651936f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_cyprus_eu_passport_date" />
            <Match idRef="Keywords_cyprus_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- pasaporte#
- pasaporte #
- passportid
- pasaportes
- passportno
- pasaporte no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

### <a name="keywords_cyprus_eu_passport_number"></a>Keywords_cyprus_eu_passport_number

- αριθμό διαβατηρίου
- pasaportu
- Αριθμός Διαβατηρίου
- κυπριακό διαβατήριο
- διαβατήριο #
- διαβατήριο
- αριθμός διαβατηρίου
- Pasaport Kimliği
- pasaport numarası
- Pasaport no.
- Αρ. Διαβατηρίου

### <a name="keywords_cyprus_eu_passport_date"></a>Keywords_cyprus_eu_passport_date

- expira el
- emitido en
