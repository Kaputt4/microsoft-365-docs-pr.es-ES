---
title: Implementar un conector para archivar datos de Twitter
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Los administradores pueden configurar un conector nativo para importar y archivar datos de Twitter a Microsoft 365. Una vez que estos datos se han importado a Microsoft 365, puede usar las características de cumplimiento, como la retención legal, la búsqueda de contenido y las directivas de retención, para administrar el gobierno de los datos de Twitter de la organización.
ms.openlocfilehash: 5a7d7749f99615d9fd6858be05cc63153cfe1d31
ms.sourcegitcommit: 9b390881fe661deb0568b4b86a5a9094f3c795f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269401"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="e9919-104">Implementar un conector para archivar datos de Twitter</span><span class="sxs-lookup"><span data-stu-id="e9919-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="e9919-105">Este artículo contiene el proceso paso a paso para implementar un conector que usa el servicio de importación de Office 365 para importar datos de la cuenta de Twitter de su organización a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e9919-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="e9919-106">Para obtener una introducción de alto nivel de este proceso y una lista de los requisitos previos necesarios para implementar un conector de Twitter, consulte [configurar un conector para archivar datos de Twitter ](archive-twitter-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="e9919-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="e9919-107">Paso 1: crear una aplicación en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e9919-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="e9919-108">Vaya a <https://portal.azure.com> e inicie sesión con las credenciales de una cuenta de administrador global de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e9919-108">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

   ![Iniciar sesión en Azure](media/TCimage01.png)

2. <span data-ttu-id="e9919-110">En el panel de navegación izquierdo, haga clic en **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="e9919-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Ir a Azure Active Directory](media/TCimage02.png)

3. <span data-ttu-id="e9919-112">En el panel de navegación izquierdo, haga clic en **registros de aplicaciones (versión preliminar)** y, a continuación, haga clic en **nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="e9919-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![Crear un nuevo registro de la aplicación](media/TCimage03.png)

4. <span data-ttu-id="e9919-114">Registrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e9919-114">Register the application.</span></span> <span data-ttu-id="e9919-115">En **URI de redireccionamiento (opcional)**, seleccione **Web** en la lista desplegable tipo de `https://portal.azure.com` aplicación y, a continuación, escriba en el cuadro del URI.</span><span class="sxs-lookup"><span data-stu-id="e9919-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="e9919-116">Tipo https://portal.azure.com de URI de redireccionamiento</span><span class="sxs-lookup"><span data-stu-id="e9919-116">Type https://portal.azure.com for the redirect URI</span></span> ](media/TCimage04.png)

5. <span data-ttu-id="e9919-117">Copie el identificador de la **aplicación (cliente)** y el **directorio (inquilino)** y guárdelos en un archivo de texto u otra ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="e9919-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="e9919-118">Estos identificadores se usan en pasos posteriores.</span><span class="sxs-lookup"><span data-stu-id="e9919-118">You use these IDs in later steps.</span></span>

    ![Copiar y guardar el identificador de la aplicación y el identificador del directorio](media/TCimage05.png)

6. <span data-ttu-id="e9919-120">Vaya a **certificados & secretos para la nueva aplicación** y, en **secretos de cliente** , haga clic en **nuevo secreto de cliente**.</span><span class="sxs-lookup"><span data-stu-id="e9919-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![Crear un nuevo secreto de cliente](media/TCimage06.png)

7. <span data-ttu-id="e9919-122">Cree un secreto nuevo.</span><span class="sxs-lookup"><span data-stu-id="e9919-122">Create a new secret.</span></span> <span data-ttu-id="e9919-123">En el cuadro Descripción, escriba el secreto y, a continuación, elija un período de expiración.</span><span class="sxs-lookup"><span data-stu-id="e9919-123">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![Escribir el secreto y elegir período de expiración](media/TCimage08.png)

8. <span data-ttu-id="e9919-125">Copie el valor del secreto y guárdelo en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="e9919-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="e9919-126">Este es el secreto de la aplicación de AAD que se usa en pasos posteriores.</span><span class="sxs-lookup"><span data-stu-id="e9919-126">This is the AAD application secret that you use in later steps.</span></span>

   ![Copiar y guardar el secreto](media/TCimage09.png)

9. <span data-ttu-id="e9919-128">Vaya al **manifiesto** y copie identifieruris a (que también se denomina el URI de la aplicación AAD), tal y como se resalta en la siguiente captura de pantalla.</span><span class="sxs-lookup"><span data-stu-id="e9919-128">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="e9919-129">Copie el URI de la aplicación de AAD en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="e9919-129">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="e9919-130">Se usa en el paso 6.</span><span class="sxs-lookup"><span data-stu-id="e9919-130">You use it in Step 6.</span></span>

    ![Copiar y guardar el URI de la aplicación AAD](media/TCimage10.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="e9919-132">Paso 2: implementar el servicio Web del conector desde GitHub a su cuenta de Azure</span><span class="sxs-lookup"><span data-stu-id="e9919-132">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="e9919-133">Vaya a [este sitio de github](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) y haga clic en **implementar en Azure**.</span><span class="sxs-lookup"><span data-stu-id="e9919-133">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Ir a la Página principal de Azure](media/FBCimage11.png)

2. <span data-ttu-id="e9919-135">Después de hacer clic en **implementar en Azure**, se le redirigirá a un portal de Azure con una página de plantilla personalizada.</span><span class="sxs-lookup"><span data-stu-id="e9919-135">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="e9919-136">Rellene los detalles de **conceptos básicos** y **configuración** y, a continuación, haga clic en **comprar**.</span><span class="sxs-lookup"><span data-stu-id="e9919-136">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![Haga clic en crear un recurso y escriba la cuenta de almacenamiento](media/FBCimage12.png)

    - <span data-ttu-id="e9919-138">**Suscripción:** Seleccione su suscripción a Azure en la que desea implementar el servicio Web del conector de Twitter.</span><span class="sxs-lookup"><span data-stu-id="e9919-138">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>
    
    - <span data-ttu-id="e9919-139">**Grupo de recursos:** Elija o cree un nuevo grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="e9919-139">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="e9919-140">Un grupo de recursos es un contenedor que contiene recursos relacionados para una solución de Azure.</span><span class="sxs-lookup"><span data-stu-id="e9919-140">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="e9919-141">**Ubicación:** Elija una ubicación.</span><span class="sxs-lookup"><span data-stu-id="e9919-141">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="e9919-142">**Nombre de la aplicación web:** Proporcione un nombre único para la aplicación web del conector.</span><span class="sxs-lookup"><span data-stu-id="e9919-142">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="e9919-143">El nombre debe tener entre 3 y 18 caracteres de longitud.</span><span class="sxs-lookup"><span data-stu-id="e9919-143">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="e9919-144">Este nombre se usa para crear la dirección URL de Azure App Service; por ejemplo, si proporciona el nombre de la aplicación Web de **twitterconnector** , la dirección URL del servicio de aplicación de Azure será **twitterconnector.azurewebsites.net**.</span><span class="sxs-lookup"><span data-stu-id="e9919-144">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="e9919-145">**tenantId:** El identificador de inquilino de su organización de Microsoft 365 que copió después de crear la aplicación de conector de Facebook en Azure Active Directory en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="e9919-145">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="e9919-146">**APISecretKey:** Puede escribir cualquier valor como secreto.</span><span class="sxs-lookup"><span data-stu-id="e9919-146">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="e9919-147">Se usa para obtener acceso a la aplicación web del conector en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="e9919-147">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="e9919-148">Una vez completada la implementación, la página tendrá un aspecto similar al de la siguiente captura de pantalla:</span><span class="sxs-lookup"><span data-stu-id="e9919-148">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![Haga clic en almacenamiento y, a continuación, en cuenta de almacenamiento](media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="e9919-150">Paso 3: crear la aplicación de Twitter</span><span class="sxs-lookup"><span data-stu-id="e9919-150">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="e9919-151">Vaya a https://developer.twitter.com, inicie sesión con las credenciales de la cuenta de desarrollador de su organización y, a continuación, haga clic en **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="e9919-151">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![Ir a https://developer.twitter.com e iniciar sesión](media/TCimage25-5.png)
2. <span data-ttu-id="e9919-153">Haga clic en **crear una aplicación**.</span><span class="sxs-lookup"><span data-stu-id="e9919-153">Click **Create an app**.</span></span>
   
   ![Ir a la página de aplicaciones para crear una aplicación](media/TCimage26.png)

3. <span data-ttu-id="e9919-155">En **detalles**de la aplicación, agregue información sobre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e9919-155">Under **App details**, add information about the application.</span></span>

   ![Escribir información sobre la aplicación](media/TCimage27.png)

4. <span data-ttu-id="e9919-157">En el panel del programador de Twitter, seleccione la aplicación que acaba de crear y copie el identificador de aplicación que se muestra y guárdelo en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="e9919-157">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="e9919-158">A continuación, haga clic en **detalles**.</span><span class="sxs-lookup"><span data-stu-id="e9919-158">Then click **Details**.</span></span>
   
   ![Copiar y guardar el identificador de la aplicación](media/TCimage28.png)

5. <span data-ttu-id="e9919-160">En la pestaña **claves y tokens** , en **claves** de la API de consumidor, copie la clave secreta de la API y guárdela en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="e9919-160">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="e9919-161">A continuación, haga clic en **crear** para generar un token de acceso y un secreto de token de acceso, y cópielos en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="e9919-161">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![Copiar y guardar en clave secreta de la API](media/TCimage29.png)

   <span data-ttu-id="e9919-163">A continuación, haga clic en **crear** para generar un token de acceso y un secreto de token de acceso, y cópielos en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="e9919-163">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="e9919-164">Haga clic en la pestaña **permisos** y configure los permisos como se muestra en la siguiente captura de pantalla:</span><span class="sxs-lookup"><span data-stu-id="e9919-164">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![Configurar permisos](media/TCimage30.png)

7. <span data-ttu-id="e9919-166">Una vez que haya guardado la configuración de permisos, haga clic en la pestaña detalles de la **aplicación** y, a continuación, haga clic en **Editar > editar detalles**.</span><span class="sxs-lookup"><span data-stu-id="e9919-166">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![Editar los detalles de la aplicación](media/TCimage31.png)

8. <span data-ttu-id="e9919-168">Realice las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="e9919-168">Do the following tasks:</span></span>

   - <span data-ttu-id="e9919-169">Active la casilla para permitir que la aplicación conector inicie sesión en Twitter.</span><span class="sxs-lookup"><span data-stu-id="e9919-169">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="e9919-170">Agregue el URI de redireccionamiento de OAuth con el siguiente formato: \*\* \<connectorserviceuri>/views/twitteroauth\*\*, donde el valor de *connectorserviceuri* es la dirección URL de Azure App Service para su organización; por ejemplo, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span><span class="sxs-lookup"><span data-stu-id="e9919-170">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![Permitir que la aplicación conector inicie sesión en Twitter y agregue el URI de redireccionamiento de OAuth](media/TCimage32.png)

<span data-ttu-id="e9919-172">La aplicación de desarrollo de Twitter ya está lista para usarse.</span><span class="sxs-lookup"><span data-stu-id="e9919-172">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="e9919-173">Paso 4: configurar la aplicación web del conector</span><span class="sxs-lookup"><span data-stu-id="e9919-173">Step 4: Configure the connector web app</span></span> 

1. <span data-ttu-id="e9919-174">Vaya a https://\<AzureAppResourceName>. azurewebsites.net (donde **AzureAppResourceName** es el nombre del recurso de la aplicación de Azure que ha nombrado en el paso 4).</span><span class="sxs-lookup"><span data-stu-id="e9919-174">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="e9919-175">Por ejemplo, si el nombre es **twitterconnector**, vaya a https://twitterconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="e9919-175">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="e9919-176">La Página principal de la aplicación es similar a la siguiente captura de pantalla:</span><span class="sxs-lookup"><span data-stu-id="e9919-176">The home page of the app looks like the following screenshot:</span></span>

   ![Ir a la página de recursos de la aplicación de Azure](media/FBCimage41.png)

2. <span data-ttu-id="e9919-178">Haga clic en **configurar** para mostrar una página de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="e9919-178">Click **Configure** to display a sign in page.</span></span>

   ![Haga clic en configurar para mostrar la página de inicio de sesión](media/FBCimage42.png)

3. <span data-ttu-id="e9919-180">En el cuadro identificador de inquilino, escriba o pegue el identificador de inquilino (que obtuvo en el paso 2).</span><span class="sxs-lookup"><span data-stu-id="e9919-180">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="e9919-181">En el cuadro contraseña, escriba o pegue el APISecretKey (que obtuvo en el paso 2) y, a continuación, haga clic en **establecer valores de configuración** para mostrar la página Detalles de la configuración.</span><span class="sxs-lookup"><span data-stu-id="e9919-181">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![Iniciar sesión con el identificador de inquilino y la clave secreta de API](media/TCimage35.png)

4. <span data-ttu-id="e9919-183">Especifique las siguientes opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="e9919-183">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="e9919-184">**Clave de API de Twitter:** El identificador de aplicación de la aplicación de Twitter que creó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="e9919-184">**Twitter Api Key:** The app ID for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="e9919-185">**Clave secreta de la API de Twitter:** Clave secreta de la API para la aplicación de Twitter que creó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="e9919-185">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="e9919-186">**Token de acceso de Twitter:** El token de acceso que ha creado en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="e9919-186">**Twitter Access Token:** The access token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="e9919-187">**Secreto de token de acceso de Twitter:** El secreto de token de acceso que creó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="e9919-187">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>
   
   - <span data-ttu-id="e9919-188">**Identificador de la aplicación de AAD:** El identificador de aplicación de la aplicación de Azure Active Directory que creó en el paso 1</span><span class="sxs-lookup"><span data-stu-id="e9919-188">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>
   
   - <span data-ttu-id="e9919-189">**Secreto de la aplicación AAD:** El valor del secreto APISecretKey que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="e9919-189">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="e9919-190">Haga clic en **Guardar** para guardar la configuración del conector.</span><span class="sxs-lookup"><span data-stu-id="e9919-190">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="e9919-191">Paso 5: configurar un conector de Twitter en el centro de cumplimiento de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e9919-191">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="e9919-192">Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y, a continuación, haga clic en **conectores de datos** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="e9919-192">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="e9919-193">En la página **conectores de datos (vista previa)** , en **Twitter**, haga clic en **Ver**.</span><span class="sxs-lookup"><span data-stu-id="e9919-193">On the **Data connectors (preview)** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="e9919-194">En la página de **Twitter** , haga clic en **Agregar conector**.</span><span class="sxs-lookup"><span data-stu-id="e9919-194">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="e9919-195">En la página **condiciones de servicio** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e9919-195">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="e9919-196">En la página **agregar credenciales para la aplicación de conector** , escriba la siguiente información y, a continuación, haga clic en **validar conexión**.</span><span class="sxs-lookup"><span data-stu-id="e9919-196">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Especificar credenciales de aplicación de conector](media/TCimage38.png)

    - <span data-ttu-id="e9919-198">En el cuadro **nombre** , escriba un nombre para el conector, como **controlador de ayuda de Twitter**.</span><span class="sxs-lookup"><span data-stu-id="e9919-198">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>
    
    - <span data-ttu-id="e9919-199">En el cuadro **dirección URL del conector** , escriba o pegue la dirección URL de Azure App Service; por ejemplo `https://twitterconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="e9919-199">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="e9919-200">En el cuadro **contraseña** , escriba o pegue el valor de la APISecretKey que creó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="e9919-200">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>
    
    - <span data-ttu-id="e9919-201">En el cuadro identificador de la **aplicación de Azure** , escriba o pegue el valor del identificador de aplicación de la aplicación de Azure (también denominado identificador de *cliente*) que obtuvo en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="e9919-201">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="e9919-202">Una vez validada correctamente la conexión, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e9919-202">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="e9919-203">En la página **autorizar a Microsoft 365 a importar datos** , escriba o pegue el APISecretKey de nuevo y, a continuación, haga clic en **iniciar sesión en la aplicación web**.</span><span class="sxs-lookup"><span data-stu-id="e9919-203">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="e9919-204">Haga clic en **iniciar sesión con Twitter**.</span><span class="sxs-lookup"><span data-stu-id="e9919-204">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="e9919-205">En la página inicio de sesión de Twitter, inicie sesión con las credenciales de la cuenta de Twitter de su organización.</span><span class="sxs-lookup"><span data-stu-id="e9919-205">On the Twitter sign in page, sign in using the credentials for your organization’s Twitter account.</span></span>

   ![Iniciar sesión en la cuenta de Twitter](media/TCimage42.png)

   <span data-ttu-id="e9919-207">Después de iniciar sesión, la página de Twitter mostrará el siguiente mensaje de error "el trabajo del conector de Twitter se configuró correctamente".</span><span class="sxs-lookup"><span data-stu-id="e9919-207">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="e9919-208">Haga clic en **continuar** para completar la configuración del conector de Twitter.</span><span class="sxs-lookup"><span data-stu-id="e9919-208">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="e9919-209">En la página **Establecer filtros** , puede aplicar un filtro para importar inicialmente los elementos que tienen una antigüedad determinada.</span><span class="sxs-lookup"><span data-stu-id="e9919-209">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="e9919-210">Seleccione una edad y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e9919-210">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="e9919-211">En la página **Elegir ubicación de almacenamiento** , escriba la dirección de correo electrónico del buzón de correo de Microsoft 365 al que se importarán los elementos de Twitter y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e9919-211">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="e9919-212">En el **acuerdo proporcionar consentimiento del administrador**, haga clic en **proporcionar consentimiento** y, a continuación, siga los pasos.</span><span class="sxs-lookup"><span data-stu-id="e9919-212">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="e9919-213">Debe ser administrador global para dar su consentimiento al servicio de importación de Office 365 para obtener acceso a los datos de su organización.</span><span class="sxs-lookup"><span data-stu-id="e9919-213">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

14. <span data-ttu-id="e9919-214">Haga clic en **siguiente** para revisar la configuración del conector y, a continuación, haga clic en **Finalizar** para completar la configuración del conector.</span><span class="sxs-lookup"><span data-stu-id="e9919-214">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

15. <span data-ttu-id="e9919-215">En el centro de cumplimiento, vaya a la página **conectores de datos** y haga clic en la pestaña **conectores** para ver el progreso del proceso de importación.</span><span class="sxs-lookup"><span data-stu-id="e9919-215">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
