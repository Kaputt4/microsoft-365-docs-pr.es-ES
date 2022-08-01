---
title: Definición de entidad de número civil uniforme de Bulgaria
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
description: Definición de entidad de tipo de información confidencial de número civil uniforme de Bulgaria.
ms.openlocfilehash: 95bbe1368ca4d6d91d98d07f5cd1c48029fd8499
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999164"
---
# <a name="bulgaria-uniform-civil-number"></a>Número del documento de identidad de Bulgaria

Este tipo de información confidencial solo está disponible para su uso en:

- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicación
- administración del ciclo de vida de los datos
- administración de registros
- Microsoft Defender for Cloud Apps

## <a name="format"></a>Formato

10 dígitos sin espacios ni delimitadores

## <a name="pattern"></a>Patrón

10 dígitos sin espacios ni delimitadores

- seis dígitos que corresponden a la fecha de nacimiento (AMMDD)
- dos dígitos que corresponden al orden de nacimiento
- un dígito que corresponde al género: un dígito par para el hombre y un dígito impar para la mujer
- un dígito de comprobación

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_bulgaria_eu_national_id_card` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_bulgaria_eu_national_id_card`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_bulgaria_eu_national_id_card` encuentra contenido que coincide con el patrón.

```xml
      <!-- Bulgaria Uniform Civil Number -->
      <Entity id="100d58b1-0a35-4fb1-aa89-e4a86fb53fcc" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Match idRef="Keywords_bulgaria_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_bulgaria_eu_telephone_number" />
            <Match idRef="Keywords_bulgaria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_bulgaria_eu_national_id_card"></a>Keywords_bulgaria_eu_national_id_card

- Bnn #
- Bnn
- bucn #
- bucn
- edinen grazhdanski nomer
- por ejemplo, #
- por ejemplo,
- identification number
- national id
- número nacional
- nationalnumber #
- nationalnumber
- id. personal
- personal no
- número personal
- personalidnumber #
- social security number
- Ssn #
- Ssn
- id. civil uniforme
- uniforme civil no
- número civil uniforme
- uniformcivilno #
- uniformcivilno
- uniformcivilnumber #
- uniformcivilnumber
- número de ciudadanía única
- егн #
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- униформ id
- униформ граждански id
- униформ граждански не
- униформ граждански номер
- униформгражданскиid #
- униформгражданскине. #