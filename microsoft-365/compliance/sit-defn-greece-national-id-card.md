---
title: Definición de entidad de tarjeta de identificación nacional de Grecia
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
description: Definición de entidad de tipo de información confidencial de la tarjeta de identificación nacional de Grecia.
ms.openlocfilehash: 9f4ae0728138a33640a4afddfb73ed04692e1723
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68379730"
---
# <a name="greece-national-id-card"></a>Documento nacional de identidad de Grecia

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

Combinación de 7 u 8 letras y números más un guión

## <a name="pattern"></a>Patrón

Siete letras y números (formato antiguo):

- Una letra (cualquier letra del alfabeto griego) 
- Un guión 
- Seis dígitos

Ocho letras y números (nuevo formato):

- Dos letras cuyos caracteres en mayúscula se encuentren tanto en el alfabeto griego como latino (ABEZHIKMNOPTYX) 
- Un guión 
- Seis dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular `Regex_greece_id_card` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_greece_id_card`.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular `Regex_greece_id_card` encuentra contenido que coincide con el patrón.

```xml
      <!-- Greece National ID Card -->
      <Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_id_card" />
          <Match idRef="Keyword_greece_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_greece_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_greece_id_card"></a>Keyword_greece_id_card

- greek id
- id. nacional griego
- griego tarjeta de identificación personal
- id. de la policía griega
- documento de identidad
- tautotita
- ταυτότητα
- ταυτότητας
