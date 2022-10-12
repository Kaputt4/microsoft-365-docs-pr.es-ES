---
title: Definición de entidad de clave privada de certificado X.509
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
description: Definición de entidad de tipo de información confidencial de clave privada del certificado X.509.
ms.openlocfilehash: ad38c72281e0c07f82f1129a23e88079721a1317
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "68537322"
---
# <a name="x509-certificate-private-key-preview"></a>Clave privada de certificado X.509 (versión preliminar)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

Esta SIT también se incluye en el SIT de [todas las credenciales](sit-defn-all-creds.md) agrupadas.

 ## <a name="format"></a>Formato

Combinación de hasta 20 000 caracteres que constan de letras, dígitos y caracteres especiales.

o

Una combinación de hasta 40 caracteres que consta de letras mayúsculas, espacios y guiones.

## <a name="pattern"></a>Patrón

Una combinación de hasta 20 000 caracteres:
 
- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/)
- o signos más (+)

Hasta dos signos iguales (==)

Por ejemplo:

`MIIKcQIBAzCCCi0GCSqGSIb3DQEHAaCCCh4EggoaMIIKFjCCBg8GCSqGSIb3DQEHAaCCBgAEggX8MIIF+DCCBfQGCyqGSIb3DQEM`

o

cinco guiones (-)

Y una combinación de hasta 30 caracteres:

- A-Z (distingue mayúsculas de minúsculas) 
- Espacios
- 5 guiones (-)

Por ejemplo:

`-----BEGIN PRIVATE KEY-----`


## <a name="credential-example"></a>Ejemplo de credencial 

`-----BEGIN PRIVATE KEY----- MIIPuQIBAzCCD38GCSqGSIb3DQEHAaCCD3AEgg9sMIIPaDCCBZ8GCSqGSIb3DQEHBqCCBZAw...`

> [!IMPORTANT]
> Este ejemplo se ha truncado. No es un ejemplo detectable de este SIT.

## <a name="checksum"></a>Suma de comprobación

Sí

Los SIT que tienen sumas de comprobación usan un cálculo único para comprobar si la información es válida. Esto significa que cuando el valor **de suma de comprobación** es **Sí**, el servicio puede realizar una detección positiva solo en función de los datos confidenciales. Cuando el valor **de suma de comprobación** es **No** se deben detectar elementos adicionales (secundarios) para que el servicio realice una detección positiva.

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa como componente privado en [certificados SSL.](/azure/key-vault/certificate-scenarios) 

Usa varios recursos principales:

- Patrones de literal de cadena codificada en Base64.
- Patrones de encabezado de clave privada de certificado.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_base64encodedstringliteral"></a>Keyword_Base64EncodedStringLiteral:

- Mii

### <a name="keyword_certificateprivatekeyheader"></a>Keyword_CertificatePrivateKeyHeader:

- clave
