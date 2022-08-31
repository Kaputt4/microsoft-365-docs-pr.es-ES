---
title: Acceso a las API de Microsoft 365 Defender
description: Obtenga información sobre cómo acceder a las API de Microsoft 365 Defender
keywords: access, apis, contexto de aplicación, contexto de usuario, aplicación de aad, token de acceso
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.custom: api
ms.openlocfilehash: 0562ff901aa8021973fb1ed36e8caf464f22d672
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481578"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Acceso a las API de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Microsoft 365 Defender expone gran parte de sus datos y acciones a través de un conjunto de API mediante programación. Estas API le ayudan a automatizar los flujos de trabajo y a hacer un uso completo de las funcionalidades de Microsoft 365 Defender.

En general, deberá realizar los pasos siguientes para usar las API:

- Creación de una aplicación de Azure Active Directory
- Obtención de un token de acceso mediante esta aplicación
- Uso del token para acceder a la API de Microsoft 365 Defender

> [!NOTE]
> El acceso a la API requiere la autenticación de OAuth2.0. Para obtener más información, vea [Flujo de código de autorización de OAuth 2.0](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Una vez que haya realizado estos pasos, estará listo para acceder a la API de Microsoft 365 Defender mediante un contexto determinado.

## <a name="application-context-recommended"></a>Contexto de aplicación (recomendado)

Use este contexto para las aplicaciones que se ejecutan sin un usuario con sesión iniciada presente, como servicios en segundo plano o demonios.

1. Cree una aplicación web de Azure Active Directory.
2. Asigne los permisos deseados a la aplicación.
3. Cree una clave para la aplicación.
4. Obtenga un token de seguridad mediante la aplicación y su clave.
5. Use el token para acceder a la API de Microsoft 365 Defender.

Para obtener más información, consulte **[Creación de una aplicación para acceder a Microsoft 365 Defender sin un usuario](api-create-app-web.md)**.

## <a name="user-context"></a>Contexto del usuario

Use este contexto para realizar acciones en nombre de un único usuario.

1. Cree una aplicación nativa de Azure Active Directory.
2. Asigne el permiso deseado a la aplicación.
3. Obtenga un token de seguridad con las credenciales de usuario de la aplicación.
4. Use el token para acceder a la API de Microsoft 365 Defender.

Para obtener más información, consulte **[Creación de una aplicación para acceder a Microsoft 365 Defender API en nombre de un usuario](api-create-app-user-context.md)**.

## <a name="partner-context"></a>Contexto de asociado

Use este contexto cuando necesite proporcionar una aplicación a muchos usuarios en [varios inquilinos](/azure/active-directory/develop/single-and-multi-tenant-apps).

1. Cree una aplicación multiinquilino de Azure Active Directory.
2. Asigne el permiso deseado a la aplicación.
3. Obtenga [el consentimiento del administrador](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) para la aplicación de cada inquilino.
4. Obtenga un token de seguridad con credenciales de usuario basadas en el identificador de inquilino de un cliente.
5. Use el token para acceder a la API de Microsoft 365 Defender.

Para obtener más información, consulte **[Creación de una aplicación con acceso de asociado a Microsoft 365 Defender API](api-partner-access.md)**.

## <a name="related-articles"></a>Artículos relacionados

- [Introducción a las API de Microsoft 365 Defender](api-overview.md)
- [Autorización de OAuth 2.0 para el inicio de sesión de usuario y el acceso a la API](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Administración de secretos en las aplicaciones de servidor con Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/)
- [Creación de una aplicación "Hola mundo" que acceda a las API de Microsoft 365](api-hello-world.md)
