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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Definición de entidad de tipo de información confidencial de tarjeta de Medicare Beneficiary Identifier (MBI).
ms.openlocfilehash: 601c34adcb0f9b19ab2c23a3df7d1c574cdd5031
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66951271"
---
# <a name="medicare-beneficiary-identifier-mbi-card"></a>Tarjeta de identificador de beneficiario de Medicare (MBI)

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

Una directiva DLP tiene una gran confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_mbi_card` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_mbi_card` .

Una directiva DLP tiene confianza media en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_mbi_card` regular busca contenido que coincida con el patrón.

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