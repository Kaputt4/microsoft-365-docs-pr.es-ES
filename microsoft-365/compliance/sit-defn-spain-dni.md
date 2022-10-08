---
title: Definición de entidad del DNI de España
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
description: Definición de entidad de tipo de información confidencial del DNI de España.
ms.openlocfilehash: 046c7ed6bcc567f5260bafa9c87a40a10a5a1a6a
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472966"
---
# <a name="spain-dni"></a>DNI de España

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

ocho dígitos seguidos de un carácter

## <a name="pattern"></a>Patrón

siete dígitos seguidos de un carácter

- ocho dígitos
- Un espacio o guión opcional
- una letra de verificación (no distingue mayúsculas de minúsculas)

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_spain_eu_DL_and_NI_number_citizen` o `Func_spain_eu_DL_and_NI_number_foreigner` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keywords_spain_eu_national_id_card"`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_spain_eu_DL_and_NI_number_citizen` o `Func_spain_eu_DL_and_NI_number_foreigner` encuentra contenido que coincide con el patrón.

```xml
      <!-- Spain DNI -->
      <Entity id="8e6251b9-47b4-40e8-a42b-0f80876be192" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

- carné de identidad
- dni#
- dni
- dninúmero#
- documento nacional de identidad
- identidad único
- identidadúnico#
- número de seguro
- national identification number
- identidad nacional
- nationalid#
- nationalidno#
- nie#
- nie
- nienúmero#
- número de identificación
- número nacional identidad
- número de identificación personal
- identidad personal no
- número de identidad único
- uniqueid#
