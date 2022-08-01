---
title: SQL Server definición de entidad de cadena de conexión
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
description: SQL Server definición de entidad de tipo de información confidencial de cadena de conexión.
ms.openlocfilehash: 503b2bae244cec8de5da29228f6517433a162ca1
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000073"
---
# <a name="sql-server-connection-string"></a>Cadena de conexión de SQL Server

## <a name="format"></a>Formato

`User Id`Cadena , `User ID`, `uid`o `UserId` seguida de los caracteres y cadenas descritos en el patrón siguiente.

## <a name="pattern"></a>Patrón

- la cadena `User Id`, `User ID`, `uid`o `UserId`
- cualquier combinación de entre 1-200 letras minúsculas o mayúsculas, dígitos, símbolos, caracteres especiales o espacios
- la cadena `Password` o `pwd` donde `pwd` no está precedida por una letra minúscula
- un signo igual (=)
- cualquier carácter que no sea un signo de dólar ($), símbolo de porcentaje (%), mayor que símbolo (>), símbolo (@), comillas ("), punto y coma (;), llave izquierda([) o corchete izquierdo ({)
- cualquier combinación de entre 7 y 128 caracteres que no sean un punto y coma (;), barra diagonal (/) o comillas (")
- un punto y coma (;) o comillas (")

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La expresión `CEP_Regex_SQLServerConnectionString` regular busca contenido que coincida con el patrón.
- No se encuentra una palabra clave de `CEP_GlobalFilter` .
- La expresión `CEP_PasswordPlaceHolder` regular no encuentra contenido que coincida con el patrón.
- La expresión `CEP_CommonExampleKeywords` regular no encuentra contenido que coincida con el patrón.

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="cep_globalfilter"></a>CEP_GlobalFilter

- some-password
- somepassword
- secretPassword
- Muestra

### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

Este tipo de información confidencial identifica estas palabras clave mediante una expresión regular, no una lista de palabras clave.

- `Password` o `pwd` seguido de 0-2 espacios, un signo igual (=), 0-2 espacios y un asterisco (*) -OR-
- `Password` o `pwd` seguido de:
    - Signo igual (=)
    - Menor que el símbolo (<)
    - Cualquier combinación de entre 1 y 200 caracteres que sean letras mayúsculas o minúsculas, dígitos, asterisco (*), guion (-), subrayado (_) o carácter de espacio en blanco
    - Mayor que el símbolo (>)

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