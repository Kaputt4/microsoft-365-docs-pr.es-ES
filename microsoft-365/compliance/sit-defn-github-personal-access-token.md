---
title: Definición de entidad de token de acceso personal de GitHub
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
description: Definición de entidad de tipo de información confidencial del token de acceso personal de GitHub.
ms.openlocfilehash: 9a887ec28d5e90ffc61a16a2a1975aa2d6f8e366
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2022
ms.locfileid: "68504048"
---
# <a name="github-personal-access-token"></a>Token de acceso personal de GitHub

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

Esta SIT también se incluye en el SIT de [todas las credenciales](sit-defn-all-creds.md) agrupadas.

 ## <a name="format"></a>Formato

Combinación de 40 caracteres que constan de letras, dígitos y caracteres especiales.

o

Nombre de usuario y contraseña emparejados usados en la dirección URL.

o

Una combinación de 40 caracteres que consta de letras y dígitos.

## <a name="pattern"></a>Patrón

- Prefijo de token (distingue mayúsculas de minúsculas) "ghp_", "gho_", "ghu_", "ghs_" o "ghr_"
- Cualquier combinación de 36 
- a-z (no distingue mayúsculas de minúsculas) o 0-9

Por ejemplo:

`ghp_abcdefghijklmnopqrstuvwxyzABCD012345`

o

Varios formatos de nombre de usuario y contraseña de dirección URL, por ejemplo:
 
`https://username:********@contoso.com/` <br>

`ftp://username:********@contoso.com:20/`<br>


o

Una combinación de 40 caracteres:

- a-f o A-F (distingue mayúsculas de minúsculas) o 0-9

Por ejemplo:

`abcdef0123456789abcdef0123456789abcdef01`

## <a name="credential-example"></a>Ejemplo de credencial 

`pat=ghp_abcdefghijklmnopqrstuvwxyzABCD012345`

## <a name="checksum"></a>Suma de comprobación

Sí

Los SIT que tienen sumas de comprobación usan un cálculo único para comprobar si la información es válida. Esto significa que cuando el valor **de suma de comprobación** es **Sí**, el servicio puede realizar una detección positiva solo en función de los datos confidenciales. Cuando el valor **de suma de comprobación** es **No** se deben detectar elementos adicionales (secundarios) para que el servicio realice una detección positiva.

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa como contraseña alternativa para la autenticación con GitHub cuando se usa [la API de GitHub o la línea de comandos](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token). 

Usa varios recursos principales:

- Patrones de PAT de GitHub identificable.
- Patrones de credenciales de inicio de sesión de usuario en la dirección URL.
- Patrones de clave simétrica de 160 bits codificada hexadecimalmente.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.
- Patrones de valores ficticios, censuras y marcadores de posición.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_githubpatidentifiablesecret"></a>Keyword_GitHubPatIdentifiableSecret:

- Gh_

### <a name="keyword_logincredentialsinurl"></a>Keyword_LoginCredentialsInUrl:

- ://

### <a name="keyword_symmetrickey160hex"></a>Keyword_SymmetricKey160Hex:

- token
