---
title: Definición de entidad de clave de acceso de la cuenta de Azure Storage (versión preliminar)
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
description: La cuenta de Azure Storage tiene acceso a la definición de entidad de tipo de información confidencial de clave.
ms.openlocfilehash: a671e350f7834d0454762d2f6c9fad9d333cddda
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999827"
---
# <a name="azure-storage-account-access-key-preview"></a>Clave de acceso de la cuenta de Azure Storage (versión preliminar)

## <a name="format"></a>Formato

Combinación de hasta 20 000 caracteres que constan de letras, dígitos y caracteres especiales.

o

Una combinación de 88 caracteres que consta de letras, dígitos y caracteres especiales.

## <a name="pattern"></a>Patrón

Cualquier combinación de hasta 20 000 caracteres que consta de:
 
- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/)
- o signos más (+)
- Hasta 2
- signos iguales (=)

Por ejemplo:

`MIIKcQIBAzCCCi0GCSqGSIb3DQEHAaCCCh4EggoaMIIKFjCCBg8GCSqGSIb3DQEHAaCCBgAEggX8MIIF+DCCBfQGCyqGSIb3DQEM` O

Cualquier combinación de 86 caracteres que consta de:

a-z (no distingue mayúsculas de minúsculas) 0-9 barras diagonales (/) o signos más (+) termina con dos signos iguales (=)

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEabcdefghijklmnopqrstuvwxyz0123456789/+ABCDE==`


## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa para realizar solicitudes en [servicios de Azure Storage](/rest/api/storageservices/authorize-with-shared-key), como blobs, colas, tablas y servicios de archivos. 

Usa varios recursos principales:

- Patrones de literal de cadena codificada en Base64.
- Patrones de clave simétrica codificada en Base64 de 512 bits.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName, Id, AccountName.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.


## <a name="keywords"></a>Palabras clave

### <a name="keyword_base64encodedstringliteral"></a>Keyword_Base64EncodedStringLiteral:

- MII

### <a name="keyword_symmetrickey512"></a>Keyword_SymmetricKey512:

- SharedAccessKey
- AccountKey
