---
title: Definición de entidad de firma de token de web hook o clave de acceso compartido de Azure (versión preliminar)
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
description: Definición de entidad de tipo de información confidencial de clave de acceso compartido de Azure o token de web hook.
ms.openlocfilehash: a97bc484551cfd5a5ceb379b1e07aca2b9e53255
ms.sourcegitcommit: fa570d90b00ed1bb40e1ca27b11c66a84c4204e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68476031"
---
# <a name="azure-shared-access-key--web-hook-token-preview"></a>Clave de acceso compartido de Azure o token de web hook (versión preliminar) 

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

Una combinación de 44 caracteres que consta de letras, dígitos y caracteres especiales.

o

Combinación de hasta 76 caracteres que constan de letras, dígitos y caracteres especiales.

## <a name="pattern"></a>Patrón

Cualquier combinación de 43 caracteres que consta de:
 
- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/)
- o signos más (+)
- termina con un signo igual (=)

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDE=`

o

Una combinación de 43 a 73 caracteres que consta de:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- signos de porcentaje (%)
- termina con un sufijo '%3d' (sin distinción entre mayúsculas y minúsculas)

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz0123456789%2F%2BABCDE%3D`

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa para acceder a [los recursos generales de Azure con permiso restringido](/azure/notification-hubs/notification-hubs-push-notification-security). 

Usa varios recursos principales:

- Patrones de clave simétrica codificada en Base64 de 256 bits.
- Patrones de clave simétrica con codificación URL de 256 bits.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName, ID.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_symmetrickey256"></a>Keyword_SymmetricKey256:

- SharedAccessKey
- AccountKey

### <a name="keyword_symmetrickey256urlencoded"></a>Keyword_SymmetricKey256UrlEncoded:

- sig=
- clave
- token
- Secreto
- contraseña
