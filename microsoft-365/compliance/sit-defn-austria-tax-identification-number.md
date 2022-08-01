---
title: Definición de entidad de número de identificación fiscal de Austria
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
description: Definición de entidad del tipo de información confidencial del número de identificación fiscal de Austria.
ms.openlocfilehash: d73bf75e554703b09ce073426f4671b296cdd884
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999947"
---
# <a name="austria-tax-identification-number"></a>Número de identificación fiscal de Austria

## <a name="format"></a>Formato

nueve dígitos con guion opcional y barra diagonal

## <a name="pattern"></a>Patrón

nueve dígitos con guion opcional y barra diagonal:

- dos dígitos
- un guion (opcional)
- tres dígitos
- una barra diagonal (opcional)
- cuatro dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_austria_eu_tax_file_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_austria_eu_tax_file_number`.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_austria_eu_tax_file_number` encuentra contenido que coincide con el patrón.

```xml
      <!-- Austria Tax Identification Number -->
      <Entity id="4fd58d22-af28-4451-b18a-6f722430a56d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_austria_eu_tax_file_number"></a>Keywords_austria_eu_tax_file_number

- Österreich
- st.nr.
- steuernummer
- id. de impuestos
- identificación fiscal no
- número de identificación fiscal
- impuestos no #
- impuestos no
- número de impuestos
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin ID
- tin no
- Lata #
- número de impuestos