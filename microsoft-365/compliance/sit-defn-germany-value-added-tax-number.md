---
title: Definición de entidad de número de impuestos agregados de Alemania
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
description: Definición de entidad de tipo de información confidencial del número de impuestos agregado de Alemania.
ms.openlocfilehash: 831b38ea1fcc7fe952ed28dc595e1d4a471ed505
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999602"
---
# <a name="germany-value-added-tax-number"></a>Número del impuesto sobre el valor añadido de Alemania

Este tipo de información confidencial solo está disponible para su uso en:

- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicación
- administración del ciclo de vida de los datos
- administración de registros
- Microsoft Defender for Cloud Apps

## <a name="format"></a>Formato

Patrón alfanumérico de 11 caracteres

## <a name="pattern"></a>Patrón

Patrón alfanumérico de 11 caracteres:

- una letra D o d
- una letra E o e
- un espacio opcional
- tres dígitos
- un espacio opcional o una coma
- tres dígitos
- un espacio opcional o una coma
- tres dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_germany_value_added_tax_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_germany_value_added_tax_number`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_germany_value_added_tax_number` encuentra contenido que coincide con el patrón.

```xml
      <!-- Germany Value Added Tax Number -->
      <Entity id="db177eb2-8811-4842-bffc-128c14aa219f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
          <Match idRef="Keywords_germany_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
        </Pattern>
      </Entity>
```
## <a name="keywords"></a>Palabras clave

### <a name="keyword_germany_value_added_tax_number"></a>Keyword_germany_value_added_tax_number

- número de iva
- vat no
- Iva #
- vat# mehrwertsteuer
- mwst
- mehrwertsteuer identifikationsnummer
- mehrwertsteuer nummer