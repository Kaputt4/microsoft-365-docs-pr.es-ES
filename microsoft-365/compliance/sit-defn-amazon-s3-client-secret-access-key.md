---
title: Definición de entidad de clave de acceso de secreto de cliente de Amazon S3 (versión preliminar)
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
description: Definición de entidad de tipo de información confidencial de clave de acceso de secreto de cliente de Amazon S3.
ms.openlocfilehash: c3026beae856097e221063732f65b805a3fd05c2
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999341"
---
# <a name="amazon-s3-client-secret-access-key-preview"></a>Clave de acceso de secreto de cliente de Amazon S3 (versión preliminar)

## <a name="format"></a>Formato

Combinación de 40 caracteres que constan de letras, dígitos y caracteres especiales. 

## <a name="pattern"></a>Patrón

Número de 13 dígitos:

Una combinación de 40 caracteres que consta de: 

- a-z (no distingue mayúsculas de minúsculas) 
- 0-9 
- barra diagonal (/) o signo más (+) 

Por ejemplo: 

`abcdefghijklmnopqrst0123456789/+ABCDEFGH`

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Este SIT está diseñado para coincidir con la información de seguridad que se usa para acceder a [Amazon Web Services.](/toolkit-for-eclipse/v1/user-guide/setup-credentials.html)


Usa varios recursos principales: 
 
- Patrones de clave simétrica codificada en Base64 de 240 bits. 
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName. 
- Patrones de valores ficticios, censuras y marcadores de posición. 
- Diccionario de palabras de vocabulario.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán. 

## <a name="keywords"></a>Palabras clave

### <a name="keyword_symmetrickey240"></a>Keyword_SymmetricKey240: 

- Secreto 
- clave 