---
title: Definición de entidad de número de identificación personal de Hungría
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
description: Definición de entidad de tipo de información confidencial del número de identificación personal de Hungría.
ms.openlocfilehash: ee3a22ffccdf9110d36e49013bfed912b2d2319b
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367277"
---
# <a name="hungary-personal-identification-number"></a>Número del documento de identidad de Hungría

## <a name="format"></a>Formato

11 dígitos

## <a name="pattern"></a>Patrón

11 dígitos:

- Un dígito que corresponde al género, 1 para el hombre, 2 para la mujer. Otros números también son posibles para ciudadanos nacidos antes de 1900 o ciudadanos con doble ciudadanía.
- Seis dígitos que corresponden a la fecha de nacimiento (AMMDD)
- Tres dígitos que corresponden a un número de serie
- Un dígito de comprobación

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_hungary_eu_national_id_card` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_hungary_eu_national_id_card`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_hungary_eu_national_id_card` encuentra contenido que coincide con el patrón.

```xml
      <!-- Hungary Personal Identification Number -->
      <Entity id="7b5cc218-7046-47d9-80c9-f325b50896ca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

- número de id.
- identification number
- sz ig
- Sz. Ig.
- sz.ig.
- személyazonosító igazolvány
- személyi igazolvány