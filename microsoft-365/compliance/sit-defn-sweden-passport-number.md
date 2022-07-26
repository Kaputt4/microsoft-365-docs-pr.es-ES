---
title: Definición de entidad de número de pasaporte de Suecia
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
description: Definición de entidad de tipo de información confidencial del número de pasaporte de Suecia.
ms.openlocfilehash: 497965aea803a162fc97bb64fa456191f8788aab
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999080"
---
# <a name="sweden-passport-number"></a>Número de pasaporte de Suecia

## <a name="format"></a>Formato

ocho dígitos

## <a name="pattern"></a>Patrón

ocho dígitos consecutivos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- la expresión regular Regex_sweden_passport_number busca contenido que coincida con el patrón.
- se encuentra una palabra clave de `Keywords_eu_passport_number` o `Keyword_sweden_passport` .
- la expresión `Regex_sweden_eu_passport_date` regular busca una fecha con el formato DD MMM/MMM YY (01 JAN/JAN 12) o se encuentra una palabra clave de `Keywords_eu_passport_date` .

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- la expresión regular Regex_sweden_passport_number busca contenido que coincida con el patrón.
- se encuentra una palabra clave de `Keywords_eu_passport_number` o `Keyword_sweden_passport` .

```xml
    <!-- Sweden Passport Number -->
    <Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_sweden_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
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

### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- tarjeta de registro de extranjeros
- Tarifas de procesamiento g3
- entrada múltiple
- Numéro de passeport
- passeport n °
- passeport non
- passeport #
- passeport #
- passeportnon
- passeportn °
- passnummer
- pass nr
- visa schengen
- visados schengen
- entrada única
- sverige pass
- visa requirements
- tramitación de visados
- tipo visa

### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha de emisión
- fecha de expiración