---
title: Definición de entidad de número de ciudadano maestro único de Eslovenia
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
description: Definición de entidad de tipo de información confidencial número de ciudadano maestro único de Eslovenia.
ms.openlocfilehash: 23c484946c8e73e7f21b251aa35935dba37b110b
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999761"
---
# <a name="slovenia-unique-master-citizen-number"></a>Número del documento de identidad único de Eslovenia

Este tipo de información confidencial solo está disponible para su uso en:

- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicación
- administración del ciclo de vida de los datos
- administración de registros
- Microsoft Defender for Cloud Apps

## <a name="format"></a>Formato

13 dígitos sin espacios ni delimitadores

## <a name="pattern"></a>Patrón

13 dígitos en el patrón especificado:

- siete dígitos que corresponden a la fecha de nacimiento (DDMMLLL) donde "LLL" corresponde a los tres últimos dígitos del año de nacimiento
- dos dígitos que corresponden al área de nacimiento "50"
- tres dígitos que corresponden a una combinación de género y número de serie para las personas nacidas en el mismo día. 000-499 para hombres y 500-999 para mujeres.
- un dígito de comprobación

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_slovenia_eu_national_id_card` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_slovenia_eu_national_id_card`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_slovenia_eu_national_id_card` encuentra contenido que coincide con el patrón.

```xml
      <!-- Slovenia Unique Master Citizen Number -->
      <Entity id="68948b27-803d-41e4-adf1-13e05eb541bb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

- edinstvena številka glavnega državljana
- emšo
- enotna maticna številka obcana
- id card
- identification number
- identifikacijska številka
- documento de identidad
- nacionalna id
- lista de potni nacionalni
- national id
- osebna izkaznica
- osebni koda
- osebni ne
- osebni številka
- código personal
- número personal
- código numérico personal
- številka državljana
- número de ciudadano único
- número de id. único
- número de identidad único
- número de ciudadano maestro único
- número de registro único
- uniqueidentityno #
- uniqueidentityno #