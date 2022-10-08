---
title: Definición de entidad de clave secreta de Azure Bot Framework
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
description: Definición de entidad de tipo de información confidencial de clave secreta de Azure Bot Framework.
ms.openlocfilehash: bb515b37f16dfe4e810ea38ef30a09563b966693
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2022
ms.locfileid: "68503414"
---
# <a name="azure-bot-framework-secret-key"></a>Clave secreta de Azure Bot Framework

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

Esta SIT también se incluye en el SIT de [todas las credenciales](sit-defn-all-creds.md) agrupadas.

 ## <a name="format"></a>Formato

Una combinación de 55 caracteres que consta de letras, dígitos y caracteres especiales.

o

Una combinación de 63 caracteres que consta de letras, dígitos y caracteres especiales.

## <a name="pattern"></a>Patrón

Una combinación de 55 caracteres:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- underlines (_)
- o puntos (.)


`abcdefghijklmnopqrstuvwxyz.0123456789_ABCDEabcdefghijkl`

o para los 63 caracteres

Una combinación de 11 caracteres:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- guiones (-)
- o subrayados (_)
- un punto

Una combinación de tres caracteres:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- guiones (-)
- o subrayados (_)
- un punto

Una combinación de tres caracteres:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- guiones (-)
- o subrayados (_)
- un punto

Una combinación de 43 caracteres

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- guiones (-)
- o subrayados (_)

Por ejemplo:

`abcdefghijk.lmn.opq.rstuvwxyz0123456789-_ABCDEFGHIJKLMNOPQRSTUV`


## <a name="credential-example"></a>Ejemplo de credencial 

`host: webchat.botframework.com/?s=abcdefghijklmnopqrstuvwxyz.0123456789_ABCDEabcdefghijkl&`

## <a name="checksum"></a>Suma de comprobación

No

Los SIT que tienen sumas de comprobación usan un cálculo único para comprobar si la información es válida. Esto significa que cuando el valor **de suma de comprobación** es **Sí**, el servicio puede realizar una detección positiva solo en función de los datos confidenciales. Cuando el valor **de suma de comprobación** es **No** se deben detectar elementos adicionales (secundarios) para que el servicio realice una detección positiva.

## <a name="definition"></a>Definición

Este SIT está diseñado para coincidir con la información de seguridad que se usa para conectarse a [los canales de WebChat desde los servicios de Bot de Azure.](/azure/bot-service/bot-service-channel-connect-webchat?view=azure-bot-service-4.0) 

Usa varios recursos principales:

- Patrones de clave simétrica de 328 bits codificada en la dirección URL base64.
- Patrones de clave simétrica de 360 bits codificada en la dirección URL base64.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_symmetrickey328url"></a>Keyword_SymmetricKey328Url:

- botframework
- clave

### <a name="keyword_symmetrickey360url"></a>Keyword_SymmetricKey360Url:

- botframework
- clave
