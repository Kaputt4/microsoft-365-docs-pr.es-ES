---
title: Definición de entidad clave de Azure Cognitive Service (versión preliminar)
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
description: Definición de entidad de tipo de información confidencial de clave de Azure Cognitive Service.
ms.openlocfilehash: cf54aa6886aa6cfed9d7540ebc8e5756994d9efb
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999722"
---
# <a name="azure-cognitive-service-key-preview"></a>Clave de Azure Cognitive Service (versión preliminar)

## <a name="format"></a>Formato

Una combinación de 32 caracteres que consta de letras y dígitos.

## <a name="pattern"></a>Patrón

Cualquier combinación de 32 caracteres que consta de:
 
- a-f o A-F (distingue mayúsculas de minúsculas)
- o 0-9

Por ejemplo:

`abcdef0123456789abcdef0123456789`

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa para autenticar las solicitudes en [Azure Cognitive Services.](/azure/search/search-security-api-keys) 

Usa varios recursos principales:

- Patrones de clave simétrica de 128 bits codificada hexadecimalmente.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.
Palabras clave

## <a name="keywords"></a>Palabras clave

### <a name="keyword_symmetrickey128hex"></a>Keyword_SymmetricKey128Hex:

- Dapi
- clave
- Secreto
- token
- contraseña
- Pw
