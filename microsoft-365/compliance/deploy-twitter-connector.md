---
title: Implementar un conector para archivar datos de Twitter en Office 365
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
description: Los administradores pueden configurar un conector nativo para importar y archivar datos de Twitter a Office 365. Una vez que estos datos se han importado a Office 365, puede usar las características de cumplimiento, como las directivas de retención legal, búsqueda de contenido y retención, para administrar el gobierno de los datos de Twitter de la organización.
ms.openlocfilehash: fda03e3e489b0ae9c754f2eba18bc60785bb3def
ms.sourcegitcommit: 1c962bd0d51dc12419c4e6e393bb734c972b7e38
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "38687784"
---
# <a name="deploy-a-connector-to-archive-twitter-data-in-office-365"></a><span data-ttu-id="4ae72-104">Implementar un conector para archivar datos de Twitter en Office 365</span><span class="sxs-lookup"><span data-stu-id="4ae72-104">Deploy a connector to archive Twitter data in Office 365</span></span>

<span data-ttu-id="4ae72-105">Este artículo contiene el proceso paso a paso para implementar un conector que usa el servicio de importación de Office 365 para importar datos de la cuenta de Twitter de su organización a Office 365.</span><span class="sxs-lookup"><span data-stu-id="4ae72-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Office 365.</span></span> <span data-ttu-id="4ae72-106">Para obtener información general de alto nivel de este proceso y una lista de los requisitos previos necesarios para implementar un conector de Twitter, vea [usar un conector de ejemplo para archivar datos de Twitter en Office 365 (versión preliminar)](archive-twitter-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="4ae72-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Use a sample connector to archive Twitter data in Office 365 (Preview)](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="4ae72-107">Paso 1: descargar el paquete</span><span class="sxs-lookup"><span data-stu-id="4ae72-107">Step 1: Download the package</span></span>

<span data-ttu-id="4ae72-108">Descargue el paquete precompilado de la sección de versiones en el repositorio [https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)de github en.</span><span class="sxs-lookup"><span data-stu-id="4ae72-108">Download the prebuilt package from the Release section in the GitHub repository at [https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span></span> <span data-ttu-id="4ae72-109">En la versión más reciente, descargue el archivo zip denominado **SampleConnector. zip**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="4ae72-110">Carga este archivo zip en Azure en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="4ae72-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="4ae72-111">Paso 2: crear una aplicación en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4ae72-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="4ae72-112">Vaya a <https://portal.azure.com> e inicie sesión con las credenciales de una cuenta de administrador global de Office 365.</span><span class="sxs-lookup"><span data-stu-id="4ae72-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

   ![Iniciar sesión en Azure](media/TCimage01.png)

2. <span data-ttu-id="4ae72-114">En el panel de navegación izquierdo, haga clic en **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-114">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Ir a Azure Active Directory](media/TCimage02.png)

3. <span data-ttu-id="4ae72-116">En el panel de navegación izquierdo, haga clic en **registros de aplicaciones (versión preliminar)** y, a continuación, haga clic en **nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-116">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![Crear un nuevo registro de la aplicación](media/TCimage03.png)

4. <span data-ttu-id="4ae72-118">Registrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4ae72-118">Register the application.</span></span> <span data-ttu-id="4ae72-119">En **URI de redireccionamiento (opcional)**, seleccione **Web** en la lista desplegable tipo de `https://portal.azure.com` aplicación y, a continuación, escriba en el cuadro del URI.</span><span class="sxs-lookup"><span data-stu-id="4ae72-119">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="4ae72-120">Tipo https://portal.azure.com de URI de redireccionamiento</span><span class="sxs-lookup"><span data-stu-id="4ae72-120">Type https://portal.azure.com for the redirect URI</span></span> ](media/TCimage04.png)

5. <span data-ttu-id="4ae72-121">Copie el identificador de la **aplicación (cliente)** y el **directorio (inquilino)** y guárdelos en un archivo de texto u otra ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="4ae72-121">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="4ae72-122">Estos identificadores se usan en pasos posteriores.</span><span class="sxs-lookup"><span data-stu-id="4ae72-122">You use these IDs in later steps.</span></span>

    ![Copiar y guardar el identificador de la aplicación y el identificador del directorio](media/TCimage05.png)

6. <span data-ttu-id="4ae72-124">Vaya a **certificados & secretos para la nueva aplicación** y, en **secretos de cliente** , haga clic en **nuevo secreto de cliente**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-124">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![Crear un nuevo secreto de cliente](media/TCimage06.png)

7. <span data-ttu-id="4ae72-126">Cree un secreto nuevo.</span><span class="sxs-lookup"><span data-stu-id="4ae72-126">Create a new secret.</span></span> <span data-ttu-id="4ae72-127">En el cuadro Descripción, escriba el secreto y, a continuación, elija un período de expiración.</span><span class="sxs-lookup"><span data-stu-id="4ae72-127">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![Escribir el secreto y elegir período de expiración](media/TCimage08.png)

8. <span data-ttu-id="4ae72-129">Copie el valor del secreto y guárdelo en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="4ae72-129">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="4ae72-130">Este es el secreto de la aplicación de AAD que se usa en pasos posteriores.</span><span class="sxs-lookup"><span data-stu-id="4ae72-130">This is the AAD application secret that you use in later steps.</span></span>

   ![Copiar y guardar el secreto](media/TCimage09.png)

9. <span data-ttu-id="4ae72-132">Vaya al **manifiesto** y copie identifieruris a (que también se denomina el URI de la aplicación AAD), tal y como se resalta en la siguiente captura de pantalla.</span><span class="sxs-lookup"><span data-stu-id="4ae72-132">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="4ae72-133">Copie el URI de la aplicación de AAD en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="4ae72-133">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="4ae72-134">Se usa en el paso 6.</span><span class="sxs-lookup"><span data-stu-id="4ae72-134">You use it in Step 6.</span></span>

    ![Copiar y guardar el URI de la aplicación AAD](media/TCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="4ae72-136">Paso 3: crear una cuenta de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="4ae72-136">Step 3: Create an Azure storage account</span></span>

1.  <span data-ttu-id="4ae72-137">Vaya a la Página principal de Azure de su organización.</span><span class="sxs-lookup"><span data-stu-id="4ae72-137">Go to the Azure home page for your organization.</span></span>

    ![Página principal de GI a Azure](media/TCimage11.png)

2. <span data-ttu-id="4ae72-139">Haga clic en **crear un recurso** y escriba la **cuenta de almacenamiento** en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4ae72-139">Click **Create a resource** and they type **storage account** in the search box.</span></span>

   ![Crear un recurso de cuenta de almacenamiento](media/TCimage12.png)

3. <span data-ttu-id="4ae72-141">Haga clic en **almacenamiento**y, a continuación, en **cuenta de almacenamiento**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-141">Click **Storage**, and then click **Storage account**.</span></span>

   ![Haga clic en almacenamiento y, a continuación, en cuenta de almacenamiento](media/TCimage13.png)

4. <span data-ttu-id="4ae72-143">En la página **crear cuenta de almacenamiento** , en el cuadro suscripción, seleccione **pay-as-go** o **Free Trial** en función del tipo de suscripción de Azure que tenga.</span><span class="sxs-lookup"><span data-stu-id="4ae72-143">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> 

   ![Selección de un tipo de cuenta de almacenamiento](media/TCimage14.png)

5. <span data-ttu-id="4ae72-145">Seleccione o cree un grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="4ae72-145">Select or create a resource group.</span></span>

   ![Seleccionar o crear un grupo de recursos](media/TCimage15.png)

6. <span data-ttu-id="4ae72-147">Escriba un nombre para la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="4ae72-147">Type a name for the storage account.</span></span>

   ![Nombre de la cuenta de almacenamiento](media/TCimage16.png)

7. <span data-ttu-id="4ae72-149">Revise y, a continuación, haga clic en **crear** para crear la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="4ae72-149">Review and then click **Create** to create the storage account.</span></span>

   ![Revise la configuración y, a continuación, cree la cuenta de almacenamiento](media/TCimage17.png)

8. <span data-ttu-id="4ae72-151">Tras unos minutos, haga clic en **Actualizar** y, a continuación, haga clic en **ir a recurso** para navegar a la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="4ae72-151">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

   ![Vaya a la cuenta de almacenamiento que acaba de crear](media/TCimage18.png)

9. <span data-ttu-id="4ae72-153">Haga clic en **teclas de acceso** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="4ae72-153">Click **Access keys** in the left navigation pane.</span></span>

   ![Haga clic en teclas de acceso](media/TCimage19.png)

10. <span data-ttu-id="4ae72-155">Copiar una **cadena de conexión** y guardarla en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="4ae72-155">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="4ae72-156">Se usa al crear un recurso de aplicación web en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="4ae72-156">You use this when creating a web app resource in Step 4.</span></span>

    ![Copiar una cadena de conexión](media/TCimage20.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="4ae72-158">Paso 4: crear un nuevo recurso de aplicación web en Azure</span><span class="sxs-lookup"><span data-stu-id="4ae72-158">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="4ae72-159">En la página **principal** de Azure portal, haga clic en **crear una \> aplicación \> Web de todos los recursos**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-159">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="4ae72-160">En la página **aplicación web** , haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-160">On the **Web app** page, click **Create**.</span></span>

   ![Crear un recurso de aplicación web en Azure](media/TCimage21.png)

2. <span data-ttu-id="4ae72-162">Rellene los detalles (como se muestra a continuación) y, a continuación, cree la aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="4ae72-162">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="4ae72-163">El nombre que escriba en el cuadro **nombre** de la aplicación se usa para crear la dirección URL de Azure App Service; por ejemplo, twitterconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="4ae72-163">The name that you enter in the **App name** box is used to create the Azure app service URL; for example, twitterconnector.azurewebsites.net.</span></span>

   ![<span data-ttu-id="4ae72-164">Nombre de tipo para el recurso de la aplicación Web; por ejemplo twitterconnector.azurewebsites.net</span><span class="sxs-lookup"><span data-stu-id="4ae72-164">Type name for the web app resource; for example twitterconnector.azurewebsites.net</span></span> ](media/TCimage22.png)

3. <span data-ttu-id="4ae72-165">Vaya al recurso de la aplicación web que acaba de crear y haga clic en configuración de la **aplicación** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="4ae72-165">Go to the newly created web app resource and click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="4ae72-166">En **configuración**de la aplicación, haga clic en **Agregar nuevo valor** y agregue las tres opciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="4ae72-166">Under **Application settings**, click **Add new setting** and add the following three settings.</span></span> <span data-ttu-id="4ae72-167">Use los valores (que copió en el archivo de texto de los pasos anteriores):</span><span class="sxs-lookup"><span data-stu-id="4ae72-167">Use the values (that you copied to the text file from the previous steps):</span></span> 

    - <span data-ttu-id="4ae72-168">**APISecretKey** : puede escribir cualquier valor como secreto.</span><span class="sxs-lookup"><span data-stu-id="4ae72-168">**APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="4ae72-169">Se usa para obtener acceso a la aplicación web del conector en el paso 7.</span><span class="sxs-lookup"><span data-stu-id="4ae72-169">This is used to access the connector web app in Step 7.</span></span>

    - <span data-ttu-id="4ae72-170">**StorageAccountConnectionString** : el URI de la cadena de conexión que copió después de crear la cuenta de almacenamiento de Azure en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="4ae72-170">**StorageAccountConnectionString** – The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    - <span data-ttu-id="4ae72-171">**tenantId** : el identificador de inquilino de su organización de Office 365 que copió después de crear la aplicación de conector de Twitter en Azure Active Directory en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="4ae72-171">**tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Twitter connector app in Azure Active Directory in Step 2.</span></span>

    ![Agregar configuración de la aplicación](media/TCimage23.png)

4. <span data-ttu-id="4ae72-173">En **Configuración general**, haga clic **en** junto a **AlwaysOn**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-173">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="4ae72-174">Haga clic en **Guardar** en la parte superior de la página para guardar la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4ae72-174">Click **Save** at the top of the page to save the application settings.</span></span>

   ![Activar el recurso de la aplicación web y, a continuación, guardarlo](media/TCimage24.png)

5. <span data-ttu-id="4ae72-176">El último paso consiste en cargar el código fuente de la aplicación conector a Azure que ha descargado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="4ae72-176">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="4ae72-177">En un explorador Web, vaya a https://<AzureAppResourceName>. scm.azurewebsites.net/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="4ae72-177">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="4ae72-178">Por ejemplo, si el nombre del recurso de la aplicación de Azure (que se menciona en el paso 2 de esta sección) es **twitterconnector**, entonces tendría https://twitterconnector.scm.azurewebsites.net/ZipDeployUique hacerlo.</span><span class="sxs-lookup"><span data-stu-id="4ae72-178">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **twitterconnector**, then you would go to https://twitterconnector.scm.azurewebsites.net/ZipDeployUi.</span></span>

6. <span data-ttu-id="4ae72-179">Arrastre y coloque el SampleConnector. zip (descargado en el paso 1) en esta página.</span><span class="sxs-lookup"><span data-stu-id="4ae72-179">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="4ae72-180">Una vez que se cargan los archivos y la implementación se realiza correctamente, la página tendrá un aspecto similar al de la siguiente captura de pantalla:</span><span class="sxs-lookup"><span data-stu-id="4ae72-180">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![Arrastre y coloque el archivo SampleConnector. zip en esta página](media/TCimage25.png)

## <a name="step-5-create-the-twitter-app"></a><span data-ttu-id="4ae72-182">Paso 5: crear la aplicación de Twitter</span><span class="sxs-lookup"><span data-stu-id="4ae72-182">Step 5: Create the Twitter app</span></span>

1. <span data-ttu-id="4ae72-183">Vaya a https://developer.twitter.com, inicie sesión con las credenciales de la cuenta de desarrollador de su organización y, a continuación, haga clic en **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-183">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![Ir a https://developer.twitter.com e iniciar sesión](media/TCimage25-5.png)
2. <span data-ttu-id="4ae72-185">Haga clic en **crear una aplicación**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-185">Click **Create an app**.</span></span>
   
   ![Ir a la página de aplicaciones para crear una aplicación](media/TCimage26.png)

3. <span data-ttu-id="4ae72-187">En **detalles**de la aplicación, agregue información sobre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4ae72-187">Under **App details**, add information about the application.</span></span>

   ![Escribir información sobre la aplicación](media/TCimage27.png)

4. <span data-ttu-id="4ae72-189">En el panel del programador de Twitter, seleccione la aplicación que acaba de crear y copie el identificador de aplicación que se muestra y guárdelo en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="4ae72-189">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="4ae72-190">A continuación, haga clic en **detalles**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-190">Then click **Details**.</span></span>
   
   ![Copiar y guardar el identificador de la aplicación](media/TCimage28.png)

5. <span data-ttu-id="4ae72-192">En la pestaña **claves y tokens** , en **claves** de la API de consumidor, copie la clave secreta de la API y guárdela en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="4ae72-192">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="4ae72-193">A continuación, haga clic en **crear** para generar un token de acceso y un secreto de token de acceso, y cópielos en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="4ae72-193">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![Copiar y guardar en clave secreta de la API](media/TCimage29.png)

   <span data-ttu-id="4ae72-195">A continuación, haga clic en **crear** para generar un token de acceso y un secreto de token de acceso, y cópielos en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="4ae72-195">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="4ae72-196">Haga clic en la pestaña **permisos** y configure los permisos como se muestra en la siguiente captura de pantalla:</span><span class="sxs-lookup"><span data-stu-id="4ae72-196">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![Configurar permisos](media/TCimage30.png)

7. <span data-ttu-id="4ae72-198">Una vez que haya guardado la configuración de permisos, haga clic en la pestaña detalles de la **aplicación** y, a continuación, haga clic en **Editar > editar detalles**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-198">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![Editar los detalles de la aplicación](media/TCimage31.png)

8. <span data-ttu-id="4ae72-200">Realice las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="4ae72-200">Do the following tasks:</span></span>

   - <span data-ttu-id="4ae72-201">Active la casilla para permitir que la aplicación conector inicie sesión en Twitter.</span><span class="sxs-lookup"><span data-stu-id="4ae72-201">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="4ae72-202">Agregue el URI de redireccionamiento de OAuth con el siguiente formato: \*\* \<connectorserviceuri>/views/twitteroauth\*\*, donde el valor de *connectorserviceuri* es la dirección URL de Azure App Service para su organización; por ejemplo, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span><span class="sxs-lookup"><span data-stu-id="4ae72-202">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![Permitir que la aplicación conector inicie sesión en Twitter y agregue el URI de redireccionamiento de OAuth](media/TCimage32.png)

<span data-ttu-id="4ae72-204">La aplicación de desarrollo de Twitter ya está lista para usarse.</span><span class="sxs-lookup"><span data-stu-id="4ae72-204">The Twitter developer app is now ready to use.</span></span>

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="4ae72-205">Paso 6: configurar la aplicación web del conector</span><span class="sxs-lookup"><span data-stu-id="4ae72-205">Step 6: Configure the connector web app</span></span> 

1. <span data-ttu-id="4ae72-206">Vaya a https://\<AzureAppResourceName>. azurewebsites.net (donde **AzureAppResourceName** es el nombre del recurso de la aplicación de Azure que ha nombrado en el paso 4).</span><span class="sxs-lookup"><span data-stu-id="4ae72-206">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="4ae72-207">Por ejemplo, si el nombre es **twitterconnector**, vaya a https://twitterconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="4ae72-207">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="4ae72-208">La Página principal de la aplicación es similar a la siguiente captura de pantalla:</span><span class="sxs-lookup"><span data-stu-id="4ae72-208">The home page of the app looks like the following screenshot:</span></span>

   ![Ir a la página de recursos de la aplicación de Azure](media/FBCimage41.png)

2. <span data-ttu-id="4ae72-210">Haga clic en **configurar** para mostrar una página de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="4ae72-210">Click **Configure** to display a sign in page.</span></span>

   ![Haga clic en configurar para mostrar la página de inicio de sesión](media/FBCimage42.png)

3. <span data-ttu-id="4ae72-212">En el cuadro identificador de inquilino, escriba o pegue el identificador de inquilino (que obtuvo en el paso 2).</span><span class="sxs-lookup"><span data-stu-id="4ae72-212">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="4ae72-213">En el cuadro contraseña, escriba o pegue el APISecretKey (que obtuvo en el paso 2) y, a continuación, haga clic en **establecer valores de configuración** para mostrar la página Detalles de la **configuración** .</span><span class="sxs-lookup"><span data-stu-id="4ae72-213">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

   ![Iniciar sesión con el identificador de inquilino y la clave secreta de API](media/TCimage35.png)

4. <span data-ttu-id="4ae72-215">En **detalles de configuración**, especifique las siguientes opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="4ae72-215">Under **Configuration Details**, enter the following configuration settings</span></span> 

   - <span data-ttu-id="4ae72-216">**Clave de API de Twitter** : el identificador de la aplicación de Twitter que creó en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="4ae72-216">**Twitter Api Key** – The app ID for the Twitter application that you created in Step 5.</span></span>
   - <span data-ttu-id="4ae72-217">**Clave secreta** de la API de Twitter: clave secreta de API de la aplicación de Twitter que creó en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="4ae72-217">**Twitter Api Secret Key** – The API secret key for the Twitter application that you created in Step 5.</span></span>
   - <span data-ttu-id="4ae72-218">**Token de acceso de Twitter** : el token de acceso que se creó en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="4ae72-218">**Twitter Access Token** – The access token that you created in Step 5.</span></span>
   - <span data-ttu-id="4ae72-219">**Token de acceso de Twitter secreto** : el secreto de token de acceso que ha creado en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="4ae72-219">**Twitter Access Token Secret** – The access token secret that you created in Step 5.</span></span>
   - <span data-ttu-id="4ae72-220">**Identificador de la aplicación AAD** : el identificador de la aplicación de la aplicación de Azure Active Directory que creó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="4ae72-220">**AAD Application ID** – The application ID for the Azure Active Directory app that you created in Step 2</span></span>
   - <span data-ttu-id="4ae72-221">**Secreto de la aplicación AAD** : el valor del secreto APISecretKey que creó en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="4ae72-221">**AAD Application Secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   - <span data-ttu-id="4ae72-222">**URI de la aplicación AAD** : el URI de la aplicación AAD obtenido en el paso 2; por ejemplo, `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.</span><span class="sxs-lookup"><span data-stu-id="4ae72-222">**AAD Application Uri** – The AAD application Uri obtained in Step 2; for example, `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.</span></span>
   - <span data-ttu-id="4ae72-223">**Clave de instrumentación de App Insights** : Deje este cuadro en blanco.</span><span class="sxs-lookup"><span data-stu-id="4ae72-223">**App Insights Instrumentation Key** – Leave this box blank.</span></span>

5. <span data-ttu-id="4ae72-224">Haga clic en **Guardar** para guardar la configuración del conector.</span><span class="sxs-lookup"><span data-stu-id="4ae72-224">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security-and-compliance-center"></a><span data-ttu-id="4ae72-225">Paso 7: configurar un conector personalizado en el centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="4ae72-225">Step 7: Set up a custom connector in the security and compliance center</span></span>

1.  <span data-ttu-id="4ae72-226">Vaya a <https://protection.office.com> y, a continuación, haga clic en **datos de terceros de importación \> \> de gobierno de datos**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-226">Go to <https://protection.office.com> and then click **Data governance \> Import \> Archive third-party data**.</span></span>

    ![Ir a la página archivar datos de terceros en el centro de seguridad y cumplimiento](media/TCimage36.png)

2. <span data-ttu-id="4ae72-228">Haga clic en **Agregar un conector** y, a continuación, en **Twitter**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-228">Click **Add a connector** and then click **Twitter**.</span></span>

   ![Haga clic en agregar un conector para agregar un conector de Twitter](media/TCimage37.png)

3. <span data-ttu-id="4ae72-230">En la página **Agregar aplicación de conector** , escriba la siguiente información y, a continuación, haga clic en **validar conector**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-230">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    - <span data-ttu-id="4ae72-231">En el primer cuadro, escriba un nombre para el conector, como **Twitter**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-231">In the first box, type a name for the connector, such as **Twitter**.</span></span>
    - <span data-ttu-id="4ae72-232">En el segundo cuadro, escriba o pegue el valor de APISecretKey que agregó en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="4ae72-232">In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    - <span data-ttu-id="4ae72-233">En el tercer cuadro, escriba o pegue la dirección URL de Azure App Service; por ejemplo, **https://twitterconnector.azurewebsites.net**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-233">In the third box, type or paste the Azure app service URL; for example, **https://twitterconnector.azurewebsites.net**.</span></span>

   <span data-ttu-id="4ae72-234">Una vez validado correctamente el conector, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-234">After the connector is successfully validated, click **Next**.</span></span>

   ![Especificar la configuración de la aplicación conector](media/TCimage38.png)

4. <span data-ttu-id="4ae72-236">Haga clic en **iniciar sesión con la aplicación conector**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-236">Click **Login with Connector App**.</span></span>

   ![Iniciar sesión en la aplicación conector](media/TCimage39.png)

5. <span data-ttu-id="4ae72-238">Escriba o pegue el APISecretKey de nuevo y, a continuación, haga clic en **iniciar sesión en el servicio de conector**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-238">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![Escribir la clave secreta de la API para iniciar sesión en el servicio conector](media/TCimage40.png)

6. <span data-ttu-id="4ae72-240">Haga clic en **continuar con Twitter**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-240">Click **Continue with Twitter**.</span></span>

7. <span data-ttu-id="4ae72-241">En la página inicio de sesión de Twitter, inicie sesión con las credenciales de la cuenta de Twitter de su organización.</span><span class="sxs-lookup"><span data-stu-id="4ae72-241">On the Twitter sign in page, sign in using the credentials for the account for your organization’s Twitter account.</span></span>

   ![Iniciar sesión en la cuenta de Twitter](media/TCimage42.png)

   <span data-ttu-id="4ae72-243">Después de iniciar sesión, la página de Twitter mostrará el siguiente mensaje de error "el trabajo del conector de Twitter se configuró correctamente".</span><span class="sxs-lookup"><span data-stu-id="4ae72-243">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

8. <span data-ttu-id="4ae72-244">Haga clic en **Finalizar** para completar la configuración del conector de Twitter.</span><span class="sxs-lookup"><span data-stu-id="4ae72-244">Click **Finish** to complete setting up the Twitter connector.</span></span>

9. <span data-ttu-id="4ae72-245">En la página **Establecer filtros** , puede aplicar un filtro para importar (y archivar) los elementos que tengan una antigüedad determinada.</span><span class="sxs-lookup"><span data-stu-id="4ae72-245">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="4ae72-246">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4ae72-246">Click **Next**.</span></span>

   ![Configurar el filtro para importar elementos de una antigüedad determinada](media/TCimage44.png)

10. <span data-ttu-id="4ae72-248">En la página **establecer cuenta de almacenamiento** , escriba la dirección de correo electrónico de un buzón de correo de Office 365 al que se importarán los elementos de Twitter.</span><span class="sxs-lookup"><span data-stu-id="4ae72-248">On the **Set Storage Account** page, type the email address of an Office 365 mailbox that the Twitter items will be imported to.</span></span>

    ![Especifique un buzón de correo de Office 365 para importar elementos de Twitter a](media/TCimage45.png)

11. <span data-ttu-id="4ae72-250">Revise la configuración y, a continuación, haga clic en **Finalizar** para completar la configuración del conector en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="4ae72-250">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![Revise la configuración y, a continuación, haga clic en finalizar](media/TCimage46.png)

    ![Pantalla que muestra que se ha completado la configuración del conector](media/TCimage47.png)

12. <span data-ttu-id="4ae72-253">Vaya a la página **archivar datos de terceros** para ver el progreso del proceso de importación.</span><span class="sxs-lookup"><span data-stu-id="4ae72-253">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![Nuevo conector mostrado en el centro de seguridad y cumplimiento](media/TCimage48.png)
