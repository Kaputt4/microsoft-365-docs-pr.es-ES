---
title: Definición de entidad nacional del número de pasaporte de Rusia
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
description: Número de pasaporte de Rusia Definición de entidad de tipo de información confidencial nacional.
ms.openlocfilehash: b28283b4bc01c74f7887fe67bc621631d8cdadcf
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68470308"
---
# <a name="russia-passport-number-domestic"></a>Número de pasaporte de Rusia (nacional)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

Número de 10 dígitos

## <a name="pattern"></a>Patrón

Número de 10 dígitos:

- dos dígitos
- un espacio opcional o un guion
- dos dígitos
- un espacio opcional
- seis dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- El regex `Regex_Russian_Passport_Number_Domestic` busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_Russian_Passport_Number`.

```xml
      <!-- Russian Passport Number Domestic -->
      <Entity id="76ec2f5d-cedb-48e1-8070-1998794af445" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_Domestic" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_russia_passport_number_domestic"></a>Keyword_russia_passport_number_domestic

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
