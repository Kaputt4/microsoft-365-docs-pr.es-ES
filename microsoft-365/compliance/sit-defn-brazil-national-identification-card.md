---
title: Definición de entidad de la tarjeta de identificación nacional (RG) del Brasil
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
description: Definición de entidad de tipo de información confidencial de la tarjeta nacional de identificación (RG) de Brasil.
ms.openlocfilehash: 7f4fe7a0eda911639c0c7650d4ac71f07dfe4f3a
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999179"
---
# <a name="brazil-national-identification-card-rg"></a>Documento nacional de identidad de Brasil (RG)

## <a name="format"></a>Formato

Registro Geral (formato antiguo): nueve dígitos

Registro de Identidade (RIC) (nuevo formato): 11 dígitos

### <a name="pattern"></a>Patrón

Registro de Geral (formato antiguo):

- dos dígitos
- un punto
- tres dígitos
- un punto
- tres dígitos
- un guion
- un dígito que es un dígito de comprobación

Registro de Identidade (RIC) (nuevo formato):

- 10 dígitos
- un guion
- un dígito que es un dígito de comprobación

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_brazil_rg` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_brazil_rg`.
- Se supera la suma de comprobación.

```xml
      <!-- Brazil National ID Card (RG) -->
      <Entity id="486de900-db70-41b3-a886-abdf25af119c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_brazil_rg" />
          <Match idRef="Keyword_brazil_rg" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_brazil_rg"></a>Keyword_brazil_rg

- Cédula de identidade
- documento de identidad
- national id
- número de rregistro
- registro de Iidentidade
- registro geral
- RG (esta palabra clave distingue mayúsculas de minúsculas)
- RIC (esta palabra clave distingue mayúsculas de minúsculas)