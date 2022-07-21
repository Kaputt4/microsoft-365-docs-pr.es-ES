---
title: Definición de entidad de número de tarjeta de ciudadano de Portugal
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
description: Definición de entidad de tipo de información confidencial de número de tarjeta de ciudadano de Portugal.
ms.openlocfilehash: 95aa6f824de748dfc513ef5d509b6ae5e1c58119
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66951143"
---
# <a name="portugal-citizen-card-number"></a>Número de tarjeta de ciudadano de Portugal

## <a name="format"></a>Formato

ocho dígitos

## <a name="pattern"></a>Patrón

ocho dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una directiva DLP tiene una gran confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_portugal_citizen_card` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_portugal_citizen_card` .

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_portugal_citizen_card"></a>Keyword_portugal_citizen_card

- bilhete de identidade
- cartão de cidadão
- tarjeta de ciudadano
- número de documento
- documento de identificação
- número de id.
- identificación no
- identification number
- identity card no
- número de tarjeta de identidad
- tarjeta de identificación nacional
- Nic
- número bi de portugal
- número de identificação civil
- número de identificação fiscal
- número do documento
- portugal bi number