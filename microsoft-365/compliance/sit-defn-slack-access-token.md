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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Definición de entidad de tipo de información confidencial del token de acceso de Slack.
ms.openlocfilehash: 18e6654abe83bcbde40a832a74ec451c24f744b0
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999926"
---
# <a name="slack-access-token-preview"></a>Token de acceso de Slack (versión preliminar)

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
