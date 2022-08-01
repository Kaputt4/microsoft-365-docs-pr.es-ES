---
title: Definición de entidad de SAS de Azure
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
description: Definición de entidad de tipo de información confidencial de SAS de Azure.
ms.openlocfilehash: c7d63497a94204b77f83c5b357700311bf332e8c
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999890"
---
# <a name="azure-sas"></a>Azure SAS

## <a name="format"></a>Formato

Cadena `sig` seguida de los caracteres y cadenas descritos en el patrón siguiente.

## <a name="pattern"></a>Patrón

- la cadena `sig`
- de cero a dos caracteres de espacios en blanco
- un signo igual (=)
- de cero a dos caracteres de espacios en blanco
- cualquier combinación de entre 43 y 53 caracteres que sean letras minúsculas o mayúsculas, dígitos o el signo de porcentaje (%)
- la cadena `%3d`
- cualquier carácter que no sea un signo de letras minúsculas o mayúsculas, dígitos o porcentajes (%)

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `CEP_Regex_AzureSAS` regular busca contenido que coincida con el patrón.

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```
