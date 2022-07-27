---
title: Definición de entidad de clave única de identificación tributaria (CUIT/CUIL) de Argentina
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
description: Definición de entidad de tipo de información confidencial de clave única de identificación tributaria (CUIT/CUIL) de Argentina.
ms.openlocfilehash: d38cb0a972add240087c816399abf30d3d9ef670
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000022"
---
# <a name="argentina-unique-tax-identification-key-cuitcuil"></a>Clave única de identificación tributaria de Argentina (CUIT/CUIL)

## <a name="format"></a>Formato

11 dígitos con guion

## <a name="pattern"></a>Patrón

11 dígitos con un guión:

- dos dígitos en 20, 23, 24, 27, 30, 33 o 34
- un guion (-)
- ocho dígitos
- un guion (-)
- un dígito de comprobación

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_Argentina_Unique_Tax_Key` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_Argentina_Unique_Tax_Key`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_Argentina_Unique_Tax_Key` encuentra contenido que coincide con el patrón.

```xml
    <!-- Argentina Unique Tax Identification Key (CUIT/CUIL) -->
      <Entity id="98da3da1-9199-4571-b7c4-b6522980b507" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
          <Match idRef="Keyword_Argentina_Unique_Tax_Key" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_argentina_unique_tax_key"></a>Keyword_Argentina_Unique_Tax_Key

- Clave Unica de Identificacion Tributaria
- CUIT
- código único de identificación laboral
- Clave Única de Identificación Tributaria
- código de identificación laboral único
- CUIL
- Clave única de identificación tributaria
- Clave de identificación laboral única
- Clave única de identificación laboral
- Código de identificación de trabajo único
- Identificación del código único de trabajo
- Clave de identificación de trabajo única
- Clave única de identificación de trabajo
- Código único de identificación fiscal
- Clave única de identificación fiscal
- Código de identificación laboral único
- Código único de identificación laboral
- Clave de identificación única de trabajo
- Clave única de identificación laboral
- Id. fiscal
- #idfiscal
- Idfiscal
- númeroidentificaciónfiscal
- número de id. fiscal
- n.º de id. fiscal
- # fiscal
- #fiscal
- Id. de contribuyente
- número de contribuyente
- n.º de contribuyente
- # de contribuyente
- #contribuyente
- identidad fiscal
- tax identification
- Número de Identificación Fiscal
- número de contribuyente