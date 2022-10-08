---
title: Definición de entidad secreta de aplicación de Azure Bot Service (versión preliminar)
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
description: Definición de entidad de tipo de información confidencial del secreto de la aplicación de Azure Bot Service.
ms.openlocfilehash: 67afea4534b81abc6dd58e459e014035a40d8d03
ms.sourcegitcommit: fa570d90b00ed1bb40e1ca27b11c66a84c4204e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68476119"
---
# <a name="azure-bot-service-app-secret-preview"></a>Secreto de aplicación de Azure Bot Service (versión preliminar)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

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

Esta SIT está diseñada para coincidir con la información de seguridad que se usa para establecer una comunicación segura entre un [bot de Azure, canales WebChat y aplicaciones cliente](/azure/bot-service/bot-builder-concept-authentication-types?view=azure-bot-service-4.0).  

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
