---
title: Definición de entidad de número de identidad personal checo
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
description: Definición de entidad de tipo de información confidencial del número de identidad personal checo.
ms.openlocfilehash: a5c6156a2f84ff96025c3f73cf20dcbd201e90d3
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000439"
---
# <a name="czech-personal-identity-number"></a>Número del documento de identidad de la República Checa

## <a name="format"></a>Formato

nueve dígitos con barra diagonal opcional (formato antiguo)

10 dígitos con barra diagonal opcional (nuevo formato)

## <a name="pattern"></a>Patrón

nueve dígitos (formato antiguo):

- seis dígitos que representan la fecha de nacimiento
- una barra diagonal opcional
- tres dígitos

10 dígitos (nuevo formato):

- seis dígitos que representan la fecha de nacimiento
- una barra diagonal opcional
- cuatro dígitos donde el último dígito es un dígito de comprobación

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_czech_id_card` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_czech_id_card`.
- Se supera la suma de comprobación.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_czech_id_card_new_format` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Czech Personal Identity Number -->
      <!-- Czech Personal Identity Number -->
      <Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_id_card" />
          <Match idRef="Keyword_czech_id_card" />
        </Pattern>
        <Version minEngineVersion="15.20.3000.000">
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Func_czech_id_card_new_format" />
          </Pattern>
        </Version>
      </Entity>
```
## <a name="keywords"></a>Palabras clave

### <a name="keyword_czech_id_card"></a>Keyword_czech_id_card

- número de nacimiento
- id. de república checa
- czechidno #
- daňové číslo
- identifikační číslo
- identity no
- número de identidad
- identityno #
- identityno
- número de seguro
- national identification number
- nationalnumber #
- número nacional
- osobní číslo
- personalidnumber #
- número de id. personal
- número de identificación personal
- número personal
- Pid #
- pid
- pojištění číslo
- rč
- rodne cislo
- rodné číslo
- Ssn
- Ssn #
- social security number
- tax id
- identificación fiscal no
- número de identificación fiscal
- impuestos no #
- impuestos no
- número de impuestos
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tin id
- tin no
- Lata #
- número de identificación único