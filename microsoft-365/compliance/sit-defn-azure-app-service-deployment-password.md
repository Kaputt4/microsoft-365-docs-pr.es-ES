---
title: definición de entidad de contraseña de implementación de Azure App Service (versión preliminar)
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
description: Azure App Service definición de entidad de tipo de información confidencial de contraseña de implementación.
ms.openlocfilehash: 6b8915b64e9b647523838284a996f1fca8721eef
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999488"
---
# <a name="azure-app-service-deployment-password-preview"></a>Azure App Service contraseña de implementación (versión preliminar)

## <a name="format"></a>Formato

Combinación de 60 caracteres que constan de letras, dígitos y caracteres especiales.

## <a name="pattern"></a>Patrón

Cualquier combinación de 60 caracteres que consta de:
 
- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- barras diagonales (/)
- o signos más (+)

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEFGHIJKLMNOPQRSTUV`



## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa para proteger [Azure App Service implementación](/azure/app-service/deploy-configure-credentials) desde un equipo local.

Usa varios recursos principales:

- Patrones de clave simétrica codificada en Base64 de 360 bits.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_symmetrickey360"></a>Keyword_SymmetricKey360:

- contraseña
- Pw
