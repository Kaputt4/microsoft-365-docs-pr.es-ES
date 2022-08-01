---
title: Definición de entidad de número de impuestos agregado del valor de Italia
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
description: Definición de entidad del tipo de información confidencial del número de impuestos agregado de Italia.
ms.openlocfilehash: d370ef3c46cf773791b3b0d599d546ea695a6e97
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000058"
---
# <a name="italy-value-added-tax-number"></a>Número del impuesto sobre el valor añadido de Italia

Este tipo de información confidencial solo está disponible para su uso en:

- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicación
- administración del ciclo de vida de los datos
- administración de registros
- Microsoft Defender for Cloud Apps

## <a name="format"></a>Formato

Patrón alfanumérico de 13 caracteres con delimitadores opcionales

## <a name="pattern"></a>Patrón

Patrón alfanumérico de 13 caracteres con delimitadores opcionales:

- Yo o yo
- T o t
- espacio opcional, punto, guion o coma
- 11 dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_italy_value_added_tax_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_italy_value_added_tax_number`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_italy_value_added_tax_number` encuentra contenido que coincide con el patrón.

```xml
      <!-- Italy Value Added Tax -->
      <Entity id="26a8cc07-2283-4a2a-ab1d-4ab643c4c67f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
          <Match idRef="Keywords_italy_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_italy_value_added_tax_number"></a>Keyword_italy_value_added_tax_number

- número de iva
- vat no
- Iva #
- iva
- iva #