---
title: Crear una aplicación para acceder a las API de Microsoft 365 defender en nombre de un usuario
description: Obtenga información sobre cómo acceder a las API de Microsoft 365 defender en nombre de un usuario.
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
ms.openlocfilehash: f1c0caea9ff7810f79026c789241a4f250ec5303
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719421"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a><span data-ttu-id="b8916-104">Crear una aplicación para acceder a las API de Microsoft 365 defender en nombre de un usuario</span><span class="sxs-lookup"><span data-stu-id="b8916-104">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b8916-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b8916-105">**Applies to:**</span></span>

- <span data-ttu-id="b8916-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8916-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8916-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="b8916-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b8916-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="b8916-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="b8916-109">En esta página se describe cómo crear una aplicación para obtener acceso mediante programación a Microsoft 365 defender en nombre de un único usuario.</span><span class="sxs-lookup"><span data-stu-id="b8916-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a single user.</span></span>

<span data-ttu-id="b8916-110">Si necesita acceso mediante programación a Microsoft 365 defender sin un usuario definido (por ejemplo, si está escribiendo una aplicación de fondo o un daemon), vea [crear una aplicación para obtener acceso a Microsoft 365 defender sin un usuario](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="b8916-110">If you need programmatic access to Microsoft 365 Defender without a defined user (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="b8916-111">Si necesita proporcionar acceso para varios inquilinos (por ejemplo, si está atendiendo a una organización de gran tamaño o a un grupo de clientes), vea [crear una aplicación con acceso de socio a las API de Microsoft 365 defender](api-partner-access.md). Si no está seguro de qué tipo de acceso necesita, consulte [Introducción](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="b8916-111">If you need to provide access for multiple tenants—for example, if you're serving a large organization or a group of customers—see [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="b8916-112">Microsoft 365 defender expone gran parte de sus datos y acciones a través de un conjunto de API de programación.</span><span class="sxs-lookup"><span data-stu-id="b8916-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="b8916-113">Estas API le ayudan a automatizar flujos de trabajo y a usar las capacidades de Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="b8916-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="b8916-114">Este acceso a la API requiere la autenticación OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="b8916-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="b8916-115">Para obtener más información, vea [flujo de código de autorización de OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="b8916-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="b8916-116">En general, deberá realizar los siguientes pasos para usar estas API:</span><span class="sxs-lookup"><span data-stu-id="b8916-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="b8916-117">Cree una aplicación de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b8916-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="b8916-118">Obtenga un token de acceso con esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="b8916-118">Get an access token using this application.</span></span>
- <span data-ttu-id="b8916-119">Use el token para obtener acceso a la API de Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="b8916-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="b8916-120">En este artículo se explica cómo:</span><span class="sxs-lookup"><span data-stu-id="b8916-120">This article explains how to:</span></span>

- <span data-ttu-id="b8916-121">Crear una aplicación de Azure AD</span><span class="sxs-lookup"><span data-stu-id="b8916-121">Create an Azure AD application</span></span>
- <span data-ttu-id="b8916-122">Obtener un token de acceso a Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="b8916-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="b8916-123">Validar el token</span><span class="sxs-lookup"><span data-stu-id="b8916-123">Validate the token</span></span>

> [!NOTE]
> <span data-ttu-id="b8916-124">Al tener acceso a la API de Microsoft 365 defender en nombre de un usuario, necesitará los permisos de usuario y permisos de usuario correctos.</span><span class="sxs-lookup"><span data-stu-id="b8916-124">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct application permissions and user permissions.</span></span>

> [!TIP]
> <span data-ttu-id="b8916-125">Si tiene permiso para realizar una acción en el portal, tiene permiso para realizar la acción en la API.</span><span class="sxs-lookup"><span data-stu-id="b8916-125">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="b8916-126">Crear una aplicación</span><span class="sxs-lookup"><span data-stu-id="b8916-126">Create an app</span></span>

1. <span data-ttu-id="b8916-127">Inicie sesión en [Azure](https://portal.azure.com) como un usuario con el rol de **administrador global** .</span><span class="sxs-lookup"><span data-stu-id="b8916-127">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="b8916-128">Navegue a registros de aplicaciones de **Azure Active Directory**  >    >  **nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="b8916-128">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Imagen de Microsoft Azure y navegación en el registro de la aplicación](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="b8916-130">En el formulario, elija un nombre para la aplicación y escriba la siguiente información para el URI de redireccionamiento y, a continuación, seleccione **registrar**.</span><span class="sxs-lookup"><span data-stu-id="b8916-130">In the form, choose a name for your application and enter the following information for the redirect URI, then select **Register**.</span></span>

   ![Imagen de la ventana Crear aplicación](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="b8916-132">**Tipo de aplicación:** Cliente público</span><span class="sxs-lookup"><span data-stu-id="b8916-132">**Application type:** Public client</span></span>
   - <span data-ttu-id="b8916-133">**URI de redireccionamiento:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="b8916-133">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="b8916-134">En la página de la aplicación, seleccione **permisos de API**  >  **Agregar** API de permisos  >  **mi organización usa** >, escriba **protección contra amenazas de Microsoft** y seleccione protección contra amenazas de **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="b8916-134">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="b8916-135">La aplicación ahora puede tener acceso a Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="b8916-135">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="b8916-136">*Microsoft Threat Protection* es un nombre antiguo para Microsoft 365 defender y no aparecerá en la lista original.</span><span class="sxs-lookup"><span data-stu-id="b8916-136">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="b8916-137">Debe empezar a escribir su nombre en el cuadro de texto para ver aparezca.</span><span class="sxs-lookup"><span data-stu-id="b8916-137">You need to start writing its name in the text box to see it appear.</span></span>

   ![Imagen de la selección de permisos de la API](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="b8916-139">Elija **permisos delegados**.</span><span class="sxs-lookup"><span data-stu-id="b8916-139">Choose **Delegated permissions**.</span></span> <span data-ttu-id="b8916-140">Elija los permisos relevantes para su escenario (por ejemplo, **Incident. Read**) y, a continuación, seleccione **Agregar permisos**.</span><span class="sxs-lookup"><span data-stu-id="b8916-140">Choose the relevant permissions for your scenario (for example **Incident.Read**), and then select **Add permissions**.</span></span>

   ![Imagen de acceso a API y selección de API](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > <span data-ttu-id="b8916-142">Debe seleccionar los permisos relevantes para su escenario.</span><span class="sxs-lookup"><span data-stu-id="b8916-142">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="b8916-143">*Leer todos los incidentes* es solo un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b8916-143">*Read all incidents* is just an example.</span></span> <span data-ttu-id="b8916-144">Para determinar qué permiso necesita, consulte la sección **permisos** en la API que quiera llamar.</span><span class="sxs-lookup"><span data-stu-id="b8916-144">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="b8916-145">Por ejemplo, para [ejecutar consultas avanzadas](api-advanced-hunting.md), seleccione el permiso "ejecutar consultas avanzadas"; para [aislar un dispositivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), seleccione el permiso "aislar equipo".</span><span class="sxs-lookup"><span data-stu-id="b8916-145">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

5. <span data-ttu-id="b8916-146">Seleccione **conceder consentimiento de administrador**.</span><span class="sxs-lookup"><span data-stu-id="b8916-146">Select **Grant admin consent**.</span></span> <span data-ttu-id="b8916-147">Cada vez que agregue un permiso, debe seleccionar **conceder consentimiento de administrador** para que surta efecto.</span><span class="sxs-lookup"><span data-stu-id="b8916-147">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

   ![Imagen de permisos de concesión](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="b8916-149">Registre el identificador de la aplicación y el identificador de inquilino en algún lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="b8916-149">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="b8916-150">Aparecen en **información general** en la página de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b8916-150">They're listed under **Overview** on your application page.</span></span>

   ![Imagen del identificador de aplicación creado](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a><span data-ttu-id="b8916-152">Obtener un token de acceso</span><span class="sxs-lookup"><span data-stu-id="b8916-152">Get an access token</span></span>

<span data-ttu-id="b8916-153">Para obtener más información sobre los tokens de Azure Active Directory, vea el [tutorial de Azure ad](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="b8916-153">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="b8916-154">Obtener un token de acceso con PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8916-154">Get an access token using PowerShell</span></span>

```PowerShell
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps } # Install the ADAL.PS package in case it's not already present

$tenantId = '' # Paste your directory (tenant) ID here.
$clientId = '' # Paste your application (client) ID here.
$redirectUri = '' # Paste your app's redirection URI

$authority = "https://login.windows.net/$tenantId"
$resourceUrl = 'https://api.security.microsoft.com'

$response = Get-ADALToken -Resource $resourceUrl -ClientId $cleintId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip

$response.AccessToken
```

## <a name="validate-the-token"></a><span data-ttu-id="b8916-155">Validar el token</span><span class="sxs-lookup"><span data-stu-id="b8916-155">Validate the token</span></span>

1. <span data-ttu-id="b8916-156">Copie y pegue el token en [JWT](https://jwt.ms) para descodificarlo.</span><span class="sxs-lookup"><span data-stu-id="b8916-156">Copy and paste the token into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="b8916-157">Asegúrese de que la notificación de *roles* dentro del token descodificado contenga los permisos deseados.</span><span class="sxs-lookup"><span data-stu-id="b8916-157">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="b8916-158">En la siguiente imagen, puede ver un token descodificado adquirido de una aplicación, con ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` y ```AdvancedHunting.Read.All``` permisos:</span><span class="sxs-lookup"><span data-stu-id="b8916-158">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Imagen de validación de tokens](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="b8916-160">Usar el token para obtener acceso a la API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="b8916-160">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="b8916-161">Elige la API que quieras usar (incidentes o búsqueda avanzada).</span><span class="sxs-lookup"><span data-stu-id="b8916-161">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="b8916-162">Para obtener más información, consulte las [API admitidas de Microsoft 365 defender](api-supported.md).</span><span class="sxs-lookup"><span data-stu-id="b8916-162">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="b8916-163">En la solicitud HTTP que va a enviar, establezca el encabezado Authorization en `"Bearer" <token>` , el *portador* es el esquema de autorización y el *token* es su token validado.</span><span class="sxs-lookup"><span data-stu-id="b8916-163">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="b8916-164">El token expirará en una hora.</span><span class="sxs-lookup"><span data-stu-id="b8916-164">The token will expire within one hour.</span></span> <span data-ttu-id="b8916-165">Puede enviar más de una solicitud durante este tiempo con el mismo token.</span><span class="sxs-lookup"><span data-stu-id="b8916-165">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="b8916-166">En el ejemplo siguiente se muestra cómo enviar una solicitud para obtener una lista de incidentes **con C#**.</span><span class="sxs-lookup"><span data-stu-id="b8916-166">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="b8916-167">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="b8916-167">Related articles</span></span>

- [<span data-ttu-id="b8916-168">Información general sobre las API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="b8916-168">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="b8916-169">Acceso a las API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="b8916-169">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="b8916-170">Crear una aplicación "Hola a todos"</span><span class="sxs-lookup"><span data-stu-id="b8916-170">Create a 'Hello world' app</span></span>](api-hello-world.md)
- [<span data-ttu-id="b8916-171">Crear una aplicación para obtener acceso a Microsoft 365 defender sin un usuario</span><span class="sxs-lookup"><span data-stu-id="b8916-171">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="b8916-172">Crear una aplicación con acceso de socio multiinquilino a las API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="b8916-172">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="b8916-173">Obtenga información sobre los límites de API y las licencias</span><span class="sxs-lookup"><span data-stu-id="b8916-173">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="b8916-174">Descripción de los códigos de error</span><span class="sxs-lookup"><span data-stu-id="b8916-174">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="b8916-175">OAuth 2,0 autorización para el inicio de sesión de usuario y el acceso a API</span><span class="sxs-lookup"><span data-stu-id="b8916-175">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
