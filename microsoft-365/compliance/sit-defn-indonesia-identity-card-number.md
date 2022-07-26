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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Definición de entidad de tipo de información confidencial de la tarjeta de identidad de Indonesia (KTP).
ms.openlocfilehash: d70e6ca902c6246e6faa67a91c5b52ae65e4fd47
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999119"
---
# <a name="indonesia-identity-card-ktp-number"></a>Número del documento de identidad de Indonesia (KTP)

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

- La expresión `Regex_indonesia_id_card` regular busca contenido que coincida con el patrón.
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

- KTP
- Kartu Tanda Penduduk
- Nomor Induk Kependudukan