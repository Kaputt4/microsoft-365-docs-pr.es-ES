---
title: Azure Container Registry definición de entidad de clave de acceso (versión preliminar)
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
description: Azure Container Registry acceder a la definición de entidad de tipo de información confidencial de clave.
ms.openlocfilehash: 96424b7a0269b9080262d0680c18ef717529b347
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999461"
---
# <a name="azure-container-registry-access-key-preview"></a>Azure Container Registry clave de acceso (versión preliminar)

## <a name="format"></a>Formato

Combinación de 32 caracteres que constan de letras, dígitos y caracteres especiales.

## <a name="pattern"></a>Patrón

Una combinación de 32 caracteres que consta de:
 
- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/)
- o signos más (+)

Por ejemplo:

`abcdefghijklmnopqr0123456789/+AB`

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa para acceder a [Azure Container Registry](/azure/container-registry/container-registry-authentication) servicios como una cuenta de administrador. 

Usa varios recursos principales:

- Patrones de clave simétrica codificada en Base64 de 192 bits.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_symmetrickey192"></a>Keyword_SymmetricKey192:

- contraseña
- -p
- azurecr
