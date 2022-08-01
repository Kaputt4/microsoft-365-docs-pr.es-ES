---
title: Definición de entidad de token de acceso personal de Azure Databricks (versión preliminar)
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
description: Definición de entidad de tipo de información confidencial del token de acceso personal de Azure Databricks.
ms.openlocfilehash: 9dfe6cb2616cc389cd122b4430c717bd099900f0
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999446"
---
# <a name="azure-databricks-personal-access-token-preview"></a>Token de acceso personal de Azure Databricks (versión preliminar) 

## <a name="format"></a>Formato

Una combinación de 32 caracteres que consta de letras y dígitos.

## <a name="pattern"></a>Patrón

Una combinación de 32 caracteres que consta de:
 
- a-f o A-F (distingue mayúsculas de minúsculas)
- o 0-9

Por ejemplo:

`abcdef0123456789abcdef0123456789`

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa para autenticarse en la [API REST de Azure Databricks](/azure/databricks/administration-guide/access-control/tokens). 

Usa varios recursos principales:

- Patrones de clave simétrica de 128 bits codificada hexadecimalmente.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.


## <a name="keywords"></a>Palabras clave

### <a name="keyword_symmetrickey128hex"></a>Keyword_SymmetricKey128Hex:

dapi key secret token password pw
