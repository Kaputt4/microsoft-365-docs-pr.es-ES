---
title: Definición de entidad clave de la API de Google (versión preliminar)
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
description: Definición de entidad de tipo de información confidencial de la API de Google.
ms.openlocfilehash: 5aef61e28dee6624620d1f254434fb860f28f1af
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999776"
---
# <a name="google-api-key-preview"></a>Clave de API de Google (versión preliminar)

## <a name="format"></a>Formato

Combinación de 39 caracteres que constan de letras, dígitos y caracteres especiales.

## <a name="pattern"></a>Patrón

Prefijo de token (distingue mayúsculas de minúsculas) 'AIza'

Una combinación de 35 caracteres:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- guiones (-)
- subrayados (_) o barras diagonales hacia atrás (\)

Por ejemplo:

`AIzaefgh0123456789_-ABCDEFGHIJKLMNOPQRS`

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa como una cadena cifrada simple que identifica un [cliente de API REST de Google](https://cloud.google.com/docs/authentication/api-keys) sin ninguna entidad de seguridad que se use para asociar solicitudes de API con el proyecto para la cuota y la facturación. 

Usa varios recursos principales:

- Patrones de clave simétrica codificada en Base64 de 210 bits.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_symmetrickey210"></a>Keyword_SymmetricKey210:

- Aiza
