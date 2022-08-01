---
title: Definición de entidad del número de entidad jurídica de Brasil (CNPJ)
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
description: Definición de entidad de tipo de información confidencial del número de entidad jurídica (CNPJ) de Brasil.
ms.openlocfilehash: a8cf09eb283cea08e72a5858e7bfd4752486a01e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000229"
---
# <a name="brazil-legal-entity-number-cnpj"></a>Código de identificación fiscal de Brasil (CNPJ)

## <a name="format"></a>Formato

14 dígitos que incluyen un número de registro, número de sucursal y dígitos de comprobación, además de delimitadores

## <a name="pattern"></a>Patrón

14 dígitos más delimitadores:

- dos dígitos
- un punto
- tres dígitos
- un punto
- tres dígitos (estos primeros ocho dígitos son el número de registro)
- una barra diagonal
- número de rama de cuatro dígitos
- un guion
- dos dígitos que son dígitos de comprobación

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_brazil_cnpj` encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de `Keyword_brazil_cnpj`.
- Se supera la suma de comprobación.

Una política de DLP tiene confianza media en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_brazil_cnpj` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_brazil_cnpj"></a>Keyword_brazil_cnpj

- CNPJ
- CNPJ/MF
- CNPJ-MF
- Registro nacional de entidades jurídicas
- Registro de contribuyentes
- Entidad jurídica
- Entidades jurídicas
- Estado de registro
- Business
- Empresa
- CNPJ
- Cadastro Nacional da Pessoa Jurídica
- Cadastro Geral de Contribuintes
- CGC
- Pessoa jurídica
- Pessoas jurídicas
- Situação cadastral
- Inscrição
- Empresa