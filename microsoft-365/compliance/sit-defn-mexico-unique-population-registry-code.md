---
title: Definición de entidad del Código único de registro de población (CURP) de México
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
description: Definición de entidad de tipo de información confidencial del Código único de población de México (CURP).
ms.openlocfilehash: 806f7e9b0d2dd797b17ad848d160c6f74c04e1e2
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66951268"
---
# <a name="mexico-unique-population-registry-code-curp"></a>Código del Registro único de población de México (CURP)

## <a name="format"></a>Formato

Patrón alfanumérico de 18 caracteres

## <a name="pattern"></a>Patrón

- cuatro letras (sin distinción entre mayúsculas y minúsculas)
- seis dígitos que indican una fecha válida
- una letra: H/h o M/m
- dos letras que indican un código de estado mexicano válido
- tres letras
- una letra o dígito
- un dígito

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una directiva DLP tiene una gran confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_mexico_population_registry_code` busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_mexico_population_registry_code` .

Una directiva DLP tiene confianza media en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_mexico_population_registry_code` busca contenido que coincida con el patrón.

```xml
    <!-- Mexico Unique Population Registry Code (CURP) -->
      <Entity id="e905ad4d-5a74-406d-bf36-b1efca798af4" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_mexico_population_registry_code" />
          <Match idRef="Keyword_mexico_population_registry_code" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_mexico_population_registry_code" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_mexico_population_registry_code"></a>Keyword_mexico_population_registry_code

- Clave Única de Registro de Población
- Clave Unica de Registro de Poblacion
- Código único del Registro de población
- código de rellenado único
- CURP
- Identificador personal
- Identificador único
- personalid
- personalidnumber
- uniqueidkey
- uniqueidnumber
- clave única
- clave unica
- clave personal Identidad
- personal Identidad Clave
- ClaveÚnica
- claveunica
- clavepersonalIdentidad