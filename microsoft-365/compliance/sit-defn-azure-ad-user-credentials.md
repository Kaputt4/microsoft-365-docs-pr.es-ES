---
title: Definición de entidad de credenciales de usuario de Azure AD
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
description: Definición de entidad de tipo de información confidencial de credenciales de usuario de Azure AD.
ms.openlocfilehash: 80ae30fa7356c549a86d0bbbd053abca48143077
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2022
ms.locfileid: "68504576"
---
# <a name="azure-ad-user-credentials"></a>Credenciales de usuario de Azure AD

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

Esta SIT también se incluye en el SIT de [todas las credenciales](sit-defn-all-creds.md) agrupadas.

 ## <a name="format"></a>Formato

Nombre de usuario y contraseña emparejados relacionados con el dominio *.onmicrosoft.com.

o

Contraseña de texto sin formato usada en fragmentos de código.

o

Contraseña de texto sin formato que se usa en la configuración XML.

## <a name="pattern"></a>Patrón

Varios formatos de nombre de usuario y contraseña, por ejemplo:

`username=...password=********` <br>
`/user:.../pass:********` <br>
`SharePointOnlineAuthenticatedContext` <br>
`sign_in`<br>


o

Varios formatos de contraseña en fragmentos de código, por ejemplo:

`new X509Certificates2( ...` <br>
`ConvertTo-SecureString -String ********...`<br>
`password = "********"...` <br>
`"password" : "********"...` <br>
`UserPasswordCredential( ...` <br>

o

Varios formatos de contraseña en XML, por ejemplo:


```xml
... <secret>********</secret> ...
... <password>********</password> ...
... <setting name="password" value="********" > ... 
... <setting name="password">********</setting> ... 
... <setting name="password"><value>********</value></setting> ... 
```


## <a name="credential-example"></a>Ejemplo de credencial 

`username=user@tenant.onmicrosoft.com;password=ZYXWVU$1;`

## <a name="checksum"></a>Suma de comprobación

No

Los SIT que tienen sumas de comprobación usan un cálculo único para comprobar si la información es válida. Esto significa que cuando el valor **de suma de comprobación** es **Sí**, el servicio puede realizar una detección positiva solo en función de los datos confidenciales. Cuando el valor **de suma de comprobación** es **No** se deben detectar elementos adicionales (secundarios) para que el servicio realice una detección positiva.

## <a name="definition"></a>Definición

Esta SIT está diseñada para coincidir con la información de seguridad que se usa como contraseñas de usuario individuales para autenticarse en [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-reset-password-azure-portal). 

Usa varios recursos principales:

- Patrones de nombre de usuario y contraseña de texto sin formato para inquilinos de Azure AD.
- Patrones de contexto de contraseña en el código.
- Patrones de contexto de contraseña en XML.
- Patrones de CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName.
- Patrones de valores ficticios, censuras y marcadores de posición.
- Diccionario de vocabulario.

Los patrones están diseñados para que coincidan con las credenciales reales con una confianza razonable. Los patrones no coinciden con las credenciales con formato de ejemplo. Los valores ficticios, los valores censurados y los marcadores de posición, como el tipo de credencial o las descripciones de uso, en la posición donde debe presentarse un valor secreto real no coincidirán.


## <a name="keywords"></a>Palabras clave

### <a name="keyword_azureactivedirectorylogincredentials"></a>Keyword_AzureActiveDirectoryLoginCredentials:

- contraseña
- Pw
- userpass
- Credenciales
- cmdkey
- Authenti
- sign_in

### <a name="keyword_passwordcontextincode"></a>Keyword_PasswordContextInCode:

- clave
- x509c
- Credencial
- contraseña
- Pw
- securestring

### <a name="keyword_passwordcontextinxml"></a>Keyword_PasswordContextInXml:

- userpass
- contraseña
- Pw
- Connectionstring
- clave
- Credencial
- token
- Sas
- Secreto

