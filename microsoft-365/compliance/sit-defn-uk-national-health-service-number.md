---
title: Reino Unido definición de entidad de número de servicio de salud nacional
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
description: Reino Unido national health service number sensitive information type entity definition.
ms.openlocfilehash: b16ac1cc66b53bff232967aedc8b9f5265908d0e
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472264"
---
# <a name="uk-national-health-service-number"></a>Reino Unido número del servicio nacional de salud

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

De 10 a 17 dígitos separados por espacios

## <a name="pattern"></a>Patrón

10-17 dígitos:

- 3 o 10 dígitos
- un espacio
- tres dígitos
- un espacio
- cuatro dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_uk_nhs_number` encuentra contenido que coincide con el patrón.
- Uno de los siguientes casos es true:
    - Se encuentra una palabra clave de `Keyword_uk_nhs_number`.
    - Se encuentra una palabra clave de `Keyword_uk_nhs_number1`.
    - Se encuentra una palabra clave de `Keyword_uk_nhs_number_dob`.
- Se supera la suma de comprobación.

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_uk_nhs_number"></a>Keyword_uk_nhs_number

- national health service
- Nhs
- health services authority
- health authority

### <a name="keyword_uk_nhs_number1"></a>Keyword_uk_nhs_number1

- patient id
- patient identification
- patient no
- patient number

### <a name="keyword_uk_nhs_number_dob"></a>Keyword_uk_nhs_number_dob

- Gp
- Dob
- D.O.B
- Fecha de nacimiento
- Fecha de nacimiento
