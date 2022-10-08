---
title: Definición de entidad de número de seguro médico de Francia
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
description: Definición de entidad de tipo de información confidencial del número de seguro médico de Francia.
ms.openlocfilehash: 59fed01945647b483601a1917fe50f2b37732ac2
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68380016"
---
# <a name="france-health-insurance-number"></a>Número del seguro sanitario de Francia

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

Número de 21 dígitos

## <a name="pattern"></a>Patrón

Número de 21 dígitos:

- 10 dígitos
- un espacio opcional
- 10 dígitos
- un espacio opcional
- un dígito

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- el regex `Regex_France_Health_Insurance_Number` busca contenido que coincida con el patrón.
- se encuentra una palabra clave de `Keyword_France_Health_Insurance_Number` .

```xml
      <!-- France Health Insurance Number -->
      <Entity id="9bc2069e-76df-4ff9-ac02-2f519469e236" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_France_Health_Insurance_Number"/>
          <Match idRef="Keyword_France_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
## <a name="keywords"></a>Palabras clave

### <a name="keyword_france_health_insurance_number"></a>Keyword_France_health_insurance_number

- tarjeta de seguro
- carte vitale
- carte d'assuré social
