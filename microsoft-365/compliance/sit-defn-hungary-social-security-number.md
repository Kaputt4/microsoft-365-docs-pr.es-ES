---
title: Definición de entidad de número de seguridad social (TAJ) de Hungría
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
description: Definición de entidad de tipo de información confidencial de número de seguridad social (TAJ) de Hungría.
ms.openlocfilehash: 52821cda4b997567a66e2527653ed0a1341a378e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000061"
---
# <a name="hungary-social-security-number-taj"></a>Número de la seguridad social de Hungría (TAJ)

## <a name="format"></a>Formato

Nueve dígitos sin espacios ni delimitadores

## <a name="pattern"></a>Patrón

Nueve dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_hungary_eu_ssn_or_equivalent` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_hungary_eu_ssn_or_equivalent`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_hungary_eu_ssn_or_equivalent` encuentra contenido que coincide con el patrón.

```xml
      <!-- Hungarian Social Security Number (TAJ) -->
      <Entity id="0de78315-9537-47f5-95ab-b3e77eba3993" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_hungary_eu_ssn_or_equivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

- número de la seguridad social húngara
- social security number
- socialsecuritynumber #
- hssn #
- socialsecuritynno
- hssn
- Taj
- Taj #
- Ssn
- Ssn #
- seguridad social no
- áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám
- magyar áfa szám