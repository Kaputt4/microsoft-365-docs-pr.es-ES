---
title: Obtener acceso a las API de Microsoft 365 Defender
description: Obtenga información sobre cómo obtener acceso a las API de Microsoft 365 Defender
keywords: access, api, contexto de aplicación, contexto de usuario, aplicación de aad, token de acceso
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ea787adfba0afb425da5f6ea0f6609f96e06b378
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932159"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Obtener acceso a las API de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información está relacionada con el producto de versión preliminar que puede modificarse considerablemente antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft 365 Defender expone gran parte de sus datos y acciones a través de un conjunto de API mediante programación. Estas API le ayudan a automatizar los flujos de trabajo y a aprovechar al máximo las capacidades de Microsoft 365 Defender.

En general, deberá seguir los pasos siguientes para usar las API:

- Crear una aplicación de Azure Active Directory
- Obtener un token de acceso con esta aplicación
- Usar el token para obtener acceso a la API de Microsoft 365 Defender

> [!NOTE]
> El acceso a la API requiere la autenticación de OAuth2.0. Para obtener más información, vea [OAuth 2.0 Flujo de código de autorización.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

Una vez que haya realizado estos pasos, estará listo para acceder a la API de Microsoft 365 Defender con un contexto determinado.

## <a name="application-context-recommended"></a>Contexto de aplicación (recomendado)

Usa este contexto para aplicaciones que se ejecutan sin que haya un usuario que haya iniciado sesión, como servicios en segundo plano o demonios.

1. Cree una aplicación web de Azure Active Directory.
2. Asigne los permisos deseados a la aplicación.
3. Cree una clave para la aplicación.
4. Obtener un token de seguridad mediante la aplicación y su clave.
5. Use el token para obtener acceso a la API de Microsoft 365 Defender.

Para obtener más información, vea **[Crear una aplicación para obtener acceso a Microsoft 365 Defender sin un usuario.](api-create-app-web.md)**

## <a name="user-context"></a>Contexto de usuario

Use este contexto para realizar acciones en nombre de un solo usuario.

1. Cree una aplicación nativa de Azure Active Directory.
2. Asigne el permiso deseado a la aplicación.
3. Obtenga un token de seguridad con las credenciales de usuario de la aplicación.
4. Use el token para obtener acceso a la API de Microsoft 365 Defender.

Para obtener más información, vea Crear una aplicación para obtener acceso a las API de **[Microsoft 365 Defender en nombre de un usuario.](api-create-app-user-context.md)**

## <a name="partner-context"></a>Contexto de partner

Use este contexto cuando necesite proporcionar una aplicación a muchos usuarios en [varios inquilinos.](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)

1. Cree una aplicación multiinquilino de Azure Active Directory.
2. Asigne el permiso deseado a la aplicación.
3. Obtener [el consentimiento del administrador](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) para la aplicación de cada inquilino.
4. Obtenga un token de seguridad con credenciales de usuario basadas en el id. de inquilino de un cliente.
5. Use el token para obtener acceso a la API de Microsoft 365 Defender.

Para obtener más información, vea Crear una aplicación con acceso de asociado a las **[API de Microsoft 365 Defender.](api-partner-access.md)**

## <a name="related-articles"></a>Artículos relacionados

- [Introducción a las API de Microsoft 365 Defender](api-overview.md)
- [Autorización de OAuth 2.0 para el inicio de sesión de usuario y el acceso a la API](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Administrar secretos en las aplicaciones de servidor con Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [Crear una aplicación "Hola a todos" que acceda a las API de Microsoft 365](api-hello-world.md)
