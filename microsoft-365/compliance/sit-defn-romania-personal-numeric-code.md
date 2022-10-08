---
title: Definición de entidad de código numérico personal (CNP) de Rumania
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
description: Definición de entidad de tipo de información confidencial de código numérico personal (CNP) de Rumania.
ms.openlocfilehash: c1241d3bdd3035b053713137a4e64feb50a6dba0
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68470374"
---
# <a name="romania-personal-numeric-code-cnp"></a>Número del documento de identidad de Rumania (CNP)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

13 dígitos sin espacios ni delimitadores

## <a name="pattern"></a>Patrón

- un dígito del 1 al 9
- seis dígitos que representan la fecha de nacimiento (AMMDD)
- dos dígitos, que pueden ser 01-52 o 99
- cuatro dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_romania_eu_national_id_card` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_romania_eu_national_id_card`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_romania_eu_national_id_card` encuentra contenido que coincide con el patrón.

```xml
      <!-- Romania Personal Numerical Code (CNP) -->
      <Entity id="eb5fa399-fe28-4c67-8188-d63a616ed89c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

- Cnp #
- Cnp
- cod identificare personal
- cod numeric personal
- cod unic identificare
- codnumericpersonal #
- codul fiscal nr.
- identificarea fiscală nr #
- id-ul taxei
- número de seguro
- insurancenumber #
- national id #
- national id
- national identification number
- număr identificare personal
- număr identitate
- număr personal unic
- număridentitate #
- număridentitate
- numărpersonalunic #
- numărpersonalunic
- număru de identificare fiscală
- numărul de identificare fiscală
- código numérico personal
- anclar #
- anclar
- archivo fiscal no
- tax file number
- tax id
- núm. identificación fiscal
- número de identificación fiscal
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
- número de identificación único
- número de identidad único
- uniqueidentityno #
- uniqueidentityno
