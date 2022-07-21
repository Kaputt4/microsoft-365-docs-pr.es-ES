---
title: Definición de entidad de clave de API o secreto de cliente (versión preliminar)
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
description: Definición de entidad de tipo de información confidencial de clave de API o secreto de cliente.
ms.openlocfilehash: 25bd50de2193abaa926d09475cc9ff537432fc62
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66951055"
---
# <a name="client-secret--api-key-preview"></a>Secreto de cliente/clave de API (versión preliminar)

## <a name="format"></a>Formato

Un secreto de cliente o un token de actualización que se usa en el protocolo OAuth 2.0.

o

Combinación de 24 caracteres que consta de letras, dígitos y caracteres especiales.

o

Una combinación de 32 caracteres que consta de letras y dígitos.

o

Una combinación de 40 caracteres que consta de letras y dígitos.

o

Una combinación de 44 caracteres que consta de letras, dígitos y caracteres especiales.

o

Una combinación de 56 caracteres que consta de letras, dígitos y caracteres especiales

o

Una combinación de 88 caracteres que consta de letras, dígitos y caracteres especiales.


## <a name="pattern"></a>Patrón

Varios formatos de token de actualización o secreto de cliente, por ejemplo:
 
`ClientSecret:********` <br>
`AppSecret=********` <br>
`ConsumerKey:=********` <br>
`Refresh_Token:********` <br>

o

Una combinación de 22 caracteres:
 
- a-z (no distingue mayúsculas de minúsculas)
- dígitos, barras diagonales o signos más
- termina con dos signos iguales (=)

Por ejemplo:

`abcdefgh0123456789/+AB==`

o

Una combinación de 32 caracteres:

- a-f o A-F (distingue mayúsculas de minúsculas)
- o 0-9

Por ejemplo:

`abcdef0123456789abcdef0123456789`

o

Una combinación de 40 caracteres:

- a-f o A-F (distingue mayúsculas de minúsculas)

o

- 0-9

Por ejemplo:

`abcdef0123456789abcdef0123456789abcdef01`

o

Una combinación de 43 caracteres:
 
- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/)
- o signos más (+)
- termina con un signo igual (=)

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDE=`

o

Una combinación de 54 caracteres:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/) o signos más (+)
- termina con dos signos iguales (==)

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEFGHIJKLMNOP==`

o

Una combinación de 86 caracteres:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/) o signos más (+)
- termina con dos signos iguales (=)

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEabcdefghijklmnopqrstuvwxyz0123456789/+ABCDE==`


## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que solo conoce la [aplicación OAuth y el servidor de autorización para intercambiar](/azure/active-directory/develop/active-directory-how-applications-are-added) por un token de acceso en tiempo de ejecución. 

Usa varios recursos principales:

- Patrones del contexto de secreto de cliente.
- Patrones de clave simétrica codificada en Base64 de 128 bits.
- Patrones de clave simétrica de 128 bits codificada hexadecimalmente.
- Patrones de clave simétrica de 160 bits codificada hexadecimalmente.
- Patrones de clave simétrica de 256 bits codificada en Base64.
- Patrones de clave simétrica de 320 bits codificada en Base64.
- Patrones de clave simétrica codificada en Base64 de 512 bits.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName, Id, AccountName.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_clientsecretcontext"></a>Keyword_ClientSecretContext:

- Secreto
- token
- auth
- securestring
- clave

### <a name="keyword_symmetrickey128"></a>Keyword_SymmetricKey128:

- Secreto
- clave
- contraseña
- Pw

### <a name="keyword_symmetrickey128hex"></a>Keyword_SymmetricKey128Hex:

- Dapi
- clave
- Secreto
- token
- contraseña
- Pw

### <a name="keyword_symmetrickey160hex"></a>Keyword_SymmetricKey160Hex:

- token

### <a name="keyword_symmetrickey256"></a>Keyword_SymmetricKey256:

- SharedAccessKey
- AccountKey

### <a name="keyword_symmetrickey320"></a>Keyword_SymmetricKey320:

- code=
- clave

### <a name="keyword_symmetrickey512"></a>Keyword_SymmetricKey512:

- SharedAccessKey
- AccountKey
