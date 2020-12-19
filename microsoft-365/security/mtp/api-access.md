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
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="64b84-104">Acceso a las API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="64b84-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="64b84-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="64b84-105">**Applies to:**</span></span>

- <span data-ttu-id="64b84-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64b84-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64b84-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="64b84-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="64b84-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="64b84-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="64b84-109">Microsoft 365 defender expone gran parte de sus datos y acciones a través de un conjunto de API de programación.</span><span class="sxs-lookup"><span data-stu-id="64b84-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="64b84-110">Estas API le ayudan a automatizar flujos de trabajo y a realizar un uso completo de las capacidades de Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="64b84-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="64b84-111">En general, deberá realizar los siguientes pasos para usar las API:</span><span class="sxs-lookup"><span data-stu-id="64b84-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="64b84-112">Crear una aplicación de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="64b84-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="64b84-113">Obtener un token de acceso con esta aplicación</span><span class="sxs-lookup"><span data-stu-id="64b84-113">Get an access token using this application</span></span>
- <span data-ttu-id="64b84-114">Usar el token para obtener acceso a la API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="64b84-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="64b84-115">El acceso a la API requiere la autenticación OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="64b84-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="64b84-116">Para obtener más información, vea [flujo de código de autorización de OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="64b84-116">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="64b84-117">Una vez que haya realizado estos pasos, estará listo para obtener acceso a la API de Microsoft 365 defender usando un contexto determinado.</span><span class="sxs-lookup"><span data-stu-id="64b84-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="64b84-118">Contexto de aplicación (recomendado)</span><span class="sxs-lookup"><span data-stu-id="64b84-118">Application context (Recommended)</span></span>

<span data-ttu-id="64b84-119">Use este contexto para aplicaciones que se ejecutan sin la presencia de un usuario que ha iniciado sesión, como los servicios en segundo plano o daemons.</span><span class="sxs-lookup"><span data-stu-id="64b84-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="64b84-120">Cree una aplicación Web de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="64b84-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="64b84-121">Asigne los permisos que desee a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="64b84-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="64b84-122">Cree una clave para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="64b84-122">Create a key for the application.</span></span>
4. <span data-ttu-id="64b84-123">Obtenga un token de seguridad mediante la aplicación y su clave.</span><span class="sxs-lookup"><span data-stu-id="64b84-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="64b84-124">Use el token para obtener acceso a la API de Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="64b84-124">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="64b84-125">Para obtener más información, vea **[crear una aplicación para obtener acceso a Microsoft 365 defender sin un usuario](api-create-app-web.md)**.</span><span class="sxs-lookup"><span data-stu-id="64b84-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="64b84-126">Contexto de usuario</span><span class="sxs-lookup"><span data-stu-id="64b84-126">User context</span></span>

<span data-ttu-id="64b84-127">Use este contexto para realizar acciones en nombre de un único usuario.</span><span class="sxs-lookup"><span data-stu-id="64b84-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="64b84-128">Cree una aplicación nativa de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="64b84-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="64b84-129">Asigne el permiso deseado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="64b84-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="64b84-130">Obtenga un token de seguridad con las credenciales de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="64b84-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="64b84-131">Use el token para obtener acceso a la API de Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="64b84-131">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="64b84-132">Para obtener más información, vea **[crear una aplicación para acceder a las API de Microsoft 365 defender en nombre de un usuario](api-create-app-user-context.md)**.</span><span class="sxs-lookup"><span data-stu-id="64b84-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="64b84-133">Contexto de socio</span><span class="sxs-lookup"><span data-stu-id="64b84-133">Partner context</span></span>

<span data-ttu-id="64b84-134">Use este contexto cuando necesite proporcionar una aplicación a muchos usuarios a través de [varios inquilinos](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).</span><span class="sxs-lookup"><span data-stu-id="64b84-134">Use this context when you need to provide an app to many users across [multiple tenants](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="64b84-135">Cree una aplicación multiinquilino de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="64b84-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="64b84-136">Asigne el permiso deseado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="64b84-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="64b84-137">Obtenga el [consentimiento del administrador](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) para la aplicación de cada inquilino.</span><span class="sxs-lookup"><span data-stu-id="64b84-137">Get [admin consent](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="64b84-138">Obtenga un token de seguridad con credenciales de usuario basadas en el identificador de inquilino de un cliente.</span><span class="sxs-lookup"><span data-stu-id="64b84-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="64b84-139">Use el token para obtener acceso a la API de Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="64b84-139">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="64b84-140">Para obtener más información, vea **[crear una aplicación con acceso de socio a las API de Microsoft 365 defender](api-partner-access.md)**.</span><span class="sxs-lookup"><span data-stu-id="64b84-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="64b84-141">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="64b84-141">Related articles</span></span>

- [<span data-ttu-id="64b84-142">Información general sobre las API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="64b84-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="64b84-143">OAuth 2,0 autorización para el inicio de sesión de usuario y el acceso a API</span><span class="sxs-lookup"><span data-stu-id="64b84-143">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="64b84-144">Administrar secretos en las aplicaciones de servidor con Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="64b84-144">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="64b84-145">Crear una aplicación "Hola a todos" que tenga acceso a las API de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="64b84-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)
