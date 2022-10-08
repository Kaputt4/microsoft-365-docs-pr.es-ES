---
title: Definición de entidad de clave de api del servicio web de Azure Machine Learning (versión preliminar)
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
description: Definición de entidad de tipo de información confidencial de la API de servicio web de Azure Machine Learning.
ms.openlocfilehash: 531befbda54224cddc4a1d4d391469a2ef1b2ff8
ms.sourcegitcommit: fa570d90b00ed1bb40e1ca27b11c66a84c4204e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68476933"
---
# <a name="azure-machine-learning-web-service-api-key-preview"></a>Clave de API del servicio web de Azure Machine Learning (versión preliminar) 

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

Combinación de 88 caracteres que consta de letras, dígitos y caracteres especiales que terminan en dos signos iguales (==).

## <a name="pattern"></a>Patrón

Cualquier combinación de 86 caracteres:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/)
- o signos más (+)

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEabcdefghijklmnopqrstuvwxyz0123456789/+ABCDE==`

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa para conectarse a [los servicios web de Azure Machine Learning](/azure/machine-learning/classic/consume-web-services). 

Usa varios recursos principales:

- Patrones de clave simétrica codificada en Base64 de 512 bits.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName, ID, AccountName.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_symmetrickey512"></a>Keyword_SymmetricKey512:

- SharedAccessKey
- AccountKey
