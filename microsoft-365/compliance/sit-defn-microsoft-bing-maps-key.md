---
title: Definición de entidad clave de mapas de Microsoft Bing (versión preliminar)
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
description: Microsoft Bing asigna la definición de entidad de tipo de información confidencial de clave.
ms.openlocfilehash: 6f25ec9716be33a0e2bbe404f12742dddad89250
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66951263"
---
# <a name="microsoft-bing-maps-key-preview"></a>Clave de mapas de Microsoft Bing (versión preliminar)

## <a name="format"></a>Formato

Una combinación de 64 caracteres que consta de letras, dígitos y caracteres especiales.

## <a name="pattern"></a>Patrón

Una combinación de 64 caracteres:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- subrayados (_) o guiones (-)

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz0123456789-_ABCDEabcdefghijklmnopqrstu`

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa para llamar a [mapas de Bing API.](/bingmaps/getting-started/bing-maps-dev-center-help/getting-a-bing-maps-key) 

Usa varios recursos principales:

- Patrones de clave simétrica de 384 bits codificada en url base64.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_symmetrickey384url"></a>Keyword_SymmetricKey384Url:

- virtualearth
- api/maps
- clave
