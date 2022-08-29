---
title: 'Japón Mi número: definición de entidad personal'
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
description: 'Japón Mi número: definición de entidad del tipo de información confidencial personal.'
ms.openlocfilehash: 343bc26e3310c4c8586a50b635ef3d5b2398967c
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2022
ms.locfileid: "67369843"
---
# <a name="japan-my-number---personal"></a>Número de identificación fiscal de Japón

## <a name="format"></a>Formato

Número de 12 dígitos

## <a name="pattern"></a>Patrón

Número de 12 dígitos:

- cuatro dígitos
- un espacio opcional, un punto o un guion
- cuatro dígitos
- un espacio opcional, un punto o un guion
- cuatro dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_japanese_my_number_personal` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_japanese_my_number_personal`.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_japanese_my_number_personal` encuentra contenido que coincide con el patrón.

```xml
      <!-- Japanese My Number – Personal -->
      <Entity id="98da8e66-7299-4ebd-9f82-c871ab37d3ef" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_personal" />
          <Match idRef="Keywords_japanese_my_number_personal" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_japanese_my_number_personal" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_japan_my_number_personal"></a>Keyword_japan_my_number_personal

- mi número
- マイナンバー
- 個人番号
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 通知カード