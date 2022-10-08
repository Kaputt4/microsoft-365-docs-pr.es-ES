---
title: Estados Unidos/Reino Unido definición de entidad de número de passport
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
description: Estados Unidos/Reino Unido Definición de entidad de tipo de información confidencial de número de passport.
ms.openlocfilehash: 96e3f270cfa49cc63a263b54960afb19c27aa3df
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68471890"
---
# <a name="usuk-passport-number"></a>Estados Unidos/Reino Unido passport number

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

nueve dígitos

## <a name="pattern"></a>Patrón

- una letra o un dígito
- ocho dígitos

## <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_usa_uk_passport` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_eu_passport_number` o `Keywords_uk_eu_passport_number`.
- Se encuentra una palabra clave de `Keywords_eu_passport_date`

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_usa_uk_passport` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_eu_passport_number` o `Keywords_uk_eu_passport_number`.

```xml
    <!-- U.S. / U.K. Passport Number -->
    <Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
       <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

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

### <a name="keywords_uk_eu_passport_number"></a>Keywords_uk_eu_passport_number

- pasaporte británico
- uk passport
