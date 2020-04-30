---
title: Implementación de un conector para archivar datos de páginas empresariales de Facebook
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
description: Los administradores pueden configurar un conector nativo para importar y archivar las páginas de empresa de Facebook a Microsoft 365. Una vez que estos datos se han importado a Microsoft 365, puede usar las características de cumplimiento, como las directivas de retención legal, búsqueda de contenido y retención, para administrar el gobierno de los datos de Facebook de la organización.
ms.openlocfilehash: 9ef7a2f3a24201ff4a32839671df7430a492bb44
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943043"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a><span data-ttu-id="0c076-104">Implementación de un conector para archivar datos de páginas empresariales de Facebook</span><span class="sxs-lookup"><span data-stu-id="0c076-104">Deploy a connector to archive Facebook Business pages data</span></span>

<span data-ttu-id="0c076-105">Este artículo contiene el proceso paso a paso para implementar un conector que usa el servicio de importación de Office 365 para importar datos de las páginas empresariales de Facebook a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c076-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="0c076-106">Para obtener información general de alto nivel de este proceso y una lista de los requisitos previos necesarios para implementar un conector de Facebook, consulte [configurar un conector para archivar datos de Facebook](archive-facebook-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="0c076-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="0c076-107">Paso 1: crear una aplicación en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0c076-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="0c076-108">Vaya a <https://portal.azure.com> e inicie sesión con las credenciales de una cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="0c076-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

    ![Crear una aplicación en AAD](../media/FBCimage1.png)

2. <span data-ttu-id="0c076-110">En el panel de navegación izquierdo, haga clic en **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0c076-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![Haga clic en Azure Active Directory](../media/FBCimage2.png)

3. <span data-ttu-id="0c076-112">En el panel de navegación izquierdo, haga clic en **registros de aplicaciones (versión preliminar)** y, a continuación, haga clic en **nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="0c076-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![Haga clic en \* \* registros de aplicaciones (versión preliminar) \* \* y, a continuación, haga clic en \* \* registro nuevo \* \*](../media/FBCimage3.png)

4. <span data-ttu-id="0c076-114">Registrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0c076-114">Register the application.</span></span> <span data-ttu-id="0c076-115">En URI de redireccionamiento, seleccione Web en la lista desplegable tipo de <https://portal.azure.com> aplicación y, a continuación, escriba en el cuadro del URI.</span><span class="sxs-lookup"><span data-stu-id="0c076-115">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![Registrar la aplicación](../media/FBCimage4.png)

5. <span data-ttu-id="0c076-117">Copie el identificador de la **aplicación (cliente)** y el **directorio (inquilino)** y guárdelos en un archivo de texto u otra ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="0c076-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="0c076-118">Estos identificadores se usan en pasos posteriores.</span><span class="sxs-lookup"><span data-stu-id="0c076-118">You use these IDs in later steps.</span></span>

   ![Copiar el identificador de la aplicación y el identificador del directorio y guardarlos](../media/FBCimage5.png)

6. <span data-ttu-id="0c076-120">Vaya a **certificados & secretos para la nueva aplicación.**</span><span class="sxs-lookup"><span data-stu-id="0c076-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![Ir a certificados & secretos para la nueva aplicación](../media/FBCimage6.png)

7. <span data-ttu-id="0c076-122">Haga clic en **nuevo secreto de cliente**</span><span class="sxs-lookup"><span data-stu-id="0c076-122">Click **New client secret**</span></span>

   ![Haga clic en nuevo secreto de cliente](../media/FBCimage7.png)

8. <span data-ttu-id="0c076-124">Cree un secreto nuevo.</span><span class="sxs-lookup"><span data-stu-id="0c076-124">Create a new secret.</span></span> <span data-ttu-id="0c076-125">En el cuadro Descripción, escriba el secreto y, a continuación, elija un período de expiración.</span><span class="sxs-lookup"><span data-stu-id="0c076-125">In the description box, type the secret and then choose an expiration period.</span></span> 

    ![Escriba el secreto y, a continuación, elija un período de expiración](../media/FBCimage8.png)

9. <span data-ttu-id="0c076-127">Copie el valor del secreto y guárdelo en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="0c076-127">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="0c076-128">Este es el secreto de la aplicación de AAD que se usa en pasos posteriores.</span><span class="sxs-lookup"><span data-stu-id="0c076-128">This is the AAD application secret that you use in later steps.</span></span>

   ![Copiar el valor del secreto y guardarlo](../media/FBCimage9.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="0c076-130">Paso 2: implementar el servicio Web del conector desde GitHub a su cuenta de Azure</span><span class="sxs-lookup"><span data-stu-id="0c076-130">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="0c076-131">Vaya a [este sitio de github](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) y haga clic en **implementar en Azure**.</span><span class="sxs-lookup"><span data-stu-id="0c076-131">Go to [this GitHub site](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Haga clic en implementar en Azure](../media/FBCGithubApp.png)

2. <span data-ttu-id="0c076-133">Después de hacer clic en **implementar en Azure**, se le redirigirá a un portal de Azure con una página de plantilla personalizada.</span><span class="sxs-lookup"><span data-stu-id="0c076-133">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="0c076-134">Rellene los detalles de **conceptos básicos** y **configuración** y, a continuación, haga clic en **comprar**.</span><span class="sxs-lookup"><span data-stu-id="0c076-134">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

    - <span data-ttu-id="0c076-135">**Suscripción:** Seleccione la suscripción a Azure en la que desea implementar el servicio Web de conector de páginas empresariales de Facebook.</span><span class="sxs-lookup"><span data-stu-id="0c076-135">**Subscription:** Select your Azure subscription that you want to deploy the Facebook Business pages connector web service to.</span></span>
    
    - <span data-ttu-id="0c076-136">**Grupo de recursos:** Elija o cree un nuevo grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="0c076-136">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="0c076-137">Un grupo de recursos es un contenedor que contiene recursos relacionados para una solución de Azure.</span><span class="sxs-lookup"><span data-stu-id="0c076-137">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="0c076-138">**Ubicación:** Elija una ubicación.</span><span class="sxs-lookup"><span data-stu-id="0c076-138">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="0c076-139">**Nombre de la aplicación web:** Proporcione un nombre único para la aplicación web del conector.</span><span class="sxs-lookup"><span data-stu-id="0c076-139">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="0c076-140">El nombre debe tener entre 3 y 18 caracteres de longitud.</span><span class="sxs-lookup"><span data-stu-id="0c076-140">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="0c076-141">Este nombre se usa para crear la dirección URL de Azure App Service; por ejemplo, si proporciona el nombre de la aplicación Web de **FBconnector** , la dirección URL del servicio de aplicación de Azure será **FBconnector.azurewebsites.net**.</span><span class="sxs-lookup"><span data-stu-id="0c076-141">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **fbconnector** then the Azure app service URL  will be **fbconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="0c076-142">**tenantId:** El identificador de inquilino de su organización de Microsoft 365 que copió después de crear la aplicación de conector de Facebook en Azure Active Directory en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="0c076-142">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="0c076-143">**APISecretKey:** Puede escribir cualquier valor como secreto.</span><span class="sxs-lookup"><span data-stu-id="0c076-143">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="0c076-144">Se usa para obtener acceso a la aplicación web del conector en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="0c076-144">This is used to access the connector web app in Step 5.</span></span>
   
     ![Haga clic en crear un recurso y escriba la cuenta de almacenamiento](../media/FBCimage12.png)

3. <span data-ttu-id="0c076-146">Una vez completada la implementación, la página tendrá un aspecto similar al de la siguiente captura de pantalla:</span><span class="sxs-lookup"><span data-stu-id="0c076-146">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

     ![Haga clic en almacenamiento y, a continuación, en cuenta de almacenamiento](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a><span data-ttu-id="0c076-148">Paso 3: registrar la aplicación de Facebook</span><span class="sxs-lookup"><span data-stu-id="0c076-148">Step 3: Register the Facebook app</span></span>

1. <span data-ttu-id="0c076-149">Vaya a <https://developers.facebook.com>, inicie sesión con las credenciales de la cuenta de las páginas de empresa de Facebook de su organización y, a continuación, haga clic en **Agregar nueva aplicación**.</span><span class="sxs-lookup"><span data-stu-id="0c076-149">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization's Facebook Business pages, and then click **Add New App**.</span></span>

   ![Adición de una nueva aplicación para la página empresarial de Facebook](../media/FBCimage25.png)

2. <span data-ttu-id="0c076-151">Cree un nuevo identificador de aplicación.</span><span class="sxs-lookup"><span data-stu-id="0c076-151">Create a new app ID.</span></span>

   ![Crear un nuevo identificador de aplicación](../media/FBCimage26.png)

3. <span data-ttu-id="0c076-153">En el panel de navegación izquierdo, haga clic en **Agregar productos** y, a continuación, haga clic en **configurar** en la ventana de **Inicio de sesión de Facebook** .</span><span class="sxs-lookup"><span data-stu-id="0c076-153">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![Haga clic en agregar productos](../media/FBCimage27.png)

4. <span data-ttu-id="0c076-155">En la página integrar inicio de sesión de Facebook, haga clic en **Web**.</span><span class="sxs-lookup"><span data-stu-id="0c076-155">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![Haga clic en Web en la página integrar inicio de sesión de Facebook](../media/FBCimage28.png)

5. <span data-ttu-id="0c076-157">Agregue la dirección URL de Azure App Service; por ejemplo `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="0c076-157">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![Agregar la dirección URL de Azure App Service](../media/FBCimage29.png)

6. <span data-ttu-id="0c076-159">Complete la sección QuickStart de la configuración de inicio de sesión de Facebook.</span><span class="sxs-lookup"><span data-stu-id="0c076-159">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![Completar la sección QuickStart](../media/FBCimage30.png)

7. <span data-ttu-id="0c076-161">En el panel de navegación izquierdo, en **Inicio de sesión de Facebook**, haga clic en **configuración**y agregue el URI de redireccionamiento de OAuth en el cuadro **válidos URI de redirección de OAuth** .</span><span class="sxs-lookup"><span data-stu-id="0c076-161">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="0c076-162">Use el formato \*\* \<connectorserviceuri>/views/facebookoauth\*\*, donde el valor de connectorserviceuri es la dirección URL de Azure App Service para su organización; por ejemplo, `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="0c076-162">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![Agregar el URI de redireccionamiento de OAuth al cuadro URI de redireccionamiento de OAuth válido](../media/FBCimage31.png)

8. <span data-ttu-id="0c076-164">En el panel de navegación izquierdo, haga clic en **Agregar productos** y, a continuación, en **webhooks.**</span><span class="sxs-lookup"><span data-stu-id="0c076-164">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="0c076-165">En el menú desplegable **Página** , haga clic en **Página**.</span><span class="sxs-lookup"><span data-stu-id="0c076-165">In the **Page** pull-down menu, click **Page**.</span></span> 

   ![Haga clic en agregar productos y, a continuación, haga clic en \* \* webhooks](../media/FBCimage32.png)

9. <span data-ttu-id="0c076-167">Agregue la dirección URL de devolución de llamada de webhook y agregue un token de comprobación.</span><span class="sxs-lookup"><span data-stu-id="0c076-167">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="0c076-168">El formato de la dirección URL de devolución de llamada, use el formato \*\* <connectorserviceuri>/API/FbPageWebhook\*\*, donde el valor de connectorserviceuri es la dirección URL de Azure App Service para su organización; por ejemplo `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="0c076-168">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span> 

    <span data-ttu-id="0c076-169">El token de comprobación debe ser similar a una contraseña segura.</span><span class="sxs-lookup"><span data-stu-id="0c076-169">The verify token should similar to a strong password.</span></span> <span data-ttu-id="0c076-170">Copie el token de comprobación en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="0c076-170">Copy the verify token to a text file or other storage location.</span></span>

        ![Add the verify token](../media/FBCimage33.png)

10. <span data-ttu-id="0c076-171">Pruebe y suscríbase al extremo para la fuente.</span><span class="sxs-lookup"><span data-stu-id="0c076-171">Test and subscribe to the endpoint for feed.</span></span>

    ![Probar y suscribirse al extremo](../media/FBCimage34.png)

11. <span data-ttu-id="0c076-173">Agregue una dirección URL de privacidad, un icono de aplicación y un uso empresarial.</span><span class="sxs-lookup"><span data-stu-id="0c076-173">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="0c076-174">Además, copie el identificador de aplicación y el secreto de aplicación en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="0c076-174">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![Agregar una dirección URL de privacidad, un icono de aplicación y un uso empresarial](../media/FBCimage35.png)

12. <span data-ttu-id="0c076-176">Hacer que la aplicación sea pública.</span><span class="sxs-lookup"><span data-stu-id="0c076-176">Make the app public.</span></span>

    ![Hacer que la aplicación sea pública](../media/FBCimage36.png)

13. <span data-ttu-id="0c076-178">Agregue un usuario al rol de administrador o de evaluador.</span><span class="sxs-lookup"><span data-stu-id="0c076-178">Add user to the admin or tester role.</span></span>

    ![Agregar un usuario al rol de administrador o de evaluador](../media/FBCimage37.png)

14. <span data-ttu-id="0c076-180">Agregue el permiso de **acceso a contenido público** de la página.</span><span class="sxs-lookup"><span data-stu-id="0c076-180">Add the **Page Public Content Access** permission.</span></span>

    ![DD la página permiso de acceso al contenido público](../media/FBCimage38.png)

15. <span data-ttu-id="0c076-182">Permiso agregar páginas de administración.</span><span class="sxs-lookup"><span data-stu-id="0c076-182">Add Manage Pages permission.</span></span>

    ![Permiso para agregar páginas de administración](../media/FBCimage39.png)

16. <span data-ttu-id="0c076-184">Obtenga la aplicación revisada por Facebook.</span><span class="sxs-lookup"><span data-stu-id="0c076-184">Get the application reviewed by Facebook.</span></span>

    ![Obtener la aplicación revisada por Facebook](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="0c076-186">Paso 4: configurar la aplicación web del conector</span><span class="sxs-lookup"><span data-stu-id="0c076-186">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="0c076-187">Vaya a https://\<AzureAppResourceName>. azurewebsites.net (donde AzureAppResourceName es el nombre del recurso de la aplicación de Azure que ha nombrado en el paso 4), por ejemplo, si el nombre es `https://fbconnector.azurewebsites.net` **FBconnector**, vaya a.</span><span class="sxs-lookup"><span data-stu-id="0c076-187">Go to https://\<AzureAppResourceName>.azurewebsites.net (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4) For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="0c076-188">La Página principal de la aplicación será similar a la siguiente captura de pantalla:</span><span class="sxs-lookup"><span data-stu-id="0c076-188">The home page of the app will look like the following screenshot:</span></span>

   ![Ir a la aplicación web del conector](../media/FBCimage41.png)

2. <span data-ttu-id="0c076-190">Haga clic en **configurar** para mostrar una página de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="0c076-190">Click **Configure** to display a sign in page.</span></span>
 
   ![Haga clic en configurar para mostrar una página de inicio de sesión](../media/FBCimage42.png)

3. <span data-ttu-id="0c076-192">En el cuadro identificador de inquilino, escriba o pegue el identificador de inquilino (que obtuvo en el paso 2).</span><span class="sxs-lookup"><span data-stu-id="0c076-192">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="0c076-193">En el cuadro contraseña, escriba o pegue el APISecretKey (que obtuvo en el paso 2) y, a continuación, haga clic en **establecer valores de configuración** para mostrar la página Detalles de la configuración.</span><span class="sxs-lookup"><span data-stu-id="0c076-193">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

    ![Iniciar sesión con el identificador de inquilino y la contraseña y ir a la página de detalles de configuración](../media/FBCimage43.png)

4. <span data-ttu-id="0c076-195">Especifique las siguientes opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="0c076-195">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="0c076-196">**Identificador de la aplicación de Facebook:** El identificador de aplicación de la aplicación de Facebook que obtuvo en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="0c076-196">**Facebook application ID:** The app ID for the Facebook application that you obtained in Step 3.</span></span>
   
   - <span data-ttu-id="0c076-197">**Secreto de la aplicación de Facebook:** El secreto de aplicación para la aplicación de Facebook que obtuvo en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="0c076-197">**Facebook application secret:** The app secret for the Facebook application that you obtained in Step 3.</span></span>
   
   - <span data-ttu-id="0c076-198">**Token de comprobación de los webhooks de Facebook:** El token de comprobación que ha creado en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="0c076-198">**Facebook webhooks verify token:** The verify token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="0c076-199">**Identificador de la aplicación de AAD:** El identificador de aplicación de la aplicación de Azure Active Directory que ha creado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="0c076-199">**AAD application ID:** The application ID for the Azure Active Directory app that you created in Step 1.</span></span>
   
   - <span data-ttu-id="0c076-200">**Secreto de la aplicación AAD:** El valor del secreto APISecretKey que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="0c076-200">**AAD application secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="0c076-201">Haga clic en **Guardar** para guardar la configuración del conector.</span><span class="sxs-lookup"><span data-stu-id="0c076-201">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="0c076-202">Paso 5: configurar un conector de Facebook en el centro de cumplimiento de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c076-202">Step 5: Set up a Facebook connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="0c076-203">Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y, a continuación, haga clic en **conectores de datos** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="0c076-203">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="0c076-204">En la página **conectores de datos (vista previa)** , en **páginas empresariales de Facebook**, haga clic en **Ver**.</span><span class="sxs-lookup"><span data-stu-id="0c076-204">On the **Data connectors (preview)** page under **Facebook Business pages**, click **View**.</span></span>

3. <span data-ttu-id="0c076-205">En la página **páginas empresariales de Facebook** , haga clic en **Agregar conector**.</span><span class="sxs-lookup"><span data-stu-id="0c076-205">On the **Facebook business pages** page, click **Add connector**.</span></span>

4. <span data-ttu-id="0c076-206">En la página **condiciones de servicio** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0c076-206">On the **Terms of service** page, click **Accept**.</span></span>

5.  <span data-ttu-id="0c076-207">En la página **agregar credenciales para la aplicación de conector** , escriba la siguiente información y, a continuación, haga clic en **validar conexión**.</span><span class="sxs-lookup"><span data-stu-id="0c076-207">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

    ![Especificar credenciales de aplicación de conector](../media/TCimage38.png)

    - <span data-ttu-id="0c076-209">En el cuadro **nombre** , escriba un nombre para el conector, como **Página de noticias de Facebook**.</span><span class="sxs-lookup"><span data-stu-id="0c076-209">In the **Name** box, type a name for the connector, such as **Facebook news page**.</span></span>
    
    - <span data-ttu-id="0c076-210">En el cuadro **dirección URL de conexión** , escriba o pegue la dirección URL de Azure App Service; por ejemplo `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="0c076-210">In the **Connection URL** box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="0c076-211">En el cuadro **contraseña** , escriba o pegue el valor de la APISecretKey que agregó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="0c076-211">In the **Password** box, type or paste the value of the APISecretKey that you added in Step 2.</span></span>
    
    - <span data-ttu-id="0c076-212">En el cuadro identificador de la **aplicación de Azure** , escriba o pegue el valor del identificador de la aplicación (cliente) también denominado identificador de la aplicación AAD que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="0c076-212">In the **Azure App ID** box, type or paste the value of the Application (client) ID also called as AAD Application ID that you created in Step 1.</span></span>
 
6. <span data-ttu-id="0c076-213">Una vez validada correctamente la conexión, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0c076-213">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="0c076-214">En la página **autorizar a Microsoft 365 a importar datos** , escriba o pegue el APISecretKey de nuevo y, a continuación, haga clic en **iniciar sesión en la aplicación web**.</span><span class="sxs-lookup"><span data-stu-id="0c076-214">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click **Login web app**.</span></span>

8. <span data-ttu-id="0c076-215">En la página **configurar la aplicación** para el conector de Facebook, haga clic en **iniciar sesión con Facebook** e inicie sesión con las credenciales de la cuenta de las páginas de empresa de Facebook de su organización.</span><span class="sxs-lookup"><span data-stu-id="0c076-215">On the **Configure Facebook connector app** page, click **Login with Facebook** and log in using the credentials for the account for your organization's Facebook Business pages.</span></span> <span data-ttu-id="0c076-216">Asegúrese de que la cuenta de Facebook a la que ha iniciado sesión tenga asignado el rol de administrador de las páginas empresariales de Facebook de su organización.</span><span class="sxs-lookup"><span data-stu-id="0c076-216">Make sure the Facebook account that you logged in to is assigned the admin role for your organization's Facebook Business pages.</span></span>

   ![Iniciar sesión con Facebook](../media/FBCimage50.png)

9. <span data-ttu-id="0c076-218">Se muestra una lista de las páginas de negocio administradas por la cuenta de Facebook en la que inició sesión.</span><span class="sxs-lookup"><span data-stu-id="0c076-218">A list of the business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="0c076-219">Seleccione la página que desea archivar y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0c076-219">Select the page to archive and then click **Next**.</span></span>

    ![Seleccione la página de empresa de la organización que desea archivar](../media/FBCimage52.png)

10. <span data-ttu-id="0c076-221">Haga clic en **continuar** para salir de la instalación de la aplicación del servicio conector.</span><span class="sxs-lookup"><span data-stu-id="0c076-221">Click **Continue** to exit the setup of the connector service app.</span></span>

11. <span data-ttu-id="0c076-222">En la página **Establecer filtros** , puede aplicar un filtro para importar inicialmente los elementos que tienen una antigüedad determinada.</span><span class="sxs-lookup"><span data-stu-id="0c076-222">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="0c076-223">Seleccione una edad y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0c076-223">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="0c076-224">En la página **Elegir ubicación de almacenamiento** , escriba la dirección de correo electrónico del buzón de correo de Microsoft 365 al que se importarán los elementos de Facebook y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0c076-224">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Facebook items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="0c076-225">En el **acuerdo proporcionar consentimiento del administrador**, haga clic en **proporcionar consentimiento** y, a continuación, siga los pasos.</span><span class="sxs-lookup"><span data-stu-id="0c076-225">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="0c076-226">Debe ser administrador global para dar su consentimiento al servicio de importación de Office 365 para obtener acceso a los datos de su organización.</span><span class="sxs-lookup"><span data-stu-id="0c076-226">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

14. <span data-ttu-id="0c076-227">Haga clic en **siguiente** para revisar la configuración del conector y, a continuación, haga clic en **Finalizar** para completar la configuración del conector.</span><span class="sxs-lookup"><span data-stu-id="0c076-227">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

15. <span data-ttu-id="0c076-228">En el centro de cumplimiento, vaya a la página **conectores de datos** y haga clic en la pestaña **conectores** para ver el progreso del proceso de importación.</span><span class="sxs-lookup"><span data-stu-id="0c076-228">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
