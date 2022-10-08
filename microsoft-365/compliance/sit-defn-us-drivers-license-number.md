---
title: Definición de entidad de número de licencia de conducir de Ee. UU.
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
description: Definición de entidad de tipo de información confidencial del número de licencia de conducir de EE. UU.
ms.openlocfilehash: 9659bfce35958409e54ffe7ff15e948e5b980d6f
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472571"
---
# <a name="us-drivers-license-number"></a>Número de licencia de conducir de EE. UU.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

Depende del estado

## <a name="pattern"></a>Patrón

depende del estado, por ejemplo, Nueva York:

- nueve dígitos con formato como ddd ddd ddd coincidirán.
- nueve dígitos como dddddddddd no coincidirán.

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_new_york_drivers_license_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_[state_name]_drivers_license_name`.
- Se encuentra una palabra clave de `Keyword_us_drivers_license`.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_new_york_drivers_license_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_[state_name]_drivers_license_name`.
- Se encuentra una palabra clave de `Keyword_us_drivers_license_abbreviations`.
- No se encuentra ninguna palabra clave de `Keyword_us_drivers_license` .

```xml
<Entity id="dfeb356f-61cd-459e-bf0f-7c6d28b458c6 patternsProximity="300">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_us_drivers_license_abbreviations"></a>Keyword_us_drivers_license_abbreviations

- Dl
- Dls
- Cdl
- CDL
- Id.
- Identificadores
- Dl #
- Dls #
- Cdl #
- CDL #
- Id #
- Identificadores #
- ID number
- ID numbers
- Lic
- Lic #
- DLN

### <a name="keyword_us_drivers_license"></a>Keyword_us_drivers_license

- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- Driver Lic
- Driver Lics
- Driver License
- Driver Licenses
- DriversLic
- DriversLics
- DriversLicense
- DriversLicenses
- Drivers Lic
- Drivers Lics
- Drivers License
- Drivers Licenses
- Driver'Lic
- Driver'Lics
- Licencia de conducir
- Licencias de conducir
- Driver' Lic
- Driver' Lics
- Driver' License
- Driver' Licenses
- Driver'sLic
- Driver'sLics
- Driver'sLicense
- Driver'sLicenses
- Driver's Lic
- Driver's Lics
- Driver's License
- Permisos de conducción
- identification number
- identification numbers
- identification #
- id card
- id cards
- identification card
- identification cards
- DriverLic #
- DriverLics #
- DriverLicense #
- DriverLicenses #
- Driver Lic#
- Driver Lics#
- Driver License#
- Driver Licenses#
- DriversLic #
- DriversLics #
- DriversLicense #
- DriversLicenses #
- Drivers Lic#
- Drivers Lics#
- Drivers License#
- Drivers Licenses#
- Driver'Lic #
- Driver'Lics #
- Licencia de conducir #
- Licencias de conducir #
- Driver' Lic#
- Driver' Lics#
- Driver' License#
- Driver' Licenses#
- Driver'sLic #
- Driver'sLics #
- Driver'sLicense #
- Driver'sLicenses #
- Driver's Lic#
- Driver's Lics#
- Driver's License#
- Driver's Licenses#
- id card#
- id cards#
- identification card#
- identification cards#

### <a name="keyword_state_name_drivers_license_name"></a>Keyword_[state_name]_drivers_license_name

- abreviatura de estado (por ejemplo, "NY")
- state name (por ejemplo, "New York")
