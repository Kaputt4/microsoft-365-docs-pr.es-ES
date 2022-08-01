---
title: Definición de entidad de número de pasaporte de Australia
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
description: Definición de entidad de tipo de información confidencial del número de pasaporte de Australia.
ms.openlocfilehash: 9f879dc2f071398f7c3ba49b7fcded8be220e07b
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999524"
---
# <a name="australia-passport-number"></a>Número de pasaporte de Australia

## <a name="format"></a>Formato

ocho o nueve caracteres alfanuméricos

## <a name="pattern"></a>Patrón

- una letra (N, E, D, F, A, C, U, X) seguida de siete dígitos o
- Dos letras (PA, PB, PC, PD, PE, PF, PU, PW, PX, PZ) seguidas de siete dígitos.

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_australia_passport_number` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_australia_passport_number`.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_australia_passport_number` regular busca contenido que coincida con el patrón.

```xml
    <!-- Australia Passport Number -->
    <Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Match idRef="Keyword_australia_passport_number" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_australia_passport_number" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

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
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- national identity card
- travel document
- issuing authority