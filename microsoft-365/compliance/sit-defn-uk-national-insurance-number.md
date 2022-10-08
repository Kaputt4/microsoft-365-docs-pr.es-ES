---
title: Reino Unido definición de entidad del número de seguro nacional (NINO)
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
description: Reino Unido número de seguro nacional (NINO) definición de entidad de tipo de información confidencial.
ms.openlocfilehash: a975ec23f2677846503e87087470452e952a7df6
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472900"
---
# <a name="uk-national-insurance-number-nino"></a>Reino Unido número de la seguridad social (NINO)

Esta entidad de tipo de información confidencial se incluye en el tipo de información confidencial Número de identificación nacional de la UE. También está disponible como una entidad de tipo de información confidencial independiente.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

siete caracteres o nueve caracteres separados por espacios o guiones

## <a name="pattern"></a>Patrón

dos patrones posibles:

- dos letras (los NINO válidos usan solo ciertos caracteres de este prefijo, que este patrón valida; no distingue mayúsculas de minúsculas)
- seis dígitos
- 'A', 'B', 'C' o 'D' (como el prefijo, solo se permiten determinados caracteres en el sufijo; no distinguen mayúsculas de minúsculas)

O

- dos letras
- un espacio o guion
- dos dígitos
- un espacio o guion
- dos dígitos
- un espacio o guion
- dos dígitos
- un espacio o guion
- 'A', 'B', 'C' o 'D'

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_uk_nino` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_uk_nino`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_uk_nino` encuentra contenido que coincide con el patrón.

```xml
    <!-- U.K. NINO -->
    <Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Match idRef="Keyword_uk_nino" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_uk_nino"></a>Keyword_uk_nino

- national insurance number
- national insurance contributions
- protection act
- Seguro
- social security number
- insurance application
- medical application
- social insurance
- medical attention
- social security
- great britain
- Número de NI
- NI No.
- NI #
- NI #
- Seguro #
- insurancenumber
- nationalinsurance #
- nationalinsurancenumber
