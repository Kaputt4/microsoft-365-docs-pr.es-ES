---
title: Definición de entidad de encabezado de autorización HTTP
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
description: Definición de entidad de tipo de información confidencial del encabezado de autorización HTTP.
ms.openlocfilehash: 052323c22f75a2ff9e843ed34b0340e11726aafa
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2022
ms.locfileid: "68503872"
---
# <a name="http-authorization-header"></a>Encabezado de autorización HTTP

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

Esta SIT también se incluye en el SIT de [todas las credenciales](sit-defn-all-creds.md) agrupadas.

 ## <a name="format"></a>Formato

Encabezado de autorización usado en la solicitud HTTP.

## <a name="pattern"></a>Patrón

Varios formatos de encabezado de autenticación, por ejemplo:
 
`authorization: basic ********` <br>
`authorization: bearer ********` <br>
`authorization: digest ********` <br>
`authorization: negotiate ********` <br>

## <a name="credential-example"></a>Ejemplo de credencial 

`Authorization: Basic ABCDEFGHIJKLMNOPQRS0123456789;`

## <a name="checksum"></a>Suma de comprobación

No

Los SIT que tienen sumas de comprobación usan un cálculo único para comprobar si la información es válida. Esto significa que cuando el valor **de suma de comprobación** es **Sí**, el servicio puede realizar una detección positiva solo en función de los datos confidenciales. Cuando el valor **de suma de comprobación** es **No** se deben detectar elementos adicionales (secundarios) para que el servicio realice una detección positiva.

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

