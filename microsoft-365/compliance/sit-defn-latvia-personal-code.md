---
title: Definición de entidad de código personal de Letonia
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
description: Definición de entidad de tipo de información confidencial de código personal de Letonia.
ms.openlocfilehash: cfcd9dd792494154601a9cafda179be64fb08078
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68384193"
---
# <a name="latvia-personal-code"></a>Número del documento de identidad de Letonia

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

11 dígitos y un guion opcional

## <a name="pattern"></a>Patrón

Formato antiguo

11 dígitos y un guion:

- seis dígitos que corresponden a la fecha de nacimiento (DDMMYY)
- un guion
- un dígito que corresponde al siglo de nacimiento ("0" para el siglo XIX, "1" para el siglo XX y "2" para el siglo XXI)
- cuatro dígitos, generados aleatoriamente

Nuevo formato

11 dígitos

- Dos dígitos "32"
- Nueve dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_latvia_eu_national_id_card` o la expresión regular `Regex_latvia_eu_national_id_card_new_format` buscan contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keywords_latvia_eu_national_id_card`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_latvia_eu_national_id_card` o la expresión regular `Regex_latvia_eu_national_id_card_new_format` buscan contenido que coincida con el patrón.

```xml
      <!-- Latvia Personal Code -->
      <Entity id="03fcf763-27c2-49ed-9422-2641c6c895c9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

- número administrativo
- alvas nē
- número de nacimiento
- número de ciudadano
- número civil
- número de censo electrónico
- número electrónico
- código fiscal
- número de usuario de healthcare
- Id #
- id-code
- identification number
- identifikācijas numurs
- id-number
- número individual
- latvija alva
- nacionālais id
- national id
- número de identificación nacional
- número de identidad nacional
- national insurance number
- número de registro nacional
- nodokļa numurs
- nodokļu id.
- nodokļu identifikācija numurs
- número de certificado personal
- código personal
- código de id. personal
- número de id. personal
- código de identificación personal
- identificador personal
- número de identidad personal
- número personal
- código numérico personal
- personalcodeno #
- personas kods
- código de identificación de población
- número de servicio público
- registration number
- número de ingresos
- social insurance number
- social security number
- código de impuestos estatales
- tax file number
- tax id
- núm. identificación fiscal
- número de identificación fiscal
- n.º de id. fiscal#
- n.º fiscal
- número de id. fiscal
- Id.fiscal#
- númidfiscal#
- númeroidentificaciónfiscal#
- núm.fiscal#
- núm.id.fiscal#
- núm.id.fisca
- id. tributaria
- n.º de id. tributario
- Número de identificación tributaria
- número de elector
