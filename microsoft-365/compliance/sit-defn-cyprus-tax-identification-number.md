---
title: Definición de entidad de número de identificación fiscal de Chipre
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
description: Definición de entidad del tipo de información confidencial del número de identificación fiscal de Chipre.
ms.openlocfilehash: 7fc56c9ddc21e85d7471d8f270af81d0723d7e78
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68363307"
---
# <a name="cyprus-tax-identification-number"></a>Número de identificación fiscal de Chipre

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

ocho dígitos y una letra en el patrón especificado

## <a name="pattern"></a>Patrón

ocho dígitos y una letra:

- un "0" o "9"
- siete dígitos
- una letra (no distingue mayúsculas de minúsculas)

## <a name="checksum"></a>Suma de comprobación

no aplicable

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_cyprus_eu_tax_file_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_cyprus_eu_tax_file_number`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_cyprus_eu_tax_file_number` encuentra contenido que coincide con el patrón.

```xml
      <!-- Cyprus Tax Identification Number -->
      <Entity id="40e64bd9-55f3-4a09-9bd6-1db18dced9dd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_cyprus_eu_tax_file_number"></a>Keywords_cyprus_eu_tax_file_number

- tax id
- código de identificación fiscal
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
- Tic #
- Tic
- id. tributaria
- n.º de id. tributario
- Número de identificación tributaria
- vergi kimlik kodu
- vergi kimlik numarası
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού
