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
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Número de pasaporte de Rusia Definición de entidad de tipo de información confidencial internacional.
ms.openlocfilehash: 1cc507d7c36a316dea8b8779a2993a907a33c375
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472066"
---
# <a name="russia-passport-number-international"></a>Número de pasaporte de Rusia (internacional)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

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
