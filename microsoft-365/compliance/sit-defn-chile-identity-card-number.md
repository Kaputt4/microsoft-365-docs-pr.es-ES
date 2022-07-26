---
title: Definición de entidad del número de tarjeta de identidad de Chile
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
description: Definición de entidad de tipo de información confidencial del número de tarjeta de identidad de Chile.
ms.openlocfilehash: 1ec3b90d52d5404bf49a343cba7fb2c7f5464870
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999791"
---
# <a name="chile-identity-card-number"></a>Número del documento de identidad de Chile

## <a name="format"></a>Formato

de siete a ocho dígitos más delimitadores, un dígito de control o una letra

## <a name="pattern"></a>Patrón

de siete a ocho dígitos más delimitadores:

- de uno a dos dígitos
- un período opcional
- tres dígitos
- un período opcional
- tres dígitos
- un guión
- un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_chile_id_card` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_chile_id_card`.
- Se supera la suma de comprobación.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_chile_id_card` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_chile_id_card"></a>Keyword_chile_id_card

- cédula de identidad
- identificación
- national identification
- national identification number
- national id
- número de identificación nacional
- rol único nacional
- rol único tributario
- RUN
- RUT
- tarjeta de identificación
- Rol Único Nacional
- Rol Único Tributario
- RUN#
- RUT#
- nationaluniqueroleID#
- nacional identidad
- número identificación
- identidad número
- numero identificacion
- identidad numero
- Identidad chilena nro.
- Número de identidad chilena
- # de entidad chilena
- Registro Fiscal Único
- Rol Único Tributario
- Rol Fiscal Único
- Número Único Tributario
- Número Único Nacional
- Rol Único Nacional
- Rol Nacional Único
- Nro. de identidad de Chile
- Número de identidad de Chile
- # de identidad de Chile
- R.U.T
- R.U.N