---
title: Definición de entidad del número de identificación de contribuyente individual (ITIN) de EE. UU.
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
description: Definición de entidad de tipo de información confidencial del número de identificación de contribuyente (ITIN) individual de EE. UU.
ms.openlocfilehash: c99635c29bb5b720ecc2d70577fe66d508ce9d9c
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000232"
---
# <a name="us-individual-taxpayer-identification-number-itin"></a>Número de identificación fiscal individual de EE. UU. (ITIN)

## <a name="format"></a>Formato

nueve dígitos que comienzan con un "9" y contienen un "7" o "8" como cuarto dígito, con formato opcional con espacios o guiones

## <a name="pattern"></a>Patrón

Formato:

- el dígito "9"
- dos dígitos
- un espacio o guion
- un "7" o "8"
- un dígito
- un espacio o guion
- cuatro dígitos

sin formato:

- el dígito "9"
- dos dígitos
- un "7" o "8"
- cinco dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_formatted_itin` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_itin`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_unformatted_itin` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_itin`.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_formatted_itin` o `Func_unformatted_itin` encuentra contenido que coincide con el patrón.

```xml
    <!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
    <Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_formatted_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_unformatted_itin" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_itin"></a>Keyword_itin

- Contribuyente
- tax id
- tax identification
- Itin
- i.t.i.n.
- Ssn
- Lata
- social security
- tax payer
- Itin
- taxid
- individual taxpayer