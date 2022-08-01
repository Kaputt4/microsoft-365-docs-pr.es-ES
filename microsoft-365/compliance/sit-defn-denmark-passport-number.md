---
title: Definición de entidad de número de pasaporte de Dinamarca
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
description: Definición de entidad de tipo de información confidencial del número de pasaporte de Dinamarca.
ms.openlocfilehash: fec977abcdb4a942910a1d2ccbbb948348ef0119
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999161"
---
# <a name="denmark-passport-number"></a>Número de pasaporte de Dinamarca

## <a name="format"></a>Formato

nueve dígitos sin espacios ni delimitadores

## <a name="pattern"></a>Patrón

nueve dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_denmark_eu_passport_number` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keywords_eu_passport_number` o `Keywords_denmark_eu_passport_number`.
- La expresión `Regex_eu_passport_date2` regular busca la fecha con el formato DD MM AAAA o se encuentra una palabra clave de .`Keywords_eu_passport_date`

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_denmark_eu_passport_number` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keywords_eu_passport_number` o `Keywords_denmark_eu_passport_number`.

```xml
      <!-- Denmark Passport Number -->
      <Entity id="25e8c47e-e6fe-4884-a211-74898f8c0196" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

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

### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- pasnummer
- Passeport n°
- pasnumre

### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha de emisión
- fecha de expiración