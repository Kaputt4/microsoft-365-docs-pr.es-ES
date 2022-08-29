---
title: Definición de entidad del número de identificación nacional (personas físicas) de Luxemburgo
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
description: Número de identificación nacional de Luxemburgo (personas físicas) definición de entidad de tipo de información confidencial.
ms.openlocfilehash: 3640f35086c72262013ad3e25b5aec1bfe8b6fa3
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367233"
---
# <a name="luxemburg-national-identification-number-natural-persons"></a>Número del documento de identidad de Luxemburgo (personas naturales)

## <a name="format"></a>Formato

13 dígitos sin espacios ni delimitadores

## <a name="pattern"></a>Patrón

13 dígitos:

- 11 dígitos
- dos dígitos de comprobación

## <a name="checksum"></a>Suma de comprobación

sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_luxemburg_eu_tax_file_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_luxemburg_eu_national_id_card`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_luxemburg_eu_tax_file_number` encuentra contenido que coincide con el patrón.

```xml
      <!-- Luxemburg National Identification Number (Natural persons) -->
      <Entity id="aaf661ed-29ec-426d-8bf9-880cad298ebb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

- eindeutige id
- eindeutige id-nummer
- eindeutigeid #
- id personnelle
- idpersonnelle #
- idpersonnelle
- código individual
- id. individual
- identificación individual
- identidad individual
- numéro d'identification personal
- id. personal
- identificación personal
- identidad personal
- personalidno #
- personalidnumber #
- persönliche identifikationsnummer
- id. único
- identidad única
- uniqueidkey #