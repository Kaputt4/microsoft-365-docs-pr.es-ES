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
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Definición de entidad de tipo de información confidencial de identificador nacional de Finlandia.
ms.openlocfilehash: 6c8c42d63610d91165c909f67845bf75aa182537
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68379673"
---
# <a name="finland-national-id"></a>Documento de identidad de Finlandia

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

seis dígitos más un carácter que indica un siglo más tres dígitos más un dígito de verificación

## <a name="pattern"></a>Patrón

El patrón debe incluir todos estos patrones:

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
- tunnistenumero
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus
