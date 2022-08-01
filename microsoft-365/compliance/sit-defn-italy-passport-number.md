---
title: Definición de entidad de número de pasaporte de Italia
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
description: Definición de entidad de tipo de información confidencial del número de pasaporte de Italia.
ms.openlocfilehash: 5ee8c1d55fd29ccd370d645711125ed10b1bf740
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999878"
---
# <a name="italy-passport-number"></a>Número de pasaporte de Italia

## <a name="format"></a>Formato

dos letras o dígitos seguidos de siete dígitos sin espacios ni delimitadores

## <a name="pattern"></a>Patrón

dos letras o dígitos seguidos de siete dígitos:

- dos dígitos o letras (no distinguen mayúsculas de minúsculas)
- siete dígitos

## <a name="checksum"></a>Suma de comprobación

no aplicable

### <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_italy_eu_passport_number` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keywords_eu_passport_number` o `Keywords_italy_eu_passport_number`.
- La expresión `Regex_italy_eu_passport_date` regular busca la fecha con el formato DD MMM/MMM AAAA (ejemplo: 01 GEN/JAN 1988) o se encuentra una palabra clave de .`Keywords_eu_passport_date`

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_italy_eu_passport_number` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keywords_eu_passport_number` o `Keywords_italy_eu_passport_number`.

```xml
      <!-- Italy Passport Number -->
      <Entity id="39811019-4750-445f-b26d-4c0e6c431544" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_italy_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
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

### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- italiana passaporto
- passaporto italiana
- passaporto numero
- numéro passeport
- numero di passaporto
- numeri del passaporto
- passeport italien

### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha de emisión
- fecha de expiración