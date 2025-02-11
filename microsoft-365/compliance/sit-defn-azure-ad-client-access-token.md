---
title: Definición de entidad de token de acceso de cliente de Azure AD
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
description: Definición de entidad de tipo de información confidencial del token de acceso de cliente de Azure AD.
ms.openlocfilehash: 99c60e5c6ff2f78b2bf4ecf610e860baea7f95d4
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2022
ms.locfileid: "68503432"
---
# <a name="azure-ad-client-access-token"></a>Token de acceso de cliente de Azure AD

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

Esta SIT también se incluye en el SIT de [todas las credenciales](sit-defn-all-creds.md) agrupadas.

 ## <a name="format"></a>Formato

Combinación de hasta 10 000 caracteres que constan de letras, dígitos y caracteres especiales.

o

Un secreto de cliente o un token de actualización que se usa en el protocolo OAuth2.0.

o

Combinación de hasta 1000 caracteres que constan de letras, dígitos y caracteres especiales.

## <a name="pattern"></a>Patrón

Cualquier combinación de:
 
- hasta 10 000 
- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/)
- o signos más (+)
- Hasta 2
- signos iguales (=)

Por ejemplo:

`"VersionProfile": null, "TokenCache": { "CacheData": 
"AgAAAAIAAACZAWh0dHBzOi8vbG9naW4ubWljcm9zb2`

o

Formatos de token de actualización o secreto de cliente variantes, por ejemplo. <br> 
`ClientSecret:********` <br>
`AppSecret=********` <br>
`ConsumerKey:=********` <br>
`Refresh_Token:********` <br>

o

3 letras: eyJ (distingue mayúsculas de minúsculas)

And

Una combinación de hasta 1000 caracteres que consta de

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- guiones (-)
- underlines (_)
- o puntos (.)

Por ejemplo:

`eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIng1dCI6Ing0Nzh4eU9wbHNNMUg3TlhrN1N4MTd4MX...`



## <a name="credential-example"></a>Ejemplo de credencial 

`Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIng1dCI6Ing0Nzh4eU9wbHNNMUg3TlhrN1N4MTd4MX...`

> [!IMPORTANT]
> Este ejemplo se ha truncado. No es un ejemplo detectable de este SIT.

## <a name="checksum"></a>Suma de comprobación

Sí

Los SIT que tienen sumas de comprobación usan un cálculo único para comprobar si la información es válida. Esto significa que cuando el valor **de suma de comprobación** es **Sí**, el servicio puede realizar una detección positiva solo en función de los datos confidenciales. Cuando el valor **de suma de comprobación** es **No** se deben detectar elementos adicionales (secundarios) para que el servicio realice una detección positiva.

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que contiene notificaciones que se pueden usar en [Azure Active Directory B2C](/azure/active-directory-b2c/active-directory-b2c-access-tokens) (Azure AD B2C) para identificar los permisos concedidos a los recursos de Azure. 

Usa varios recursos principales:

- Patrones de Azure PowerShell caché de tokens
- Patrones de contexto de secreto de cliente
- Patrones de json web token
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName
- Patrones de valores ficticios, censuras y marcadores de posición
- Diccionario de vocabulario

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.



## <a name="keywords"></a>Palabras clave

### <a name="keyword_symmetrickeycontextinxml"></a>Keyword_SymmetricKeyContextInXml:

- tokencache

### <a name="keyword_clientsecretcontext"></a>Keyword_ClientSecretContext:

- Secreto
- token
- auth
- securestring
- clave

### <a name="keyword_jsonwebtoken"></a>Keyword_JsonWebToken:

- eyJ

