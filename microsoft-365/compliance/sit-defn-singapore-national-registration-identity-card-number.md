---
title: Definición de entidad de número de tarjeta de identidad de registro nacional (NRIC) de Singapur
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
description: Definición de entidad de tipo de información confidencial del número de tarjeta de identidad de registro nacional (NRIC) de Singapur.
ms.openlocfilehash: f77564f85444f3928a3ed6d3437d04e19774c411
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68471802"
---
# <a name="singapore-national-registration-identity-card-nric-number"></a>Número del documento de identidad del registro nacional de Singapur (NRIC)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

nueve letras y dígitos

## <a name="pattern"></a>Patrón

- nueve letras y dígitos:

- la letra "F", "G", "M", "S" o "T" (no distingue mayúsculas de minúsculas)
- siete dígitos
- un dígito de comprobación alfabético

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular `Regex_singapore_nric` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_singapore_nric`.
- Se supera la suma de comprobación.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular `Regex_singapore_nric` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_singapore_nric"></a>Keyword_singapore_nric

- Tarjeta de identidad de registro nacional
- Número de tarjeta de identidad
- NRIC
- Ic
- Número de identificación de extranjeros
- Aleta
- 身份证
- 身份證
