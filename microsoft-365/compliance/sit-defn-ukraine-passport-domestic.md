---
title: Definición de entidad nacional de Pasaporte de Ucrania
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
description: Definición de entidad del tipo de información confidencial nacional de Ucrania passport.
ms.openlocfilehash: 9880c595b0814d71cc84d6fffd1c691cf40e68df
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68471912"
---
# <a name="ukraine-passport-domestic"></a>Pasaporte nacional de Ucrania

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

nueve dígitos

## <a name="pattern"></a>Patrón

nueve dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- El regex `Regex_Ukraine_Passport_Domestic` busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_Ukraine_Passport_Domestic`.

```xml
      <!-- Ukraine Passport Domestic -->
      <Entity id="1817a540-221f-4459-9202-3bd78b81d803" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_Ukraine_Passport_Domestic"/>
          <Match idRef="Keyword_Ukraine_Passport_Domestic"/>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_ukraine_passport_domestic"></a>Keyword_ukraine_passport_domestic

- ucrania pasaporte
- passport number
- pasaporte no
- паспорт України
- номер паспорта
- персональний
