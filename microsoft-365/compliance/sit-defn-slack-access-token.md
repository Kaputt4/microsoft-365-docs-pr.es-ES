---
title: Definición de entidad de token de acceso de Slack (versión preliminar)
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
description: Definición de entidad de tipo de información confidencial del token de acceso de Slack.
ms.openlocfilehash: 03625b59e35dd9f265988dab84c39d8735b0e8be
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68471824"
---
# <a name="slack-access-token-preview"></a>Token de acceso de Slack (versión preliminar)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Formato

Una combinación de hasta 34 caracteres que consta de letras, dígitos y caracteres especiales.

## <a name="pattern"></a>Patrón

Prefijo de token (distingue mayúsculas de minúsculas) "xoxp-", "xoxb-", "xoxa-", "xoxr-", "xoxo-", "xoxs-" o "xoxe-"

Una combinación de hasta 29 caracteres:

- 29 a-z (no distingue mayúsculas de minúsculas)
- 0-9 o guiones (-)

Por ejemplo:

`xoxp-abcdef-abcdef-abcdef-abcdef` 

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa para acceder a [las funcionalidades de la plataforma Slack](https://api.slack.com/docs/token-type) (por ejemplo, tokens de bot, tokens de usuario y tokens de nivel de aplicación). 

Usa varios recursos principales:

- Patrones de token de usuario, bot o área de trabajo de Slack.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.
- Patrones de valores ficticios, censuras y marcadores de posición.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_slacktokens"></a>Keyword_SlackTokens:

- Xox
