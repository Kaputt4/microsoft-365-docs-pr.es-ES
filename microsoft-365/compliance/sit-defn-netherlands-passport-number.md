---
title: Definición de entidad de número de pasaporte neerlandés
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
description: Definición de entidad de tipo de información confidencial de número de pasaporte neerlandés.
ms.openlocfilehash: 3766db12bbef6576f7bfb5d81b23fe3745bf4aa5
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999833"
---
# <a name="netherlands-passport-number"></a>Número de pasaporte de los Países Bajos

## <a name="format"></a>Formato

nueve letras o dígitos sin espacios ni delimitadores

## <a name="pattern"></a>Patrón

nueve letras o dígitos

## <a name="checksum"></a>Suma de comprobación

no aplicable

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_netherlands_eu_passport_number` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keywords_eu_passport_number` o `Keywords_netherlands_eu_passport_number`.
- La expresión `Regex_netherlands_eu_passport_date` regular busca la fecha con el formato DD MMM/MMM AAAA (ejemplo: 26 MAA/MAR 2012)

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_netherlands_eu_passport_number` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keywords_eu_passport_number` o `Keywords_netherlands_eu_passport_number`.

```xml
      <!-- Netherlands Passport Number -->
      <Entity id="61786727-bafd-45f6-94d9-888d815e228e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Regex_netherlands_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
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

### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- paspoort nummer
- paspoortnummers
- paspoortnummer
- paspoort nr