---
title: Acceso a las API de Microsoft 365 defender
description: Obtenga información sobre cómo acceder a las API de Microsoft 365 defender
keywords: acceso, API, contexto de aplicación, contexto de usuario, aplicación AAD, token de acceso
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 5e01aaf2ee9255fd909b26278346fd4ccf54729a
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719243"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Acceso a las API de Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft 365 defender expone gran parte de sus datos y acciones a través de un conjunto de API de programación. Estas API le ayudan a automatizar flujos de trabajo y a realizar un uso completo de las capacidades de Microsoft 365 defender.

En general, deberá realizar los siguientes pasos para usar las API:

- Crear una aplicación de Azure Active Directory
- Obtener un token de acceso con esta aplicación
- Usar el token para obtener acceso a la API de Microsoft 365 defender

> [!NOTE]
> El acceso a la API requiere la autenticación OAuth 2.0. Para obtener más información, vea [flujo de código de autorización de OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Una vez que haya realizado estos pasos, estará listo para obtener acceso a la API de Microsoft 365 defender usando un contexto determinado.

## <a name="application-context-recommended"></a>Contexto de aplicación (recomendado)

Use este contexto para aplicaciones que se ejecutan sin la presencia de un usuario que ha iniciado sesión, como los servicios en segundo plano o daemons.

1. Cree una aplicación Web de Azure Active Directory.
2. Asigne los permisos que desee a la aplicación.
3. Cree una clave para la aplicación.
4. Obtenga un token de seguridad mediante la aplicación y su clave.
5. Use el token para obtener acceso a la API de Microsoft 365 defender.

Para obtener más información, vea **[crear una aplicación para obtener acceso a Microsoft 365 defender sin un usuario](api-create-app-web.md)**.

## <a name="user-context"></a>Contexto de usuario

Use este contexto para realizar acciones en nombre de un único usuario.

1. Cree una aplicación nativa de Azure Active Directory.
2. Asigne el permiso deseado a la aplicación.
3. Obtenga un token de seguridad con las credenciales de usuario de la aplicación.
4. Use el token para obtener acceso a la API de Microsoft 365 defender.

Para obtener más información, vea **[crear una aplicación para acceder a las API de Microsoft 365 defender en nombre de un usuario](api-create-app-user-context.md)**.

## <a name="partner-context"></a>Contexto de socio

Use este contexto cuando necesite proporcionar una aplicación a muchos usuarios a través de [varios inquilinos](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).

1. Cree una aplicación multiinquilino de Azure Active Directory.
2. Asigne el permiso deseado a la aplicación.
3. Obtenga el [consentimiento del administrador](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) para la aplicación de cada inquilino.
4. Obtenga un token de seguridad con credenciales de usuario basadas en el identificador de inquilino de un cliente.
5. Use el token para obtener acceso a la API de Microsoft 365 defender.

Para obtener más información, vea **[crear una aplicación con acceso de socio a las API de Microsoft 365 defender](api-partner-access.md)**.

## <a name="related-articles"></a>Artículos relacionados

- [Información general sobre las API de Microsoft 365 defender](api-overview.md)
- [OAuth 2,0 autorización para el inicio de sesión de usuario y el acceso a API](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Administrar secretos en las aplicaciones de servidor con Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [Crear una aplicación "Hola a todos" que tenga acceso a las API de 365 de Microsoft](api-hello-world.md)
