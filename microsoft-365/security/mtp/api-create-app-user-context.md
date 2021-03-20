---
title: Crear una aplicación para tener acceso a las API de Microsoft 365 Defender en nombre de un usuario
description: Obtenga información sobre cómo obtener acceso a las API de Microsoft 365 Defender en nombre de un usuario.
keywords: acceso, en nombre del usuario, api, aplicación, usuario, token de acceso, token,
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
ms.openlocfilehash: 85c41c0bae9590e76801c18b2a33401874cc7cc3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903957"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a><span data-ttu-id="ed3ae-104">Crear una aplicación para tener acceso a las API de Microsoft 365 Defender en nombre de un usuario</span><span class="sxs-lookup"><span data-stu-id="ed3ae-104">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ed3ae-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ed3ae-105">**Applies to:**</span></span>

- <span data-ttu-id="ed3ae-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed3ae-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ed3ae-107">Parte de la información está relacionada con el producto predefinido que puede modificarse considerablemente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="ed3ae-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="ed3ae-109">En esta página se describe cómo crear una aplicación para obtener acceso mediante programación a Microsoft 365 Defender en nombre de un único usuario.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a single user.</span></span>

<span data-ttu-id="ed3ae-110">Si necesitas acceso mediante programación a Microsoft 365 Defender sin un usuario definido (por ejemplo, si estás escribiendo una aplicación en segundo plano o un demonio), consulta Crear una aplicación para tener acceso a [Microsoft 365 Defender](api-create-app-web.md)sin un usuario .</span><span class="sxs-lookup"><span data-stu-id="ed3ae-110">If you need programmatic access to Microsoft 365 Defender without a defined user (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="ed3ae-111">Si necesita proporcionar acceso a varios inquilinos (por ejemplo, si está prestando servicio a una organización grande o a un grupo de clientes), consulte Crear una aplicación con acceso de asociado a las API de [Microsoft 365 Defender.](api-partner-access.md) Si no está seguro del tipo de acceso que necesita, vea [Introducción.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="ed3ae-111">If you need to provide access for multiple tenants—for example, if you're serving a large organization or a group of customers—see [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="ed3ae-112">Microsoft 365 Defender expone gran parte de sus datos y acciones a través de un conjunto de API programáticas.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="ed3ae-113">Estas API le ayudan a automatizar flujos de trabajo y a usar las capacidades de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="ed3ae-114">Este acceso a la API requiere autenticación de OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="ed3ae-115">Para obtener más información, vea Flujo de código de autorización de [OAuth 2.0](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="ed3ae-115">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="ed3ae-116">En general, deberá seguir los siguientes pasos para usar estas API:</span><span class="sxs-lookup"><span data-stu-id="ed3ae-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="ed3ae-117">Crear una aplicación de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="ed3ae-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="ed3ae-118">Obtener un token de acceso con esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-118">Get an access token using this application.</span></span>
- <span data-ttu-id="ed3ae-119">Use el token para obtener acceso a la API de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="ed3ae-120">En este artículo se explica cómo:</span><span class="sxs-lookup"><span data-stu-id="ed3ae-120">This article explains how to:</span></span>

- <span data-ttu-id="ed3ae-121">Crear una aplicación de Azure AD</span><span class="sxs-lookup"><span data-stu-id="ed3ae-121">Create an Azure AD application</span></span>
- <span data-ttu-id="ed3ae-122">Obtener un token de acceso a Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed3ae-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="ed3ae-123">Validar el token</span><span class="sxs-lookup"><span data-stu-id="ed3ae-123">Validate the token</span></span>

> [!NOTE]
> <span data-ttu-id="ed3ae-124">Al obtener acceso a la API de Microsoft 365 Defender en nombre de un usuario, necesitará los permisos de aplicación y de usuario correctos.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-124">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct application permissions and user permissions.</span></span>

> [!TIP]
> <span data-ttu-id="ed3ae-125">Si tiene permiso para realizar una acción en el portal, tiene permiso para realizar la acción en la API.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-125">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="ed3ae-126">Crear una aplicación</span><span class="sxs-lookup"><span data-stu-id="ed3ae-126">Create an app</span></span>

1. <span data-ttu-id="ed3ae-127">Inicie sesión en [Azure](https://portal.azure.com) como usuario con el rol **Administrador** global.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-127">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="ed3ae-128">Vaya a **Azure Active Directory** App  >  **registrations** New  >  **registration**.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-128">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Imagen de Microsoft Azure y navegación al registro de aplicaciones](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="ed3ae-130">En el formulario, elija un nombre para la aplicación y escriba la siguiente información para el URI de redireccionamiento y, a continuación, **seleccione Registrar**.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-130">In the form, choose a name for your application and enter the following information for the redirect URI, then select **Register**.</span></span>

   ![Imagen de la ventana Crear aplicación](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="ed3ae-132">**Tipo de aplicación:** Cliente público</span><span class="sxs-lookup"><span data-stu-id="ed3ae-132">**Application type:** Public client</span></span>
   - <span data-ttu-id="ed3ae-133">**URI de redireccionamiento:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="ed3ae-133">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="ed3ae-134">En la página de la aplicación, seleccione **Permisos** de API Agregar API de permisos que mi organización usa  >    >   >, escriba Protección contra amenazas de Microsoft y seleccione **Protección contra** amenazas de Microsoft .</span><span class="sxs-lookup"><span data-stu-id="ed3ae-134">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="ed3ae-135">La aplicación ahora puede acceder a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-135">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="ed3ae-136">*Microsoft Threat Protection* es un nombre antiguo de Microsoft 365 Defender y no aparecerá en la lista original.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-136">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="ed3ae-137">Debe empezar a escribir su nombre en el cuadro de texto para verlo aparecer.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-137">You need to start writing its name in the text box to see it appear.</span></span>

   ![Imagen de selección de permisos de API](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="ed3ae-139">Elija **Permisos delegados**.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-139">Choose **Delegated permissions**.</span></span> <span data-ttu-id="ed3ae-140">Elija los permisos relevantes para su escenario (por **ejemplo, Incident.Read**) y, a continuación, **seleccione Agregar permisos**.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-140">Choose the relevant permissions for your scenario (for example **Incident.Read**), and then select **Add permissions**.</span></span>

   ![Imagen de acceso a api y selección de API](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > <span data-ttu-id="ed3ae-142">Debe seleccionar los permisos relevantes para su escenario.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-142">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="ed3ae-143">*Leer todos los incidentes* es solo un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-143">*Read all incidents* is just an example.</span></span> <span data-ttu-id="ed3ae-144">Para determinar qué permiso necesita, consulte la sección **Permisos** de la API a la que desea llamar.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-144">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="ed3ae-145">Por ejemplo, para [ejecutar consultas avanzadas,](api-advanced-hunting.md)seleccione el permiso "Ejecutar consultas avanzadas"; para [aislar un dispositivo,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)seleccione el permiso "Aislar máquina".</span><span class="sxs-lookup"><span data-stu-id="ed3ae-145">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

5. <span data-ttu-id="ed3ae-146">Seleccione **Conceder consentimiento de administrador**.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-146">Select **Grant admin consent**.</span></span> <span data-ttu-id="ed3ae-147">Cada vez que agregue un permiso, debe seleccionar Conceder consentimiento **de administrador** para que su efecto.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-147">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

   ![Imagen de concesión de permisos](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="ed3ae-149">Registre el identificador de la aplicación y el identificador de inquilino en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-149">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="ed3ae-150">Aparecen en Información **general en** la página de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-150">They're listed under **Overview** on your application page.</span></span>

   ![Imagen del identificador de aplicación creado](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a><span data-ttu-id="ed3ae-152">Obtener un token de acceso</span><span class="sxs-lookup"><span data-stu-id="ed3ae-152">Get an access token</span></span>

<span data-ttu-id="ed3ae-153">Para obtener más información sobre los tokens de Azure Active Directory, consulte el [tutorial de Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="ed3ae-153">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="ed3ae-154">Obtener un token de acceso con PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed3ae-154">Get an access token using PowerShell</span></span>

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

## <a name="validate-the-token"></a><span data-ttu-id="ed3ae-155">Validar el token</span><span class="sxs-lookup"><span data-stu-id="ed3ae-155">Validate the token</span></span>

1. <span data-ttu-id="ed3ae-156">Copie y pegue el token en [JWT](https://jwt.ms) para descodificarlo.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-156">Copy and paste the token into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="ed3ae-157">Asegúrese de que la notificación *de roles* dentro del token descodificado contiene los permisos deseados.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-157">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="ed3ae-158">En la siguiente imagen, puedes ver un token descodificado adquirido desde una aplicación, con ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` y ```AdvancedHunting.Read.All``` permisos:</span><span class="sxs-lookup"><span data-stu-id="ed3ae-158">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Imagen de validación de tokens](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="ed3ae-160">Usar el token para obtener acceso a la API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed3ae-160">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="ed3ae-161">Elige la API que quieras usar (incidentes o búsqueda avanzada).</span><span class="sxs-lookup"><span data-stu-id="ed3ae-161">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="ed3ae-162">Para obtener más información, vea [Supported Microsoft 365 Defender API](api-supported.md).</span><span class="sxs-lookup"><span data-stu-id="ed3ae-162">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="ed3ae-163">En la solicitud http que está a punto de enviar, establezca el encabezado de autorización en , Bearer es el esquema de autorización `"Bearer" <token>` y el *token* es el token validado. </span><span class="sxs-lookup"><span data-stu-id="ed3ae-163">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="ed3ae-164">El token expirará en una hora.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-164">The token will expire within one hour.</span></span> <span data-ttu-id="ed3ae-165">Puede enviar más de una solicitud durante este tiempo con el mismo token.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-165">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="ed3ae-166">En el ejemplo siguiente se muestra cómo enviar una solicitud para obtener una lista de incidentes **mediante C#**.</span><span class="sxs-lookup"><span data-stu-id="ed3ae-166">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="ed3ae-167">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="ed3ae-167">Related articles</span></span>

- [<span data-ttu-id="ed3ae-168">Introducción a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed3ae-168">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="ed3ae-169">Obtener acceso a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed3ae-169">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="ed3ae-170">Crear una aplicación "Hello world"</span><span class="sxs-lookup"><span data-stu-id="ed3ae-170">Create a 'Hello world' app</span></span>](api-hello-world.md)
- [<span data-ttu-id="ed3ae-171">Crear una aplicación para tener acceso a Microsoft 365 Defender sin un usuario</span><span class="sxs-lookup"><span data-stu-id="ed3ae-171">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="ed3ae-172">Crear una aplicación con acceso de asociado multiinquilino a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed3ae-172">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="ed3ae-173">Más información sobre los límites de api y las licencias</span><span class="sxs-lookup"><span data-stu-id="ed3ae-173">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="ed3ae-174">Comprender códigos de error</span><span class="sxs-lookup"><span data-stu-id="ed3ae-174">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="ed3ae-175">Autorización de OAuth 2.0 para el inicio de sesión de usuario y el acceso a la API</span><span class="sxs-lookup"><span data-stu-id="ed3ae-175">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)