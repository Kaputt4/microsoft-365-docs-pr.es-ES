---
title: Firma de acceso compartido de la cuenta de Azure Storage para la definición de entidad de recursos de alto riesgo (versión preliminar)
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
description: Firma de acceso compartido de la cuenta de Azure Storage para la definición de entidad de tipo de información confidencial de recursos de alto riesgo.
ms.openlocfilehash: 007016f38f0aa6409cd81c317653cb0acc71a881
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999608"
---
# <a name="azure-storage-account-shared-access-signature-for-high-risk-resources-preview"></a>Firma de acceso compartido de la cuenta de Azure Storage para recursos de alto riesgo (versión preliminar)

## <a name="format"></a>Formato

Una combinación de 44 caracteres que consta de letras, dígitos y caracteres especiales.

o

Combinación de hasta 76 caracteres que constan de letras, dígitos y caracteres especiales.

## <a name="pattern"></a>Patrón

Cualquier combinación de 43 caracteres que consta de:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/)
- o signos más (+)
- termina con un signo igual (=)

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDE=`

o

Cualquier combinación de 43 a 73 caracteres que consta de:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- o signos de porcentaje (%)
- termina con un sufijo "%3d" (no distingue mayúsculas de minúsculas)

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz0123456789%2F%2BABCDE%3D`

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa para conceder derechos de acceso restringido a [recursos de Azure Storage de alto riesgo, como certificados, configuraciones o paquetes de implementación](/rest/api/storageservices/delegate-access-with-shared-access-signature). 

Usa varios recursos principales:

- Patrones de clave simétrica de 256 bits codificada en Base64.
- Patrones de clave simétrica con codificación URL de 256 bits.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName, Id.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.


## <a name="keywords"></a>Palabras clave

### <a name="keyword_symmetrickey256"></a>Keyword_SymmetricKey256:

- SharedAccessKey
- AccountKey

### <a name="keyword_symmetrickey256urlencoded"></a>Keyword_SymmetricKey256UrlEncoded:

- sig=
- clave
- token
- Secreto
- contraseña
