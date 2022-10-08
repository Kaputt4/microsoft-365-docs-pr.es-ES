---
title: Definición de entidad de número de tarjeta de identidad de Alemania
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
description: Definición de entidad de tipo de información confidencial del número de tarjeta de identidad de Alemania.
ms.openlocfilehash: e37f941d959e633f1d51f8bed6b8164bb071e648
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68379972"
---
# <a name="germany-identity-card-number"></a>Número del documento de identidad de Alemania

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

desde el 1 de noviembre de 2010: de nueve a 11 letras y dígitos

del 1 de abril de 1987 al 31 de octubre de 2010: 10 dígitos

## <a name="pattern"></a>Patrón

desde el 1 de noviembre de 2010: patrón alfanumérico de 9 a 11 caracteres
- una L, M, N, P, R, T, V, W, X, Y (sin distinción entre mayúsculas y minúsculas)
- ocho dígitos o letras en C, F, G, H, J, K, L, M, N, P, R, T, V, W, X, Y y Z (sin distinción entre mayúsculas y minúsculas)
- dígito de comprobación opcional
- D/D opcional

del 1 de abril de 1987 al 31 de octubre de 2010:

- 10 dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_german_id_card_with_check` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_germany_id_card`.
- Se supera la suma de comprobación.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_germany_id_card` regular busca contenido que coincida con el patrón (9 caracteres sin dígito de comprobación emitidos antes de 2010 o patrón de 10 dígitos emitido posy 2010).
- Se encuentra una palabra clave de `Keyword_germany_id_card`.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_german_id_card_with_check` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
      <!-- Germany Identity Card Number -->
      <Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
         <IdMatch idRef="Regex_germany_id_card" />
         <Match idRef="Keyword_germany_id_card" />
        </Pattern>
        <Version minEngineVersion="15.20.4545.000">
          <Pattern confidenceLevel="85">
           <IdMatch idRef="Func_german_id_card_with_check" />
            <Match idRef="Keyword_germany_id_card" />
          </Pattern>
          <Pattern confidenceLevel="65">
           <IdMatch idRef="Func_german_id_card_with_check" />
          </Pattern>
        </Version>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- ausweis
- gpid
- Identificación
- identificación
- identifizierungsnummer
- documento de identidad
- número de identidad
- id-nummer
- id. personal
- personalausweis
- persönliche id nummer
- persönliche identifikationsnummer
- persönliche-id-nummer
