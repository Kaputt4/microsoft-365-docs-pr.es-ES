---
title: Definición de entidad de número de tarjeta de identidad residente (PRC) de China
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
description: Definición de entidad de tipo de información confidencial de número de tarjeta de identidad residente (PRC) de China.
ms.openlocfilehash: 9ab0f1af6de2c8ffdcb835824e1559ab1a574718
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999377"
---
# <a name="china-resident-identity-card-prc-number"></a>Número del documento de identidad de residente de China (PRC)

## <a name="format"></a>Formato

18 dígitos

## <a name="pattern"></a>Patrón

18 dígitos:

- seis dígitos que son un código de dirección
- ocho dígitos con el formato AAAAMMDD, que son la fecha de nacimiento
- tres dígitos que son un código de pedido
- un dígito que es un dígito de comprobación

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_china_resident_id` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_china_resident_id`.
- Se supera la suma de comprobación.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_china_resident_id` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

## <a name="keyword_china_resident_id"></a>Keyword_china_resident_id

- Tarjeta de identidad de residente
- PRC
- Tarjeta de identificación nacional
- 身份证
- 居民 身份证
- 居民身份证
- 鉴定
- 身分證
- 居民 身份證
- 鑑定