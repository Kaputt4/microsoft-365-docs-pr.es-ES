---
title: Definición de entidad de tarjeta de identidad de Chipre
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
description: Definición de entidad de tipo de información confidencial de la tarjeta de identidad de Chipre.
ms.openlocfilehash: 8ba4861932a1ac04941b850e8eb27f6498d3a455
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68361724"
---
# <a name="cyprus-identity-card"></a>Documento de identidad de Chipre

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

10 dígitos sin espacios ni delimitadores

## <a name="pattern"></a>Patrón

10 dígitos

## <a name="checksum"></a>Suma de comprobación

no aplicable

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular `Regex_cyprus_eu_national_id_card` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_cyprus_eu_national_id_card`.

```xml
      <!-- Cyprus Identity Card -->
      <Entity id="3ba8afe5-7a6c-4929-8247-0001b6878438" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

- número de tarjeta de identificación
- número de tarjeta de identidad
- kimlik karti
- national identification number
- número de id. personal
- ταυτοτητασ
