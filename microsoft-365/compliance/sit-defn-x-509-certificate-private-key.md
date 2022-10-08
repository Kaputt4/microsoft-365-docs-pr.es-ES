---
title: Definición de entidad de clave privada de certificado X.509 (versión preliminar)
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
ms.openlocfilehash: 144eff9826dcbb3bcfc03930442a4d4e3a36e22c
ms.sourcegitcommit: fa570d90b00ed1bb40e1ca27b11c66a84c4204e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68476141"
---
# <a name="x509-certificate-private-key-preview"></a>Clave privada de certificado X.509 (versión preliminar)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

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


## <a name="checksum"></a>Suma de comprobación

Sí

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
