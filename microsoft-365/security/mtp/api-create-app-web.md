---
title: Crear una aplicación para obtener acceso a Microsoft Threat Protection sin un usuario
description: Obtenga información sobre cómo crear una aplicación para obtener acceso a Microsoft Threat Protection sin un usuario
keywords: aplicación, Access, API, crear
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
ms.openlocfilehash: 57ba0eb77ccb855cc0c0224b5321f11809e21ae8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201424"
---
# <a name="create-an-app-to-access-microsoft-threat-protection-without-a-user"></a><span data-ttu-id="1fb74-104">Crear una aplicación para obtener acceso a Microsoft Threat Protection sin un usuario</span><span class="sxs-lookup"><span data-stu-id="1fb74-104">Create an app to access Microsoft Threat Protection without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1fb74-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="1fb74-105">**Applies to:**</span></span>
- <span data-ttu-id="1fb74-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="1fb74-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="1fb74-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="1fb74-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1fb74-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="1fb74-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="1fb74-109">En esta página se describe cómo crear una aplicación para obtener acceso mediante programación a Microsoft Threat Protection sin un usuario.</span><span class="sxs-lookup"><span data-stu-id="1fb74-109">This page describes how to create an application to get programmatic access to Microsoft Threat Protection without a user.</span></span> <span data-ttu-id="1fb74-110">Si necesita acceso mediante programación a la protección contra amenazas de Microsoft en nombre de un usuario, vea [Get Access With User context](api-create-app-user-context.md).</span><span class="sxs-lookup"><span data-stu-id="1fb74-110">If you need programmatic access to Microsoft Threat Protection on behalf of a user, see [Get access with user context](api-create-app-user-context.md).</span></span> <span data-ttu-id="1fb74-111">Si no está seguro de qué acceso necesita [, consulte Introducción](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="1fb74-111">If you are not sure which access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="1fb74-112">Microsoft Threat Protection expone gran parte de sus datos y acciones a través de un conjunto de API de programación.</span><span class="sxs-lookup"><span data-stu-id="1fb74-112">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="1fb74-113">Estas API le ayudarán a automatizar los flujos de trabajo y la innovación en función de las capacidades de Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="1fb74-113">Those APIs will help you automate work flows and innovate based on Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="1fb74-114">El acceso a la API requiere la autenticación OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="1fb74-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="1fb74-115">Para obtener más información, vea [flujo de código de autorización de OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="1fb74-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="1fb74-116">En general, deberá realizar los siguientes pasos para usar las API:</span><span class="sxs-lookup"><span data-stu-id="1fb74-116">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="1fb74-117">Cree una aplicación de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="1fb74-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="1fb74-118">Obtenga un token de acceso con esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="1fb74-118">Get an access token using this application.</span></span>
- <span data-ttu-id="1fb74-119">Use el token para acceder a la API de Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="1fb74-119">Use the token to access Microsoft Threat Protection API.</span></span>

<span data-ttu-id="1fb74-120">En este artículo se explica cómo crear una aplicación de Azure AD, obtener un token de acceso a la protección contra amenazas de Microsoft y validar el token.</span><span class="sxs-lookup"><span data-stu-id="1fb74-120">This article explains how to create an Azure AD application, get an access token to Microsoft Threat Protection, and validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="1fb74-121">Crear una aplicación</span><span class="sxs-lookup"><span data-stu-id="1fb74-121">Create an app</span></span>

1. <span data-ttu-id="1fb74-122">Inicie sesión en [Azure](https://portal.azure.com) con un usuario que tenga el rol de **administrador global** .</span><span class="sxs-lookup"><span data-stu-id="1fb74-122">Log on to [Azure](https://portal.azure.com) with a user that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="1fb74-123">Navegue a registros de aplicaciones de **Azure Active Directory**  >  **App registrations**  >  **nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="1fb74-123">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Imagen de Microsoft Azure y navegación en el registro de la aplicación](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="1fb74-125">En el formulario de registro, elija un nombre para la aplicación y, a continuación, seleccione **registrar**.</span><span class="sxs-lookup"><span data-stu-id="1fb74-125">In the registration form, choose a name for your application, and then select **Register**.</span></span>

4. <span data-ttu-id="1fb74-126">Para habilitar la aplicación para que acceda a la protección contra amenazas de Microsoft y asignarle permisos, en la página de la aplicación, seleccione **permisos de API**  >  **Agregar**API de permisos  >  **mi organización usa** >, escriba **protección contra amenazas de Microsoft**y, a continuación, seleccione protección contra amenazas de **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="1fb74-126">To enable your app to access Microsoft Threat Protection and assign it permissions, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and then select **Microsoft Threat Protection**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1fb74-127">La protección contra amenazas de Microsoft no aparece en la lista original.</span><span class="sxs-lookup"><span data-stu-id="1fb74-127">Microsoft Threat Protection does not appear in the original list.</span></span> <span data-ttu-id="1fb74-128">Debe empezar a escribir su nombre en el cuadro de texto para ver aparezca.</span><span class="sxs-lookup"><span data-stu-id="1fb74-128">You need to start writing its name in the text box to see it appear.</span></span>

   ![Imagen de acceso a API y selección de API](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="1fb74-130">Seleccione **permisos de aplicación** > elija los permisos relevantes para su escenario, por ejemplo, **Incident. Read. All**y, a continuación, seleccione **Agregar permisos**.</span><span class="sxs-lookup"><span data-stu-id="1fb74-130">Select **Application permissions** > Choose the relevant permissions for your scenario, e.g. **Incident.Read.All**, and then select **Add permissions**.</span></span>

   ![Imagen de acceso a API y selección de API](../../media/request-api-permissions.PNG)

    >[!NOTE]
    ><span data-ttu-id="1fb74-132">Debe seleccionar los permisos relevantes para su escenario, **' leer todos los incidentes '** es solo un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1fb74-132">You need to select the relevant permissions for your scenario, **'Read all incidents'** is just an example.</span></span> <span data-ttu-id="1fb74-133">Para determinar qué permiso necesita, consulte la sección **permisos** en la API que le interesa llamar.</span><span class="sxs-lookup"><span data-stu-id="1fb74-133">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="1fb74-134">Seleccione **conceder consentimiento**.</span><span class="sxs-lookup"><span data-stu-id="1fb74-134">Select **Grant consent**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="1fb74-135">Cada vez que agregue un permiso, debe seleccionar **conceder consentimiento** para que el nuevo permiso surta efecto.</span><span class="sxs-lookup"><span data-stu-id="1fb74-135">Every time you add a permission, you must select **Grant consent** for the new permission to take effect.</span></span>

    ![Imagen de permisos de concesión](../../media/grant-consent.PNG)

6. <span data-ttu-id="1fb74-137">Para agregar un secreto a la aplicación, seleccione **certificados & secretos**, agregue una descripción al secreto y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1fb74-137">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, and then select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1fb74-138">Después de seleccionar **Agregar**, seleccione **copiar el valor de secreto generado**.</span><span class="sxs-lookup"><span data-stu-id="1fb74-138">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="1fb74-139">No podrá recuperar este valor después de salir.</span><span class="sxs-lookup"><span data-stu-id="1fb74-139">You won't be able to retrieve this value after you leave.</span></span>

    ![Imagen de crear clave de aplicación](../../media/webapp-create-key2.png)

7. <span data-ttu-id="1fb74-141">Anote el identificador de la aplicación y el identificador de inquilino.</span><span class="sxs-lookup"><span data-stu-id="1fb74-141">Write down your application ID and your tenant ID.</span></span> <span data-ttu-id="1fb74-142">En la página de la aplicación, vaya a **información general** y copie lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="1fb74-142">On your application page, go to **Overview** and copy the following.</span></span>

   ![Imagen del identificador de aplicación creado](../../media/app-and-tenant-ids.png)

8. <span data-ttu-id="1fb74-144">**Solo para los asociados de Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="1fb74-144">**For Microsoft Threat Protection Partners only**.</span></span> <span data-ttu-id="1fb74-145">[Siga las instrucciones que se indican aquí](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access).</span><span class="sxs-lookup"><span data-stu-id="1fb74-145">[Follow the instructions here](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access).</span></span> <span data-ttu-id="1fb74-146">Configure la aplicación para que sea multiinquilino (disponible en todos los inquilinos tras el consentimiento).</span><span class="sxs-lookup"><span data-stu-id="1fb74-146">Set your app to be multi-tenanted (available in all tenants after consent).</span></span> <span data-ttu-id="1fb74-147">Esto es **necesario** para aplicaciones de terceros (por ejemplo, si crea una aplicación que se va a ejecutar en el inquilino de varios clientes).</span><span class="sxs-lookup"><span data-stu-id="1fb74-147">This is **required** for third-party apps (for example, if you create an app that is intended to run in multiple customers' tenant).</span></span> <span data-ttu-id="1fb74-148">Esto **no es necesario** si crea un servicio que solo desea ejecutar en su espacio empresarial (por ejemplo, si crea una aplicación para su propio uso que solo interactúe con sus propios datos).</span><span class="sxs-lookup"><span data-stu-id="1fb74-148">This is **not required** if you create a service that you want to run in your tenant only (for example, if you create an application for your own usage that will only interact with your own data).</span></span> <span data-ttu-id="1fb74-149">Para configurar la aplicación para que sea multiinquilino:</span><span class="sxs-lookup"><span data-stu-id="1fb74-149">To set your app to be multi-tenanted:</span></span>

    - <span data-ttu-id="1fb74-150">Vaya a **autenticación**y agregue https://portal.azure.com como el **URI de redireccionamiento**.</span><span class="sxs-lookup"><span data-stu-id="1fb74-150">Go to **Authentication**, and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="1fb74-151">En la parte inferior de la página, en **tipos de cuenta admitidos**, seleccione las **cuentas de cualquier** consentimiento de la aplicación del directorio de la organización para la aplicación multiempresa.</span><span class="sxs-lookup"><span data-stu-id="1fb74-151">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="1fb74-152">Necesita que su aplicación se apruebe en cada inquilino donde vaya a usarla.</span><span class="sxs-lookup"><span data-stu-id="1fb74-152">You need your application to be approved in each tenant where you intend to use it.</span></span> <span data-ttu-id="1fb74-153">Esto se debe a que la aplicación interactúa con la protección contra amenazas de Microsoft en nombre de su cliente.</span><span class="sxs-lookup"><span data-stu-id="1fb74-153">This is because your application interacts Microsoft Threat Protection on behalf of your customer.</span></span>

    <span data-ttu-id="1fb74-154">Usted (o su cliente si está escribiendo una aplicación de terceros) necesita seleccionar el vínculo de consentimiento y aprobar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1fb74-154">You (or your customer if you are writing a third-party app) need to select the consent link and approve your app.</span></span> <span data-ttu-id="1fb74-155">El consentimiento debe realizarse con un usuario que tenga privilegios administrativos en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1fb74-155">The consent should be done with a user who has administrative privileges in Active Directory.</span></span>

    <span data-ttu-id="1fb74-156">El vínculo de consentimiento se compone de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="1fb74-156">The consent link is formed as follows:</span></span> 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="1fb74-157">Donde 00000000-0000-0000-0000-000000000000 se reemplaza por el identificador de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1fb74-157">Where 00000000-0000-0000-0000-000000000000 is replaced with your application ID.</span></span>


<span data-ttu-id="1fb74-158">**Realiza!**</span><span class="sxs-lookup"><span data-stu-id="1fb74-158">**Done!**</span></span> <span data-ttu-id="1fb74-159">Se ha registrado correctamente una aplicación.</span><span class="sxs-lookup"><span data-stu-id="1fb74-159">You have successfully registered an application!</span></span> <span data-ttu-id="1fb74-160">Vea los siguientes ejemplos para la adquisición y validación de tokens.</span><span class="sxs-lookup"><span data-stu-id="1fb74-160">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="1fb74-161">Obtener un token de acceso</span><span class="sxs-lookup"><span data-stu-id="1fb74-161">Get an access token</span></span>

<span data-ttu-id="1fb74-162">Para obtener más información sobre los tokens de Azure AD, vea el [tutorial de Azure ad](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="1fb74-162">For more details on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="use-powershell"></a><span data-ttu-id="1fb74-163">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="1fb74-163">Use PowerShell</span></span>

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

### <a name="use-c"></a><span data-ttu-id="1fb74-164">Usar C#:</span><span class="sxs-lookup"><span data-stu-id="1fb74-164">Use C#:</span></span>

<span data-ttu-id="1fb74-165">El siguiente código se probó con Nuget Microsoft. IdentityModel. clients. ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="1fb74-165">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="1fb74-166">Cree una nueva aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="1fb74-166">Create a new console application.</span></span>
1. <span data-ttu-id="1fb74-167">Instale Nuget [Microsoft. IdentityModel. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="1fb74-167">Install Nuget [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="1fb74-168">Agregue lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1fb74-168">Add the following:</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="1fb74-169">Copie y pegue el código siguiente en la aplicación (no olvide actualizar las tres variables: ```tenantId, appId, appSecret``` ):</span><span class="sxs-lookup"><span data-stu-id="1fb74-169">Copy and paste the following code in your app (don't forget to update the three variables: ```tenantId, appId, appSecret```):</span></span>

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a><span data-ttu-id="1fb74-170">Usar Python</span><span class="sxs-lookup"><span data-stu-id="1fb74-170">Use Python</span></span> 

```
import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```
### <a name="use-curl"></a><span data-ttu-id="1fb74-171">Usar rizo</span><span class="sxs-lookup"><span data-stu-id="1fb74-171">Use Curl</span></span>

> [!NOTE]
> <span data-ttu-id="1fb74-172">El siguiente procedimiento presupone que doblez para Windows ya está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="1fb74-172">The following procedure assumes that Curl for Windows is already installed on your computer.</span></span>

1. <span data-ttu-id="1fb74-173">Abra un símbolo del sistema y establezca CLIENT_ID en el identificador de la aplicación de Azure.</span><span class="sxs-lookup"><span data-stu-id="1fb74-173">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="1fb74-174">Establezca CLIENT_SECRET en el secreto de la aplicación de Azure.</span><span class="sxs-lookup"><span data-stu-id="1fb74-174">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="1fb74-175">Establezca TENANT_ID el identificador de inquilino de Azure del cliente que quiera usar su aplicación para acceder a la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1fb74-175">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft Threat Protection.</span></span>
1. <span data-ttu-id="1fb74-176">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1fb74-176">Run the following command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="1fb74-177">Recibirá una respuesta con el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="1fb74-177">You will get an answer in the following form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="1fb74-178">Validar el token</span><span class="sxs-lookup"><span data-stu-id="1fb74-178">Validate the token</span></span>

<span data-ttu-id="1fb74-179">Asegúrese de que obtuvo el token correcto:</span><span class="sxs-lookup"><span data-stu-id="1fb74-179">Ensure that you got the correct token:</span></span>

1. <span data-ttu-id="1fb74-180">Copie y pegue el token que obtuvo en el paso anterior en [JWT](https://jwt.ms) para poder descodificarlo.</span><span class="sxs-lookup"><span data-stu-id="1fb74-180">Copy and paste the token you got in the previous step into [JWT](https://jwt.ms) in order to decode it.</span></span>
1. <span data-ttu-id="1fb74-181">Validar que obtiene una notificación de ' roles ' con los permisos deseados</span><span class="sxs-lookup"><span data-stu-id="1fb74-181">Validate that you get a 'roles' claim with the desired permissions</span></span>
1. <span data-ttu-id="1fb74-182">En la siguiente imagen, puede ver un token descodificado adquirido de una aplicación con ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` y ```AdvancedHunting.Read.All``` permisos:</span><span class="sxs-lookup"><span data-stu-id="1fb74-182">In the following image, you can see a decoded token acquired from an app with ```Incidents.Read.All```, ```Incidents.ReadWrite.All``` and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Imagen de validación de tokens](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-threat-protection-api"></a><span data-ttu-id="1fb74-184">Usar el token para acceder a la API de protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="1fb74-184">Use the token to access Microsoft Threat Protection API</span></span>

1. <span data-ttu-id="1fb74-185">Elija la API que desea usar.</span><span class="sxs-lookup"><span data-stu-id="1fb74-185">Choose the API you want to use.</span></span> <span data-ttu-id="1fb74-186">Para obtener más información, consulte [API admitidas de Microsoft Threat Protection](api-supported.md).</span><span class="sxs-lookup"><span data-stu-id="1fb74-186">For more information, see [Supported Microsoft Threat Protection APIs](api-supported.md).</span></span>

2. <span data-ttu-id="1fb74-187">Establezca el encabezado Authorization en la solicitud HTTP que envía a "Bearer {token}" (Bearer es el esquema de autorización).</span><span class="sxs-lookup"><span data-stu-id="1fb74-187">Set the authorization header in the http request you send to "Bearer {token}" (Bearer is the authorization scheme).</span></span>

3. <span data-ttu-id="1fb74-188">La fecha de expiración del token es una hora.</span><span class="sxs-lookup"><span data-stu-id="1fb74-188">The expiration time of the token is one hour.</span></span> <span data-ttu-id="1fb74-189">Puede enviar más de una solicitud con el mismo token.</span><span class="sxs-lookup"><span data-stu-id="1fb74-189">You can send more then one request with the same token.</span></span>

<span data-ttu-id="1fb74-190">A continuación, se muestra un ejemplo de cómo enviar una solicitud para obtener una lista de incidentes **con C#**:</span><span class="sxs-lookup"><span data-stu-id="1fb74-190">The following is an example of sending a request to get a list of incidents **using C#**:</span></span> 

```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="related-topics"></a><span data-ttu-id="1fb74-191">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1fb74-191">Related topics</span></span>
- [<span data-ttu-id="1fb74-192">Acceso a las API de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1fb74-192">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="1fb74-193">Acceso a Microsoft Threat Protection con contexto de aplicación</span><span class="sxs-lookup"><span data-stu-id="1fb74-193">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="1fb74-194">Acceso a Microsoft Threat Protection con contexto de usuario</span><span class="sxs-lookup"><span data-stu-id="1fb74-194">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
