---
title: Definición de entidad de código de identificación de población tailandesa
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
description: Definición de entidad de tipo de información confidencial del código de identificación de población tailandesa.
ms.openlocfilehash: 6d39a5a95a4969af61b32bec474d8d3b025f8f8a
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68471978"
---
# <a name="thai-population-identification-code"></a>Código de identificación de la población tailandesa

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

13 dígitos

## <a name="pattern"></a>Patrón

13 dígitos:

- el primer dígito no es cero o nueve
- 12 dígitos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_Thai_Citizen_Id` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_Thai_Citizen_Id`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_Thai_Citizen_Id` encuentra contenido que coincide con el patrón.

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_thai_citizen_id"></a>Keyword_thai_citizen_Id

- Número de id.
- Número de identificación
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน
