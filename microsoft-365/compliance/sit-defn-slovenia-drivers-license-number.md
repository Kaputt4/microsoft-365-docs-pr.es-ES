---
title: Definición de entidad de número de licencia de conducir de Eslovenia
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
description: Definición de entidad de tipo de información confidencial del número de licencia de conducir de Eslovenia.
ms.openlocfilehash: 760972a7780ef6438b9e1c3109be26ddcba75dcb
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950900"
---
# <a name="slovenia-drivers-license-number"></a>Número de licencia de conducir de Eslovenia

## <a name="format"></a>Formato

nueve dígitos sin espacios ni delimitadores

## <a name="pattern"></a>Patrón

nueve dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una directiva DLP tiene confianza media en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_slovenia_eu_driver's_license_number` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keywords_eu_driver's_license_number` o `Keywords_slovenia_eu_driver's_license_number` .

```xml
      <!-- Slovenia Driver's License Number -->
      <Entity id="d5bc089a-f2ee-433d-a6b1-5c253051d6f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
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

### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver's_license_number

- vozniško dovoljenje
- licencia de vozniška številka
- vozniških dovoljenj
- številka vozniškega dovoljenja
- številke vozniških dovoljenj