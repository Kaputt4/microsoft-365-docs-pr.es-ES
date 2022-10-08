---
title: Definición de entidad del código de identificación personal de Estonia
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
description: Definición de entidad de tipo de información confidencial del código de identificación personal de Estonia.
ms.openlocfilehash: d14d5cade3a714cdae5983470960dd0144d2082e
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68361677"
---
# <a name="estonia-personal-identification-code"></a>Número del documento de identidad de Estonia

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

11 dígitos sin espacios ni delimitadores

## <a name="pattern"></a>Patrón

11 dígitos:

- un dígito que corresponde al sexo y siglo de nacimiento (número impar varón, número par femenino; 1-2: siglo XIX; 3-4: siglo XX; 5-6: siglo XXI)
- seis dígitos que corresponden a la fecha de nacimiento (AMMDD)
- tres dígitos que corresponden a un número de serie que separa a las personas nacidas en la misma fecha
- un dígito de comprobación

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_estonia_eu_national_id_card` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_estonia_eu_national_id_card`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_estonia_eu_national_id_card` encuentra contenido que coincide con el patrón.

```xml
      <!-- Estonia Personal Identification Code -->
      <Entity id="bfb26de6-dad5-4d48-ab72-4789cdd0654c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_estonia_eu_telephone_number" />
            <Match idRef="Keywords_estonia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

- id-kaart
- Ik
- isikukood #
- isikukood
- maksu id
- maksukohustuslase identifitseerimisnumber
- maksunumber
- national identification number
- número nacional
- código personal
- número de id. personal
- código de identificación personal
- número de identificación personal
- personalidnumber #
- tax id
- núm. identificación fiscal
- número de identificación fiscal
- n.º de id. fiscal#
- n.º fiscal
- número de id. fiscal
- número de registro fiscal
- Id.fiscal#
- númidfiscal#
- númeroidentificaciónfiscal#
- núm.fiscal#
- núm.id.fiscal#
- núm.id.fisca
- id. tributaria
- n.º de id. tributario
- Número de identificación tributaria
