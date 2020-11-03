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
ms.openlocfilehash: bf7a6a70cefda7bfac83d42f8e8dd6355c479914
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845025"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="57062-104">Acceso a las API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="57062-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="57062-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="57062-105">**Applies to:**</span></span>
- <span data-ttu-id="57062-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="57062-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="57062-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="57062-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="57062-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="57062-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


 <span data-ttu-id="57062-109">Microsoft 365 defender expone gran parte de sus datos y acciones a través de un conjunto de API de programación.</span><span class="sxs-lookup"><span data-stu-id="57062-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="57062-110">Estas API le permitirán automatizar flujos de trabajo y innovar en función de las capacidades de Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="57062-110">Those APIs will enable you to automate workflows and innovate based on  Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="57062-111">El acceso a la API requiere la autenticación OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="57062-111">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="57062-112">Para obtener más información, vea [flujo de código de autorización de OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="57062-112">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>


<span data-ttu-id="57062-113">En general, deberá realizar los siguientes pasos para usar las API:</span><span class="sxs-lookup"><span data-stu-id="57062-113">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="57062-114">Crear una aplicación de AAD</span><span class="sxs-lookup"><span data-stu-id="57062-114">Create an AAD application</span></span>
- <span data-ttu-id="57062-115">Obtener un token de acceso con esta aplicación</span><span class="sxs-lookup"><span data-stu-id="57062-115">Get an access token using this application</span></span>
- <span data-ttu-id="57062-116">Usar el token para obtener acceso a la API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="57062-116">Use the token to access  Microsoft 365 Defender API</span></span>


<span data-ttu-id="57062-117">Puede tener acceso a la API de Microsoft 365 defender con **contexto de aplicación** o **contexto de usuario**.</span><span class="sxs-lookup"><span data-stu-id="57062-117">You can access Microsoft 365 Defender API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="57062-118">**Contexto de aplicación: (recomendado)**</span><span class="sxs-lookup"><span data-stu-id="57062-118">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="57062-119">Lo usan las aplicaciones que se ejecutan sin la presencia de un usuario que ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="57062-119">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="57062-120">por ejemplo, aplicaciones que se ejecutan como daemons o servicios en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="57062-120">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="57062-121">Pasos que se deben seguir para acceder a la API de Microsoft 365 defender con el contexto de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="57062-121">Steps that need to be taken to access  Microsoft 365 Defender API with application context:</span></span>

  1. <span data-ttu-id="57062-122">Cree una aplicación Web de AAD.</span><span class="sxs-lookup"><span data-stu-id="57062-122">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="57062-123">Asigne el permiso deseado a applicationFor example, **Incident. Read. All** , **AdvancedHunting. Read. All**.</span><span class="sxs-lookup"><span data-stu-id="57062-123">Assign the desired permission to the applicationFor example, **Incident.Read.All** , **AdvancedHunting.Read.All**.</span></span> 
  3. <span data-ttu-id="57062-124">Cree una clave para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="57062-124">Create a key for this Application.</span></span>
  4. <span data-ttu-id="57062-125">Obtiene el token mediante la aplicación con su clave.</span><span class="sxs-lookup"><span data-stu-id="57062-125">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="57062-126">Usar el token para obtener acceso a la API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="57062-126">Use the token to access  Microsoft 365 Defender API</span></span>

     <span data-ttu-id="57062-127">Para obtener más información, vea [Get Access with Application context](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="57062-127">For more information, see [Get access with application context](api-create-app-web.md).</span></span>


- <span data-ttu-id="57062-128">**Contexto de usuario:**</span><span class="sxs-lookup"><span data-stu-id="57062-128">**User Context:**</span></span> <br>
    <span data-ttu-id="57062-129">Se usa para realizar acciones en la API en nombre de un usuario.</span><span class="sxs-lookup"><span data-stu-id="57062-129">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="57062-130">Pasos que se deben seguir para acceder a la API de Microsoft 365 defender con el contexto de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="57062-130">Steps that needs to be taken to access  Microsoft 365 Defender API with application context:</span></span>
  1. <span data-ttu-id="57062-131">Cree una aplicación nativa de AAD.</span><span class="sxs-lookup"><span data-stu-id="57062-131">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="57062-132">Asigne el permiso deseado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="57062-132">Assign the desired permission to the application.</span></span> <span data-ttu-id="57062-133">Por ejemplo, **Incident. Read** , **AdvancedHunting. Read**.</span><span class="sxs-lookup"><span data-stu-id="57062-133">For example, **Incident.Read** , **AdvancedHunting.Read**.</span></span>
  3. <span data-ttu-id="57062-134">Obtiene el token mediante la aplicación con las credenciales de usuario.</span><span class="sxs-lookup"><span data-stu-id="57062-134">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="57062-135">Usar el token para obtener acceso a la API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="57062-135">Use the token to access  Microsoft 365 Defender API</span></span>

     <span data-ttu-id="57062-136">Para obtener más información, vea [obtener acceso con contexto de usuario](api-create-app-user-context.md).</span><span class="sxs-lookup"><span data-stu-id="57062-136">For more information, see [Get access with user context](api-create-app-user-context.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="57062-137">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="57062-137">Related topics</span></span>
- [<span data-ttu-id="57062-138">API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="57062-138">Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="57062-139">Acceso a Microsoft 365 defender con contexto de aplicación</span><span class="sxs-lookup"><span data-stu-id="57062-139">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="57062-140">Acceso a Microsoft 365 defender con contexto de usuario</span><span class="sxs-lookup"><span data-stu-id="57062-140">Access  Microsoft 365 Defender with user context</span></span>](api-create-app-user-context.md)
