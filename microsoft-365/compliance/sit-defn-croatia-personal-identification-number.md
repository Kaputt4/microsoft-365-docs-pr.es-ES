---
title: Definición de entidad de número de identificación personal (OIB) de Croacia
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
description: Definición de entidad de tipo de información confidencial de número de identificación personal (OIB) de Croacia.
ms.openlocfilehash: 683ee32f3e12255583958766e1d94efd6eeedfb7
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68362978"
---
# <a name="croatia-personal-identification-oib-number"></a>Número del documento de identidad de Croacia (OIB)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

11 dígitos

## <a name="pattern"></a>Patrón

11 dígitos:

- 10 dígitos
- el último dígito es un dígito de comprobación

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_croatia_oib_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_croatia_eu_tax_file_number`.
- Se supera la suma de comprobación.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_croatia_oib_number` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
      <!-- Croatia Personal Identification (OIB) Number -->
      <Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_oib_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_oib_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

- majstorski broj građana
- número de ciudadano maestro
- nacionalni identifikacijski broj
- national identification number
- oib #
- oib
- osobna iskaznica
- osobni id.
- osobni identifikacijski broj
- número de identificación personal
- porezni broj
- porezni identifikacijski broj
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
