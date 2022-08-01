---
title: Definición de entidad de clave de autenticación de Azure DocumentDB
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
description: Definición de entidad de tipo de información confidencial de clave de autenticación de Azure DocumentDB.
ms.openlocfilehash: e499d185b0a1752960f71f659a212aa0422154f4
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999428"
---
# <a name="azure-documentdb-auth-key"></a>Clave de autenticación de Azure DocumentDB

## <a name="format"></a>Formato

Cadena `DocumentDb` seguida de los caracteres y cadenas descritos en el patrón siguiente.

## <a name="pattern"></a>Patrón

- Cadena `DocumentDb`
- Cualquier combinación de entre 3-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- Mayor que el símbolo (>), un signo igual (=), una comilla (") o un apóstrofo (')
- Cualquier combinación de 86 letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)
- Dos signos iguales (=)

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `CEP_Regex_AzureDocumentDBAuthKey` regular busca contenido que coincida con el patrón.
- La expresión `CEP_CommonExampleKeywords` regular no encuentra contenido que coincida con el patrón.

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

Este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave.

- Contoso
- Fabrikam
- Northwind
- Sandbox
- Onebox
- Localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int.<!--no-hyperlink-->Red
