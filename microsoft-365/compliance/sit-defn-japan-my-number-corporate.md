---
title: 'Japón Mi número: definición de entidad corporativa'
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
description: 'Japón Mi número: definición de entidad de tipo de información confidencial corporativa.'
ms.openlocfilehash: 083e8b0bca98d11ea65e6b5644186be1232f296d
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367299"
---
# <a name="japan-my-number---corporate"></a>Código de identificación fiscal de Japón

## <a name="format"></a>Formato

Número de 13 dígitos

## <a name="pattern"></a>Patrón

Número de 13 dígitos:

- un dígito de uno a nueve
- 12 dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_japanese_my_number_corporate` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_japanese_my_number_corporate`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_japanese_my_number_corporate` encuentra contenido que coincide con el patrón.

```xml
      <!-- Japanese My Number – Corporate -->
      <Entity id="9e0eaf79-ff20-4ffb-b3e4-e7368d5db6ff" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
          <Match idRef="Keywords_japanese_my_number_corporate" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_japan_my_number_corporate"></a>Keyword_japan_my_number_corporate

- número corporativo
- マイナンバー
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 法人番号
- 指定通知書