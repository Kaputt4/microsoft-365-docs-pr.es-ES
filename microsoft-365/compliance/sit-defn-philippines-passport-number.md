---
title: Definición de entidad de número de pasaporte de Filipinas
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
description: Definición de entidad de tipo de información confidencial del número de pasaporte de Filipinas.
ms.openlocfilehash: 227b1eda0571aeccac84be5fc82c469ae1724517
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68382939"
---
# <a name="philippines-passport-number"></a>Número de pasaporte de Filipinas

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

siete u ocho o nueve caracteres alfanuméricos

## <a name="pattern"></a>Patrón

Siete u ocho o nueve caracteres alfanuméricos:

- una letra seguida de seis dígitos o
- dos letras seguidas de seis dígitos o
- dos letras seguidas de siete dígitos o
- una letra seguida de siete dígitos seguida de una letra.

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres: 

- La expresión regular Regex_philippines_passport_number busca contenido que coincida con el patrón. 
- Se encuentra una palabra clave de Keyword_philippines_passport_number. 

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres: 

- La expresión regular Regex_philippines_passport_number busca contenido que coincida con el patrón. 

```xml
     <!-- Philippines Passport Number -->
     <Entity id="6fa57f91-314a-4561-8248-7ab921957448" patternsProximity="300" recommendedConfidence="85" relaxProximity="true" filters="philippines_passport_filter">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_philippines_passport_number" />
          <Match idRef="Keyword_philippines_passport_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_philippines_passport_number" />
        </Pattern>
     </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_philippines_passport_number"></a>Keyword_philippines_passport_number 

- Pasaporte 
- pasaporte no 
- passport number 
- pasaporte# 
- passportno 
- passport no. 
- passportno # 
- libro de pasaportes 
- passportbook # 
- pasaporte 
- numero ng pasaporte 
- libro ng pasaporte 
