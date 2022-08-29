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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Definición de entidad del tipo de información confidencial internacional de Ucrania passport.
ms.openlocfilehash: a383fea21990437199287f3e212debe8530d1521
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2022
ms.locfileid: "67370197"
---
# <a name="ukraine-passport-international"></a>Pasaporte internacional de Ucrania

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
