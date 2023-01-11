---
title: Definición de entidad de número de la seguridad social (SSN) de España
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
description: Definición de entidad de tipo de información confidencial del número de la seguridad social (SSN) de España.
ms.openlocfilehash: 8a87fcc82af413e074e7e37302bb72de0f9a501a
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68470572"
---
# <a name="spain-social-security-number-ssn"></a>Número de la seguridad social de España (NSS)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

11 o 12 dígitos

## <a name="pattern"></a>Patrón

11-12 dígitos:

- dos dígitos
- una barra diagonal (opcional)
- de siete a ocho dígitos
- una barra diagonal (opcional)
- dos dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_spanish_social_security_number` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.
    - Se encuentra una palabra clave de `Keywords_spain_eu_ssn_or_equivalent`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_spanish_social_security_number` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
    <!-- Spain SSN -->
    <Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85" relaxProximity="true" >
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spanish_social_security_number" />
          <Match idRef="Keywords_spain_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spanish_social_security_number" />
        </Pattern>
    </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- ssn
- númeroseguridadsocial#
- socialsecurityno
- nro. seguridad social
- social security number
- número de la seguridad social
