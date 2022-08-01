---
title: Definición de entidad de número de impuestos de valor agregado de Países Bajos
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
description: Definición de entidad de tipo de información confidencial del número de impuestos de los Países Bajos.
ms.openlocfilehash: 478f2086a29e610f098f64b48c3debd9a30e22cd
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999830"
---
# <a name="netherlands-value-added-tax-number"></a>Número del impuesto sobre el valor añadido de los Países Bajos

Este tipo de información confidencial solo está disponible para su uso en:

- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicación
- administración del ciclo de vida de los datos
- administración de registros
- Microsoft Defender for Cloud Apps

## <a name="format"></a>Formato

Patrón alfanumérico de 14 caracteres

## <a name="pattern"></a>Patrón

Patrón alfanumérico de 14 caracteres:

- N o n
- L o l
- espacio opcional, punto o guion
- nueve dígitos
- espacio opcional, punto o guion
- B o b
- dos dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_netherlands_value_added_tax_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_netherlands_value_added_tax_number`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_netherlands_value_added_tax_number` encuentra contenido que coincide con el patrón.

```xml
      <!-- Netherlands Value Added Tax Number -->
      <Entity id="4f320d9b-4972-41ae-b337-88d499bb1ade" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
          <Match idRef="Keywords_netherlands_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_netherlands_value_added_tax_number"></a>Keyword_netherlands_value_added_tax_number

- número de iva
- vat no
- Iva #
- wearde tafoege tax getal
- btw nûmer
- btw-nummer