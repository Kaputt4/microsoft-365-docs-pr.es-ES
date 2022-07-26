---
title: Definición de entidad de número de registro residente de Corea del Sur
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
description: Definición de entidad de tipo de información confidencial del número de registro residente de Corea del Sur.
ms.openlocfilehash: 94de2ebb31e8bd7a0d9c175e318e166da691bbca
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999086"
---
# <a name="south-korea-resident-registration-number"></a>Número de registro de residente de Corea del Sur

## <a name="format"></a>Formato

13 dígitos que contienen un guión

## <a name="pattern"></a>Patrón

13 dígitos:

- seis dígitos en el formato AAAADD, que son la fecha de nacimiento
- un guion
- un dígito determinado por el siglo y el género
- código de región de nacimiento de cuatro dígitos
- un dígito utilizado para diferenciar a las personas para las que los números anteriores son idénticos
- un dígito de comprobación.

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_south_korea_resident_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_south_korea_resident_number`.
- Se supera la suma de comprobación.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_south_korea_resident_number` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_south_korea_resident_number"></a>Keyword_south_korea_resident_number

- Tarjeta de id. nacional
- Número de registro de ciudadano
- Jumin deungnok beonho
- RRN
- 주민등록번호