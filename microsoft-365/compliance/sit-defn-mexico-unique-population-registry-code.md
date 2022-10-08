---
title: Definición de entidad de Clave Única de Registro de Población (CURP) de México
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
description: Definición de entidad de tipo de información confidencial de Clave Única de Registro de Población (CURP) de México.
ms.openlocfilehash: 20afce26f7769e1a322c21109a8b934dbf14ca3d
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68384083"
---
# <a name="mexico-unique-population-registry-code-curp"></a>Clave Única de Registro de Población (CURP) de México

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

patrón alfanumérico de 18 caracteres

## <a name="pattern"></a>Patrón

- cuatro letras (sin distinción entre mayúsculas y minúsculas)
- seis dígitos que indican una fecha válida
- una letra - H/h o M/m
- dos letras que indican un código de estado nacional válido
- tres letras
- una letra o un dígito
- un dígito

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_mexico_population_registry_code` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_mexico_population_registry_code`.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_mexico_population_registry_code` encuentra contenido que coincide con el patrón.

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
- Unique Population Registry Code
- unique population code
- CURP
- Personal ID
- Unique ID
- personalid
- personalidnumber
- uniqueidkey
- uniqueidnumber
- clave única
- clave unica
- clave personal Identidad
- clave de identidad personal
- ClaveÚnica
- claveunica
- clavepersonalIdentidad
