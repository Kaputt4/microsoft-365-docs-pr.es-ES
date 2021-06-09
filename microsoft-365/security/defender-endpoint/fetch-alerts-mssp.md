---
title: Capturar alertas desde el inquilino del cliente de MSSP
description: Obtenga información sobre cómo capturar alertas de un inquilino de cliente
keywords: proveedor de servicios de seguridad administrados, mssp, configuración, integración
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 456507533265bc085adc1008f3264e123569a6ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770774"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a><span data-ttu-id="41c82-104">Capturar alertas desde el inquilino del cliente de MSSP</span><span class="sxs-lookup"><span data-stu-id="41c82-104">Fetch alerts from MSSP customer tenant</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="41c82-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="41c82-105">**Applies to:**</span></span>
- [<span data-ttu-id="41c82-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="41c82-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="41c82-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="41c82-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="41c82-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="41c82-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!NOTE]
><span data-ttu-id="41c82-109">El MSSP toma esta acción.</span><span class="sxs-lookup"><span data-stu-id="41c82-109">This action is taken by the MSSP.</span></span>


<span data-ttu-id="41c82-110">Hay dos formas de capturar alertas:</span><span class="sxs-lookup"><span data-stu-id="41c82-110">There are two ways you can fetch alerts:</span></span>
- <span data-ttu-id="41c82-111">Uso del método SIEM</span><span class="sxs-lookup"><span data-stu-id="41c82-111">Using the SIEM method</span></span>
- <span data-ttu-id="41c82-112">Uso de API</span><span class="sxs-lookup"><span data-stu-id="41c82-112">Using APIs</span></span>

## <a name="fetch-alerts-into-your-siem"></a><span data-ttu-id="41c82-113">Capturar alertas en siem</span><span class="sxs-lookup"><span data-stu-id="41c82-113">Fetch alerts into your SIEM</span></span>

<span data-ttu-id="41c82-114">Para capturar alertas en el sistema SIEM, deberá seguir los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="41c82-114">To fetch alerts into your SIEM system, you'll need to take the following steps:</span></span>

<span data-ttu-id="41c82-115">Paso 1: Crear una aplicación de terceros</span><span class="sxs-lookup"><span data-stu-id="41c82-115">Step 1: Create a third-party application</span></span>

<span data-ttu-id="41c82-116">Paso 2: Obtener tokens de acceso y actualización desde el inquilino del cliente</span><span class="sxs-lookup"><span data-stu-id="41c82-116">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
 
<span data-ttu-id="41c82-117">Paso 3: permitir que la aplicación se Centro de seguridad de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="41c82-117">Step 3: allow your application on Microsoft Defender Security Center</span></span>
 
### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a><span data-ttu-id="41c82-118">Paso 1: Crear una aplicación en Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="41c82-118">Step 1: Create an application in Azure Active Directory (Azure AD)</span></span>
 
<span data-ttu-id="41c82-119">Deberá crear una aplicación y concederle permisos para capturar alertas desde el inquilino de Microsoft Defender para endpoint del cliente.</span><span class="sxs-lookup"><span data-stu-id="41c82-119">You'll need to create an application and grant it permissions to fetch alerts from your customer's Microsoft Defender for Endpoint tenant.</span></span>

1. <span data-ttu-id="41c82-120">Inicie sesión en [Azure AD Portal](https://aad.portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="41c82-120">Sign in to the [Azure AD portal](https://aad.portal.azure.com/).</span></span>

2. <span data-ttu-id="41c82-121">Seleccione **Azure Active Directory**  >  **registros de la aplicación**.</span><span class="sxs-lookup"><span data-stu-id="41c82-121">Select **Azure Active Directory** > **App registrations**.</span></span>
 
3. <span data-ttu-id="41c82-122">Haga clic **en Nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="41c82-122">Click **New registration**.</span></span>

4. <span data-ttu-id="41c82-123">Especifique los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="41c82-123">Specify the following values:</span></span>

    - <span data-ttu-id="41c82-124">Nombre: \<Tenant_name\> Siem MSSP Connector (reemplace Tenant_name por el nombre para mostrar del espacio empresarial)</span><span class="sxs-lookup"><span data-stu-id="41c82-124">Name: \<Tenant_name\> SIEM MSSP Connector (replace Tenant_name with the tenant display name)</span></span>
 
    - <span data-ttu-id="41c82-125">Tipos de cuentas compatibles: solo cuenta en este directorio de la organización</span><span class="sxs-lookup"><span data-stu-id="41c82-125">Supported account types: Account in this organizational directory only</span></span> 
    - <span data-ttu-id="41c82-126">URI de redireccionamiento: seleccione Web y escriba `https://<domain_name>/SiemMsspConnector` (reemplace <domain_name> por el nombre del inquilino)</span><span class="sxs-lookup"><span data-stu-id="41c82-126">Redirect URI: Select Web and type `https://<domain_name>/SiemMsspConnector`(replace <domain_name> with the tenant name)</span></span>

5. <span data-ttu-id="41c82-127">Haga clic en **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="41c82-127">Click **Register**.</span></span> <span data-ttu-id="41c82-128">La aplicación se muestra en la lista de aplicaciones de su propiedad.</span><span class="sxs-lookup"><span data-stu-id="41c82-128">The application is displayed in the list of applications you own.</span></span>

6. <span data-ttu-id="41c82-129">Seleccione la aplicación y, a continuación, haga clic **en Información general**.</span><span class="sxs-lookup"><span data-stu-id="41c82-129">Select the application, then click **Overview**.</span></span>

7. <span data-ttu-id="41c82-130">Copie el valor del campo **Id. de aplicación (cliente)** en un lugar seguro, lo necesitará en el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="41c82-130">Copy the value from the **Application (client) ID** field to a safe place, you will need this in the next step.</span></span>

8. <span data-ttu-id="41c82-131">Seleccione **Certificados & secretos** en el nuevo panel de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="41c82-131">Select **Certificate & secrets** in the new application panel.</span></span>

9. <span data-ttu-id="41c82-132">Haga **clic en Nuevo secreto de cliente**.</span><span class="sxs-lookup"><span data-stu-id="41c82-132">Click **New client secret**.</span></span>

    - <span data-ttu-id="41c82-133">Descripción: escriba una descripción para la clave.</span><span class="sxs-lookup"><span data-stu-id="41c82-133">Description: Enter a description for the key.</span></span>
    - <span data-ttu-id="41c82-134">Expira: seleccionar **en 1 año**</span><span class="sxs-lookup"><span data-stu-id="41c82-134">Expires: Select **In 1 year**</span></span>

 
10. <span data-ttu-id="41c82-135">Haga **clic en** Agregar , copie el valor del secreto de cliente en un lugar seguro, lo necesitará en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="41c82-135">Click **Add**, copy the value of the client secret to a safe place, you will need this in the next step.</span></span>
 

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a><span data-ttu-id="41c82-136">Paso 2: Obtener tokens de acceso y actualización desde el inquilino del cliente</span><span class="sxs-lookup"><span data-stu-id="41c82-136">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
<span data-ttu-id="41c82-137">Esta sección le guía sobre cómo usar un script de PowerShell para obtener los tokens del inquilino del cliente.</span><span class="sxs-lookup"><span data-stu-id="41c82-137">This section guides you on how to use a PowerShell script to get the tokens from your customer's tenant.</span></span> <span data-ttu-id="41c82-138">Este script usa la aplicación del paso anterior para obtener los tokens de acceso y actualización mediante el código de autorización de OAuth Flow.</span><span class="sxs-lookup"><span data-stu-id="41c82-138">This script uses the application from the previous step to get the access and refresh tokens using the OAuth Authorization Code Flow.</span></span>

<span data-ttu-id="41c82-139">Después de proporcionar sus credenciales, deberá conceder el consentimiento a la aplicación para que la aplicación se aprovisione en el inquilino del cliente.</span><span class="sxs-lookup"><span data-stu-id="41c82-139">After providing your credentials, you'll need to grant consent to the application so that the application is provisioned in the customer's tenant.</span></span>


1. <span data-ttu-id="41c82-140">Cree una nueva carpeta y así mismo: `MsspTokensAcquisition` .</span><span class="sxs-lookup"><span data-stu-id="41c82-140">Create a new folder and name it: `MsspTokensAcquisition`.</span></span>

2. <span data-ttu-id="41c82-141">Descargue el [módulo LoginBrowser.psm1](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) y guárdelo en la `MsspTokensAcquisition` carpeta.</span><span class="sxs-lookup"><span data-stu-id="41c82-141">Download the [LoginBrowser.psm1 module](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) and save it in the `MsspTokensAcquisition` folder.</span></span>

    >[!NOTE]
    ><span data-ttu-id="41c82-142">En la línea 30, reemplace `authorzationUrl` por `authorizationUrl` .</span><span class="sxs-lookup"><span data-stu-id="41c82-142">In line 30, replace `authorzationUrl` with `authorizationUrl`.</span></span>

3. <span data-ttu-id="41c82-143">Cree un archivo con el siguiente contenido y guárdelo con el nombre `MsspTokensAcquisition.ps1` de la carpeta:</span><span class="sxs-lookup"><span data-stu-id="41c82-143">Create a file with the following content and save it with the name `MsspTokensAcquisition.ps1` in the folder:</span></span>
    ```
    param (
        [Parameter(Mandatory=$true)][string]$clientId,
        [Parameter(Mandatory=$true)][string]$secret,
        [Parameter(Mandatory=$true)][string]$tenantId
    )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

    # Load our Login Browser Function
    Import-Module .\LoginBrowser.psm1

    # Configuration parameters
    $login = "https://login.microsoftonline.com"
    $redirectUri = "https://SiemMsspConnector"
    $resourceId = "https://graph.windows.net"

    Write-Host 'Prompt the user for his credentials, to get an authorization code'
    $authorizationUrl = ("{0}/{1}/oauth2/authorize?prompt=select_account&response_type=code&client_id={2}&redirect_uri={3}&resource={4}" -f
                        $login, $tenantId, $clientId, $redirectUri, $resourceId)
    Write-Host "authorzationUrl: $authorizationUrl"

    # Fake a proper endpoint for the Redirect URI
    $code = LoginBrowser $authorizationUrl $redirectUri

    # Acquire token using the authorization code

    $Body = @{
        grant_type = 'authorization_code'
        client_id = $clientId
        code = $code
        redirect_uri = $redirectUri
        resource = $resourceId
        client_secret = $secret
    }

    $tokenEndpoint = "$login/$tenantId/oauth2/token?"
    $Response = Invoke-RestMethod -Method Post -Uri $tokenEndpoint -Body $Body
    $token = $Response.access_token
    $refreshToken= $Response.refresh_token

    Write-Host " -----------------------------------  TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " -----------------------------------  REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken 
    ```
4. <span data-ttu-id="41c82-144">Abra un símbolo del sistema de PowerShell con privilegios elevados en la `MsspTokensAcquisition` carpeta.</span><span class="sxs-lookup"><span data-stu-id="41c82-144">Open an elevated PowerShell command prompt in the `MsspTokensAcquisition` folder.</span></span>

5. <span data-ttu-id="41c82-145">Ejecute el siguiente comando: `Set-ExecutionPolicy -ExecutionPolicy Bypass`</span><span class="sxs-lookup"><span data-stu-id="41c82-145">Run the following command: `Set-ExecutionPolicy -ExecutionPolicy Bypass`</span></span>

6. <span data-ttu-id="41c82-146">Escriba los siguientes comandos: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span><span class="sxs-lookup"><span data-stu-id="41c82-146">Enter the following commands: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span></span>
 
    - <span data-ttu-id="41c82-147">Reemplace \<client_id\> por el identificador de aplicación **(cliente)** que obtuvo del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="41c82-147">Replace \<client_id\> with the **Application (client) ID** you got from the previous step.</span></span>
    - <span data-ttu-id="41c82-148">Reemplace \<app_key\> por el secreto de **cliente** que creó a partir del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="41c82-148">Replace \<app_key\> with the **Client Secret** you created from the previous step.</span></span>
    - <span data-ttu-id="41c82-149">Reemplace \<customer_tenant_id\> por el identificador de inquilino del **cliente**.</span><span class="sxs-lookup"><span data-stu-id="41c82-149">Replace \<customer_tenant_id\> with your customer's **Tenant ID**.</span></span> 
 

7. <span data-ttu-id="41c82-150">Se le pedirá que proporcione sus credenciales y consentimiento.</span><span class="sxs-lookup"><span data-stu-id="41c82-150">You'll be asked to provide your credentials and consent.</span></span> <span data-ttu-id="41c82-151">Ignore el redireccionamiento de página.</span><span class="sxs-lookup"><span data-stu-id="41c82-151">Ignore the page redirect.</span></span>

8. <span data-ttu-id="41c82-152">En la ventana de PowerShell, recibirá un token de acceso y un token de actualización.</span><span class="sxs-lookup"><span data-stu-id="41c82-152">In the PowerShell window, you'll receive an access token and a refresh token.</span></span> <span data-ttu-id="41c82-153">Guarde el token de actualización para configurar el conector SIEM.</span><span class="sxs-lookup"><span data-stu-id="41c82-153">Save the refresh token to configure your SIEM connector.</span></span> 
 
### <a name="step-3-allow-your-application-on-microsoft-defender-security-center"></a><span data-ttu-id="41c82-154">Paso 3: Permitir que la aplicación se Centro de seguridad de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="41c82-154">Step 3: Allow your application on Microsoft Defender Security Center</span></span>
<span data-ttu-id="41c82-155">Tendrás que permitir la aplicación que creaste en Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="41c82-155">You'll need to allow the application you created in Microsoft Defender Security Center.</span></span>
 
<span data-ttu-id="41c82-156">Deberá tener permiso Administrar configuración **del sistema del portal** para permitir la aplicación.</span><span class="sxs-lookup"><span data-stu-id="41c82-156">You'll need to have **Manage portal system settings** permission to allow the application.</span></span> <span data-ttu-id="41c82-157">De lo contrario, tendrá que solicitar al cliente que le permita la aplicación.</span><span class="sxs-lookup"><span data-stu-id="41c82-157">Otherwise, you'll need to request your customer to allow the application for you.</span></span>

1. <span data-ttu-id="41c82-158">Vaya a `https://securitycenter.windows.com?tid=<customer_tenant_id>` (reemplace \<customer_tenant_id\> por el identificador de inquilino del cliente.</span><span class="sxs-lookup"><span data-stu-id="41c82-158">Go to `https://securitycenter.windows.com?tid=<customer_tenant_id>` (replace \<customer_tenant_id\> with the customer's tenant ID.</span></span>

2. <span data-ttu-id="41c82-159">Haga **clic Configuración**  >  **siem**.</span><span class="sxs-lookup"><span data-stu-id="41c82-159">Click **Settings** > **SIEM**.</span></span> 

3. <span data-ttu-id="41c82-160">Seleccione la **pestaña MSSP.**</span><span class="sxs-lookup"><span data-stu-id="41c82-160">Select the **MSSP** tab.</span></span>

4. <span data-ttu-id="41c82-161">Escriba el **id. de** aplicación del primer paso y el identificador **de inquilino**.</span><span class="sxs-lookup"><span data-stu-id="41c82-161">Enter the **Application ID** from the first step and your **Tenant ID**.</span></span>

5. <span data-ttu-id="41c82-162">Haga clic **en Autorizar aplicación**.</span><span class="sxs-lookup"><span data-stu-id="41c82-162">Click **Authorize application**.</span></span> 

 
<span data-ttu-id="41c82-163">Ahora puede descargar el archivo de configuración correspondiente para siem y conectarse a la API de Defender para endpoints.</span><span class="sxs-lookup"><span data-stu-id="41c82-163">You can now download the relevant configuration file for your SIEM and connect to the Defender for Endpoint API.</span></span> <span data-ttu-id="41c82-164">Para obtener más información, vea [Pull alerts to your SIEM tools](configure-siem.md).</span><span class="sxs-lookup"><span data-stu-id="41c82-164">For more information, see, [Pull alerts to your SIEM tools](configure-siem.md).</span></span>
 

- <span data-ttu-id="41c82-165">En el archivo de configuración de ArcSight / Archivo de propiedades de autenticación splunk, escriba la clave de la aplicación manualmente estableciendo el valor secreto.</span><span class="sxs-lookup"><span data-stu-id="41c82-165">In the ArcSight configuration file / Splunk Authentication Properties file, write your application key manually by setting the secret value.</span></span>
- <span data-ttu-id="41c82-166">En lugar de adquirir un token de actualización en el portal, use el script del paso anterior para adquirir un token de actualización (o adquirirlo por otros medios).</span><span class="sxs-lookup"><span data-stu-id="41c82-166">Instead of acquiring a refresh token in the portal, use the script from the previous step to acquire a refresh token (or acquire it by other means).</span></span>

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a><span data-ttu-id="41c82-167">Capturar alertas desde el inquilino del cliente de MSSP mediante API</span><span class="sxs-lookup"><span data-stu-id="41c82-167">Fetch alerts from MSSP customer's tenant using APIs</span></span>
 
<span data-ttu-id="41c82-168">Para obtener información sobre cómo capturar alertas mediante la API de REST, vea [Extraer alertas mediante la API de REST](pull-alerts-using-rest-api.md).</span><span class="sxs-lookup"><span data-stu-id="41c82-168">For information on how to fetch alerts using REST API, see [Pull alerts using REST API](pull-alerts-using-rest-api.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="41c82-169">Consulte también</span><span class="sxs-lookup"><span data-stu-id="41c82-169">See also</span></span>
- [<span data-ttu-id="41c82-170">Conceder acceso a MSSP al portal</span><span class="sxs-lookup"><span data-stu-id="41c82-170">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="41c82-171">Acceder al portal de clientes de MSSP</span><span class="sxs-lookup"><span data-stu-id="41c82-171">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="41c82-172">Configurar notificaciones de alerta</span><span class="sxs-lookup"><span data-stu-id="41c82-172">Configure alert notifications</span></span>](configure-mssp-notifications.md)
