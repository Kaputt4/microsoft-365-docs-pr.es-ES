---
title: Definición de entidad de número de identificación única de la India (Aadhaar)
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
description: Definición de entidad de tipo de información confidencial de identificación única de India (Aadhaar).
ms.openlocfilehash: 242a186bf229b9d5bf05db2a72cbd060906311c4
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68380487"
---
# <a name="india-unique-identification-aadhaar-number"></a>Número de identificación único de India (Aadhaar)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

12 dígitos que contienen espacios o guiones opcionales

## <a name="pattern"></a>Patrón

12 dígitos:

- Un dígito que no es 0 o 1
- Tres dígitos
- Un guión o un espacio opcional 
- Cuatro dígitos
- Un guión o un espacio opcional 
- El dígito final, que es el dígito de comprobación

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_india_aadhaar` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_india_aadhar`.
- Se supera la suma de comprobación.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_india_aadhaar` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_india_aadhar"></a>Keyword_india_aadhar

- Aadhaar
- aadhar
- aadhar #
- uid
- आधार
- uidai
