---
title: Definición de entidad de clave secreta de Azure Bot Framework (versión preliminar)
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
description: Definición de entidad de tipo de información confidencial de clave secreta de Azure Bot Framework.
ms.openlocfilehash: c436436b00dda8a5273939665920ef709ff164c5
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999479"
---
# <a name="azure-bot-framework-secret-key-preview"></a>Clave secreta de Azure Bot Framework (versión preliminar)

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

Una combinación de 3 caracteres:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- guiones (-)
- o subrayados (_)
- un punto

Una combinación de 3 caracteres:

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


## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Este SIT está diseñado para coincidir con la información de seguridad que se usa para conectarse a [los canales de WebChat desde los servicios de Bot de Azure.](/azure/bot-service/bot-service-channel-connect-webchat?view=azure-bot-service-4.0) 

Usa varios recursos principales:

- Patrones de clave simétrica con codificación URL base64 de 328 bits.
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
