---
title: Definición de entidad de firma de acceso compartido de Azure Logic App (versión preliminar)
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
description: Definición de entidad de tipo de información confidencial de firma de acceso compartido de Azure Logic App.
ms.openlocfilehash: ff777170f9c9cc7ea3865a4a01e794c20137f7db
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999419"
---
# <a name="azure-logic-app-shared-access-signature-preview"></a>Firma de acceso compartido de Azure Logic App (versión preliminar) 

## <a name="format"></a>Formato

Combinación de hasta 76 caracteres que constan de letras, dígitos y caracteres especiales.

## <a name="pattern"></a>Patrón

Cualquier combinación de 43 a 73 caracteres que consta de:

- a-z (no distingue mayúsculas de minúsculas)
- 0-9
- o signos de porcentaje (%)
- termina con un sufijo "%3d" (no distingue mayúsculas de minúsculas)

Por ejemplo:

`abcdefghijklmnopqrstuvwxyz0123456789%2F%2BABCDE%3D`

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa para conceder acceso a un punto de conexión de solicitud en [Azure Logic Apps.](/azure/logic-apps/logic-apps-securing-a-logic-app?tabs=azure-portal) 

Usa varios recursos principales:

Patrones de clave simétrica con codificación URL de 256 bits.
Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.
Patrones de valores ficticios, censuras y marcadores de posición.
Diccionario de vocabulario

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.


## <a name="keywords"></a>Palabras clave

### <a name="keyword_symmetrickey256urlencoded"></a>Keyword_SymmetricKey256UrlEncoded:

- sig=
- clave
- token
- Secreto
- contraseña
