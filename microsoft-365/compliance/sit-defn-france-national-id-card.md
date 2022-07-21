---
title: Definición de entidad de la tarjeta de identificación nacional (CNI) de Francia
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
description: Definición de entidad de tipo de información confidencial de la tarjeta de identificación nacional (CNI) de Francia.
ms.openlocfilehash: 35a6481e657d20a83ed1b80a6d06ad8ebf1c9cdf
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66951324"
---
# <a name="france-national-id-card-cni"></a>Tarjeta de identificación nacional de Francia (CNI)

## <a name="format"></a>Formato

12 dígitos

## <a name="pattern"></a>Patrón

12 dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_france_cni` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keywords_france_eu_national_id_card` .

```xml
    <!-- France CNI -->
    <Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
        <Match idRef="Keywords_france_eu_national_id_card" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_france_eu_national_id_card"></a>Keywords_france_eu_national_id_card

- card number
- carte nationale d'identité
- carte nationale d'idenite no
- Cni #
- Cni
- compte bancaire
- national identification number
- identidad nacional
- nationalidno #
- numéro d'assurance maladie
- numéro de carte vitale