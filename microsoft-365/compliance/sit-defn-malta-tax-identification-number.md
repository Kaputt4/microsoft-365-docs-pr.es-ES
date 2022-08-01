---
title: Definición de entidad de número de identificación fiscal de Malta
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
description: Definición de entidad del tipo de información confidencial del número de identificación fiscal de Malta.
ms.openlocfilehash: 5f77f6755ff69bf200a3999e684901bf39bdf6d9
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999569"
---
# <a name="malta-tax-identification-number"></a>Número de identificación fiscal de Malta

## <a name="format"></a>Formato

Para los ciudadanos malteses:

- siete dígitos y una letra en el patrón especificado

Nacionales no malteses y entidades maltesas:

- nueve dígitos

## <a name="pattern"></a>Patrón

Ciudadanos malteses: siete dígitos y una letra

- siete dígitos
- una letra (no distingue mayúsculas de minúsculas)

Nacionales no malteses y entidades maltesas: nueve dígitos

- nueve dígitos

## <a name="checksum"></a>Suma de comprobación

No aplicable

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- El objeto regex `Regex_malta_eu_tax_file_number`  o `Regex_malta_eu_tax_file_number_non_maltese_national` busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keywords_malta_eu_tax_file_number`.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- El objeto regex `Regex_malta_eu_tax_file_number` o `Regex_malta_eu_tax_file_number_non_maltese_national` busca contenido que coincida con el patrón.

```xml
      <!-- Malta Tax ID Number -->
      <Entity id="ec830c63-65f4-45d0-9d8c-910dc8334b20" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

- número de servicio ciudadano
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- código numérico personal
- tax id
- identificación fiscal no
- número de identificación fiscal
- impuestos no #
- impuestos no
- número de impuestos
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- Lata #
- número de identificación único
- número de identidad único
- uniqueidentityno #