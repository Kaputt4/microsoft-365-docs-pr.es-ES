---
title: Definición de entidad de número de impuestos de valor agregado de Bélgica
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
description: Definición de entidad de tipo de información confidencial del número de impuestos agregado de Bélgica.
ms.openlocfilehash: 59411672288d3a9c47aef1a54a7d4727876a498f
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999206"
---
# <a name="belgium-value-added-tax-number"></a>Número del impuesto sobre el valor añadido de Bélgica

Este tipo de información confidencial solo está disponible para su uso en:

- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicación
- administración del ciclo de vida de los datos
- administración de registros
- Microsoft Defender for Cloud Apps

## <a name="format"></a>Formato

Patrón alfanumérico de 12 caracteres

## <a name="pattern"></a>Patrón

Patrón alfanumérico de 12 caracteres:

- una letra B o b
- una letra E o e
- un dígito 0
- un dígito de 1 a 9
- un punto opcional, un guion o un espacio
- cuatro dígitos
- un punto opcional, un guion o un espacio
- cuatro dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_belgium_value_added_tax_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_belgium_value_added_tax_number`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_belgium_value_added_tax_number` encuentra contenido que coincide con el patrón.

```xml
      <!-- Belgium Value Added Tax Number -->
      <Entity id="85b5b3c3-f2de-4ae8-ac46-fd3cb38bf9ed" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
          <Match idRef="Keywords_belgium_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
        </Pattern>
      </Entity>
    </Version>
```
## <a name="keywords"></a>Palabras clave

### <a name="keyword_belgium_value_added_tax_number"></a>Keyword_belgium_value_added_tax_number

- nº tva
- número de iva
- vat no
- numéro t.v.a
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- Por cierto
- Por cierto #
- Iva #
