---
title: Definición de entidad de clave de acceso de Azure EventGrid (versión preliminar)
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
- tier2
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Azure EventGrid tiene acceso a la definición de entidad de tipo de información confidencial de clave.
ms.openlocfilehash: 55d637a4ad578948bf7bf46ac745a33d689610ee
ms.sourcegitcommit: fa570d90b00ed1bb40e1ca27b11c66a84c4204e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68476889"
---
# <a name="azure-eventgrid-access-key-preview"></a>Clave de acceso de Azure EventGrid (versión preliminar)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

Combinación de 43 caracteres que consta de letras, dígitos y caracteres especiales que terminan en un signo igual (=) que no forma parte del patrón.

## <a name="pattern"></a>Patrón

Una combinación de 43 caracteres que consta de:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/)
- o signos más (+)

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDE=`

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa para autenticar eventos de publicación de aplicaciones en [Azure Event Grid recursos (temas y dominios).](/azure/event-grid/get-access-keys)

Usa varios recursos principales:

- Patrones de clave simétrica codificada en Base64 de 256 bits.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName, ID.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_symmetrickey256"></a>Keyword_SymmetricKey256:

- SharedAccessKey
- AccountKey
