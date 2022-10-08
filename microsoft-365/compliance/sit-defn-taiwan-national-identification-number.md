---
title: Definición de entidad de número de identificación nacional de Taiwán
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
description: Definición de entidad de tipo de información confidencial del número de identificación nacional de Taiwán.
ms.openlocfilehash: 52f8bbd3f7d43cc57d655febdef7c218453581d8
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472330"
---
# <a name="taiwan-national-identification-number"></a>Número de identificación nacional de Taiwán

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

una letra (en inglés) seguida de nueve dígitos

## <a name="pattern"></a>Patrón

una letra (en inglés) seguida de nueve dígitos:

- una letra (en inglés, no distingue mayúsculas de minúsculas)
- el dígito "1" o "2"
- ocho dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_taiwanese_national_id` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_taiwanese_national_id`.
- Se supera la suma de comprobación.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_taiwanese_national_id` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
       <Pattern confidenceLevel="75">
         <IdMatch idRef="Func_taiwanese_national_id" />
       </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_taiwan_national_id"></a>Keyword_taiwan_national_id

- 身份證字號
- 身份證
- 身份證號碼
- 身份證號
- 身分證字號
- 身分證
- 身分證號碼
- 身份證號
- 身分證統一編號
- 國民身分證統一編號
- 簽名
- 蓋章
- 簽名或蓋章
- 簽章
