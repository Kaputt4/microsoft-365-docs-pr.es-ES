---
title: Definición de entidad internacional número de pasaporte de Rusia
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
description: Número de pasaporte de Rusia Definición de entidad de tipo de información confidencial internacional.
ms.openlocfilehash: 4f8c581dccac25d3c7f402e2d273037918c05868
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367431"
---
# <a name="russia-passport-number-international"></a>Número de pasaporte de Rusia (internacional)

## <a name="format"></a>Formato

número de nueve dígitos

## <a name="pattern"></a>Patrón

número de nueve dígitos:

- dos dígitos
- un espacio opcional o un guion
- siete dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- El regex `Regex_Russian_Passport_Number_International` busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_Russian_Passport_Number`.

```xml
      <!-- Russian Passport Number International -->
      <Entity id="ac5f4878-75e4-4b82-af2d-02e13ea9f411" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_International" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_russia_passport_number_international"></a>Keywords_russia_passport_number_international

- passport number
- pasaporte no
- pasaporte #
- id. de passport
- passportno #
- passportnumber #
- паспорт нет
- паспорт id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #