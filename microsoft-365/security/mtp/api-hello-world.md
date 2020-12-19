---
title: Hola a todos sobre la API de REST de Microsoft 365 defender
description: Obtenga información sobre cómo crear una aplicación y usar un token para obtener acceso a las API de Microsoft 365 defender
keywords: App, token, Access, AAD, App, registro de aplicaciones, PowerShell, script, administrador global, permiso, Microsoft 365 defender
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
ms.openlocfilehash: b36a6acca5880a455a66b03b5355cdf1fb85b29b
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719315"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="eba12-104">Hola a todos sobre la API de REST de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="eba12-104">Hello World for Microsoft 365 Defender REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="eba12-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="eba12-105">**Applies to:**</span></span>

- <span data-ttu-id="eba12-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eba12-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eba12-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="eba12-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="eba12-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="eba12-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="eba12-109">Obtener incidentes con un script de PowerShell simple</span><span class="sxs-lookup"><span data-stu-id="eba12-109">Get incidents using a simple PowerShell script</span></span>

<span data-ttu-id="eba12-110">Este proyecto debe tardar de 5 a 10 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="eba12-110">It should take 5 to 10 minutes to complete this project.</span></span> <span data-ttu-id="eba12-111">Esta estimación de tiempo incluye el registro de la aplicación y la aplicación del código del script de ejemplo de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eba12-111">This time estimate includes registering the application, and applying the code from the PowerShell sample script.</span></span>

### <a name="register-an-app-in-azure-active-directory"></a><span data-ttu-id="eba12-112">Registrar una aplicación en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="eba12-112">Register an app in Azure Active Directory</span></span>

1. <span data-ttu-id="eba12-113">Inicie sesión en [Azure](https://portal.azure.com) como un usuario con el rol de **administrador global** .</span><span class="sxs-lookup"><span data-stu-id="eba12-113">Sign in to [Azure](https://portal.azure.com) as a user with the **Global administrator** role.</span></span>

2. <span data-ttu-id="eba12-114">Navegue a registros de aplicaciones de **Azure Active Directory**  >    >  **nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="eba12-114">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Imagen de Microsoft Azure y navegación en el registro de la aplicación](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="eba12-116">En el formulario de registro, elija un nombre para la aplicación y, después, seleccione **registrar**.</span><span class="sxs-lookup"><span data-stu-id="eba12-116">In the registration form, choose a name for your application, then select **Register**.</span></span> <span data-ttu-id="eba12-117">La selección de un URI de redireccionamiento es opcional.</span><span class="sxs-lookup"><span data-stu-id="eba12-117">Selecting a redirect URI is optional.</span></span> <span data-ttu-id="eba12-118">No necesitará uno para completar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="eba12-118">You won't need one to complete this example.</span></span>

4. <span data-ttu-id="eba12-119">En la página de la aplicación, seleccione **permisos de API**  >  **Agregar** API de permisos  >  **mi organización usa** >, escriba **protección contra amenazas de Microsoft** y seleccione protección contra amenazas de **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="eba12-119">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="eba12-120">La aplicación ahora puede tener acceso a Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="eba12-120">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="eba12-121">*Microsoft Threat Protection* es un nombre antiguo para Microsoft 365 defender y no aparecerá en la lista original.</span><span class="sxs-lookup"><span data-stu-id="eba12-121">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="eba12-122">Debe empezar a escribir su nombre en el cuadro de texto para ver aparezca.</span><span class="sxs-lookup"><span data-stu-id="eba12-122">You need to start writing its name in the text box to see it appear.</span></span>
   <span data-ttu-id="eba12-123">![Imagen de la selección de permisos de la API](../../media/apis-in-my-org-tab.PNG)</span><span class="sxs-lookup"><span data-stu-id="eba12-123">![Image of API permission selection](../../media/apis-in-my-org-tab.PNG)</span></span>

   - <span data-ttu-id="eba12-124">Elija **permisos de aplicación**  >  **Incident. Read. All** y seleccione **Agregar permisos**.</span><span class="sxs-lookup"><span data-stu-id="eba12-124">Choose **Application permissions** > **Incident.Read.All** and select **Add permissions**.</span></span>

   ![Imagen de acceso a API y selección de API](../../media/request-api-permissions.PNG)

5. <span data-ttu-id="eba12-126">Seleccione **conceder consentimiento de administrador**.</span><span class="sxs-lookup"><span data-stu-id="eba12-126">Select **Grant admin consent**.</span></span> <span data-ttu-id="eba12-127">Cada vez que agregue un permiso, debe seleccionar **conceder consentimiento de administrador** para que surta efecto.</span><span class="sxs-lookup"><span data-stu-id="eba12-127">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Imagen de permisos de concesión](../../media/grant-consent.PNG)

6. <span data-ttu-id="eba12-129">Agregue un secreto a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="eba12-129">Add a secret to the application.</span></span> <span data-ttu-id="eba12-130">Seleccione **certificados & secretos**, agregue una descripción al secreto y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="eba12-130">Select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="eba12-131">Después de seleccionar **Agregar**, seleccione **copiar el valor de secreto generado**.</span><span class="sxs-lookup"><span data-stu-id="eba12-131">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="eba12-132">No podrá recuperar el valor secreto después de salir.</span><span class="sxs-lookup"><span data-stu-id="eba12-132">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Imagen de crear clave de aplicación](../../media/webapp-create-key2.png)

7. <span data-ttu-id="eba12-134">Registre el identificador de la aplicación y el identificador de inquilino en algún lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="eba12-134">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="eba12-135">Aparecen en **información general** en la página de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="eba12-135">They're listed under **Overview** on your application page.</span></span>

   ![Imagen del identificador de aplicación creado](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a><span data-ttu-id="eba12-137">Obtener un token con la aplicación y usar el token para obtener acceso a la API</span><span class="sxs-lookup"><span data-stu-id="eba12-137">Get a token using the app and use the token to access the API</span></span>

<span data-ttu-id="eba12-138">Para obtener más información sobre los tokens de Azure Active Directory, vea el [tutorial de Azure ad](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="eba12-138">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eba12-139">Aunque el ejemplo de esta aplicación de demostración le anima a pegar el valor del secreto con fines de prueba, no debe **codificar secretos** en una aplicación que se ejecuta en producción.</span><span class="sxs-lookup"><span data-stu-id="eba12-139">Although the example in this demo app encourage you to paste in your secret value for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="eba12-140">Un tercero puede usar su secreto para obtener acceso a los recursos.</span><span class="sxs-lookup"><span data-stu-id="eba12-140">A third party could use your secret to access resources.</span></span> <span data-ttu-id="eba12-141">Puede ayudar a mantener la seguridad de los secretos de la aplicación mediante [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span><span class="sxs-lookup"><span data-stu-id="eba12-141">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="eba12-142">Para obtener un ejemplo práctico de cómo puede proteger su aplicación, consulte [Manage Secrets in your Server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span><span class="sxs-lookup"><span data-stu-id="eba12-142">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

1. <span data-ttu-id="eba12-143">Copie el script siguiente y péguelo en su editor de texto preferido.</span><span class="sxs-lookup"><span data-stu-id="eba12-143">Copy the script below and paste it into your favorite text editor.</span></span> <span data-ttu-id="eba12-144">Guardar como **Get-Token.ps1**.</span><span class="sxs-lookup"><span data-stu-id="eba12-144">Save as **Get-Token.ps1**.</span></span> <span data-ttu-id="eba12-145">También puede ejecutar el código tal y como está en PowerShell ISE, pero debe guardarlo, ya que tendremos que volver a ejecutarlo cuando use el script de recuperación de incidentes de la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="eba12-145">You can also run the code as-is in PowerShell ISE, but you should save it, because we'll need to run it again when we use the incident-fetching script in the next section.</span></span>

    <span data-ttu-id="eba12-146">Este script generará un token y lo guardará en la carpeta de trabajo con el nombre, *Latest-token.txt*.</span><span class="sxs-lookup"><span data-stu-id="eba12-146">This script will generate a token and save it in the working folder under the name, *Latest-token.txt*.</span></span>

    ```PowerShell
    # This script gets the app context token and saves it to a file named "Latest-token.txt" under the current directory.
    # Paste in your tenant ID, client ID and app secret (App key).

    $tenantId = '' # Paste your directory (tenant) ID here
    $clientId = '' # Paste your application (client) ID here
    $appSecret = '' # # Paste your own app secret here to test, then store it in a safe place!

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

#### <a name="validate-the-token"></a><span data-ttu-id="eba12-147">Validar el token</span><span class="sxs-lookup"><span data-stu-id="eba12-147">Validate the token</span></span>

1. <span data-ttu-id="eba12-148">Copie y pegue el token que recibió en [JWT](https://jwt.ms) para descodificarlo.</span><span class="sxs-lookup"><span data-stu-id="eba12-148">Copy and paste the token you received into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="eba12-149">Las siglas de *JWT* para *token web JSON*.</span><span class="sxs-lookup"><span data-stu-id="eba12-149">*JWT* stands for *JSON Web Token*.</span></span> <span data-ttu-id="eba12-150">El token descodificado contendrá varios elementos o notificaciones con formato JSON.</span><span class="sxs-lookup"><span data-stu-id="eba12-150">The decoded token will contain a number of JSON-formatted items or claims.</span></span> <span data-ttu-id="eba12-151">Asegúrese de que la notificación de *roles* dentro del token descodificado contenga los permisos deseados.</span><span class="sxs-lookup"><span data-stu-id="eba12-151">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

    <span data-ttu-id="eba12-152">En la siguiente imagen, puede ver un token descodificado adquirido de una aplicación, con ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` y ```AdvancedHunting.Read.All``` permisos:</span><span class="sxs-lookup"><span data-stu-id="eba12-152">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

    ![Image jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a><span data-ttu-id="eba12-154">Obtener una lista de incidentes recientes</span><span class="sxs-lookup"><span data-stu-id="eba12-154">Get a list of recent incidents</span></span>

<span data-ttu-id="eba12-155">El siguiente script usará **Get-Token.ps1** para obtener acceso a la API.</span><span class="sxs-lookup"><span data-stu-id="eba12-155">The script below will use **Get-Token.ps1** to access the API.</span></span> <span data-ttu-id="eba12-156">A continuación, recupera una lista de los incidentes que se actualizaron por última vez en los últimos 48 horas y guarda la lista como un archivo JSON.</span><span class="sxs-lookup"><span data-stu-id="eba12-156">It then retrieves a list of incidents that were last updated within the past 48 hours, and saves the list as a JSON file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eba12-157">Guarde este script en la misma carpeta que guardó **Get-Token.ps1**.</span><span class="sxs-lookup"><span data-stu-id="eba12-157">Save this script in the same folder you saved **Get-Token.ps1**.</span></span>

```PowerShell
# This script returns incidents last updated within the past 48 hours.

$token = ./Get-Token.ps1

# Get incidents from the past 48 hours.
# The script may appear to fail if you don't have any incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# This URL contains the type of query and the time filter we created above.
# Note that `$filter` does not refer to a local variable in our script --
# it's actually an OData operator and part of the API's syntax.
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the webrequest headers
$headers = @{
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the request and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results.
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get a string containing the execution time. We concatenate that string to the name 
# of the output file to avoid overwriting the file on consecutive runs of the script.
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"

Out-File -FilePath $outputJsonPath -InputObject $incidents
```

<span data-ttu-id="eba12-158">Ya ha terminado.</span><span class="sxs-lookup"><span data-stu-id="eba12-158">You're all done!</span></span> <span data-ttu-id="eba12-159">Ha realizado correctamente:</span><span class="sxs-lookup"><span data-stu-id="eba12-159">You've successfully:</span></span>

- <span data-ttu-id="eba12-160">Se ha creado y registrado una aplicación.</span><span class="sxs-lookup"><span data-stu-id="eba12-160">Created and registered an application.</span></span>
- <span data-ttu-id="eba12-161">Permiso concedido para que la aplicación Lea las alertas.</span><span class="sxs-lookup"><span data-stu-id="eba12-161">Granted permission for that application to read alerts.</span></span>
- <span data-ttu-id="eba12-162">Conectado a la API.</span><span class="sxs-lookup"><span data-stu-id="eba12-162">Connected to the API.</span></span>
- <span data-ttu-id="eba12-163">Se usó un script de PowerShell para devolver los incidentes actualizados en las últimas 48 horas.</span><span class="sxs-lookup"><span data-stu-id="eba12-163">Used a PowerShell script to return incidents updated in the past 48 hours.</span></span>

## <a name="related-articles"></a><span data-ttu-id="eba12-164">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="eba12-164">Related articles</span></span>

- [<span data-ttu-id="eba12-165">Información general sobre las API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="eba12-165">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="eba12-166">Acceso a las API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="eba12-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="eba12-167">Crear una aplicación para obtener acceso a Microsoft 365 defender sin un usuario</span><span class="sxs-lookup"><span data-stu-id="eba12-167">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="eba12-168">Crear una aplicación para acceder a las API de Microsoft 365 defender en nombre de un usuario</span><span class="sxs-lookup"><span data-stu-id="eba12-168">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="eba12-169">Crear una aplicación con acceso de socio multiinquilino a las API de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="eba12-169">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="eba12-170">Administrar secretos en las aplicaciones de servidor con Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="eba12-170">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="eba12-171">OAuth 2,0 autorización para el inicio de sesión de usuario y el acceso a API</span><span class="sxs-lookup"><span data-stu-id="eba12-171">OAuth 2.0 Authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
