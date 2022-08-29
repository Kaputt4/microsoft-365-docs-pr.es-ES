---
title: Definición de entidad de código fiscal de Italia
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
description: Definición de entidad de tipo de información confidencial del código fiscal de Italia.
ms.openlocfilehash: dd7fae7b927532d9224cc852419f01e31f5dbef4
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2022
ms.locfileid: "67368573"
---
# <a name="italy-fiscal-code"></a>Número de identificación fiscal de Italia

## <a name="format"></a>Formato

una combinación de 16 caracteres de letras y dígitos en el patrón especificado

## <a name="pattern"></a>Patrón

Una combinación de 16 caracteres de letras y dígitos:

- tres letras que corresponden a las tres primeras consonantes en el nombre de la familia
- tres letras que corresponden a las consonantes primera, tercera y cuarta en el nombre
- dos dígitos que corresponden a los últimos dígitos del año de nacimiento
- una letra que corresponde a la letra del mes de nacimiento: las letras se usan en orden alfabético, pero solo se usan las letras A a E, H, L, M, P, R a T (por lo tanto, enero es A y Octubre es R)
- dos dígitos que corresponden al día del mes de nacimiento con el fin de diferenciar entre géneros, 40 se agregan al día de nacimiento de las mujeres
- cuatro dígitos que corresponden al código de área específico del municipio donde nació la persona (los códigos de todo el país se usan para los países extranjeros)
- un dígito de paridad

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_italy_eu_national_id_card` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_italy_eu_national_id_card`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_italy_eu_national_id_card` encuentra contenido que coincide con el patrón.

```xml
      <!-- Italy Fiscal Code -->
      <Entity id="4cd79172-8da9-4ff5-9188-98b1e7e2eca6" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

- codice fiscal
- codice fiscale
- codice id personale
- codice personale
- código fiscal
- numero certificato personale
- numero di identificazione fiscale
- numero id personale
- numero personale
- número de certificado personal
- código personal
- código de id. personal
- número de id. personal
- personalcodeno #
- Código fiscal
- tax id
- núm. identificación fiscal
- número de identificación fiscal
- número de identidad fiscal
- n.º de id. fiscal#
- n.º fiscal
- número de id. fiscal
- número de registro fiscal
- Id.fiscal#
- númidfiscal#
- númeroidentificaciónfiscal#
- núm.fiscal#
- núm.id.fiscal#
- núm.id.fisca
- id. tributaria
- n.º de id. tributario
- Número de identificación tributaria