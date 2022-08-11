---
title: Definición de entidad secreta de aplicación de Azure DevOps (versión preliminar)
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
description: Definición de entidad de tipo de información confidencial del secreto de aplicación de Azure DevOps.
ms.openlocfilehash: d689cb184cd329d1d5686a5dde486305b5375078
ms.sourcegitcommit: 771f7bbb241f910b3e16b4d1f9bbd9c0c8c6fa34
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2022
ms.locfileid: "67309359"
---
# <a name="azure-devops-app-secret-preview"></a>Secreto de aplicación de Azure DevOps (versión preliminar)

## <a name="format"></a>Formato

Una combinación de 52 caracteres que consta de letras, dígitos y caracteres especiales.

## <a name="pattern"></a>Patrón

Cualquier combinación de 52 caracteres que consta de:
 
- a-z o A-Z (distingue mayúsculas de minúsculas)
- o 2-7

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz234567abcdefghijklmnopqrst`


## <a name="checksum"></a>Suma de comprobación

Sí

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa para autenticar a los usuarios de aplicaciones web para el [acceso a la API REST de Azure DevOps.](/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops) 

Usa varios recursos principales:

- Patrones de clave simétrica codificada en Base32 de 256 bits.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_symmetrickey256b32"></a>Keyword_SymmetricKey256B32:

- palmadita
- token
- Ado
- Vsts
- azuredevops
- visualstudio.com
- dev.azure.com
