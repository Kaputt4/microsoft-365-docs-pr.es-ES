---
title: Definición de entidad de id. nacional de Suecia
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
description: Definición de entidad de tipo de información confidencial del identificador nacional de Suecia.
ms.openlocfilehash: 77d0fd72a4293bdc8cae0aa806899b30baa21ed8
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000226"
---
# <a name="sweden-national-id"></a>Número del documento nacional de identidad de Suecia

## <a name="format"></a>Formato

10 o 12 dígitos y un delimitador opcional

## <a name="pattern"></a>Patrón

10 o 12 dígitos y un delimitador opcional:

- dos dígitos (opcional)
- Seis dígitos en fecha de formato AAMMDD
- delimitador de "-" o "+" (opcional)
- cuatro dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_swedish_national_identifier` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_swedish_national_identifier`
- Se supera la suma de comprobación.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_swedish_national_identifier` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
    <!-- Sweden National ID -->
    <Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
        <Match idRef="Keywords_swedish_national_identifier" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_swedish_national_identifier" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_swedish_national_identifier"></a>Keywords_swedish_national_identifier

- id no
- número de id.
- Id #
- identificación no
- identification number
- identifikationsnumret #
- identifikationsnumret
- identitetshandling
- documento de identidad
- identity no
- número de identidad
- id-nummer
- id. personal
- personnummer #
- personnummer
- skatteidentifikationsnummer