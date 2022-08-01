---
title: Definición de entidad de número de tarjeta de identificación de Malasia
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
description: Definición de entidad de tipo de información confidencial del número de tarjeta de identificación de Malasia.
ms.openlocfilehash: ed233a9aa91c1c178644c4468271ee6839c55268
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999935"
---
# <a name="malaysia-identification-card-number"></a>Número del documento de identidad de Malasia

## <a name="format"></a>Formato

12 dígitos que contienen guiones opcionales

## <a name="pattern"></a>Patrón

12 dígitos:

- seis dígitos en el formato AAAADD, que son la fecha de nacimiento
- un guión (opcional)
- código de lugar de nacimiento de dos letras
- un guión (opcional)
- tres dígitos aleatorios
- código de género de un dígito

## <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `Regex_malaysia_id_card_number` regular busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_malaysia_id_card_number`.

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_malaysia_id_card_number"></a>Keyword_malaysia_id_card_number

- tarjeta de aplicación digital
- i/c
- i/c no
- Ic
- ic no
- id card
- tarjeta de identificación
- documento de identidad
- k/p
- k/p no
- kad akuan diri
- kad aplikasi digital
- kad pengenalan malasia
- Kp
- kp no
- mykad
- mykas
- mykid
- mypr
- mytentera
- tarjeta de identidad de malasia
- tarjeta de identidad malasia
- nric
- tarjeta de identificación personal