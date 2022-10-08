---
title: Definición de entidad internacional de Pasaporte de Ucrania
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
description: Definición de entidad del tipo de información confidencial internacional de Ucrania passport.
ms.openlocfilehash: 91e15a1d39c95ceb00186b6521d79cd4172b72cb
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68470440"
---
# <a name="ukraine-passport-international"></a>Pasaporte internacional de Ucrania

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

patrón alfanumérico de ocho caracteres

## <a name="pattern"></a>Patrón

Patrón alfanumérico de ocho caracteres:

- dos letras o dígitos
- seis dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- El regex `Regex_Ukraine_Passport_International` busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_Ukraine_Passport_International`.

```xml
      <!-- Ukraine Passport International -->
      <Entity id="cfbe032d-22e0-4f28-ab68-d66e9641f1e2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Ukraine_Passport_International"/>
          <Match idRef="Keyword_Ukraine_Passport_International"/>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_ukraine_passport_international"></a>Keyword_ukraine_passport_international

- ucrania pasaporte
- passport number
- pasaporte no
- паспорт України
- номер паспорта
