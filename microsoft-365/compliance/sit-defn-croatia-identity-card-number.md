---
title: Definición de entidad de número de tarjeta de identidad de Croacia
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
description: Definición de entidad de tipo de información confidencial del número de tarjeta de identidad de Croacia.
ms.openlocfilehash: c1a281af470557623e649f29c98594992848779d
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000118"
---
# <a name="croatia-identity-card-number"></a>Número del documento de identidad de Croacia

Esta entidad se incluye en el tipo de información confidencial Número de identificación nacional de la UE. Está disponible como una entidad de tipo de información confidencial independiente.

## <a name="format"></a>Formato

nueve dígitos

## <a name="pattern"></a>Patrón

nueve dígitos consecutivos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_croatia_id_card` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_croatia_id_card`.

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_croatia_id_card"></a>Keyword_croatia_id_card

- majstorski broj građana
- número de ciudadano maestro
- nacionalni identifikacijski broj
- national identification number
- oib #
- oib
- osobna iskaznica
- osobni id.
- osobni identifikacijski broj
- número de identificación personal
- porezni broj
- porezni identifikacijski broj
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