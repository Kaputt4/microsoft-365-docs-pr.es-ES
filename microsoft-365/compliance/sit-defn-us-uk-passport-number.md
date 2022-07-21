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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Estados Unidos/Reino Unido Definición de entidad de tipo de información confidencial de número de passport.
ms.openlocfilehash: 88caf63983d6f459f5ff201ae695f909489569cb
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66951076"
---
# <a name="usuk-passport-number"></a>Estados Unidos/Reino Unido passport number

## <a name="format"></a>Formato

nueve dígitos

## <a name="pattern"></a>Patrón

- una letra o dígito
- ocho dígitos

## <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP tiene una gran confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_usa_uk_passport` busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keywords_eu_passport_number` o `Keywords_uk_eu_passport_number` .
- Se encuentra una palabra clave de `Keywords_eu_passport_date`

Una directiva DLP tiene confianza media en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_usa_uk_passport` busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keywords_eu_passport_number` o `Keywords_uk_eu_passport_number` .

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

- Pasaporte #
- Pasaporte #
- passportid
- Pasaportes
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números de pasaporte

### <a name="keywords_uk_eu_passport_number"></a>Keywords_uk_eu_passport_number

- pasaporte británico
- uk passport