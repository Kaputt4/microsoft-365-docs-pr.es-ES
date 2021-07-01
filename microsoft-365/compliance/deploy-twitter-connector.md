---
title: Implementar un conector para archivar datos de Twitter
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Los administradores pueden configurar un conector nativo para importar y archivar datos de Twitter en Microsoft 365. Después de importar estos datos a Microsoft 365, puede usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar el gobierno de los datos de Twitter de su organización.
ms.openlocfilehash: 0a0ebb18cb39b7dd7416f2d03dcb5b4d21332c9b
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227060"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="d4f02-104">Implementar un conector para archivar datos de Twitter</span><span class="sxs-lookup"><span data-stu-id="d4f02-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="d4f02-105">Este artículo contiene el proceso paso a paso para implementar un conector que usa el servicio de importación de Office 365 para importar datos de la cuenta de Twitter de su organización a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4f02-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="d4f02-106">Para obtener información general de alto nivel sobre este proceso y una lista de requisitos previos necesarios para implementar un conector de Twitter, vea Configurar un conector para [archivar datos de Twitter ](archive-twitter-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="d4f02-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="d4f02-107">Paso 1: Crear una aplicación en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d4f02-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="d4f02-108">Vaya a <https://portal.azure.com> e inicie sesión con las credenciales de una cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="d4f02-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

   ![Iniciar sesión en Azure](../media/TCimage01.png)

2. <span data-ttu-id="d4f02-110">En el panel de navegación izquierdo, haga clic en **Azure Active Directory**</span><span class="sxs-lookup"><span data-stu-id="d4f02-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Vaya a Azure Active Directory](../media/TCimage02.png)

3. <span data-ttu-id="d4f02-112">En el panel de navegación izquierdo, haga clic en **Registros de aplicaciones (versión preliminar)** y, a continuación, haga clic **en Nuevo registro.**</span><span class="sxs-lookup"><span data-stu-id="d4f02-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![Crear un registro de aplicación nuevo](../media/TCimage03.png)

4. <span data-ttu-id="d4f02-114">Registrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d4f02-114">Register the application.</span></span> <span data-ttu-id="d4f02-115">En **URI de redireccionamiento (opcional),** seleccione **Web** en la lista desplegable tipo de aplicación y, a continuación, escriba el cuadro para `https://portal.azure.com` el URI.</span><span class="sxs-lookup"><span data-stu-id="d4f02-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![Tipo https://portal.azure.com para el URI de redireccionamiento](../media/TCimage04.png)

5. <span data-ttu-id="d4f02-117">Copie el **identificador de aplicación (cliente)** y el id. de directorio **(inquilino)** y guárdelos en un archivo de texto u otra ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="d4f02-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="d4f02-118">Estos IDs se usan en pasos posteriores.</span><span class="sxs-lookup"><span data-stu-id="d4f02-118">You use these IDs in later steps.</span></span>

    ![Copiar y guardar el id. de aplicación y el id. de directorio](../media/TCimage05.png)

6. <span data-ttu-id="d4f02-120">Vaya a **Certificados & secretos de la** nueva aplicación y, en Secretos **de** cliente, haga clic en Nuevo secreto **de cliente.**</span><span class="sxs-lookup"><span data-stu-id="d4f02-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![Crear un nuevo secreto de cliente](../media/TCimage06.png)

7. <span data-ttu-id="d4f02-122">Cree un nuevo secreto.</span><span class="sxs-lookup"><span data-stu-id="d4f02-122">Create a new secret.</span></span> <span data-ttu-id="d4f02-123">En el cuadro descripción, escriba el secreto y, a continuación, elija un período de expiración.</span><span class="sxs-lookup"><span data-stu-id="d4f02-123">In the description box, type the secret and then choose an expiration period.</span></span>

   ![Escriba el secreto y elija el período de expiración](../media/TCimage08.png)

8. <span data-ttu-id="d4f02-125">Copie el valor del secreto y guárdelo en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="d4f02-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="d4f02-126">Este es el secreto de aplicación de AAD que se usa en los pasos posteriores.</span><span class="sxs-lookup"><span data-stu-id="d4f02-126">This is the AAD application secret that you use in later steps.</span></span>

   ![Copiar y guardar el secreto](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="d4f02-128">Paso 2: Implementar el servicio web del conector GitHub en su cuenta de Azure</span><span class="sxs-lookup"><span data-stu-id="d4f02-128">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="d4f02-129">Vaya a [este GitHub y](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) haga clic en Implementar en **Azure**.</span><span class="sxs-lookup"><span data-stu-id="d4f02-129">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Vaya a la página principal de Azure](../media/FBCimage11.png)

2. <span data-ttu-id="d4f02-131">Después de hacer **clic en Implementar en Azure,** se le redirigirá a un Portal de Azure con una página de plantilla personalizada.</span><span class="sxs-lookup"><span data-stu-id="d4f02-131">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="d4f02-132">Rellene los detalles **básicos** **y Configuración** y, a continuación, haga clic en **Comprar**.</span><span class="sxs-lookup"><span data-stu-id="d4f02-132">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![Haga clic en Crear un recurso y escriba cuenta de almacenamiento](../media/FBCimage12.png)

    - <span data-ttu-id="d4f02-134">**Suscripción:** Seleccione la suscripción de Azure en la que desea implementar el servicio web del conector de Twitter.</span><span class="sxs-lookup"><span data-stu-id="d4f02-134">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>

    - <span data-ttu-id="d4f02-135">**Grupo de recursos:** Elija o cree un nuevo grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="d4f02-135">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="d4f02-136">Un grupo de recursos es un contenedor que contiene recursos relacionados para una solución de Azure.</span><span class="sxs-lookup"><span data-stu-id="d4f02-136">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="d4f02-137">**Ubicación:** Elija una ubicación.</span><span class="sxs-lookup"><span data-stu-id="d4f02-137">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="d4f02-138">**Nombre de aplicación web:** Proporcione un nombre único para la aplicación web del conector.</span><span class="sxs-lookup"><span data-stu-id="d4f02-138">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="d4f02-139">Th nombre debe tener entre 3 y 18 caracteres de longitud.</span><span class="sxs-lookup"><span data-stu-id="d4f02-139">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="d4f02-140">Este nombre se usa para crear la dirección URL del servicio de aplicaciones de Azure; por ejemplo, si proporciona el nombre de la aplicación web **de twitterconnector,** la dirección URL del servicio de aplicaciones de Azure **se mostrará twitterconnector.azurewebsites.net**.</span><span class="sxs-lookup"><span data-stu-id="d4f02-140">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>

    - <span data-ttu-id="d4f02-141">**tenantId:** El identificador de inquilino de la Microsoft 365 que copió después de crear la aplicación de conector de Facebook en Azure Active Directory en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="d4f02-141">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>

   - <span data-ttu-id="d4f02-142">**APISecretKey:** Puede escribir cualquier valor como secreto.</span><span class="sxs-lookup"><span data-stu-id="d4f02-142">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="d4f02-143">Esto se usa para tener acceso a la aplicación web del conector en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="d4f02-143">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="d4f02-144">Una vez que la implementación se realiza correctamente, la página tendrá un aspecto similar a la siguiente captura de pantalla:</span><span class="sxs-lookup"><span data-stu-id="d4f02-144">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![Haga clic Storage y, a continuación, haga clic Storage cuenta](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="d4f02-146">Paso 3: Crear la aplicación de Twitter</span><span class="sxs-lookup"><span data-stu-id="d4f02-146">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="d4f02-147">Vaya a , inicie sesión con las credenciales de la cuenta de desarrollador de su organización y, a https://developer.twitter.com continuación, haga clic en **Aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="d4f02-147">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![Ir a https://developer.twitter.com e iniciar sesión](../media/TCimage25-5.png)
2. <span data-ttu-id="d4f02-149">Haz **clic en Crear una aplicación**.</span><span class="sxs-lookup"><span data-stu-id="d4f02-149">Click **Create an app**.</span></span>

   ![Ir a la página Aplicaciones para crear una aplicación](../media/TCimage26.png)

3. <span data-ttu-id="d4f02-151">En **Detalles de la** aplicación, agregue información sobre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d4f02-151">Under **App details**, add information about the application.</span></span>

   ![Escribir información sobre la aplicación](../media/TCimage27.png)

4. <span data-ttu-id="d4f02-153">En el panel de desarrolladores de Twitter, seleccione la aplicación que acaba de crear y, a continuación, haga clic en **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="d4f02-153">On the Twitter developer dashboard, select the app that you just created and then click **Details**.</span></span>

   ![Copiar y guardar el identificador de aplicación](../media/TCimage28.png)

5. <span data-ttu-id="d4f02-155">En la pestaña Claves y **tokens,** en **Claves de la API** de consumidor, copie la clave api y la clave secreta de la API y guárdelas en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="d4f02-155">On the **Keys and tokens** tab, under **Consumer API keys** copy both the API Key and the API secret key and save them to a text file or other storage location.</span></span> <span data-ttu-id="d4f02-156">A **continuación,** haga clic en Crear para generar un token de acceso y un secreto de token de acceso y copiarlos en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="d4f02-156">Then click **Create** to generate an access token and access token secret and copy these to a text file or other storage location.</span></span>

   ![Copiar y guardar en clave secreta de API](../media/TCimage29.png)

   <span data-ttu-id="d4f02-158">A **continuación,** haga clic en Crear para generar un token de acceso y un secreto de token de acceso, y cópielos en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="d4f02-158">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="d4f02-159">Haga clic **en la pestaña Permisos** y configure los permisos como se muestra en la siguiente captura de pantalla:</span><span class="sxs-lookup"><span data-stu-id="d4f02-159">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![Configurar permisos](../media/TCimage30.png)

7. <span data-ttu-id="d4f02-161">Después de guardar la configuración de permisos, haga clic en la **pestaña Detalles** de la aplicación y, a continuación, haga clic en Editar > **Editar detalles.**</span><span class="sxs-lookup"><span data-stu-id="d4f02-161">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![Editar los detalles de la aplicación](../media/TCimage31.png)

8. <span data-ttu-id="d4f02-163">Realice las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="d4f02-163">Do the following tasks:</span></span>

   - <span data-ttu-id="d4f02-164">Selecciona la casilla para permitir que la aplicación del conector inicie sesión en Twitter.</span><span class="sxs-lookup"><span data-stu-id="d4f02-164">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>

   - <span data-ttu-id="d4f02-165">Agregue el Uri de redireccionamiento de OAuth con el siguiente formato: **\<connectorserviceuri> /Views/TwitterOAuth**, donde el valor de *connectorserviceuri* es la dirección URL del servicio de aplicaciones de Azure para su organización; por ejemplo, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth .</span><span class="sxs-lookup"><span data-stu-id="d4f02-165">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![Permitir que la aplicación del conector inicie sesión en Twitter y agregue uri de redireccionamiento de OAuth](../media/TCimage32.png)

<span data-ttu-id="d4f02-167">La aplicación para desarrolladores de Twitter ya está lista para usarse.</span><span class="sxs-lookup"><span data-stu-id="d4f02-167">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="d4f02-168">Paso 4: Configurar la aplicación web del conector</span><span class="sxs-lookup"><span data-stu-id="d4f02-168">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="d4f02-169">Vaya a https:// \<AzureAppResourceName> .azurewebsites.net (donde **AzureAppResourceName** es el nombre del recurso de la aplicación de Azure que nombra en el paso 4).</span><span class="sxs-lookup"><span data-stu-id="d4f02-169">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="d4f02-170">Por ejemplo, si el nombre es **twitterconnector**, vaya a https://twitterconnector.azurewebsites.net .</span><span class="sxs-lookup"><span data-stu-id="d4f02-170">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="d4f02-171">La página principal de la aplicación tiene el aspecto de la siguiente captura de pantalla:</span><span class="sxs-lookup"><span data-stu-id="d4f02-171">The home page of the app looks like the following screenshot:</span></span>

   ![Ir a la página de recursos de la aplicación de Azure](../media/FBCimage41.png)

2. <span data-ttu-id="d4f02-173">Haga **clic en** Configurar para mostrar una página de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="d4f02-173">Click **Configure** to display a sign in page.</span></span>

   ![Haga clic en Configurar para mostrar la página de inicio de sesión](../media/FBCimage42.png)

3. <span data-ttu-id="d4f02-175">En el cuadro Identificador de inquilino, escriba o pegue el identificador de inquilino (que obtuvo en el paso 2).</span><span class="sxs-lookup"><span data-stu-id="d4f02-175">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="d4f02-176">En el cuadro contraseña, escriba o pegue APISecretKey (que obtuvo en el paso 2) y, a **continuación,** haga clic en Establecer configuración Configuración para mostrar la página de detalles de configuración.</span><span class="sxs-lookup"><span data-stu-id="d4f02-176">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![Iniciar sesión con el identificador de inquilino y la clave secreta de la API](../media/TCimage35.png)

4. <span data-ttu-id="d4f02-178">Escriba las siguientes opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="d4f02-178">Enter the following configuration settings</span></span>

   - <span data-ttu-id="d4f02-179">**Clave de api de Twitter:** La clave de API para la aplicación de Twitter que creó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="d4f02-179">**Twitter Api Key:** The API key for the Twitter application that you created in Step 3.</span></span>

   - <span data-ttu-id="d4f02-180">**Clave secreta de api de Twitter:** La clave secreta de api para la aplicación de Twitter que creó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="d4f02-180">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>

   - <span data-ttu-id="d4f02-181">**Token de acceso de Twitter:** El token de acceso que creó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="d4f02-181">**Twitter Access Token:** The access token that you created in Step 3.</span></span>

   - <span data-ttu-id="d4f02-182">**Secreto de token de acceso de Twitter:** El secreto de token de acceso que creó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="d4f02-182">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>

   - <span data-ttu-id="d4f02-183">**Id. de aplicación de AAD:** El identificador de la aplicación Azure Active Directory que creaste en el paso 1</span><span class="sxs-lookup"><span data-stu-id="d4f02-183">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>

   - <span data-ttu-id="d4f02-184">**Secreto de aplicación de AAD:** Valor del secreto APISecretKey que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="d4f02-184">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="d4f02-185">Haga **clic en** Guardar para guardar la configuración del conector.</span><span class="sxs-lookup"><span data-stu-id="d4f02-185">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="d4f02-186">Paso 5: Configurar un conector de Twitter en el Centro de cumplimiento de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d4f02-186">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="d4f02-187">Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y, a continuación, haga clic **en Conectores de datos** en la navegación izquierda.</span><span class="sxs-lookup"><span data-stu-id="d4f02-187">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="d4f02-188">En la página **Conectores de datos** de **Twitter,** haga clic en **Ver**.</span><span class="sxs-lookup"><span data-stu-id="d4f02-188">On the **Data connectors** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="d4f02-189">En la página **de Twitter,** haga clic **en Agregar conector**.</span><span class="sxs-lookup"><span data-stu-id="d4f02-189">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="d4f02-190">En la **página Términos de** servicio, haga clic **en Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d4f02-190">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="d4f02-191">En la **página Agregar credenciales para la aplicación del conector,** escriba la siguiente información y, a continuación, haga clic en Validar **conexión**.</span><span class="sxs-lookup"><span data-stu-id="d4f02-191">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Escribir credenciales de la aplicación del conector](../media/TCimage38.png)

    - <span data-ttu-id="d4f02-193">En el **cuadro** Nombre, escriba un nombre para el conector, como el controlador **de ayuda de Twitter**.</span><span class="sxs-lookup"><span data-stu-id="d4f02-193">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>

    - <span data-ttu-id="d4f02-194">En el **cuadro Dirección URL del** conector, escriba o pegue la dirección URL del servicio de aplicaciones de Azure; por ejemplo `https://twitterconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="d4f02-194">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>

    - <span data-ttu-id="d4f02-195">En el **cuadro Contraseña,** escriba o pegue el valor de APISecretKey que creó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="d4f02-195">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>

    - <span data-ttu-id="d4f02-196">En el **cuadro Id. de** aplicación de Azure, escriba o pegue el valor del identificador de aplicación de aplicación de Azure (también denominado identificador de cliente) que obtuvo en el paso 1. </span><span class="sxs-lookup"><span data-stu-id="d4f02-196">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="d4f02-197">Después de validar correctamente la conexión, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d4f02-197">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="d4f02-198">En la **página Autorizar Microsoft 365** importar datos, escriba o pegue la APISecretKey de nuevo y, a continuación, haga clic en Iniciar sesión en la aplicación **web**.</span><span class="sxs-lookup"><span data-stu-id="d4f02-198">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="d4f02-199">Haga clic **en Iniciar sesión con Twitter**.</span><span class="sxs-lookup"><span data-stu-id="d4f02-199">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="d4f02-200">En la página de inicio de sesión de Twitter, inicie sesión con las credenciales de la cuenta de Twitter de su organización.</span><span class="sxs-lookup"><span data-stu-id="d4f02-200">On the Twitter sign in page, sign in using the credentials for your organization's Twitter account.</span></span>

   ![Iniciar sesión en la cuenta de Twitter](../media/TCimage42.png)

   <span data-ttu-id="d4f02-202">Después de iniciar sesión, la página de Twitter mostrará el siguiente mensaje: "Trabajo del conector de Twitter configurado correctamente".</span><span class="sxs-lookup"><span data-stu-id="d4f02-202">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="d4f02-203">Haga **clic en** Continuar para completar la configuración del conector de Twitter.</span><span class="sxs-lookup"><span data-stu-id="d4f02-203">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="d4f02-204">En la **página Establecer filtros,** puede aplicar un filtro para importar inicialmente elementos que tienen una edad determinada.</span><span class="sxs-lookup"><span data-stu-id="d4f02-204">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="d4f02-205">Seleccione una antigüedad y, a continuación, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d4f02-205">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="d4f02-206">En la **página Elegir ubicación de** almacenamiento, escriba la dirección de correo electrónico del buzón Microsoft 365 al que se importarán los elementos de Twitter y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d4f02-206">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="d4f02-207">Haga **clic en** Siguiente para revisar la configuración del conector y, a continuación, haga clic en **Finalizar** para completar la configuración del conector.</span><span class="sxs-lookup"><span data-stu-id="d4f02-207">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="d4f02-208">En el Centro de cumplimiento, vaya a la  página **Conectores** de datos y haga clic en la pestaña Conectores para ver el progreso del proceso de importación.</span><span class="sxs-lookup"><span data-stu-id="d4f02-208">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
