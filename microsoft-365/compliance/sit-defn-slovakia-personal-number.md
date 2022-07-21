---
title: Definición de entidad de número personal de Eslovaquia
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
description: Definición de entidad de tipo de información confidencial de número personal de Eslovaquia.
ms.openlocfilehash: 4f923c714cf94543828d184164631d5e0c60e9e8
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950909"
---
# <a name="slovakia-personal-number"></a>Número personal de Eslovaquia

Este tipo de información confidencial solo está disponible para su uso en:

- directivas de prevención de pérdida de datos
- directivas de cumplimiento de comunicación
- administración del ciclo de vida de los datos
- administración de registros
- Microsoft Defender for Cloud Apps

## <a name="format"></a>Formato

nueve o 10 dígitos que contienen barra diagonal inversa opcional

## <a name="pattern"></a>Patrón

- seis dígitos que representan la fecha de nacimiento
- barra diagonal opcional (/)
- tres dígitos
- un dígito de comprobación opcional

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una directiva DLP tiene una gran confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_slovakia_eu_national_id_card` busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keywords_slovakia_eu_national_id_card` .

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_slovakia_eu_national_id_card` busca contenido que coincida con el patrón.

```xml
      <!-- Slovakia Personal Number -->
      <Entity id="951c26b7-3b35-4f73-924b-15dd599cb9ab" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
      </Entity>
    </Version>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

- azonosító szám
- número de nacimiento
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- número de id.
- identificación no
- identification number
- identifikačná karta č
- identifikačné číslo
- identity card no
- número de tarjeta de identidad
- národná identifikačná značka č
- número nacional
- nationalnumber #
- nemzeti személyazonosító igazolvány
- personalidnumber #
- rč
- rodne cislo
- rodné číslo
- social security number
- Ssn #
- Ssn
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- archivo de impuestos no
- tax file number
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