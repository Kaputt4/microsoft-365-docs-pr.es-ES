---
title: Definición de entidad de encabezado de autorización HTTP (versión preliminar)
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
description: Definición de entidad de tipo de información confidencial del encabezado de autorización HTTP.
ms.openlocfilehash: b72934a88f85c0245320baa4b774d3c69196eb47
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000424"
---
# <a name="http-authorization-header-preview"></a>Encabezado de autorización HTTP (versión preliminar)

## <a name="format"></a>Formato

Encabezado de autorización usado en la solicitud HTTP.

## <a name="pattern"></a>Patrón

Varios formatos de encabezado de autenticación, por ejemplo:
 
`authorization: basic ********` <br>
`authorization: bearer ********` <br>
`authorization: digest ********` <br>
`authorization: negotiate ********` <br>

## <a name="checksum"></a>Suma de comprobación

No

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa en el encabezado de una [solicitud HTTP de autenticación y autorización.](/dotnet/api/system.net.http.headers.httprequestheaders.authorization?view=netframework-4.8) 

Usa varios recursos principales:

- Patrones de encabezado de autorización Http.
- Patrones de CredentialName, CredentialFeatures, ResourceType.
- Patrones de valores ficticios, censuras y marcadores de posición.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.

## <a name="keywords"></a>Palabras clave

### <a name="keyword_httpauthorizationheader"></a>Keyword_HttpAuthorizationHeader:

- Autorización

