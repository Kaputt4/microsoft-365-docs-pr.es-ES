---
title: Crear una aplicación para tener acceso a Microsoft 365 Defender sin un usuario
description: Aprende a crear una aplicación para tener acceso a Microsoft 365 Defender sin un usuario.
keywords: aplicación, acceso, api, crear
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
ms.openlocfilehash: 8ffa04492f42f7e1ee5f3fc7fadad963e6bb7fbe
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074795"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a><span data-ttu-id="d3965-104">Crear una aplicación para tener acceso a Microsoft 365 Defender sin un usuario</span><span class="sxs-lookup"><span data-stu-id="d3965-104">Create an app to access Microsoft 365 Defender without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d3965-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d3965-105">**Applies to:**</span></span>

- <span data-ttu-id="d3965-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3965-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3965-107">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="d3965-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d3965-108">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="d3965-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="d3965-109">En esta página se describe cómo crear una aplicación para obtener acceso mediante programación a Microsoft 365 Defender sin un usuario definido, por ejemplo, si está creando un demonio o un servicio en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="d3965-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender without a defined user—for example, if you're creating a daemon or background service.</span></span>

<span data-ttu-id="d3965-110">Si necesitas acceso mediante programación a Microsoft 365 Defender en nombre de uno o varios usuarios, consulta Crear una aplicación para tener acceso a las API de [Microsoft 365 Defender](api-create-app-user-context.md) en nombre de un usuario y Crear una aplicación con acceso de asociado a las API de [Microsoft 365 Defender](api-partner-access.md).</span><span class="sxs-lookup"><span data-stu-id="d3965-110">If you need programmatic access to Microsoft 365 Defender on behalf of one or more users, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md) and [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).</span></span> <span data-ttu-id="d3965-111">Si no está seguro del tipo de acceso que necesita, vea [Introducción.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="d3965-111">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="d3965-112">Microsoft 365 Defender expone gran parte de sus datos y acciones a través de un conjunto de API programáticas.</span><span class="sxs-lookup"><span data-stu-id="d3965-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="d3965-113">Estas API le ayudan a automatizar flujos de trabajo y a usar las capacidades de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d3965-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="d3965-114">Este acceso a la API requiere autenticación de OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="d3965-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="d3965-115">Para obtener más información, vea Flujo de código de autorización de [OAuth 2.0](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="d3965-115">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="d3965-116">En general, deberá seguir los siguientes pasos para usar estas API:</span><span class="sxs-lookup"><span data-stu-id="d3965-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="d3965-117">Crear una aplicación de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="d3965-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="d3965-118">Obtener un token de acceso con esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="d3965-118">Get an access token using this application.</span></span>
- <span data-ttu-id="d3965-119">Use el token para obtener acceso a la API de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d3965-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="d3965-120">En este artículo se explica cómo:</span><span class="sxs-lookup"><span data-stu-id="d3965-120">This article explains how to:</span></span>

- <span data-ttu-id="d3965-121">Crear una aplicación Azure AD</span><span class="sxs-lookup"><span data-stu-id="d3965-121">Create an Azure AD application</span></span>
- <span data-ttu-id="d3965-122">Obtener un token de acceso a Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3965-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="d3965-123">Valide el token.</span><span class="sxs-lookup"><span data-stu-id="d3965-123">Validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="d3965-124">Crear una aplicación</span><span class="sxs-lookup"><span data-stu-id="d3965-124">Create an app</span></span>

1. <span data-ttu-id="d3965-125">Inicie sesión en [Azure](https://portal.azure.com) como usuario con el rol **Administrador** global.</span><span class="sxs-lookup"><span data-stu-id="d3965-125">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="d3965-126">Vaya a **Azure Active Directory** App  >  **registrations** New  >  **registration**.</span><span class="sxs-lookup"><span data-stu-id="d3965-126">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Imagen de Microsoft Azure y navegación al registro de aplicaciones](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="d3965-128">En el formulario, elija un nombre para la aplicación y, a continuación, **seleccione Registrar**.</span><span class="sxs-lookup"><span data-stu-id="d3965-128">In the form, choose a name for your application, then select **Register**.</span></span>

4. <span data-ttu-id="d3965-129">En la página de la aplicación, seleccione **Permisos** de API Agregar API de permisos que mi organización usa  >    >   >, escriba Protección contra amenazas de Microsoft y seleccione **Protección contra** amenazas de Microsoft .</span><span class="sxs-lookup"><span data-stu-id="d3965-129">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="d3965-130">La aplicación ahora puede acceder a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d3965-130">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="d3965-131">*Microsoft Threat Protection* es un nombre antiguo de Microsoft 365 Defender y no aparecerá en la lista original.</span><span class="sxs-lookup"><span data-stu-id="d3965-131">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="d3965-132">Debe empezar a escribir su nombre en el cuadro de texto para verlo aparecer.</span><span class="sxs-lookup"><span data-stu-id="d3965-132">You need to start writing its name in the text box to see it appear.</span></span>

   ![Imagen de selección de permisos de API](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="d3965-134">Seleccione **Permisos de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="d3965-134">Select **Application permissions**.</span></span> <span data-ttu-id="d3965-135">Elija los permisos relevantes para su escenario (por ejemplo, **Incident.Read.All**) y, a continuación, **seleccione Agregar permisos**.</span><span class="sxs-lookup"><span data-stu-id="d3965-135">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![Imagen de acceso a api y selección de API](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="d3965-137">Debe seleccionar los permisos relevantes para su escenario.</span><span class="sxs-lookup"><span data-stu-id="d3965-137">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="d3965-138">*Leer todos los incidentes* es solo un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d3965-138">*Read all incidents* is just an example.</span></span> <span data-ttu-id="d3965-139">Para determinar qué permiso necesita, consulte la sección **Permisos** de la API a la que desea llamar.</span><span class="sxs-lookup"><span data-stu-id="d3965-139">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="d3965-140">Por ejemplo, para [ejecutar consultas avanzadas,](api-advanced-hunting.md)seleccione el permiso "Ejecutar consultas avanzadas"; para [aislar un dispositivo,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)seleccione el permiso "Aislar máquina".</span><span class="sxs-lookup"><span data-stu-id="d3965-140">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="d3965-141">Seleccione **Conceder consentimiento de administrador**.</span><span class="sxs-lookup"><span data-stu-id="d3965-141">Select **Grant admin consent**.</span></span> <span data-ttu-id="d3965-142">Cada vez que agregue un permiso, debe seleccionar Conceder consentimiento **de administrador** para que su efecto.</span><span class="sxs-lookup"><span data-stu-id="d3965-142">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Imagen de concesión de permisos](../../media/grant-consent.PNG)

7. <span data-ttu-id="d3965-144">Para agregar un secreto a la aplicación, seleccione Certificados **& secretos,** agregue una descripción al secreto y, a continuación, **seleccione Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d3965-144">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="d3965-145">Después de seleccionar **Agregar**, seleccione **copiar el valor secreto generado**.</span><span class="sxs-lookup"><span data-stu-id="d3965-145">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="d3965-146">No podrá recuperar el valor secreto después de salir.</span><span class="sxs-lookup"><span data-stu-id="d3965-146">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Imagen de crear clave de aplicación](../../media/webapp-create-key2.png)

8. <span data-ttu-id="d3965-148">Registre el identificador de la aplicación y el identificador de inquilino en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="d3965-148">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="d3965-149">Aparecen en Información **general en** la página de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d3965-149">They're listed under **Overview** on your application page.</span></span>

   ![Imagen del identificador de aplicación creado](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="d3965-151">Solo para partners de Microsoft [](./api-partner-access.md) **365 Defender:** siga estas instrucciones para el acceso de partners a través de las API de Microsoft 365 Defender, establezca la aplicación como multiinquilino, de modo que pueda estar disponible en todos los inquilinos una vez que reciba el consentimiento del administrador.</span><span class="sxs-lookup"><span data-stu-id="d3965-151">**For Microsoft 365 Defender Partners only**: [Follow these instructions](./api-partner-access.md) for partner access through the Microsoft 365 Defender APIs, set your app to be multi-tenant, so it can be available in all tenants once you receive admin consent.</span></span> <span data-ttu-id="d3965-152">El acceso de **partners es** necesario para aplicaciones de terceros, por ejemplo, si creas una aplicación destinada a ejecutarse en los inquilinos de varios clientes.</span><span class="sxs-lookup"><span data-stu-id="d3965-152">Partner access is **required** for third-party apps—for example, if you create an app that is intended to run in multiple customers' tenants.</span></span> <span data-ttu-id="d3965-153">No es **necesario si** crea un servicio que desea ejecutar solo en el espacio empresarial, como una aplicación para su propio uso que solo interactuará con sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="d3965-153">It is **not required** if you create a service that you want to run in your tenant only, such as an application for your own usage that will only interact with your own data.</span></span> <span data-ttu-id="d3965-154">Para establecer la aplicación como multiinquilino:</span><span class="sxs-lookup"><span data-stu-id="d3965-154">To set your app to be multi-tenant:</span></span>

    - <span data-ttu-id="d3965-155">Vaya a **Autenticación** y agregue https://portal.azure.com como uri de **redireccionamiento**.</span><span class="sxs-lookup"><span data-stu-id="d3965-155">Go to **Authentication**, and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="d3965-156">En la parte inferior de la página, en **Tipos** de cuenta admitidos, seleccione el consentimiento **cuentas** en cualquier aplicación de directorio de la organización para la aplicación multiinquilino.</span><span class="sxs-lookup"><span data-stu-id="d3965-156">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="d3965-157">Dado que la aplicación interactúa con Microsoft 365 Defender en nombre de los usuarios, debe aprobarse para todos los inquilinos en los que tenga previsto usarlo.</span><span class="sxs-lookup"><span data-stu-id="d3965-157">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

    <span data-ttu-id="d3965-158">El administrador global de Active Directory para cada inquilino debe seleccionar el vínculo de consentimiento y aprobar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d3965-158">The Active Directory global admin for each tenant needs to select the consent link and approve your app.</span></span>

    <span data-ttu-id="d3965-159">El vínculo de consentimiento tiene la siguiente estructura:</span><span class="sxs-lookup"><span data-stu-id="d3965-159">The consent link has the following structure:</span></span>

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="d3965-160">Los `00000000-0000-0000-0000-000000000000` dígitos deben reemplazarse por su id. de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d3965-160">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>  

<span data-ttu-id="d3965-161">**¡Listo!**</span><span class="sxs-lookup"><span data-stu-id="d3965-161">**Done!**</span></span> <span data-ttu-id="d3965-162">Ha registrado correctamente una aplicación.</span><span class="sxs-lookup"><span data-stu-id="d3965-162">You've successfully registered an application!</span></span> <span data-ttu-id="d3965-163">Vea ejemplos a continuación para la adquisición y validación de tokens.</span><span class="sxs-lookup"><span data-stu-id="d3965-163">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="d3965-164">Obtener un token de acceso</span><span class="sxs-lookup"><span data-stu-id="d3965-164">Get an access token</span></span>

<span data-ttu-id="d3965-165">Para obtener más información sobre los tokens de Azure Active Directory, consulte el [tutorial de Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="d3965-165">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3965-166">Aunque los ejemplos de esta sección le animan a pegar  valores secretos con fines de prueba, nunca debe codificar los secretos en una aplicación que se ejecute en producción.</span><span class="sxs-lookup"><span data-stu-id="d3965-166">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="d3965-167">Un tercero podría usar el secreto para obtener acceso a los recursos.</span><span class="sxs-lookup"><span data-stu-id="d3965-167">A third party could use your secret to access resources.</span></span> <span data-ttu-id="d3965-168">Puedes ayudar a proteger los secretos de la aplicación con [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span><span class="sxs-lookup"><span data-stu-id="d3965-168">You can help keep your app's secrets secure by using [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="d3965-169">Para obtener un ejemplo práctico de cómo proteger la aplicación, consulta Administrar secretos en las aplicaciones de servidor [con Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span><span class="sxs-lookup"><span data-stu-id="d3965-169">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="d3965-170">Obtener un token de acceso con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3965-170">Get an access token using PowerShell</span></span>

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$tenantId/oauth2/token"

$authBody = [Ordered] @{
    resource = $resourceAppIdUri
    client_id = $clientId
    client_secret = $appSecret
    grant_type = 'client_credentials'
}

$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token

Out-File -FilePath "./Latest-token.txt" -InputObject $token

return $token
```

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="d3965-171">Obtener un token de acceso con C\#</span><span class="sxs-lookup"><span data-stu-id="d3965-171">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="d3965-172">El código siguiente se ha probado con Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="d3965-172">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="d3965-173">Crear una nueva aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="d3965-173">Create a new console application.</span></span>

1. <span data-ttu-id="d3965-174">Instalar NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="d3965-174">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>

1. <span data-ttu-id="d3965-175">Agregue la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="d3965-175">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="d3965-176">Copie y pegue el siguiente código en la aplicación (no olvide actualizar las tres variables: `tenantId` , `clientId` , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="d3965-176">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

    ```C#
    string tenantId = ""; // Paste your directory (tenant) ID here
    string clientId = ""; // Paste your application (client) ID here
    string appSecret = ""; // Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(clientId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="d3965-177">Obtener un token de acceso con Python</span><span class="sxs-lookup"><span data-stu-id="d3965-177">Get an access token using Python</span></span>

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.security.microsoft.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : clientId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="d3965-178">Obtener un token de acceso con el rizo</span><span class="sxs-lookup"><span data-stu-id="d3965-178">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="d3965-179">El rizo está preinstalado en Windows 10, versiones 1803 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="d3965-179">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="d3965-180">Para otras versiones de Windows, descarga e instala la herramienta directamente desde el [sitio web oficial de curl](https://curl.haxx.se/windows/).</span><span class="sxs-lookup"><span data-stu-id="d3965-180">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="d3965-181">Abra un símbolo del sistema y establezca CLIENT_ID en el identificador de la aplicación de Azure.</span><span class="sxs-lookup"><span data-stu-id="d3965-181">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>

1. <span data-ttu-id="d3965-182">Establece CLIENT_SECRET en el secreto de la aplicación de Azure.</span><span class="sxs-lookup"><span data-stu-id="d3965-182">Set CLIENT_SECRET to your Azure application secret.</span></span>

1. <span data-ttu-id="d3965-183">Establece TENANT_ID el identificador de inquilino de Azure del cliente que desea usar la aplicación para tener acceso a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d3965-183">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft 365 Defender.</span></span>

1. <span data-ttu-id="d3965-184">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="d3965-184">Run the following command:</span></span>

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   <span data-ttu-id="d3965-185">Una respuesta correcta tendrá este aspecto:</span><span class="sxs-lookup"><span data-stu-id="d3965-185">A successful response will look like this:</span></span>

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a><span data-ttu-id="d3965-186">Validar el token</span><span class="sxs-lookup"><span data-stu-id="d3965-186">Validate the token</span></span>

1. <span data-ttu-id="d3965-187">Copie y pegue el token en el sitio web del validador de [tokens web JSON, JWT,](https://jwt.ms) para descodificarlo.</span><span class="sxs-lookup"><span data-stu-id="d3965-187">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>

1. <span data-ttu-id="d3965-188">Asegúrese de que la notificación *de roles* dentro del token descodificado contiene los permisos deseados.</span><span class="sxs-lookup"><span data-stu-id="d3965-188">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

   <span data-ttu-id="d3965-189">En la siguiente imagen, puedes ver un token descodificado adquirido desde una aplicación, con `Incidents.Read.All` , `Incidents.ReadWrite.All` y `AdvancedHunting.Read.All` permisos:</span><span class="sxs-lookup"><span data-stu-id="d3965-189">In the following image, you can see a decoded token acquired from an app, with `Incidents.Read.All`, `Incidents.ReadWrite.All`, and `AdvancedHunting.Read.All` permissions:</span></span>

   ![Imagen de validación de tokens](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="d3965-191">Usar el token para obtener acceso a la API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3965-191">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="d3965-192">Elige la API que quieras usar (incidentes o búsqueda avanzada).</span><span class="sxs-lookup"><span data-stu-id="d3965-192">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="d3965-193">Para obtener más información, vea [Supported Microsoft 365 Defender API](api-supported.md).</span><span class="sxs-lookup"><span data-stu-id="d3965-193">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>

2. <span data-ttu-id="d3965-194">En la solicitud http que está a punto de enviar, establezca el encabezado de autorización en , Bearer es el esquema de autorización `"Bearer" <token>` y el *token* es el token validado. </span><span class="sxs-lookup"><span data-stu-id="d3965-194">In the http request you are about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>

3. <span data-ttu-id="d3965-195">El token expirará en una hora.</span><span class="sxs-lookup"><span data-stu-id="d3965-195">The token will expire within one hour.</span></span> <span data-ttu-id="d3965-196">Puede enviar más de una solicitud durante este tiempo con el mismo token.</span><span class="sxs-lookup"><span data-stu-id="d3965-196">You can send more than one request during this time with the same token.</span></span>

<span data-ttu-id="d3965-197">En el ejemplo siguiente se muestra cómo enviar una solicitud para obtener una lista de incidentes **mediante C#**.</span><span class="sxs-lookup"><span data-stu-id="d3965-197">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="d3965-198">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="d3965-198">Related articles</span></span>

- [<span data-ttu-id="d3965-199">Introducción a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3965-199">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="d3965-200">Obtener acceso a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3965-200">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="d3965-201">Crear una aplicación "Hello world"</span><span class="sxs-lookup"><span data-stu-id="d3965-201">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="d3965-202">Crear una aplicación para tener acceso a las API de Microsoft 365 Defender en nombre de un usuario</span><span class="sxs-lookup"><span data-stu-id="d3965-202">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="d3965-203">Crear una aplicación con acceso de asociado multiinquilino a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3965-203">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="d3965-204">Más información sobre los límites de api y las licencias</span><span class="sxs-lookup"><span data-stu-id="d3965-204">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="d3965-205">Comprender códigos de error</span><span class="sxs-lookup"><span data-stu-id="d3965-205">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="d3965-206">Administrar secretos en las aplicaciones de servidor con Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="d3965-206">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="d3965-207">Autorización de OAuth 2.0 para el inicio de sesión de usuario y el acceso a la API</span><span class="sxs-lookup"><span data-stu-id="d3965-207">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)