---
title: Definición de entidad de clave de AZURE Function Master/API (versión preliminar)
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
description: Definición de entidad de tipo de información confidencial de clave de Azure Function Master/API.
ms.openlocfilehash: 78a4af95c6390cc16f6a60bd3874be660e3cfa5c
ms.sourcegitcommit: fa570d90b00ed1bb40e1ca27b11c66a84c4204e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68476395"
---
# <a name="azure-function-master--api-key-preview"></a>Clave de API o maestro de funciones de Azure (versión preliminar)  

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

Una combinación de 56 caracteres que consta de letras, dígitos y caracteres especiales.

o

Combinación de hasta 90 caracteres que constan de letras, dígitos y caracteres especiales.

## <a name="pattern"></a>Patrón

Cualquier combinación de 54 caracteres que consta de:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/)
- o signos más (+)
- termina con dos signos iguales (=)

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEFGHIJKLMNOP==`

o

Una combinación de 54 a 84 caracteres que consta de:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- o signos de porcentaje (%)
- termina con un sufijo "%3d%3d" (no distingue mayúsculas de minúsculas)

Por ejemplo:

abcdefghijklmnopqrstuvwxyz0123456789%2F%2BABCDEF0123456789%3D%3D


## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa para solicitar [La API de funciones de Azure](/azure/azure-functions/functions-how-to-use-azure-function-app-settings?tabs=portal) cuando su nivel de autorización se establece en un valor distinto del anónimo. 

Usa varios recursos principales:

- Patrones de clave simétrica codificada en Base64 de 320 bits.
- Patrones de clave simétrica con codificación URL de 320 bits.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.


## <a name="keywords"></a>Palabras clave

### <a name="keyword_symmetrickey320"></a>Keyword_SymmetricKey320:

- code=
- clave

### <a name="keyword_symmetrickey320urlencoded"></a>Keyword_SymmetricKey320UrlEncoded:

- code=
- clave
