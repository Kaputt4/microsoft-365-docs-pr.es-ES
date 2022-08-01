---
title: Definición de entidad de clave simétrica general (versión preliminar)
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
description: Definición de entidad de tipo de información confidencial de clave simétrica general.
ms.openlocfilehash: 539fe92e769442de430252d7d14b5fc1e5febfb8
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999128"
---
# <a name="general-symmetric-key-preview"></a>Clave simétrica general (versión preliminar)

## <a name="format"></a>Formato

Una combinación de 44 caracteres que consta de letras, dígitos y caracteres especiales.

o

Una combinación de 88 caracteres que consta de letras, dígitos y caracteres especiales.

## <a name="pattern"></a>Patrón

Una combinación de 43 caracteres:
 
- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/) o signos más (+)
- termina con un signo igual (=)

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDE=`

o

Una combinación de 86 caracteres:
 
- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/) o signos más (+)
- termina con dos signos iguales (=)

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEabcdefghijklmnopqrstuvwxyz0123456789/+ABCDE==`

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa en el [proceso de autenticación general.](/dotnet/api/system.security.cryptography.aes?view=net-5.0) 

Usa varios recursos principales:

- Patrones de clave simétrica de 256 bits codificada en Base64.
- Patrones de clave simétrica codificada en Base64 de 512 bits.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName, Id, AccountName.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_symmetrickey256"></a>Keyword_SymmetricKey256:

- SharedAccessKey
- AccountKey

### <a name="keyword_symmetrickey512"></a>Keyword_SymmetricKey512:

- SharedAccessKey
- AccountKey
