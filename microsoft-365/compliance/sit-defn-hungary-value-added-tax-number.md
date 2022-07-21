---
title: Definición de entidad de número de impuestos de valor agregado de Hungría
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
description: Definición de entidad del tipo de información confidencial del número de impuestos agregado de Hungría.
ms.openlocfilehash: 3ebc5921e0fd09fb98b1e86699aa3941bd214b96
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66951039"
---
# <a name="hungary-value-added-tax-number"></a>Número de impuestos sobre el valor añadido de Hungría

Este tipo de información confidencial solo está disponible para su uso en:

- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicación
- administración del ciclo de vida de los datos
- administración de registros
- Microsoft Defender for Cloud Apps

## <a name="format"></a>Formato

Patrón alfanumérico de 10 caracteres

## <a name="pattern"></a>Patrón

Patrón alfanumérico de 10 caracteres:

- dos letras: HU o hu
- espacio opcional
- ocho dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una directiva DLP tiene una gran confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_hungarian_value_added_tax_number` busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keywords_hungarian_value_added_tax_number` .

Una directiva DLP tiene confianza media en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_hungarian_value_added_tax_number` busca contenido que coincida con el patrón.

```xml
      <!-- Hungarian Value Added Tax Number -->
      <Entity id="976349a0-683b-477a-90f8-ff0a220d5592" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
          <Match idRef="Keywords_hungarian_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_hungary_value_added_tax_number"></a>Keyword_Hungary_value_added_tax_number

- Iva
- número de impuestos de valor añadido
- Iva #
- vatno #
- hungarianvatno #
- impuestos no.
- impuestos sobre el valor añadido áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám