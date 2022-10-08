---
title: Definición de entidad de número de identificación personal de Dinamarca
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
description: Definición de entidad de tipo de información confidencial del número de identificación personal de Dinamarca.
ms.openlocfilehash: a9e47db57f98ab2ad06ba34dee3bc73d3b558863
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68363131"
---
# <a name="denmark-personal-identification-number"></a>Número del documento de identidad de Dinamarca

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

10 dígitos que contienen un guión

## <a name="pattern"></a>Patrón

10 dígitos:

- seis dígitos en el formato DDMMYY, que son la fecha de nacimiento
- un espacio opcional o un guion
- cuatro dígitos donde el dígito final es un dígito de comprobación

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular `Func_denmark_eu_tax_file_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_denmark_id`.
- Se supera la suma de comprobación.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular `Func_denmark_eu_tax_file_number` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Denmark Personal Identification Number -->
    <!-- Denmark Personal Identification Number -->
      <Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keyword_denmark_id" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- centrale personregister
- civilt registreringssystem
- Rcp
- Rcp #
- gesundheitskarte nummer
- gesundheitsversicherungkarte nummer
- tarjeta sanitaria
- número de tarjeta de seguro médico
- número de seguro médico
- identification number
- identifikationsnummer
- identifikationsnummer #
- número de identidad
- krankenkassennummer
- nationalid#
- nationalnumber #
- número nacional
- personalidnumber #
- personalidentityno #
- número de id. personal
- personnummer
- personnummer #
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- ssn
- númeroseguridadsocial#
- skat id
- skat kode
- skat nummer
- skattenummer
- social security number
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- Código fiscal
- tarjeta de seguro médico de viaje
- uniqueidentityno #
- número de id. fiscal
- número de registro fiscal
- tax id
- número de identificación fiscal
- Id.fiscal#
- núm.id.fiscal#
- n.º de id. fiscal
- núm.fiscal#
- núm.id.fisca
- núm. identificación fiscal
- Número de identificación tributaria
- númidfiscal#
- númeroidentificaciónfiscal#
- n.º de id. fiscal#
- id. tributaria
- n.º de id. tributario
- cpr.nr
- cprnr
- cprnummer
- personnr
- personregister
- sygesikringsbevis
- sygesikringsbevisnr
- sygesikringsbevisnummer
- sygesikringskort
- sygesikringskortnr
- sygesikringskortnummer
- sygesikringsnr
- sygesikringsnummer
