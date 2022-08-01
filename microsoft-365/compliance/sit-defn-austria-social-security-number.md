---
title: Definición de entidad de número de seguridad social de Austria
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
description: Definición de entidad de tipo de información confidencial de número de seguridad social de Austria.
ms.openlocfilehash: 24b909e2b45bce3db5c4b4cfd1e0d3cf3d74296c
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999782"
---
# <a name="austria-social-security-number"></a>Número de la seguridad social de Austria

## <a name="format"></a>Formato

10 dígitos en el formato especificado

## <a name="pattern"></a>Patrón

10 dígitos:

- tres dígitos que corresponden a un número de serie
- un dígito de comprobación
- seis dígitos que corresponden a la fecha de nacimiento (DDMMYY)

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_austria_eu_ssn_or_equivalent` encuentra contenido que coincide con el patrón.
- se encuentra una palabra clave de `Keywords_austria_eu_ssn_or_equivalent` .

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_austria_eu_ssn_or_equivalent` encuentra contenido que coincide con el patrón.

```xml
      <!-- Austria Social Security Number -->
      <Entity id="6896a906-86c9-4d19-a2da-6e43ccd19b7b" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_austria_eu_telephone_number" />
            <Match idRef="Keywords_austria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- austriaco ssn
- número ehic
- ehic no
- código de seguro
- insurancecode #
- número de seguro
- seguro no
- krankenkassennummer
- krankenversicherung
- socialsecurityno
- socialsecurityno #
- seguridad social no
- social security number
- social security code
- sozialversicherungsnummer
- sozialversicherungsnummer #
- soziale sicherheit kein
- sozialesicherheitkein #
- Ssn #
- Ssn
- versicherungscode
- versicherungsnummer
- zdravstveno zavarovanje