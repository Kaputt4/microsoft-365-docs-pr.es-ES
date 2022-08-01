---
title: Definición de entidad de token de acceso personal de GitHub (versión preliminar)
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
description: Definición de entidad de tipo de información confidencial del token de acceso personal de GitHub.
ms.openlocfilehash: e1da4eaf09ef480ad29928d8066dc91612cf779e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999797"
---
# <a name="github-personal-access-token-preview"></a>Token de acceso personal de GitHub (versión preliminar)

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

## <a name="checksum"></a>Suma de comprobación

Sí

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

- gh_

### <a name="keyword_logincredentialsinurl"></a>Keyword_LoginCredentialsInUrl:

- ://

### <a name="keyword_symmetrickey160hex"></a>Keyword_SymmetricKey160Hex:

- token
