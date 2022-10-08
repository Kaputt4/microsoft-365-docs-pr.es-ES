---
title: Definición de entidad de número de tarjeta de identidad de Hong Kong (HKID)
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
description: Definición de entidad de tipo de información confidencial de número de tarjeta de identidad de Hong Kong (HKID).
ms.openlocfilehash: a3a006024ea63734bec5f1dc2a8e8b2dd60944ed
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68380632"
---
# <a name="hong-kong-identity-card-hkid-number"></a>Número del documento de identidad de Hong Kong (HKID)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

Combinación de 8 o 9 letras y números, más paréntesis opcionales alrededor del carácter final

## <a name="pattern"></a>Patrón

Combinación de 8 o 9 letras:

- 1-2 letras (no distingue mayúsculas de minúsculas)
- Seis dígitos
- espacio opcional
- un carácter de comprobación (cualquier dígito o la letra A) que se incluye opcionalmente entre paréntesis.

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_hong_kong_id_card` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_hong_kong_id_card`.
- Se supera la suma de comprobación.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_hong_kong_id_card` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_hong_kong_id_card"></a>Keyword_hong_kong_id_card

- hkid
- tarjeta de identidad de hong kong
- HKIDC
- id card
- documento de identidad
- hk identity card
- hong kong id.
- 香港身份證
- 香港永久性居民身份證
- 身份證
- 身份証
- 身分證
- 身分証
- 香港身份証
- 香港身分證
- 香港身分証
- 香港身份證
- 香港居民身份證
- 香港居民身份証
- 香港居民身分證
- 香港居民身分証
- 香港永久性居民身份証
- 香港永久性居民身分證
- 香港永久性居民身分証
- 香港永久性居民身份證
- 香港非永久性居民身份證
- 香港非永久性居民身份証
- 香港非永久性居民身分證
- 香港非永久性居民身分証
- 香港特別行政區永久性居民身份證
- 香港特別行政區永久性居民身份証
- 香港特別行政區永久性居民身分證
- 香港特別行政區永久性居民身分証
- 香港特別行政區非永久性居民身份證
- 香港特別行政區非永久性居民身份証
- 香港特別行政區非永久性居民身分證
- 香港特別行政區非永久性居民身分証
