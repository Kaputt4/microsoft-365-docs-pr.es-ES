---
title: Reino Unido Definición de entidad de número de referencia de contribuyente único
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
description: Reino Unido Definición de entidad de tipo de información confidencial número de contribuyente único.
ms.openlocfilehash: 2e11ebcdeab402cbba9710e4b8658fd3ab63b7c2
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472088"
---
# <a name="uk-unique-taxpayer-reference-number"></a>Reino Unido Número único de identificación fiscal

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

10 dígitos sin espacios ni delimitadores

## <a name="pattern"></a>Patrón

10 dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_uk_eu_tax_file_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_uk_eu_tax_file_number`.

```xml
      <!-- U.K. Unique Taxpayer Reference Number -->
      <Entity id="ad4a8116-0db8-439a-b545-6d967642f0ec" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_uk_eu_tax_file_number"></a>Keywords_uk_eu_tax_file_number

- número de id. fiscal
- archivo de impuestos
- tax id
- núm. identificación fiscal
- número de identificación fiscal
- n.º de id. fiscal#
- n.º fiscal
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
