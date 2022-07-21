---
title: Definición de entidad de número de licencia de conducir de Eslovaquia
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
description: Eslovaquia driver's license number sensitive information type entity definition.
ms.openlocfilehash: c08bbccf21ed33939a36012d44fb448ad6fd7c56
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950912"
---
# <a name="slovakia-drivers-license-number"></a>Número de licencia de conducir de Eslovaquia

## <a name="format"></a>Formato

un carácter seguido de siete dígitos

## <a name="pattern"></a>Patrón

un carácter seguido de siete dígitos

- una letra (no distingue mayúsculas de minúsculas) o un dígito
- siete dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una directiva DLP tiene confianza media en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_slovakia_eu_driver's_license_number` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keywords_eu_driver's_license_number` o `Keywords_slovakia_eu_driver's_license_number` .

```xml
      <!-- Slovakia Driver's License Number -->
      <Entity id="14240c22-b6de-4ce5-a90b-137f74252513" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver's_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- lics del conductor
- driver license
- driver licenses
- permiso de conducir
- licencias de conducir
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- licencias de conducir
- driver'lic
- driver'lics
- driver'license
- licencias de conducir
- permiso de conducir
- licencias de conducir
- lic del conductor
- lics del conductor
- licencia de conducir
- licencias de conducir
- permiso de conducir
- licencias de conducir
- driver'slic
- slics del conductor
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic del conductor
- lics del conductor
- driver's license
- driver's licenses
- driver's licence
- licencias de conducir
- Dl #
- Dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- lics del conductor #
- licencia de conducir #
- licencias de conducir #
- licencias de conducir #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- licencia de conducir #
- licencias de conducir #
- permiso de conducir #
- licencias de conducir #
- driver'lic #
- driver'lics #
- driver'license #
- licencias de conducir #
- permiso de conducir #
- licencias de conducir #
- lic del conductor #
- lics del conductor #
- licencia de conducir #
- licencias de conducir #
- permiso de conducir #
- licencias de conducir #
- driver'slic #
- slics del conductor #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic del conductor #
- lics del conductor #
- licencia de conducir #
- licencias de conducir #
- permiso de conducir #
- licencias de conducir #
- driving licence
- driving license
- dlno #
- driv lic
- driv licen
- licencia driv
- licencias de driv
- licencia driv
- licencias de driv
- driver licen
- drivers licen
- licencia de conductor
- conducir lic
- conducir licen
- licencias de conducir
- driving licence
- driving licences
- permiso de conducir
- dl no
- dlno
- dl number

### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver's_license_number

- vodičský preukaz
- vodičské preukazy
- vodičského preukazu
- vodičských preukazov