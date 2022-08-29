---
title: Definición de entidad de tarjeta de identidad de Austria
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
description: Definición de entidad de tipo de información confidencial de la tarjeta de identidad de Austria.
ms.openlocfilehash: d180c3e46c3810997bfe54a3521c840f833aff02
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367629"
---
# <a name="austria-identity-card"></a>Documento de identidad de Austria

## <a name="format"></a>Formato

Una combinación de 24 caracteres de letras, dígitos y caracteres especiales

## <a name="pattern"></a>Patrón

24 caracteres:

- 22 letras (sin distinguir mayúsculas de minúsculas), dígitos, barras diagonales inversas, barras diagonales o signos más

- dos letras (no distinguen mayúsculas de minúsculas), dígitos, barras diagonales inversas, barras diagonales, signos más o signos iguales

## <a name="checksum"></a>Suma de comprobación

No aplicable

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión regular `Regex_austria_eu_national_id_card` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_austria_eu_national_id_card`.

```xml
      <!-- Austria Identity Card -->
      <Entity id="5ec06c3b-007e-4820-8343-7ff73b889735" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

- número de identidad
- national id
- personalausweis republik österreich