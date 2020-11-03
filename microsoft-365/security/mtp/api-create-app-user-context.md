---
title: Acceso a las API de Microsoft 365 defender con en nombre de usuario
description: Obtenga información sobre cómo acceder a las API de Microsoft 365 defender con en nombre de usuario
keywords: acceso, en nombre de usuario, API, aplicación, usuario, token de acceso, token
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
ms.openlocfilehash: a72bc7648045e5cc37a1d899f9e15237ce29ed37
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847361"
---
# <a name="access-microsoft-365-defender-apis-on-behalf-of-user"></a><span data-ttu-id="0a78c-104">Acceso a las API de Microsoft 365 defender en nombre del usuario</span><span class="sxs-lookup"><span data-stu-id="0a78c-104">Access Microsoft 365 Defender APIs on behalf of user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0a78c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0a78c-105">**Applies to:**</span></span>
- <span data-ttu-id="0a78c-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="0a78c-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="0a78c-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="0a78c-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="0a78c-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="0a78c-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="0a78c-109">En esta página se describe cómo crear una aplicación para obtener acceso mediante programación a Microsoft 365 defender en nombre de un usuario.</span><span class="sxs-lookup"><span data-stu-id="0a78c-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a user.</span></span>

<span data-ttu-id="0a78c-110">Si necesita tener acceso mediante programación a Microsoft 365 defender sin un usuario, consulte [crear una aplicación para obtener acceso a microsoft 365 defender sin un usuario](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="0a78c-110">If you need programmatic access Microsoft 365 Defender without a user, refer to [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span>

<span data-ttu-id="0a78c-111">Si no está seguro de qué acceso necesita, lea el [acceso a las API de Microsoft 365 defender](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="0a78c-111">If you are not sure which access you need, read the [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="0a78c-112">Microsoft 365 defender expone gran parte de sus datos y acciones a través de un conjunto de API de programación.</span><span class="sxs-lookup"><span data-stu-id="0a78c-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="0a78c-113">Estas API le permitirán automatizar los flujos de trabajo y innovar en función de las capacidades de Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="0a78c-113">Those APIs will enable you to automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="0a78c-114">El acceso a la API requiere la autenticación OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="0a78c-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="0a78c-115">Para obtener más información, vea [flujo de código de autorización de OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="0a78c-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="0a78c-116">En general, deberá realizar los siguientes pasos para usar las API:</span><span class="sxs-lookup"><span data-stu-id="0a78c-116">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="0a78c-117">Crear una aplicación de AAD</span><span class="sxs-lookup"><span data-stu-id="0a78c-117">Create an AAD application</span></span>
- <span data-ttu-id="0a78c-118">Obtener un token de acceso con esta aplicación</span><span class="sxs-lookup"><span data-stu-id="0a78c-118">Get an access token using this application</span></span>
- <span data-ttu-id="0a78c-119">Usar el token para obtener acceso a la API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="0a78c-119">Use the token to access Microsoft 365 Defender API</span></span>

<span data-ttu-id="0a78c-120">En esta página se explica cómo crear una aplicación AAD, cómo obtener un token de acceso a Microsoft 365 defender y cómo validar el token.</span><span class="sxs-lookup"><span data-stu-id="0a78c-120">This page explains how to create an AAD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

>[!NOTE]
> <span data-ttu-id="0a78c-121">Al tener acceso a la API de Microsoft 365 defender en nombre de un usuario, necesitará el permiso de aplicación y el permiso de usuario correctos.</span><span class="sxs-lookup"><span data-stu-id="0a78c-121">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct Application permission and user permission.</span></span>


>[!TIP]
> <span data-ttu-id="0a78c-122">Si tiene permiso para realizar una acción en el portal, tiene permiso para realizar la acción en la API.</span><span class="sxs-lookup"><span data-stu-id="0a78c-122">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="0a78c-123">Crear una aplicación</span><span class="sxs-lookup"><span data-stu-id="0a78c-123">Create an app</span></span>

1. <span data-ttu-id="0a78c-124">Inicie sesión en [Azure](https://portal.azure.com) con un usuario que tenga un rol de **administrador global** .</span><span class="sxs-lookup"><span data-stu-id="0a78c-124">Log on to [Azure](https://portal.azure.com) with user that has **Global Administrator** role.</span></span>

2. <span data-ttu-id="0a78c-125">Navegue a registros de aplicaciones de **Azure Active Directory**  >  **App registrations**  >  **nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="0a78c-125">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Imagen de Microsoft Azure y navegación en el registro de la aplicación](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="0a78c-127">En el registro desde, especifique la siguiente información y, a continuación, haga clic en **registrar**.</span><span class="sxs-lookup"><span data-stu-id="0a78c-127">In the registration from, enter the following information then click **Register**.</span></span>

   ![Imagen de la ventana Crear aplicación](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="0a78c-129">**Name:** El nombre de la aplicación</span><span class="sxs-lookup"><span data-stu-id="0a78c-129">**Name:** Your application name</span></span>
   - <span data-ttu-id="0a78c-130">**Tipo de aplicación:** Cliente público</span><span class="sxs-lookup"><span data-stu-id="0a78c-130">**Application type:** Public client</span></span>
   - <span data-ttu-id="0a78c-131">**URI de redireccionamiento:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="0a78c-131">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="0a78c-132">Para habilitar la aplicación para que acceda a Microsoft 365 defender y asignarle permisos, en la página de la aplicación, seleccione **permisos de API**  >  **Agregar** API de permisos  >  **mi organización usa** >, escriba **Microsoft 365 defender** y, a continuación, seleccione **Microsoft 365 defender**.</span><span class="sxs-lookup"><span data-stu-id="0a78c-132">To enable your app to access Microsoft 365 Defender and assign it permissions, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft 365 Defender** , and then select **Microsoft 365 Defender**.</span></span>

    >[!NOTE]
    > <span data-ttu-id="0a78c-133">Microsoft 365 defender no aparece en la lista original.</span><span class="sxs-lookup"><span data-stu-id="0a78c-133">Microsoft 365 Defender does not appear in the original list.</span></span> <span data-ttu-id="0a78c-134">Debe empezar a escribir su nombre en el cuadro de texto para ver aparezca.</span><span class="sxs-lookup"><span data-stu-id="0a78c-134">You need to start writing its name in the text box to see it appear.</span></span>

      ![Imagen de acceso a API y selección de API](../../media/apis-in-my-org-tab.PNG)

    - <span data-ttu-id="0a78c-136">Elija **permisos Delegados** > elegir los permisos relevantes para su escenario, por ejemplo, **Incident. Read** y, a continuación, seleccione **Agregar permisos**.</span><span class="sxs-lookup"><span data-stu-id="0a78c-136">Choose **Delegated permissions** > Choose the relevant permissions for your scenario, e.g. **Incident.Read** , and then select **Add permissions**.</span></span>

      ![Imagen de acceso a API y selección de API](../../media/request-api-permissions-delegated.PNG)

     >[!IMPORTANT]
     ><span data-ttu-id="0a78c-138">Debe seleccionar los permisos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="0a78c-138">You need to select the relevant permissions.</span></span> 

    -  <span data-ttu-id="0a78c-139">Para determinar qué permiso necesita, consulte la sección **permisos** en la API que le interesa llamar.</span><span class="sxs-lookup"><span data-stu-id="0a78c-139">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

    - <span data-ttu-id="0a78c-140">Haga clic en **conceder consentimiento**</span><span class="sxs-lookup"><span data-stu-id="0a78c-140">Click **Grant consent**</span></span>

      >[!NOTE]
      ><span data-ttu-id="0a78c-141">Cada vez que agregue permisos, deberá hacer clic en **conceder consentimiento** para que el nuevo permiso surta efecto.</span><span class="sxs-lookup"><span data-stu-id="0a78c-141">Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

      ![Imagen de permisos de concesión](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="0a78c-143">Anote el identificador de la aplicación y el identificador de su espacio empresarial:</span><span class="sxs-lookup"><span data-stu-id="0a78c-143">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="0a78c-144">En la página de la aplicación, vaya a **información general** y copie lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0a78c-144">On your application page, go to **Overview** and copy the following:</span></span>

   ![Imagen del identificador de aplicación creado](../../media/app-and-tenant-ids.png)


## <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="0a78c-146">Obtener un token de acceso con PowerShell</span><span class="sxs-lookup"><span data-stu-id="0a78c-146">Get an access token using PowerShell</span></span>

```
#Install the ADAL.PS package if it's not installed.
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps }

$authority = "https://login.windows.net/{tenant-id}" # replace {tenant-id} with your tenant ID.

$clientId = "{application-id}" #replace {application-id} with your application ID.

$redirectUri = "{redirect-uri}" # replace {redirect-uri} with your application redirect URI.

$resourceUrl = "https://api.security.microsoft.com"

$response = Get-ADALToken -Resource $resourceUrl -ClientId $clientId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip
$response.AccessToken
```

## <a name="related-topics"></a><span data-ttu-id="0a78c-147">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0a78c-147">Related topics</span></span>
- [<span data-ttu-id="0a78c-148">Acceso a las API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="0a78c-148">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="0a78c-149">Acceso a Microsoft 365 defender con contexto de aplicación</span><span class="sxs-lookup"><span data-stu-id="0a78c-149">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
