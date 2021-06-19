---
title: Obtener acceso a Microsoft 365 Defender API de acceso
description: Obtenga información sobre cómo obtener acceso a Microsoft 365 Defender API
keywords: access, apis, application context, user context, aad application, access token
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 03fd82cd5dc24653b6d67fa47cc225d355bfac45
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028804"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Obtener acceso a Microsoft 365 Defender API de acceso

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Microsoft 365 Defender expone gran parte de sus datos y acciones a través de un conjunto de API mediante programación. Estas API le ayudan a automatizar los flujos de trabajo y a aprovechar al máximo Microsoft 365 Defender capacidades del usuario.

En general, deberá seguir los pasos siguientes para usar las API:

- Crear una Azure Active Directory aplicación
- Obtener un token de acceso con esta aplicación
- Usar el token para obtener acceso a la API Microsoft 365 Defender usuario

> [!NOTE]
> El acceso a la API requiere autenticación de OAuth2.0. Para obtener más información, vea Código de autorización [de OAuth 2.0 Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Una vez que haya realizado estos pasos, estará listo para tener acceso a la API Microsoft 365 Defender mediante un contexto determinado.

## <a name="application-context-recommended"></a>Contexto de aplicación (recomendado)

Usa este contexto para aplicaciones que se ejecutan sin que haya un usuario que haya iniciado sesión, como servicios en segundo plano o demonios.

1. Crear una Azure Active Directory web.
2. Asigne los permisos deseados a la aplicación.
3. Cree una clave para la aplicación.
4. Obtener un token de seguridad con la aplicación y su clave.
5. Use el token para obtener acceso a Microsoft 365 Defender API.

Para obtener más información, consulta **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.

## <a name="user-context"></a>Contexto del usuario

Use este contexto para realizar acciones en nombre de un único usuario.

1. Cree una Azure Active Directory nativa.
2. Asigne el permiso deseado a la aplicación.
3. Obtener un token de seguridad con las credenciales de usuario de la aplicación.
4. Use el token para obtener acceso a Microsoft 365 Defender API.

Para obtener más información, consulta **[Create an app to access Microsoft 365 Defender API on behalf of a user](api-create-app-user-context.md)**.

## <a name="partner-context"></a>Contexto del partner

Usa este contexto cuando necesites proporcionar una aplicación a muchos usuarios en [varios inquilinos.](/azure/active-directory/develop/single-and-multi-tenant-apps)

1. Cree una Azure Active Directory multiinquilino.
2. Asigne el permiso deseado a la aplicación.
3. Obtener [el consentimiento de administrador](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) para la aplicación de cada inquilino.
4. Obtener un token de seguridad con credenciales de usuario basadas en el identificador de inquilino de un cliente.
5. Use el token para obtener acceso a Microsoft 365 Defender API.

Para obtener más información, consulta **[Create an app with partner access to Microsoft 365 Defender API](api-partner-access.md)**.

## <a name="related-articles"></a>Artículos relacionados

- [Microsoft 365 Defender Introducción a las API](api-overview.md)
- [Autorización de OAuth 2.0 para el inicio de sesión de usuario y el acceso a la API](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Administrar secretos en las aplicaciones de servidor con Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/)
- [Crear una aplicación "Hello world" que acceda a las API de Microsoft 365 web](api-hello-world.md)