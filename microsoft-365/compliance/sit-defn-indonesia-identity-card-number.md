---
title: Definición de entidad de número de tarjeta de identidad de Indonesia (KTP)
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
description: Definición de entidad de tipo de información confidencial de la tarjeta de identidad de Indonesia (KTP).
ms.openlocfilehash: 0569be435baf2763c6de63db77926189bfb4a78c
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68380617"
---
# <a name="indonesia-identity-card-ktp-number"></a>Número del documento de identidad de Indonesia (KTP)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

16 dígitos que contienen puntos opcionales

## <a name="pattern"></a>Patrón

16 dígitos:

- Código de la provincia de dos dígitos 
- Un punto (opcional) 
- Código de ciudad o regencia de dos dígitos 
- Código de subdistrito de dos dígitos 
- Un punto (opcional) 
- Seis dígitos con el formato DDMMYY, que son la fecha de nacimiento
- Un punto (opcional) 
- Cuatro dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular `Regex_indonesia_id_card` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_indonesia_id_card`.

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_indonesia_id_card"></a>Keyword_indonesia_id_card

- Ktp
- Kartu Tanda Penduduk
- Nomor Induk Kependudukan
