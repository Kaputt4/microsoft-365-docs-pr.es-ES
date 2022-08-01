---
title: Definición de entidad secreta de cliente de Azure AD (versión preliminar)
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
description: Definición de entidad de tipo de información confidencial del secreto de cliente de Azure AD.
ms.openlocfilehash: ea597fc5493db6b6f919d907dcb61af115299ea1
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999515"
---
# <a name="azure-ad-client-secret-preview"></a>Secreto de cliente de Azure AD (versión preliminar)

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

## <a name="checksum"></a>Suma de comprobación

Sí

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
- assword
- clave

