---
title: Definición de entidad de número de ministerio de salud de Nueva Zelanda
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
description: Definición de entidad de tipo de información confidencial del ministerio de salud de Nueva Zelanda.
ms.openlocfilehash: 62a7b181626d36930da36451ccd109ecc6d04812
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000340"
---
# <a name="new-zealand-ministry-of-health-number"></a>Número de la tarjeta sanitaria de Nueva Zelanda

## <a name="format"></a>Formato

tres letras y cuatro dígitos

## <a name="pattern"></a>Patrón

- tres letras (no distingue mayúsculas de minúsculas), excepto "I" y "O"
- cuatro dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_new_zealand_ministry_of_health_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_nz_terms`.
- Se supera la suma de comprobación.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_new_zealand_ministry_of_health_number` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
    <!-- New Zealand Health Number -->
    <Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
          <Match idRef="Keyword_nz_terms" />
      </Pattern>
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
       </Pattern>
    </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_nz_terms"></a>Keyword_nz_terms

- NHI
- New Zealand
- Índice nacional de salud
- NHI #
- Índice nacional de salud #