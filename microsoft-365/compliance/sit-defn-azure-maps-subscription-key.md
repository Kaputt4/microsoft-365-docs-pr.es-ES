---
title: Azure Maps definición de entidad de clave de suscripción (versión preliminar)
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
description: Azure Maps definición de entidad de tipo de información confidencial de la clave de suscripción.
ms.openlocfilehash: f1ebfe0018fac9bd792dc102df39bb0aada84fdf
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999398"
---
# <a name="azure-maps-subscription-key-preview"></a>Azure Maps clave de suscripción (versión preliminar)

## <a name="format"></a>Formato

Una combinación de 43 caracteres que consta de letras, dígitos y caracteres especiales.

## <a name="pattern"></a>Patrón

Cualquier combinación de 43 caracteres que consta de:
 
- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- guiones (-)
- o subrayados (_)

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz0123456789-_ABCDE`

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa para acceder a los recursos de [Azure Maps cuentas](/azure/azure-maps/how-to-manage-authentication). 

Usa varios recursos principales:

- Patrones de clave simétrica de 256 bits codificada en la dirección URL base64.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_symmetrickey256url"></a>Keyword_SymmetricKey256Url:

- clave
- microsoft.maps
