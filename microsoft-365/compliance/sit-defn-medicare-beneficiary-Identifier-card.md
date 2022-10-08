---
title: Definición de entidad de tarjeta del identificador de beneficiario de Medicare (MBI)
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
description: Definición de entidad de tipo de información confidencial de tarjeta de Medicare Beneficiary Identifier (MBI).
ms.openlocfilehash: 7ee3545a7a0eb177f7cf8cbb6581aa43546c8f88
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68382499"
---
# <a name="medicare-beneficiary-identifier-mbi-card"></a>Tarjeta de beneficiario de Medicare (MBI)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

Patrón alfanumérico de 11 caracteres

## <a name="pattern"></a>Patrón

- un dígito entre 1 y 9
- una letra excepto S, L, O, I, B, Z
- un dígito o letra excepto S, L, O, I, B, Z
- un dígito
- un guion opcional
- una letra excepto S, L, O, I, B, Z
- un dígito o letra excepto S, L, O, I, B, Z
- un dígito
- un guion opcional
- dos letras excepto S, L, O, I, B, Z
- dos dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular `Regex_mbi_card` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_mbi_card`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular `Regex_mbi_card` encuentra contenido que coincide con el patrón.

```xml
    <!-- Medicare Beneficiary Identifier (MBI) card -->
      <Entity id="f753a286-f5cc-47e6-a592-4be25fd02591" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_mbi_card" />
          <Match idRef="Keyword_mbi_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_mbi_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_mbi_card"></a>Keyword_mbi_card

- Mbi
- Mbi #
- beneficiario de medicare #
- identificador de beneficiario de medicare
- medicare beneficiary no
- medicare beneficiary number
- beneficiario de medicare #
