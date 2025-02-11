---
title: Definición de entidad de número del servicio de ciudadanos neerlandeses (BSN)
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
description: Definición de entidad de tipo de información confidencial del servicio de ciudadanos neerlandeses (BSN).
ms.openlocfilehash: 11b4c2a2354b074277761dca5d513747892d5d40
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68383313"
---
# <a name="netherlands-citizens-service-bsn-number"></a>Número del documento de identidad (BSN) de Países Bajos

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

ocho o nueve dígitos que contienen espacios opcionales

## <a name="pattern"></a>Patrón

ocho y nueve dígitos:

- tres dígitos
- un espacio (opcional)
- tres dígitos
- un espacio (opcional)
- dos o tres dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- Contenido de la función `Func_netherlands_bsn finds` que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_netherlands_bsn`.
- Se supera la suma de comprobación.

```xml
      <!-- Netherlands Citizen's Service (BSN) Number -->
      <Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_bsn" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card

- Bsn #
- Bsn
- burgerservicenummer
- número de servicio ciudadano
- número de persona
- número personal
- código numérico personal
- número relacionado con la persona
- persoonlijk nummer
- código de numerieke persoonlijke
- persoonsgebonden
- persoonsnummer
- nummer sociaal-fiscaal
- número social-fiscal
- Sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- número de identificación único
- número de identidad único
- uniqueidentityno #
