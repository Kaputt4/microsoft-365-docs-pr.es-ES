---
title: Definición de entidad de número de bienestar social de Nueva Zelanda
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
description: Definición de entidad de tipo de información confidencial de número de bienestar social de Nueva Zelanda.
ms.openlocfilehash: 6bd9a61fd5e54d83fedf941afc7a97653f8bef7e
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68382565"
---
# <a name="new-zealand-social-welfare-number"></a>Número de seguridad social de Nueva Zelanda

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

nueve dígitos

## <a name="pattern"></a>Patrón

nueve dígitos

- tres dígitos
- un guion opcional
- tres dígitos
- un guion opcional
- tres dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_newzealand_social_welfare_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_newzealand_social_welfare_number`.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_newzealand_social_welfare_number` encuentra contenido que coincide con el patrón.

```xml
      <!-- Newzealand Social Welfare Number -->
      <Entity id="20f3c48d-4ac1-4cd2-86bd-34ecc1826e9d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
          <Match idRef="Keywords_newzealand_social_welfare_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
        </Pattern>
      </Entity>
    </Version>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_new_zealand_social_welfare_number"></a>Keyword_new_zealand_social_welfare_number

- bienestar social #
- bienestar social #
- bienestar social No.
- número de bienestar social
- Swn #
