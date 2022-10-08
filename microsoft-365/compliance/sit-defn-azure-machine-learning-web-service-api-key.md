---
title: Definición de entidad clave de la API del servicio web de Azure Machine Learning
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
ms.openlocfilehash: 0f0ee89c7968baa95b53593216c921ec18844386
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2022
ms.locfileid: "68503146"
---
# <a name="azure-machine-learning-web-service-api-key"></a>Clave de API del servicio web de Azure Machine Learning 

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

Esta SIT también se incluye en el SIT de [todas las credenciales](sit-defn-all-creds.md) agrupadas.

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

## <a name="credential-example"></a>Ejemplo de credencial 

`host: account.azureml.net/services/01234567-abcd-abcd-abcd-abcdef012345/workspaces/01234567-abcd-abcd-abcd-abcdef012345/; apikey: abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEabcdefghijklmnopqrstuvwxyz0123456789/+ABCDE==;`

## <a name="checksum"></a>Suma de comprobación

No

Los SIT que tienen sumas de comprobación usan un cálculo único para comprobar si la información es válida. Esto significa que cuando el valor **de suma de comprobación** es **Sí**, el servicio puede realizar una detección positiva solo en función de los datos confidenciales. Cuando el valor **de suma de comprobación** es **No** se deben detectar elementos adicionales (secundarios) para que el servicio realice una detección positiva.

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
