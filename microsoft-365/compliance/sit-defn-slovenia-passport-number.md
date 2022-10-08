---
title: Definición de entidad de número de pasaporte de Eslovenia
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
description: Definición de entidad de tipo de información confidencial de número de pasaporte de Eslovenia.
ms.openlocfilehash: d01581a14f50c41252f134b12a5ffe00d5971f77
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68470594"
---
# <a name="slovenia-passport-number"></a>Número de pasaporte de Eslovenia

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

dos letras seguidas de siete dígitos sin espacios ni delimitadores

## <a name="pattern"></a>Patrón

dos letras seguidas de siete dígitos:

- la letra "P"
- una letra mayúscula
- siete dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular `Regex_slovenia_eu_passport_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_eu_passport_number` o `Keywords_slovenia_eu_passport_number`.
- La expresión `Regex_eu_passport_date1` regular busca la fecha con el formato DD.MM.AAAA o se encuentra una palabra clave de .`Keywords_eu_passport_date`

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular `Regex_slovenia_eu_passport_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_eu_passport_number` o `Keywords_slovenia_eu_passport_number`.

```xml
      <!-- Slovenia Passport Number -->
      <Entity id="235b7976-7bbe-4df5-bb40-08678e749d1a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
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

### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- številka potnega lista
- potek veljavnosti
- lista de potni #
- datum rojstva
- lista de potni
- številke potnih listov

### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha de emisión
- fecha de expiración
