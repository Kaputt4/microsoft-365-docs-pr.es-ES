---
title: Definición de entidad de número de la Agencia antidrogas (DEA)
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
description: Definición de entidad de tipo de información confidencial de número de la Agencia de aplicación de drogas (DEA).
ms.openlocfilehash: 7b1ade056621f619d8be0293708dd51cfc2e85dd
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999329"
---
# <a name="drug-enforcement-agency-dea-number"></a>Número de la Administración de Control de Drogas (DEA)

## <a name="format"></a>Formato

dos letras seguidas de siete dígitos

## <a name="pattern"></a>Patrón

El patrón debe incluir todo lo siguiente:

- una letra (no distingue mayúsculas de minúsculas) de este conjunto de letras posibles: A/B/F/G/M/P/R, que es un código registrador
- una letra (no distingue mayúsculas de minúsculas), que es la primera letra del apellido o el dígito '9' del solicitante de registro
- siete dígitos, el último de los cuales es el dígito de comprobación

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_dea_number` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_dea_number`
- Se supera la suma de comprobación.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_dea_number` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
    <!-- DEA Number -->
    <Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_dea_number" />
      </Pattern>
      <Version minEngineVersion="15.20.1207.000" maxEngineVersion="15.20.3134.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
        </Pattern>
      </Version>
      <Version minEngineVersion="15.20.3135.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
          <Match idRef="Keyword_dea_number" />
        </Pattern>
      </Version>
    </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_dea_number"></a>Keyword_dea_number

- Dea
- Dea #
- administración de la aplicación de drogas
- agencia de aplicación de drogas