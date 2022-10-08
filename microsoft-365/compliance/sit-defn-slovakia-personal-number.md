---
title: Definición de entidad de número personal de Eslovaquia
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
description: Definición de entidad de tipo de información confidencial de número personal de Eslovaquia.
ms.openlocfilehash: 3783022b44917e8b2d14144db4b5f27f9cb8b4ec
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68471692"
---
# <a name="slovakia-personal-number"></a>Número del documento de identidad de Eslovaquia

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

nueve o 10 dígitos que contienen barra diagonal inversa opcional

## <a name="pattern"></a>Patrón

- seis dígitos que representan la fecha de nacimiento
- barra diagonal opcional (/)
- tres dígitos
- un dígito de comprobación opcional

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_slovakia_eu_national_id_card` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_slovakia_eu_national_id_card`.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_slovakia_eu_national_id_card` encuentra contenido que coincide con el patrón.

```xml
      <!-- Slovakia Personal Number -->
      <Entity id="951c26b7-3b35-4f73-924b-15dd599cb9ab" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
      </Entity>
    </Version>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

- azonosító szám
- número de nacimiento
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- número de id.
- identificación no
- identification number
- identifikačná karta č
- identifikačné číslo
- identity card no
- número de tarjeta de identidad
- národná identifikačná značka č
- número nacional
- nationalnumber #
- nemzeti személyazonosító igazolvány
- personalidnumber #
- rč
- rodne cislo
- rodné číslo
- social security number
- númeroseguridadsocial#
- ssn
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- archivo fiscal no
- tax file number
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
