---
title: Crednetial en la dirección URL
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
description: Credenciales en la definición de entidad de tipo de información confidencial de dirección URL.
ms.openlocfilehash: f7a363539ec9bdd7fa0ddaab30ac7e2d20afb69b
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999734"
---
# <a name="credentials-in-url"></a>Credenciales de URL

## <a name="format"></a>Formato

Nombre de usuario y contraseña emparejados usados en la dirección URL

o

Contraseña de texto sin formato usada en el script

## <a name="pattern"></a>Patrón

Varios formatos de nombre de usuario y contraseña de dirección URL, por ejemplo: 

`https://username:********@contoso.com/...`
`ftp://username:********@contoso.com:20/...`

por ejemplo: `https://myuser:mypassword@localhost`

o

Varios formatos de contraseña en el script, por ejemplo: 

`password = ********...`

Por ejemplo:

`password=ZYXWVU_1`

## <a name="checksum"></a>Suma de comprobación

No

## <a name="description"></a>Descripción

Esta SIT está diseñada para coincidir con la información de seguridad que se usa como token en la dirección URL para realizar la validación del cliente o el [proceso de inicio de sesión de usuario](/azure/key-vault/quick-create-portal) de identificación. Usa varios recursos principales:

- Patrones de credenciales de inicio de sesión de usuario en la dirección URL.
- Patrones de contexto de contraseña en el script.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.
- Patrones de valores ficticios, censuras y marcadores de posición.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_logincredentialsinurl"></a>Keyword_LoginCredentialsInUrl

- ://

### <a name="keyword_passwordcontextinscript"></a>Keyword_PasswordContextInScript

- Secreto
- contraseña
- Pw
