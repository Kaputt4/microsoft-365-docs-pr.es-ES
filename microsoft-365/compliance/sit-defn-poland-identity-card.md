---
title: Definición de entidad de tarjeta de identidad de Polonia
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
description: Definición de entidad de tipo de información confidencial de la tarjeta de identidad de Polonia.
ms.openlocfilehash: cf0cd4abe57c3b27bb97d17673be0f855c1bab96
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68470011"
---
# <a name="poland-identity-card"></a>Documento de identidad de Polonia

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

tres letras y seis dígitos

## <a name="pattern"></a>Patrón

tres letras (sin distinguir mayúsculas de minúsculas) seguidas de seis dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_polish_national_id` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_polish_national_id_passport_number`.
- Se supera la suma de comprobación.

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Dowód osobisty
- Numer dowodu osobistego
- Nazwa i numer dowodu osobistego
- Nazwa i nr dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- Dow. os.
