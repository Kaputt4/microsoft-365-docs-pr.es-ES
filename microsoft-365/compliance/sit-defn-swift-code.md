---
title: Definición de entidad de código SWIFT
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
description: Definición de entidad de tipo de información confidencial del código SWIFT.
ms.openlocfilehash: b1bbadf8f2b56218a90eec1cfd2fac7d550efe0e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999071"
---
# <a name="swift-code"></a>Código SWIFT

## <a name="format"></a>Formato

cuatro letras seguidas de 5-31 letras o dígitos

## <a name="pattern"></a>Patrón

cuatro letras seguidas de 5-31 letras o dígitos:

- código bancario de cuatro letras (no distingue mayúsculas de minúsculas)
- un espacio opcional
- 4-28 letras o dígitos (el número básico de cuenta bancaria (BBAN))
- un espacio opcional
- de una a tres letras o dígitos (resto del BBAN)

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_swift` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_swift`.

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_swift"></a>Keyword_swift

- international organization for standardization 9362
- iso 9362
- iso9362
- veloz #
- swiftcode
- swiftnumber
- swiftroutingnumber
- swift code
- swift number #
- swift routing number
- bic number
- bic code
- bic #
- Bic #
- bank identifier code
- Organisation internationale de normalisation 9362
- rapide #
- code SWIFT
- le numéro de swift
- swift numéro d'acheminement
- le numéro BIC
- \# BIC
- code identificateur de banque
- SWIFTコード
- SWIFT番号
- BIC番号
- BICコード
- SWIFT コード
- SWIFT 番号
- BIC 番号
- BIC コード
- 金融機関識別コード
- 金融機関コード
- 銀行コード