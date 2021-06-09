---
title: Acceder a las API de Microsoft Defender para punto de conexión
ms.reviewer: ''
description: Obtenga información sobre cómo usar las API para automatizar flujos de trabajo e innovar en función de las capacidades de Microsoft Defender para puntos de conexión
keywords: apis, api, wdatp, open api, microsoft defender para la api de punto de conexión, atp de microsoft defender, api pública, api admitida, alertas, dispositivo, usuario, dominio, ip, archivo, búsqueda avanzada, consulta
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9d3f4431825193d189f7ea1d73b6a99163cac428
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843703"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="c4293-104">Acceder a las API de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c4293-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c4293-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c4293-105">**Applies to:**</span></span>
- [<span data-ttu-id="c4293-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c4293-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c4293-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4293-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="c4293-108">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c4293-108">**Applies to:**</span></span> 
- [<span data-ttu-id="c4293-109">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c4293-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="c4293-110">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="c4293-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c4293-111">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="c4293-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="c4293-112">Defender for Endpoint expone gran parte de sus datos y acciones a través de un conjunto de API programáticas.</span><span class="sxs-lookup"><span data-stu-id="c4293-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="c4293-113">Estas API le permitirán automatizar flujos de trabajo e innovar en función de las capacidades de Defender para endpoints.</span><span class="sxs-lookup"><span data-stu-id="c4293-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="c4293-114">El acceso a la API requiere autenticación de OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="c4293-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="c4293-115">Para obtener más información, vea Código de autorización [de OAuth 2.0 Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="c4293-115">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="c4293-116">Vea este vídeo para obtener una introducción rápida a las API de Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="c4293-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="c4293-117">En general, deberá seguir los pasos siguientes para usar las API:</span><span class="sxs-lookup"><span data-stu-id="c4293-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="c4293-118">Crear una [aplicación de AAD](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span><span class="sxs-lookup"><span data-stu-id="c4293-118">Create an [AAD application](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span></span>
- <span data-ttu-id="c4293-119">Obtener un token de acceso con esta aplicación</span><span class="sxs-lookup"><span data-stu-id="c4293-119">Get an access token using this application</span></span>
- <span data-ttu-id="c4293-120">Usar el token para obtener acceso a la API de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c4293-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="c4293-121">Puede obtener acceso a defender para la API de extremo con **contexto de aplicación o** contexto de **usuario.**</span><span class="sxs-lookup"><span data-stu-id="c4293-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="c4293-122">**Contexto de aplicación: (recomendado)**</span><span class="sxs-lookup"><span data-stu-id="c4293-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="c4293-123">Se usa en aplicaciones que se ejecutan sin que haya un usuario que haya iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="c4293-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="c4293-124">por ejemplo, aplicaciones que se ejecutan como servicios en segundo plano o demonios.</span><span class="sxs-lookup"><span data-stu-id="c4293-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="c4293-125">Pasos que deben seguirse para obtener acceso a la API de Defender para Endpoint con el contexto de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="c4293-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="c4293-126">Crear una aplicación web de AAD.</span><span class="sxs-lookup"><span data-stu-id="c4293-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="c4293-127">Asigne el permiso deseado a la aplicación, por ejemplo, "Leer alertas", "Aislar máquinas".</span><span class="sxs-lookup"><span data-stu-id="c4293-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="c4293-128">Cree una clave para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="c4293-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="c4293-129">Obtener token con la aplicación con su clave.</span><span class="sxs-lookup"><span data-stu-id="c4293-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="c4293-130">Usar el token para obtener acceso a la API de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="c4293-130">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="c4293-131">Para obtener más información, vea [Obtener acceso con contexto de aplicación](exposed-apis-create-app-webapp.md).</span><span class="sxs-lookup"><span data-stu-id="c4293-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="c4293-132">**Contexto de usuario:**</span><span class="sxs-lookup"><span data-stu-id="c4293-132">**User Context:**</span></span> <br>
    <span data-ttu-id="c4293-133">Se usa para realizar acciones en la API en nombre de un usuario.</span><span class="sxs-lookup"><span data-stu-id="c4293-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="c4293-134">Pasos a seguir para obtener acceso a la API de Defender for Endpoint con el contexto de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="c4293-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="c4293-135">Crear una aplicación nativa de AAD.</span><span class="sxs-lookup"><span data-stu-id="c4293-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="c4293-136">Asigne el permiso deseado a la aplicación, por ejemplo, "Leer alertas", "Aislar máquinas", etc.</span><span class="sxs-lookup"><span data-stu-id="c4293-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="c4293-137">Obtener token con la aplicación con credenciales de usuario.</span><span class="sxs-lookup"><span data-stu-id="c4293-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="c4293-138">Usar el token para obtener acceso a la API de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="c4293-138">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="c4293-139">Para obtener más información, vea [Obtener acceso con contexto de usuario](exposed-apis-create-app-nativeapp.md).</span><span class="sxs-lookup"><span data-stu-id="c4293-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="c4293-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c4293-140">Related topics</span></span>
- [<span data-ttu-id="c4293-141">Microsoft Defender para api de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c4293-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="c4293-142">Access Microsoft Defender for Endpoint with application context</span><span class="sxs-lookup"><span data-stu-id="c4293-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="c4293-143">Access Microsoft Defender for Endpoint with user context</span><span class="sxs-lookup"><span data-stu-id="c4293-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
