---
title: Definición de entidad de número de seguridad social de Francia
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
description: Definición de entidad de tipo de información confidencial del número de seguridad social de Francia (INSEE).
ms.openlocfilehash: 3378b452e8136e5ca62fe49932ba23949eb6a85d
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66951316"
---
# <a name="france-social-security-number-insee"></a>Número de seguridad social de Francia (INSEE)

## <a name="format"></a>Formato

15 dígitos

## <a name="pattern"></a>Patrón

Debe coincidir uno de los dos patrones:

- 13 dígitos seguidos de un espacio seguido de dos dígitos

  o

- 15 dígitos consecutivos

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una directiva DLP tiene una gran confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_french_insee` busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_fr_insee` .
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza media en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_french_insee` o `Func_fr_insee` busca contenido que coincida con el patrón.
- Se supera la suma de comprobación.

```xml
    <!-- France INSEE -->
    <Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Keyword_fr_insee" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- code sécu
- d'identité nationale
- Insee
- fssn #
- le numéro d'identification nationale
- le code de la sécurité sociale
- national id
- national identification
- no d'identité
- No. d'identité
- numéro d'assurance
- numéro d'identité
- numero d'identite
- numéro de sécu
- numéro de sécurité sociale
- no d'identite
- No. d'identite
- Ssn
- Ssn #
- sécurité sociale
- securité sociale
- securite sociale
- socialsecuritynumber
- social security number
- social security code
- social insurance number