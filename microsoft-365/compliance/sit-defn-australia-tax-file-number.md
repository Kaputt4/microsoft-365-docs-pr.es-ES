---
title: Definición de entidad de número de archivo fiscal de Australia
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
description: Definición de entidad de tipo de información confidencial del número de archivo fiscal de Australia.
ms.openlocfilehash: 155bdbd2142d0c6c097907b0ab651ff74cfac46d
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000184"
---
# <a name="australia-tax-file-number"></a>Número de identificación fiscal (TFN) de Australia

## <a name="format"></a>Formato

de ocho a nueve dígitos

## <a name="pattern"></a>Patrón

Normalmente, los espacios se presentan de ocho a nueve dígitos como se indica a continuación:

- tres dígitos
- un espacio opcional
- tres dígitos
- un espacio opcional
- de dos a tres dígitos donde el último dígito es un dígito de comprobación

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función Func_australian_tax_file_number encuentra contenido que coincide con el patrón.
- No se encuentra ninguna palabra clave de Keyword_Australia_Tax_File_Number ni Keyword_number_exclusions.
- Se supera la suma de comprobación.

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_australia_tax_file_number"></a>Keyword_australia_tax_file_number

- australian business number
- marginal tax rate
- medicare levy
- portfolio number
- service veterans
- withholding tax
- individual tax return
- tax file number
- Tfn
