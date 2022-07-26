---
title: Definición de entidad del número de cuenta permanente (PAN) de la India
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
description: Definición de entidad de tipo de información confidencial del número de cuenta permanente (PAN) de la India.
ms.openlocfilehash: bf712e0949bba5f1e5396d61ff70f41b70ba579d
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999290"
---
# <a name="india-permanent-account-number-pan"></a>Número de cuenta permanente de India (PAN)

## <a name="format"></a>Formato

10 letras o dígitos

## <a name="pattern"></a>Patrón

10 letras o dígitos:

- Tres letras (no distinguen mayúsculas de minúsculas)
- Una letra en C, P, H, F, A, T, B, L, J, G (no distingue mayúsculas de minúsculas)
- Una letra
- Cuatro dígitos
- Una letra que es un dígito de comprobación alfabético

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_india_permanent_account_number` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_india_permanent_account_number`.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_india_permanent_account_number` regular busca contenido que coincida con el patrón.

```xml
      <!-- India Permanent Account Number -->
      <Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_india_permanent_account_number" />
          <Match idRef="Keyword_india_permanent_account_number" />
        </Pattern>
        <Version minEngineVersion="15.20.3520.000">
          <Pattern confidenceLevel="65">
            <IdMatch idRef="Regex_india_permanent_account_number" />
          </Pattern>
        </Version>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Número de cuenta permanente
- CACEROLA