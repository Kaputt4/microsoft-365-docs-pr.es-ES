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
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Definición de entidad del tipo de información confidencial del número de identificación fiscal de Malta.
ms.openlocfilehash: 6d483f84ad64f7d85eb5d28a33777be516d5c2df
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68384149"
---
# <a name="malta-tax-identification-number"></a>Número de identificación fiscal de Malta

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

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
- número de identificación único
- número de identidad único
- uniqueidentityno #
