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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Definición de entidad de tipo de información confidencial del número de identificación personal de Dinamarca.
ms.openlocfilehash: 8fbdd3fc2bd273b34fcf3625fa9f021d1f948358
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999884"
---
# <a name="denmark-personal-identification-number"></a>Número del documento de identidad de Dinamarca

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

- La expresión `Func_denmark_eu_tax_file_number` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_denmark_id`.
- Se supera la suma de comprobación.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Func_denmark_eu_tax_file_number` regular busca contenido que coincida con el patrón.
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
- nationalid #
- nationalnumber #
- número nacional
- personalidnumber #
- personalidentityno #
- número de id. personal
- personnummer
- personnummer #
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- Ssn
- Ssn #
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
- número de impuestos
- número de registro fiscal
- tax id
- número de identificación fiscal
- taxid #
- taxnumber #
- impuestos no
- taxno #
- taxnumber
- identificación fiscal no
- Lata #
- taxidno #
- taxidnumber #
- impuestos no #
- tin id
- tin no
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