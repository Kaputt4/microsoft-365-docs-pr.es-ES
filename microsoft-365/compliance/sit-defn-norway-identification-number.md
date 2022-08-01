---
title: Definición de entidad de número de identificación de Noruega
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
description: Definición de entidad de tipo de información confidencial del número de identificación de Noruega.
ms.openlocfilehash: 9edce24b1fef475ce30b50d3703214d4388a1338
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000331"
---
# <a name="norway-identification-number"></a>Número del documento de identidad de Noruega

## <a name="format"></a>Formato

11 dígitos

## <a name="pattern"></a>Patrón

11 dígitos:

- seis dígitos en el formato DDMMYY, que son la fecha de nacimiento
- número individual de tres dígitos
- dos dígitos de comprobación

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_norway_id_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_norway_id_number`.
- Se supera la suma de comprobación.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_norway_id_number` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_norway_id_number"></a>Keyword_norway_id_number

- Número de identificación personal
- Número de id. noruego
- Número de id.
- Identificación
- Personnummer
- Fødselsnummer