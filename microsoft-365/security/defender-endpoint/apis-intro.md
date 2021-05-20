---
title: Acceder a las API de Microsoft Defender para punto de conexión
ms.reviewer: ''
description: Descubra cómo puede usar las API para automatizar flujos de trabajo e innovar en función de las capacidades de Microsoft Defender para endpoints
keywords: apis, api, wdatp, api abierta, microsoft defender para la api de punto de conexión, microsoft defender ATP, api pública, apis admitidas, alertas, dispositivo, usuario, dominio, ip, archivo, caza avanzada, consulta
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
ms.technology: mde
ms.openlocfilehash: a91a401d5d57c7757bc043178c95dc42e7733b41
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571834"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="f3624-104">Acceder a las API de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="f3624-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f3624-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f3624-105">**Applies to:**</span></span>
- [<span data-ttu-id="f3624-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="f3624-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f3624-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3624-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="f3624-108">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f3624-108">**Applies to:**</span></span> 
- [<span data-ttu-id="f3624-109">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="f3624-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="f3624-110">¿Desea experimentar Microsoft Defender para Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f3624-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f3624-111">Regístrese para una prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="f3624-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="f3624-112">Defender for Endpoint expone gran parte de sus datos y acciones a través de un conjunto de API programáticas.</span><span class="sxs-lookup"><span data-stu-id="f3624-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="f3624-113">Esas API le permitirán automatizar flujos de trabajo e innovar en función de las capacidades de Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="f3624-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="f3624-114">El acceso a la API requiere autenticación OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="f3624-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="f3624-115">Para obtener más información, consulte [Código de autorización de OAuth 2.0 Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="f3624-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="f3624-116">Vea este vídeo para obtener una visión general rápida de las API de Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="f3624-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="f3624-117">En general, deberá seguir los siguientes pasos para usar las API:</span><span class="sxs-lookup"><span data-stu-id="f3624-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="f3624-118">Crear una [aplicación AAD](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span><span class="sxs-lookup"><span data-stu-id="f3624-118">Create an [AAD application](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span></span>
- <span data-ttu-id="f3624-119">Obtenga un token de acceso con esta aplicación</span><span class="sxs-lookup"><span data-stu-id="f3624-119">Get an access token using this application</span></span>
- <span data-ttu-id="f3624-120">Use el token para obtener acceso a Defender para endpoint API</span><span class="sxs-lookup"><span data-stu-id="f3624-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="f3624-121">Puede acceder a Defender para endpoint API con **contexto de aplicación** o contexto de **usuario**.</span><span class="sxs-lookup"><span data-stu-id="f3624-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="f3624-122">**Contexto de aplicación: (recomendado)**</span><span class="sxs-lookup"><span data-stu-id="f3624-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="f3624-123">Utilizado por aplicaciones que se ejecutan sin un usuario que ha iniciado sesión presente.</span><span class="sxs-lookup"><span data-stu-id="f3624-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="f3624-124">por ejemplo, aplicaciones que se ejecutan como servicios en segundo plano o demonios.</span><span class="sxs-lookup"><span data-stu-id="f3624-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="f3624-125">Pasos que deben tomarse para tener acceso a defender para la API de punto de conexión con el contexto de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="f3624-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="f3624-126">Cree una aplicación web AAD.</span><span class="sxs-lookup"><span data-stu-id="f3624-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="f3624-127">Asigne el permiso deseado a la aplicación, por ejemplo, "Leer alertas", "Aislar máquinas".</span><span class="sxs-lookup"><span data-stu-id="f3624-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="f3624-128">Cree una clave para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="f3624-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="f3624-129">Obtenga token con la aplicación con su clave.</span><span class="sxs-lookup"><span data-stu-id="f3624-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="f3624-130">Use el token para tener acceso a la API de Microsoft Defender para Endpoint</span><span class="sxs-lookup"><span data-stu-id="f3624-130">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="f3624-131">Para obtener más información, consulte [Obtener acceso con el contexto de la aplicación.](exposed-apis-create-app-webapp.md)</span><span class="sxs-lookup"><span data-stu-id="f3624-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="f3624-132">**Contexto del usuario:**</span><span class="sxs-lookup"><span data-stu-id="f3624-132">**User Context:**</span></span> <br>
    <span data-ttu-id="f3624-133">Se utiliza para realizar acciones en la API en nombre de un usuario.</span><span class="sxs-lookup"><span data-stu-id="f3624-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="f3624-134">Pasos a seguir para acceder a defender para endpoint API con contexto de aplicación:</span><span class="sxs-lookup"><span data-stu-id="f3624-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="f3624-135">Cree AAD Native-Application.</span><span class="sxs-lookup"><span data-stu-id="f3624-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="f3624-136">Asigne el permiso deseado a la aplicación, por ejemplo, "Leer alertas", 'Aislar máquinas', etc.</span><span class="sxs-lookup"><span data-stu-id="f3624-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="f3624-137">Obtenga token con la aplicación con credenciales de usuario.</span><span class="sxs-lookup"><span data-stu-id="f3624-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="f3624-138">Use el token para tener acceso a la API de Microsoft Defender para Endpoint</span><span class="sxs-lookup"><span data-stu-id="f3624-138">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="f3624-139">Para obtener más información, consulte [Obtener acceso con el contexto del usuario.](exposed-apis-create-app-nativeapp.md)</span><span class="sxs-lookup"><span data-stu-id="f3624-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="f3624-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f3624-140">Related topics</span></span>
- [<span data-ttu-id="f3624-141">Microsoft Defender para las API de endpoints</span><span class="sxs-lookup"><span data-stu-id="f3624-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="f3624-142">Acceda a Microsoft Defender para endpoint con contexto de aplicación</span><span class="sxs-lookup"><span data-stu-id="f3624-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="f3624-143">Acceda a Microsoft Defender para endpoint con contexto de usuario</span><span class="sxs-lookup"><span data-stu-id="f3624-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
