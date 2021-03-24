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
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="14d43-104">Obtener acceso a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="14d43-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="14d43-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="14d43-105">**Applies to:**</span></span>

- <span data-ttu-id="14d43-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="14d43-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14d43-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="14d43-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="14d43-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="14d43-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="14d43-109">Microsoft 365 Defender expone gran parte de sus datos y acciones a través de un conjunto de API programáticas.</span><span class="sxs-lookup"><span data-stu-id="14d43-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="14d43-110">Estas API le ayudan a automatizar flujos de trabajo y a aprovechar al máximo las capacidades de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="14d43-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="14d43-111">En general, deberá seguir los pasos siguientes para usar las API:</span><span class="sxs-lookup"><span data-stu-id="14d43-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="14d43-112">Crear una aplicación de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="14d43-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="14d43-113">Obtener un token de acceso con esta aplicación</span><span class="sxs-lookup"><span data-stu-id="14d43-113">Get an access token using this application</span></span>
- <span data-ttu-id="14d43-114">Usar el token para obtener acceso a la API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="14d43-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="14d43-115">El acceso a la API requiere autenticación de OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="14d43-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="14d43-116">Para obtener más información, vea Flujo de código de autorización de [OAuth 2.0](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="14d43-116">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="14d43-117">Una vez que hayas realizado estos pasos, estás listo para acceder a la API de Microsoft 365 Defender con un contexto determinado.</span><span class="sxs-lookup"><span data-stu-id="14d43-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="14d43-118">Contexto de aplicación (recomendado)</span><span class="sxs-lookup"><span data-stu-id="14d43-118">Application context (Recommended)</span></span>

<span data-ttu-id="14d43-119">Usa este contexto para aplicaciones que se ejecutan sin que haya un usuario que haya iniciado sesión, como servicios en segundo plano o demonios.</span><span class="sxs-lookup"><span data-stu-id="14d43-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="14d43-120">Crear una aplicación web de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="14d43-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="14d43-121">Asigne los permisos deseados a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="14d43-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="14d43-122">Cree una clave para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="14d43-122">Create a key for the application.</span></span>
4. <span data-ttu-id="14d43-123">Obtener un token de seguridad con la aplicación y su clave.</span><span class="sxs-lookup"><span data-stu-id="14d43-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="14d43-124">Use el token para obtener acceso a la API de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="14d43-124">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="14d43-125">Para obtener más información, consulta **[Crear una aplicación para tener acceso a Microsoft 365 Defender sin un usuario.](api-create-app-web.md)**</span><span class="sxs-lookup"><span data-stu-id="14d43-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="14d43-126">Contexto de usuario</span><span class="sxs-lookup"><span data-stu-id="14d43-126">User context</span></span>

<span data-ttu-id="14d43-127">Use este contexto para realizar acciones en nombre de un único usuario.</span><span class="sxs-lookup"><span data-stu-id="14d43-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="14d43-128">Crear una aplicación nativa de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="14d43-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="14d43-129">Asigne el permiso deseado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="14d43-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="14d43-130">Obtener un token de seguridad con las credenciales de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="14d43-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="14d43-131">Use el token para obtener acceso a la API de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="14d43-131">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="14d43-132">Para obtener más información, consulta Crear una aplicación para tener acceso a las API de **[Microsoft 365 Defender en nombre de un usuario.](api-create-app-user-context.md)**</span><span class="sxs-lookup"><span data-stu-id="14d43-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="14d43-133">Contexto del partner</span><span class="sxs-lookup"><span data-stu-id="14d43-133">Partner context</span></span>

<span data-ttu-id="14d43-134">Usa este contexto cuando necesites proporcionar una aplicación a muchos usuarios en [varios inquilinos.](/azure/active-directory/develop/single-and-multi-tenant-apps)</span><span class="sxs-lookup"><span data-stu-id="14d43-134">Use this context when you need to provide an app to many users across [multiple tenants](/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="14d43-135">Crear una aplicación multiinquilino de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="14d43-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="14d43-136">Asigne el permiso deseado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="14d43-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="14d43-137">Obtener [el consentimiento de administrador](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) para la aplicación de cada inquilino.</span><span class="sxs-lookup"><span data-stu-id="14d43-137">Get [admin consent](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="14d43-138">Obtener un token de seguridad con credenciales de usuario basadas en el identificador de inquilino de un cliente.</span><span class="sxs-lookup"><span data-stu-id="14d43-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="14d43-139">Use el token para obtener acceso a la API de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="14d43-139">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="14d43-140">Para obtener más información, consulta Crear una aplicación con acceso de asociado a las **[API de Microsoft 365 Defender.](api-partner-access.md)**</span><span class="sxs-lookup"><span data-stu-id="14d43-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="14d43-141">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="14d43-141">Related articles</span></span>

- [<span data-ttu-id="14d43-142">Introducción a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="14d43-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="14d43-143">Autorización de OAuth 2.0 para el inicio de sesión de usuario y el acceso a la API</span><span class="sxs-lookup"><span data-stu-id="14d43-143">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="14d43-144">Administrar secretos en las aplicaciones de servidor con Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="14d43-144">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="14d43-145">Crear una aplicación "Hello world" que acceda a las API de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="14d43-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)