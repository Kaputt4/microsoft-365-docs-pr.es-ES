---
title: Azure SQL definición de entidad de cadena de conexión (versión preliminar)
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
description: Azure SQL definición de entidad de tipo de información confidencial de cadena de conexión.
ms.openlocfilehash: 7091c50d96f22370358f5743a3992a10025ea29f
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999617"
---
# <a name="azure-sql-connection-string-preview"></a>Azure SQL cadena de conexión (versión preliminar)

## <a name="format"></a>Formato

Combinación de hasta 20 000 caracteres de letras, dígitos y caracteres especiales.

o

Un par de nombre de usuario y contraseña usados en el proceso de autenticación general.


## <a name="pattern"></a>Patrón

Cualquier combinación de hasta 20 000 caracteres que consta de:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/)
- o signos más (+)
- Hasta 2
- signos iguales (=)

Por ejemplo: 

`MIIKcQIBAzCCCi0GCSqGSIb3DQEHAaCCCh4EggoaMIIKFjCCBg8GCSqGSIb3DQEHAaCCBgAEggX8MIIF+DCCBfQGCyqGSIb3DQEM`

o

Formatos de nombre de usuario y contraseña variantes, por ejemplo:

`username=...;password=********;` <br>
`user id=...;password=********;` <br>
`uid=...;pwd=********;` <br>
`DB_USER=...;DB_PASS=********;` <br>
`Service Account=...;Password=********;` <br>


## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa para conectarse a [bases de datos de Azure SQL](/azure/sql-database/sql-database-aad-authentication-configure).

Usa varios recursos principales:

- Patrones de literal de cadena codificada en Base64.
- Patrones de nombre de usuario y contraseña de texto sin formato.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.
- Patrones de valores ficticios, censuras y marcadores de posición.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_base64encodedstringliteral"></a>Keyword_Base64EncodedStringLiteral:

- MII

### <a name="keyword_logincredentials"></a>Keyword_LoginCredentials:

- contraseña
- Pw
- DB_
