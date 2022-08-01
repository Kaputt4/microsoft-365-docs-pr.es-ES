---
title: Definición de entidad de número de seguro social de Canadá
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
description: Definición de entidad de tipo de información confidencial del número de seguro social de Canadá.
ms.openlocfilehash: 9af5cc026da5ac6bd414ebd80ded934efb90effb
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999863"
---
# <a name="canada-social-insurance-number"></a>Número de seguridad social de Canadá

## <a name="format"></a>Formato

nueve dígitos con guiones o espacios opcionales

## <a name="pattern"></a>Patrón

Formato:

- tres dígitos
- un guion o un espacio
- tres dígitos
- un guion o un espacio
- tres dígitos

Sin formato: nueve dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función Func_canadian_sin encuentra contenido que coincide con el patrón.
- Al menos dos de los siguientes patrones:
    - Se encuentra una palabra clave de `Keyword_sin`.
    - Se encuentra una palabra clave de `Keyword_sin_collaborative`.
    - La función `Func_eu_date` busca una fecha en el formato de fecha correcto.
- Se supera la suma de comprobación.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función Func_unformatted_canadian_sin encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_sin`.
- Se supera la suma de comprobación.

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_sin"></a>Keyword_sin

- sin
- social insurance
- numero d'assurance sociale
- Pecados
- Ssn
- Ssn
- social security
- numero d'assurance social
- national identification number
- national id
- Pecado #
- soc ins
- social ins

### <a name="keyword_sin_collaborative"></a>Keyword_sin_collaborative

- driver's license
- drivers license
- driver's licence
- drivers licence
- DOB
- Fecha de nacimiento
- Birthday
- Fecha de nacimiento