---
title: Definición de entidad de credenciales de inicio de sesión de usuario (versión preliminar)
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
description: Definición de entidad de tipo de información confidencial de credenciales de inicio de sesión de usuario.
ms.openlocfilehash: d75fcb7069e8393b5b03ce08071057ff503a4bfb
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999134"
---
# <a name="user-login-credentials-preview"></a>Credenciales de inicio de sesión de usuario (versión preliminar)

## <a name="format"></a>Formato

Nombre de usuario y contraseña emparejados usados en el proceso de autenticación general.

o

Nombre de usuario y contraseña emparejados que se usan en el administrador de conexiones PuTTY.

o

Contraseña de texto sin formato usada en fragmentos de código.

o

Una combinación de 88 caracteres que consta de letras, dígitos y caracteres especiales.

## <a name="pattern"></a>Patrón

Varios formatos de nombre de usuario y contraseña, por ejemplo:
 
`username=...;password=********;` <br>
`user id=...;password=********;` <br>
`uid=...;pwd=********;` <br>
`DB_USER=...;DB_PASS=********;` <br>
`Service Account=...;Password=********;` <br>

o

```xml
An XML element <login>
An embeded XML element <login>
Inner XML content
An embeded XML element </login>
An embeded XML element <password>
Inner XML content
An embeded XML element </password>
An XML element </login>
```

por ejemplo,

`<login> <login>ZYXWVU_1</login> <password>ZY…`

o

Varios formatos de contraseña en fragmentos de código, por ejemplo:

`new X509Certificates2(` <br>
`ConvertTo-SecureString -String ********` <br>
`password = "********"` <br>
`"password" : "********"`<br>
`UserPasswordCredential(` <br>

o

Una combinación de 86 caracteres:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/)
- o signos más (+)
- termina con dos signos iguales (=)

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEabcdefghijklmnopqrstuvwxyz0123456789/+ABCDE==`

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa en el [proceso de inicio de sesión](/azure/key-vault/quick-create-portal) general del usuario. 

Usa varios recursos principales:

- Patrones de nombre de usuario y contraseña de texto sin formato.
- Patrones de nombre de usuario y contraseña de texto sin formato en el archivo de base de datos PuTTYcm.
- Patrones de contexto de contraseña en el código.
- Patrones de clave simétrica codificada en Base64 de 512 bits.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName, Id, AccountName.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_logincredentials"></a>Keyword_LoginCredentials:

- contraseña
- Pw
- DB_

### <a name="keyword_logincredentialsputty"></a>Keyword_LoginCredentialsPutty:

- Iniciar sesión

### <a name="keyword_passwordcontextincode"></a>Keyword_PasswordContextInCode:

- clave
- x509c
- Credencial
- contraseña
- Pw
- securestring

### <a name="keyword_symmetrickey512"></a>Keyword_SymmetricKey512:

- SharedAccessKey
- AccountKey
