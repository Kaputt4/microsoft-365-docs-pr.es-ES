---
title: Definición de entidad de id. nacional de Finlandia
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
description: Definición de entidad de tipo de información confidencial de identificador nacional de Finlandia.
ms.openlocfilehash: 7d196482051afb6a889d855c80616a4a15ce1df2
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000265"
---
# <a name="finland-national-id"></a>Documento de identidad de Finlandia

## <a name="format"></a>Formato

seis dígitos más un carácter que indica un siglo más tres dígitos más un dígito de verificación

## <a name="pattern"></a>Patrón

El patrón debe incluir todo lo siguiente:

- seis dígitos en el formato DDMMYY, que son una fecha de nacimiento
- marcador century (ya sea '-', '+' o 'a')
- número de identificación personal de tres dígitos
- un dígito o una letra (que no distingue mayúsculas de minúsculas) que es un dígito de comprobación

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- la función `Func_finnish_national_id` busca contenido que coincida con el patrón
- se encuentra una palabra clave de `Keyword_finnish_national_id`
- la suma de comprobación pasa

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- la función `Func_finnish_national_id` busca contenido que coincida con el patrón
- la suma de comprobación pasa

```xml
      <!-- Finnish National ID-->
      <Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finnish_national_id" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero #
- henkilötunnusnumero
- hetu
- id no
- número de id.
- identification number
- identiteetti numero
- número de identidad
- Idnumber
- kansallinen henkilötunnus
- kansallisen henkilökortin
- tarjeta de identificación nacional
- national id no.
- id. personal
- código de identidad personal
- personalidnumber #
- personbeteckning
- personnummer
- social security number
- sosiaaliturvatunnus
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
- tunnistenumero
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus