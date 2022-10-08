---
title: Definición de entidad del número de seguro social (SSN) de EE. UU.
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
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Definición de entidad de tipo de información confidencial del número de seguridad social (SSN) de EE. UU.
ms.openlocfilehash: 4efa2b71c062f03a93c568641e894281666d078c
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472242"
---
# <a name="us-social-security-number-ssn"></a>Número de seguridad social de EE. UU. (SSN)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

nueve dígitos, que pueden estar en un patrón con formato o sin formato

> [!NOTE]
> Si se ha emitido antes de mediados de 2011, el SSN tiene un formato seguro en aquellas partes del número que deben incluirse dentro de ciertos rangos para que sean válidas (pero no hay ninguna suma de comprobación).

## <a name="pattern"></a>Patrón

cuatro funciones buscan SSN en cuatro patrones diferentes:

- `Func_ssn` busca SSN con formato seguro anterior a 2011 con formato con guiones o espacios (ddd-dd-ddd OR ddd ddd ddd)
- `Func_unformatted_ssn` busca SSN con formato seguro anterior a 2011 que no tienen formato como nueve dígitos consecutivos (ddddddddd)
- `Func_randomized_formatted_ssn` busca SSN posteriores a 2011 con formato de guiones o espacios (ddd-dd-ddd OR ddd ddd ddd)
- `Func_randomized_unformatted_ssn` busca los SSN posteriores a 2011 que no tienen formato como nueve dígitos consecutivos (dddddddddd)

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_ssn` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_ssn`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_unformatted_ssn` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_ssn`.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_randomized_formatted_ssn` o `Func_randomized_unformatted_ssn` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_ssn`.

```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_ssn"></a>Keyword_ssn

- Número de SSA
- social security number
- seguridad social #
- seguridad social #
- nro. seguridad social
- Social Security#
- Soc Sec
- Ssn
- SSN
- Ssn #
- Ss #
- SSID
