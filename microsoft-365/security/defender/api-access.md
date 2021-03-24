---
title: Obtener acceso a las API de Microsoft 365 Defender
description: Obtenga información sobre cómo obtener acceso a las API de Microsoft 365 Defender
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
ms.openlocfilehash: 1fbba132e664f4773496eac7123a0a408db5b3bd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072760"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Obtener acceso a las API de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Microsoft 365 Defender expone gran parte de sus datos y acciones a través de un conjunto de API programáticas. Estas API le ayudan a automatizar flujos de trabajo y a aprovechar al máximo las capacidades de Microsoft 365 Defender.

En general, deberá seguir los pasos siguientes para usar las API:

- Crear una aplicación de Azure Active Directory
- Obtener un token de acceso con esta aplicación
- Usar el token para obtener acceso a la API de Microsoft 365 Defender

> [!NOTE]
> El acceso a la API requiere autenticación de OAuth2.0. Para obtener más información, vea Flujo de código de autorización de [OAuth 2.0](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Una vez que hayas realizado estos pasos, estás listo para acceder a la API de Microsoft 365 Defender con un contexto determinado.

## <a name="application-context-recommended"></a>Contexto de aplicación (recomendado)

Usa este contexto para aplicaciones que se ejecutan sin que haya un usuario que haya iniciado sesión, como servicios en segundo plano o demonios.

1. Crear una aplicación web de Azure Active Directory.
2. Asigne los permisos deseados a la aplicación.
3. Cree una clave para la aplicación.
4. Obtener un token de seguridad con la aplicación y su clave.
5. Use el token para obtener acceso a la API de Microsoft 365 Defender.

Para obtener más información, consulta **[Crear una aplicación para tener acceso a Microsoft 365 Defender sin un usuario.](api-create-app-web.md)**

## <a name="user-context"></a>Contexto de usuario

Use este contexto para realizar acciones en nombre de un único usuario.

1. Crear una aplicación nativa de Azure Active Directory.
2. Asigne el permiso deseado a la aplicación.
3. Obtener un token de seguridad con las credenciales de usuario de la aplicación.
4. Use el token para obtener acceso a la API de Microsoft 365 Defender.

Para obtener más información, consulta Crear una aplicación para tener acceso a las API de **[Microsoft 365 Defender en nombre de un usuario.](api-create-app-user-context.md)**

## <a name="partner-context"></a>Contexto del partner

Usa este contexto cuando necesites proporcionar una aplicación a muchos usuarios en [varios inquilinos.](/azure/active-directory/develop/single-and-multi-tenant-apps)

1. Crear una aplicación multiinquilino de Azure Active Directory.
2. Asigne el permiso deseado a la aplicación.
3. Obtener [el consentimiento de administrador](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) para la aplicación de cada inquilino.
4. Obtener un token de seguridad con credenciales de usuario basadas en el identificador de inquilino de un cliente.
5. Use el token para obtener acceso a la API de Microsoft 365 Defender.

Para obtener más información, consulta Crear una aplicación con acceso de asociado a las **[API de Microsoft 365 Defender.](api-partner-access.md)**

## <a name="related-articles"></a>Artículos relacionados

- [Introducción a las API de Microsoft 365 Defender](api-overview.md)
- [Autorización de OAuth 2.0 para el inicio de sesión de usuario y el acceso a la API](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Administrar secretos en las aplicaciones de servidor con Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/)
- [Crear una aplicación "Hello world" que acceda a las API de Microsoft 365](api-hello-world.md)