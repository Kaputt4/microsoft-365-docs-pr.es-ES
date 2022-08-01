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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Definición de entidad de tipo de información confidencial de número de bienestar social de Nueva Zelanda.
ms.openlocfilehash: 9885956e7011f2c52a8b78d4e03822f8201c1b3a
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000334"
---
# <a name="new-zealand-social-welfare-number"></a>Número de seguridad social de Nueva Zelanda

Este tipo de información confidencial solo está disponible para su uso en:

- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicación
- administración del ciclo de vida de los datos
- administración de registros
- Microsoft Defender for Cloud Apps

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