---
title: Definición de entidad de número de identificación fiscal de Suecia
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
description: Definición de entidad de tipo de información confidencial del número de identificación fiscal de Suecia.
ms.openlocfilehash: 8e7691d478ab23a1b454bab0f0a739f60d9ac59e
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472593"
---
# <a name="sweden-tax-identification-number"></a>Número de identificación fiscal de Suecia

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

10 dígitos y un símbolo en el patrón especificado

## <a name="pattern"></a>Patrón

10 dígitos y un símbolo:

- seis dígitos que corresponden a la fecha de nacimiento (AMMDD)
- signo más o signo menos
- tres dígitos que hacen que el número de identificación sea único donde:
  - para los números emitidos antes de 1990, el séptimo y octavo dígito identifican el condado de nacimiento o personas nacidas en el extranjero
  - el dígito en la novena posición indica el género por impar para el hombre o incluso para la mujer
- un dígito de comprobación

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_sweden_eu_tax_file_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_sweden_eu_tax_file_number`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_sweden_eu_tax_file_number` encuentra contenido que coincide con el patrón.

```xml
      <!-- Sweden Tax Identification Number -->
      <Entity id="139acba0-a5bc-4fbb-876d-f7a493ae8a40" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_sweden_eu_telephone_number" />
            <Match idRef="Keywords_sweden_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

- número de id. personal
- personnummer
- skatt id nummer
- skatt identifikation
- skattebetalarens identifikationsnummer
- sverige tin
- archivo de impuestos
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
