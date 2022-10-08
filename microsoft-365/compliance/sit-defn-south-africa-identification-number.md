---
title: Definición de entidad de número de identificación de Sudáfrica
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
description: Definición de entidad de tipo de información confidencial del número de identificación de Sudáfrica.
ms.openlocfilehash: ca385d9255ce5906769307ad1b29b5c377cec4bf
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472044"
---
# <a name="south-africa-identification-number"></a>Número del documento de identidad de Sudáfrica

### <a name="format"></a>Formato

13 dígitos que pueden contener espacios

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="pattern"></a>Patrón

13 dígitos:

- seis dígitos en el formato AAAADD, que son la fecha de nacimiento
- cuatro dígitos
- un indicador de ciudadanía de un solo dígito
- el dígito "8" o "9"
- un dígito, que es un dígito de suma de comprobación

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_south_africa_identification_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_south_africa_identification_number`.
- Se supera la suma de comprobación.

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_south_africa_identification_number"></a>Keyword_south_africa_identification_number

- tarjeta de identidad
- Id.
- Identificación
