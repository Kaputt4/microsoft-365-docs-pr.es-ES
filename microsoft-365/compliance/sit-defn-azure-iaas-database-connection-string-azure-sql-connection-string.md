---
title: Cadena de conexión de base de datos de IAAS de Azure y definición de entidad de cadena de conexión Azure SQL
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
description: Cadena de conexión de base de datos iaas de Azure y Azure SQL definición de entidad de tipo de información confidencial de cadena de conexión.
ms.openlocfilehash: 894a849c318ad15ab9baac8343192428d633ce1b
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999713"
---
# <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Cadena de conexión de base de datos IAAS de Azure y cadena de conexión SQL de Azure

## <a name="format"></a>Formato

`Server`Cadena , `server`o `data source` seguida de los caracteres y cadenas descritos en el patrón siguiente, incluida la cadena `cloudapp.azure.com` o o `cloudapp.azure.net` `database.windows.net`, y la cadena `Password` o `password` o `pwd`.

## <a name="pattern"></a>Patrón

- la cadena `Server`, `server`o `data source`
- de cero a dos caracteres de espacios en blanco
- un signo igual (=)
- de cero a dos caracteres de espacios en blanco
- cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- Cadena "cloudapp.azure.<!--no-hyperlink-->com", "cloudapp.azure.<!--no-hyperlink-->net" o "database.windows.<!--no-hyperlink-->net"
- cualquier combinación de entre 1-300 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- la cadena `Password`, `password`o `pwd`
- de cero a dos caracteres de espacios en blanco
- un signo igual (=)
- de cero a dos caracteres de espacios en blanco
- uno o más caracteres que no son un punto y coma (;), comillas (") o apóstrofos (')
- un punto y coma (;), comillas (") o apóstrofos (')

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `CEP_Regex_AzureConnectionString` regular busca contenido que coincida con el patrón.
- La expresión `CEP_CommonExampleKeywords` regular no encuentra contenido que coincida con el patrón.

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
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
