---
title: Definición de entidad de número de pasaporte de Japón
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
description: Definición de entidad de tipo de información confidencial del número de pasaporte de Japón.
ms.openlocfilehash: 52117216fbfbbf9a4b5f4db4e627e020b892bcb5
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000271"
---
# <a name="japan-passport-number"></a>Número de pasaporte de Japón

## <a name="format"></a>Formato

dos letras seguidas de siete dígitos

## <a name="pattern"></a>Patrón

dos letras (no distinguen mayúsculas de minúsculas) seguidas de siete dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_jp_passport` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_jp_passport`.

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_jp_passport"></a>Keyword_jp_passport

- Pasaporte
- Passport Number
- Pasaporte No.
- Passport #
- パスポート
- パスポート番号
- パスポートナンバー
- パスポート＃
- パスポート #
- パスポートNo.
- 旅券番号
- 旅券番号＃
- 旅券番号♯
- 旅券ナンバー