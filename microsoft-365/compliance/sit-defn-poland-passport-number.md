---
title: Definición de entidad de número de pasaporte de Polonia
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
description: Definición de entidad de tipo de información confidencial del número de pasaporte de Polonia.
ms.openlocfilehash: 10f6b0b849053773059232f5faeba8300a02131d
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68470022"
---
# <a name="poland-passport-number"></a>Número de pasaporte de Polonia

Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial Número de pasaporte de la UE. También está disponible como una entidad de tipo de información confidencial independiente.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

dos letras y siete dígitos

## <a name="pattern"></a>Patrón

Dos letras (sin distinguir mayúsculas de minúsculas) seguidas de siete dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_polish_passport_number_v2` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.
- Se encuentra una palabra clave de `Keywords_eu_passport_number` o `Keyword_polish_national_passport_number`.
- Se encuentra una palabra clave de `Keywords_eu_passport_date`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_polish_passport_number_v2` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.
- Se encuentra una palabra clave de `Keywords_eu_passport_number` o `Keyword_polish_national_passport_number`.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_polish_passport_number_v2` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
      <!-- Poland Passport Number -->
      <Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_passport_number_v2" />
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

### <a name="keyword_polish_national_passport_number"></a>Keyword_polish_national_passport_number

- numer paszportu
- numery paszportów
- numery paszportowe
- nr paszportu
- N.º paszportu
- nr paszportów
- n° passeport
- passeport n°

### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- fecha de emisión
- fecha de expiración
