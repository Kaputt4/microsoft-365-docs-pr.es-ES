---
title: Definición de entidad de número de cuenta médica de Australia
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
description: Definición de entidad de tipo de información confidencial de número de cuenta médica de Australia.
ms.openlocfilehash: c17de71ef0c16b5c14ba118c66ae0d9274ce4468
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999530"
---
# <a name="australia-medical-account-number"></a>Número de la tarjeta sanitaria de Australia

## <a name="format"></a>Formato

Entre 10 y 11 dígitos

## <a name="pattern"></a>Patrón

Entre 10 y 11 dígitos:

- el primer dígito está en el intervalo de 2 a 6
- El noveno dígito es un dígito de comprobación
- El décimo dígito es el dígito de emisión
- El dígito 11 (opcional) es el número individual.

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función Func_australian_medical_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_Australia_Medical_Account_Number.
- Se supera la suma de comprobación.

```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_australia_medical_account_number"></a>Keyword_Australia_Medical_Account_Number

- bank account details
- medicare payments
- mortgage account
- bank payments
- information branch
- credit card loan
- department of human services
- local service
- Medicare
