---
title: Definición de entidad de número de seguro médico europeo de Finlandia
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
description: Definición de entidad de tipo de información confidencial de número de seguro médico europeo de Finlandia.
ms.openlocfilehash: 799f664f03f91fa35c01cc87701046faddab5dde
ms.sourcegitcommit: 72d10d0bc29ecc8b19c395f1815dc48b549096d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2022
ms.locfileid: "67367387"
---
# <a name="finland-european-health-insurance-number"></a>Número de la tarjeta sanitaria europea de Finlandia

## <a name="format"></a>Formato

Número de 20 dígitos

## <a name="pattern"></a>Patrón

Número de 20 dígitos:

- 10 dígitos: 8024680246
- un espacio opcional o un guion
- 10 dígitos

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- El regex `Regex_Finland_European_Health_Insurance_Number` busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_Finland_European_Health_Insurance_Number`.

```xml
      <!-- Finland European Health Insurance Number -->
      <Entity id="60f75aed-81bf-4625-89b0-0846b9248ee7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Finland_European_Health_Insurance_Number"/>
          <Match idRef="Keyword_Finland_European_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_finland_european_health_insurance_number"></a>Keyword_finland_european_health_insurance_number

- ehic #
- ehic
- finlandehicnumber #
- finska sjukförsäkringskort
- tarjeta sanitaria
- tarjeta de seguro médico
- número de seguro médico
- hälsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- sjukförsäkring nummer
- sjukförsäkringskort
- suomen sairausvakuutuskortti
- terveyskortti
