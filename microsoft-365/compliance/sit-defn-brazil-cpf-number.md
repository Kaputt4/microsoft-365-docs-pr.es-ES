---
title: Definición de entidad de número CPF de Brasil
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
description: Definición de entidad de tipo de información confidencial del número CPF de Brasil.
ms.openlocfilehash: b8164d44f20237b5eb74d45369f3bffbe1dc07e3
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66950969"
---
# <a name="brazil-cpf-number"></a>Número de CPF de Brasil

## <a name="format"></a>Formato

11 dígitos incluido un dígito de control y que pueden tener o no formato

## <a name="pattern"></a>Patrón

Formato:

- tres dígitos
- un punto
- tres dígitos
- un punto
- tres dígitos
- un guion
- dos dígitos que son dígitos de comprobación

Sin formato:

- 11 dígitos, donde los dos últimos dígitos son dígitos de control

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una directiva DLP tiene una gran confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_brazil_cpf` busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de `Keyword_brazil_cpf` .
- Se supera la suma de comprobación.

Una directiva DLP tiene confianza media en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_brazil_cpf` busca contenido que coincida con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_brazil_cpf"></a>Keyword_brazil_cpf

- CPF
- Identificación
- Registro
- Ingresos
- Cadastro de Pessoas Físicas
- Imposto
- Identificação
- Inscrição
- Receita