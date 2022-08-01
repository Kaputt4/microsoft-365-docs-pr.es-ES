---
title: Definición de entidad de número de enrutamiento de ABA
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
description: Definición de entidad de tipo de información confidencial del número de enrutamiento de ABA.
ms.openlocfilehash: 5efc835b5d5dced7fbfe9a0b1ce7c59b89b60ac0
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999740"
---
# <a name="aba-routing-number"></a>Número de enrutamiento ABA

## <a name="format"></a>Formato

nueve dígitos que pueden estar en un patrón con formato o sin formato

## <a name="pattern"></a>Patrón

- dos dígitos en los intervalos 00-12, 21-32, 61-72 o 80
- dos dígitos
- un guion opcional
- cuatro dígitos
- un guion opcional
- un dígito

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una directiva tiene confianza media en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función Func_aba_routing encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_ABA_Routing.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función Func_aba_routing encuentra contenido que coincide con el patrón.

```xml
    <!-- ABA Routing Number -->
    <Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_aba_routing" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_aba_routing"></a>Keyword_aba_routing

- aba number
- Aba #
- Aba
- abarouting #
- abaroutingnumber
- americanbankassociationrouting #
- americanbankassociationroutingnumber
- bankrouting #
- bankroutingnumber
- Enrutamiento #
- enrutamiento no
- número de ruta
- routing transit number
- Enrutamiento #
- RTN
