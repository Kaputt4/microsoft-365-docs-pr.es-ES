---
title: Definición de entidad de cadena de conexión de caché de Azure Redis
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
description: Definición de entidad de tipo de información confidencial de cadena de conexión de Azure Redis Cache.
ms.openlocfilehash: f195440c1f93ec1818bf10e1c57cf391085cb733
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999893"
---
# <a name="azure-redis-cache-connection-string"></a>Cadena de conexión de caché de Azure Redis

## <a name="format"></a>Formato

`redis.cache.windows.net` Cadena seguida de los caracteres y cadenas descritos en el patrón siguiente, incluida la cadena `password` o `pwd`.

## <a name="pattern"></a>Patrón

- la cadena `redis.cache.windows.net`
- cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- la cadena `password` o `pwd`
- de cero a dos caracteres de espacios en blanco
- un signo igual (=)
- de cero a dos caracteres de espacios en blanco
- cualquier combinación de 43 caracteres que sean letras minúsculas o mayúsculas, dígitos, barra diagonal (/) o signo más (+)
- un signo igual (=)

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `CEP_Regex_AzureRedisCacheConnectionString` regular busca contenido que coincida con el patrón.
- La expresión `CEP_CommonExampleKeywords` regular no encuentra contenido que coincida con el patrón.

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

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
