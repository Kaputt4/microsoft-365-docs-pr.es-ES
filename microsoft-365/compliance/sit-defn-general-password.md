---
title: Definición general de entidad de contraseña (versión preliminar)
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
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Definición general del tipo de información confidencial de contraseña.
ms.openlocfilehash: 39a789fed5d0cf1467da4be0e05324dea3d5a12d
ms.sourcegitcommit: fa570d90b00ed1bb40e1ca27b11c66a84c4204e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68476757"
---
# <a name="general-password-preview"></a>Contraseña general (versión preliminar)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

Combinación de hasta 20 000 caracteres de letras, dígitos y caracteres especiales.

o

Credenciales de inicio de sesión usadas en las líneas de comandos

o

Contraseña de texto sin formato usada en fragmentos de código

o

Contraseña de texto sin formato usada en el script

o

Contraseña de texto sin formato usada en la configuración XML

o

Combinación de 24 caracteres que consta de letras, dígitos y caracteres especiales.

o

Una combinación de 32 caracteres que consta de letras y dígitos.

o

Combinación de 32 caracteres que constan de letras, dígitos y caracteres especiales.

o

Una combinación de 44 caracteres que consta de letras, dígitos y caracteres especiales.

o

Combinación de 88 caracteres de letras, dígitos y caracteres especiales.

## <a name="pattern"></a>Patrón

Cualquier combinación de hasta 20 000 caracteres que consta de:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/) o signos más (+)
- Hasta dos signos iguales (=)

Por ejemplo:

`MIIKcQIBAzCCCi0GCSqGSIb3DQEHAaCCCh4EggoaMIIKFjCCBg8GCSqGSIb3DQEHAaCCBgAEggX8MIIF+DCCBfQGCyqGSIb3DQEM`

o

Varios formatos de credenciales de inicio de sesión de línea de comandos, por ejemplo: 

`-u username:********`

o

`-u username -p ********`

o

`/f ... /p ********`

o

`-Password ********`

o

`-U username%********`

o

`-secrets:********`

Por ejemplo:

`zDbg.DataPuller.exe -secrets:eyJ`

o

Varios formatos de contraseña en fragmentos de código, por ejemplo:

`new X509Certificates2(`

o

`ConvertTo-SecureString -String ********`

o

`password = "********"`

o

`"password" : "********"`

o

`UserPasswordCredential(`

Por ejemplo:

`password = "ZYXWVU_1";`

o

Varios formatos de contraseña en el script, por ejemplo:

`password = ********`

Por ejemplo:

`password=ZYXWVU_1`

o

Varios formatos de contraseña en XML, por ejemplo:

```xml
<secret>********</secret>
<password>********</password>
<setting name="password" value="********" >
<setting name="password">********</setting>
<setting name="password"><value>********</value></setting>
```

Por ejemplo:

`<secret>ZYXWVU_1</secret>`

o

Cualquier combinación de 22 caracteres que consta de:

- a-z (no distingue mayúsculas de minúsculas)
- dígitos, barras diagonales o signos más
- termina con dos signos iguales (=)

Por ejemplo:

`abcdefgh0123456789/+AB==`

o

Cualquier combinación de 32 caracteres que consta de:

- a-f o A-F (distingue mayúsculas de minúsculas) o 0-9

Por ejemplo:

`abcdef0123456789abcdef0123456789`

o

Cualquier combinación de 32 caracteres que consta de:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/) o signos más (+)

Por ejemplo:

`abcdefghijklmnopqr0123456789/+AB`

o

Cualquier combinación de 43 caracteres que consta de:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/) o signos más (+)
- termina con un signo igual (=)

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDE=`

o

Cualquier combinación de 86 caracteres que consta de:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/) o signos más (+)
- termina con dos signos iguales (=)

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEabcdefghijklmnopqrstuvwxyz0123456789/+ABCDE==`

## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="description"></a>Descripción

Esta SIT está diseñada para coincidir con la información de seguridad que es como los nombres de usuario y las contraseñas que se usan en el proceso general de inicio de sesión del [usuario](/azure/key-vault/quick-create-portal). Usa varios recursos principales:

- Patrones de literal de cadena codificada en Base64.
- Patrones de contexto de contraseña en la línea de comandos.
- Patrones de contexto de contraseña en el código.
- Patrones de contexto de contraseña en el script.
- Patrones de contexto de contraseña en XML.
- Patrones de clave simétrica codificada en Base64 de 128 bits.
- Patrones de clave simétrica de 128 bits codificada hexadecimalmente.
- Patrones de clave simétrica codificada en Base64 de 192 bits.
- Patrones de clave simétrica codificada en Base64 de 256 bits.
- Patrones de clave simétrica codificada en Base64 de 512 bits.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName, ID, AccountName.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de palabras de vocabulario.


Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_base64encodedstringliteral"></a>Keyword_Base64EncodedStringLiteral

- Mii

### <a name="keyword_passwordcontextincmdline"></a>Keyword_PasswordContextInCmdLine

- Certutil
- zdbg
- Secreto
- VSTS_TOKEN
- Enrollamiento
- PowerShell
- ps1
- -u
- Smc
- AutoLogon
- Ldifde
- Rclone
- --Env
- SignTool
- Winexe
- Red

## <a name="keyword_passwordcontextincode"></a>Keyword_PasswordContextInCode

- clave
- x509c
- Credencial
- contraseña
- Pw
- securestring

### <a name="keyword_passwordcontextinscript"></a>Keyword_PasswordContextInScript

- Secreto
- contraseña
- Pw

### <a name="keyword_passwordcontextinxml"></a>Keyword_PasswordContextInXml

- userpass
- contraseña
- Pw
- Connectionstring
- clave
- Credencial
- token
- Sas
- Secreto

### <a name="keyword_symmetrickey128"></a>Keyword_SymmetricKey128

- Secreto
- clave
- contraseña
- Pw

### <a name="keyword_symmetrickey128hex"></a>Keyword_SymmetricKey128Hex

- Dapi
- clave
- Secreto
- token
- contraseña
- Pw

### <a name="keyword_symmetrickey192"></a>Keyword_SymmetricKey192

- contraseña
- -P
- azurecr

### <a name="keyword_symmetrickey256"></a>Keyword_SymmetricKey256

- SharedAccessKey
- AccountKey

### <a name="keyword_symmetrickey512"></a>Keyword_SymmetricKey512

- SharedAccessKey
- AccountKey
