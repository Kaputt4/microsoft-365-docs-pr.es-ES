---
title: Definición de entidad secreta de cliente de Azure AD
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
description: Definición de entidad de tipo de información confidencial del secreto de cliente de Azure AD.
ms.openlocfilehash: b94130c5ec5a7125890c8fdd2fad4529e461bc5b
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2022
ms.locfileid: "68503454"
---
# <a name="azure-ad-client-secret"></a>Secreto de cliente de Azure AD

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

Esta SIT también se incluye en el SIT de [todas las credenciales](sit-defn-all-creds.md) agrupadas.

 ## <a name="format"></a>Formato

Combinación de hasta 40 caracteres que constan de letras, dígitos y caracteres especiales.

## <a name="pattern"></a>Patrón

Una combinación de hasta 40 caracteres que consta de:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- guiones (-)
- underlines (_)
- puntos (.) 
- o acentos de tilde (~)

Por ejemplo:

`abc7Q~defghijklmnopqrs0t123456789-_.~`

## <a name="credential-example"></a>Ejemplo de credencial 

`"AppId=01234567-abcd-abcd-abcd-abcdef012345;AppSecret=abc7Q~defghijklmnopqrstuvwxyz-_.~0123"`

## <a name="checksum"></a>Suma de comprobación

Sí

Los SIT que tienen sumas de comprobación usan un cálculo único para comprobar si la información es válida. Esto significa que cuando el valor **de suma de comprobación** es **Sí**, el servicio puede realizar una detección positiva solo en función de los datos confidenciales. Cuando el valor **de suma de comprobación** es **No** se deben detectar elementos adicionales (secundarios) para que el servicio realice una detección positiva.

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa para proteger las [entidades de servicio de Azure Active Directory](/azure/active-directory/fundamentals/service-accounts-principal). 

Usa varios recursos principales:

- Patrones de secreto de cliente con formato específico.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_appsecret"></a>Keyword_AppSecret:

- Secreto
- contraseña
- clave

