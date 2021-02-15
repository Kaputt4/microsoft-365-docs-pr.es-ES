---
title: Implementar un conector para archivar datos de páginas empresariales de Facebook
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
description: Los administradores pueden configurar un conector nativo para importar y archivar páginas empresariales de Facebook en Microsoft 365. Después de importar estos datos a Microsoft 365, puede usar características de cumplimiento como suspensión legal, búsqueda de contenido y directivas de retención para administrar el gobierno de los datos de Facebook de su organización.
ms.openlocfilehash: b771c50eb5c2eb5f99269f1f399d27043ebee6bb
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619956"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a><span data-ttu-id="ee2ba-104">Implementar un conector para archivar datos de páginas empresariales de Facebook</span><span class="sxs-lookup"><span data-stu-id="ee2ba-104">Deploy a connector to archive Facebook Business pages data</span></span>

<span data-ttu-id="ee2ba-105">Este artículo contiene el proceso paso a paso para implementar un conector que usa el servicio de importación de Office 365 para importar datos de páginas de Facebook Business a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="ee2ba-106">Para obtener información general de alto nivel sobre este proceso y una lista de los requisitos previos necesarios para implementar un conector de Facebook, vea Configurar un conector para archivar [datos de Facebook.](archive-facebook-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="ee2ba-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="ee2ba-107">Paso 1: Crear una aplicación en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ee2ba-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="ee2ba-108">Vaya a <https://portal.azure.com> e inicie sesión con las credenciales de una cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

    ![Crear una aplicación en AAD](../media/FBCimage1.png)

2. <span data-ttu-id="ee2ba-110">En el panel de navegación izquierdo, haga clic **en Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="ee2ba-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![Haga clic en Azure Active Directory](../media/FBCimage2.png)

3. <span data-ttu-id="ee2ba-112">En el panel de navegación izquierdo, haga clic en **Registros de aplicaciones (vista previa)** y, a continuación, haga clic **en Nuevo registro.**</span><span class="sxs-lookup"><span data-stu-id="ee2ba-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![Haga clic en **Registros de aplicaciones (versión preliminar)** y, a continuación, haga clic en **Nuevo registro**](../media/FBCimage3.png)

4. <span data-ttu-id="ee2ba-114">Registre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-114">Register the application.</span></span> <span data-ttu-id="ee2ba-115">En URI de redireccionamiento, seleccione Web en la lista desplegable de tipos de aplicación y, a continuación, <https://portal.azure.com> escriba el cuadro para el URI.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-115">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![Registrar la aplicación](../media/FBCimage4.png)

5. <span data-ttu-id="ee2ba-117">Copie el **id. de aplicación (cliente)** y el id. de directorio **(inquilino)** y guárdelos en un archivo de texto u otra ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="ee2ba-118">Estos iDs se usan en pasos posteriores.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-118">You use these IDs in later steps.</span></span>

   ![Copie el id. de aplicación y el id. de directorio y guárdelos](../media/FBCimage5.png)

6. <span data-ttu-id="ee2ba-120">Ve a **Certificados & secretos de la nueva aplicación.**</span><span class="sxs-lookup"><span data-stu-id="ee2ba-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![Vaya a Certificados & secretos de la nueva aplicación](../media/FBCimage6.png)

7. <span data-ttu-id="ee2ba-122">Haga clic **en Nuevo secreto de cliente**</span><span class="sxs-lookup"><span data-stu-id="ee2ba-122">Click **New client secret**</span></span>

   ![Haga clic en Nuevo secreto de cliente](../media/FBCimage7.png)

8. <span data-ttu-id="ee2ba-124">Cree un nuevo secreto.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-124">Create a new secret.</span></span> <span data-ttu-id="ee2ba-125">En el cuadro de descripción, escriba el secreto y, a continuación, elija un período de expiración.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-125">In the description box, type the secret and then choose an expiration period.</span></span>

    ![Escriba el secreto y, a continuación, elija un período de expiración](../media/FBCimage8.png)

9. <span data-ttu-id="ee2ba-127">Copie el valor del secreto y guárdelo en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-127">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="ee2ba-128">Este es el secreto de aplicación de AAD que se usa en pasos posteriores.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-128">This is the AAD application secret that you use in later steps.</span></span>

   ![Copiar el valor del secreto y guardarlo](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="ee2ba-130">Paso 2: Implementar el servicio web del conector desde GitHub en su cuenta de Azure</span><span class="sxs-lookup"><span data-stu-id="ee2ba-130">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="ee2ba-131">Vaya a [este sitio de GitHub](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) y haga **clic en Implementar en Azure.**</span><span class="sxs-lookup"><span data-stu-id="ee2ba-131">Go to [this GitHub site](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Haga clic en Implementar en Azure](../media/FBCGithubApp.png)

2. <span data-ttu-id="ee2ba-133">Después de hacer **clic en Implementar en Azure,** se le redirigirá a un portal de Azure con una página de plantilla personalizada.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-133">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="ee2ba-134">Rellene los detalles **de conceptos básicos** **y configuración** y, a continuación, haga clic en **Comprar**.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-134">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   - <span data-ttu-id="ee2ba-135">**Suscripción:** Seleccione la suscripción de Azure en la que desea implementar el servicio web del conector de páginas empresariales de Facebook.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-135">**Subscription:** Select your Azure subscription that you want to deploy the Facebook Business pages connector web service to.</span></span>

   - <span data-ttu-id="ee2ba-136">**Grupo de recursos:** Elija o cree un nuevo grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-136">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="ee2ba-137">Un grupo de recursos es un contenedor que contiene recursos relacionados para una solución de Azure.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-137">A resource group is a container that holds related resources for an Azure solution.</span></span>

   - <span data-ttu-id="ee2ba-138">**Ubicación:** Elija una ubicación.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-138">**Location:** Choose a location.</span></span>

   - <span data-ttu-id="ee2ba-139">**Nombre de aplicación web:** Proporcione un nombre único para la aplicación web del conector.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-139">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="ee2ba-140">El nombre debe tener entre 3 y 18 caracteres de longitud.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-140">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="ee2ba-141">Este nombre se usa para crear la dirección URL del servicio de aplicaciones de Azure; por ejemplo, si proporciona el nombre de la aplicación web **de fbconnector,** la dirección URL del servicio de aplicaciones de Azure **será fbconnector.azurewebsites.net**.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-141">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **fbconnector** then the Azure app service URL  will be **fbconnector.azurewebsites.net**.</span></span>

   - <span data-ttu-id="ee2ba-142">**tenantId:** El id. de inquilino de su organización de Microsoft 365 que copió después de crear la aplicación conector de Facebook en Azure Active Directory en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-142">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

   - <span data-ttu-id="ee2ba-143">**APISecretKey:** Puede escribir cualquier valor como secreto.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-143">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="ee2ba-144">Esto se usa para obtener acceso a la aplicación web del conector en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-144">This is used to access the connector web app in Step 5.</span></span>

     ![Haga clic en Crear una cuenta de almacenamiento de tipo y recurso](../media/FBCimage12.png)

3. <span data-ttu-id="ee2ba-146">Una vez que la implementación se realiza correctamente, la página tendrá un aspecto similar a la siguiente captura de pantalla:</span><span class="sxs-lookup"><span data-stu-id="ee2ba-146">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![Haga clic en Almacenamiento y, a continuación, haga clic en Cuenta de almacenamiento](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a><span data-ttu-id="ee2ba-148">Paso 3: Registrar la aplicación de Facebook</span><span class="sxs-lookup"><span data-stu-id="ee2ba-148">Step 3: Register the Facebook app</span></span>

1. <span data-ttu-id="ee2ba-149">Vaya a , inicie sesión con las credenciales de la cuenta de las páginas empresariales de Facebook de su organización y, a continuación, haga clic <https://developers.facebook.com> **en Agregar nueva aplicación.**</span><span class="sxs-lookup"><span data-stu-id="ee2ba-149">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization's Facebook Business pages, and then click **Add New App**.</span></span>

   ![Agregar una nueva página de aplicación para empresas de Facebook](../media/FBCimage25.png)

2. <span data-ttu-id="ee2ba-151">Crea un nuevo identificador de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-151">Create a new app ID.</span></span>

   ![Crear un nuevo identificador de aplicación](../media/FBCimage26.png)

3. <span data-ttu-id="ee2ba-153">En el panel de navegación izquierdo, haga clic **en Agregar productos** y, a continuación, haga clic en Configurar **en** el icono Inicio de sesión **de Facebook.**</span><span class="sxs-lookup"><span data-stu-id="ee2ba-153">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![Haga clic en Agregar productos](../media/FBCimage27.png)

4. <span data-ttu-id="ee2ba-155">En la página Integrar inicio de sesión de Facebook, haga clic **en Web.**</span><span class="sxs-lookup"><span data-stu-id="ee2ba-155">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![Haga clic en Web en la página Integrar inicio de sesión de Facebook](../media/FBCimage28.png)

5. <span data-ttu-id="ee2ba-157">Agregar la dirección URL del servicio de aplicaciones de Azure; por `https://fbconnector.azurewebsites.net` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-157">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![Agregar la dirección URL del servicio de aplicaciones de Azure](../media/FBCimage29.png)

6. <span data-ttu-id="ee2ba-159">Complete la sección Inicio rápido de la configuración de inicio de sesión de Facebook.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-159">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![Completar la sección Inicio rápido](../media/FBCimage30.png)

7. <span data-ttu-id="ee2ba-161">En el panel de navegación izquierdo, en Inicio de sesión de **Facebook,** haga clic en Configuración y agregue el URI de redireccionamiento de OAuth en el cuadro URI de redireccionamiento **de OAuth** válido.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-161">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="ee2ba-162">Use el formato **\<connectorserviceuri> /Views/FacebookOAuth**, donde el valor de connectorserviceuri es la dirección URL del servicio de aplicaciones de Azure para su organización; por ejemplo, `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="ee2ba-162">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![Agregar el URI de redireccionamiento de OAuth al cuadro URI de redireccionamiento de OAuth válidos](../media/FBCimage31.png)

8. <span data-ttu-id="ee2ba-164">En el panel de navegación izquierdo, haga clic **en Agregar productos** y, a continuación, en **Webhooks.**</span><span class="sxs-lookup"><span data-stu-id="ee2ba-164">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="ee2ba-165">En el **menú** desplegable Página, haga clic en **Página.**</span><span class="sxs-lookup"><span data-stu-id="ee2ba-165">In the **Page** pull-down menu, click **Page**.</span></span>

   ![Haga clic en Agregar productos y, a continuación, haga clic en \*\*Webhooks](../media/FBCimage32.png)

9. <span data-ttu-id="ee2ba-167">Agregue la dirección URL de devolución de llamada de webhooks y agregue un token de comprobación.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-167">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="ee2ba-168">El formato de la dirección URL de devolución de llamada, use el formato **<connectorserviceuri> /api/FbPageWebhook**, donde el valor de connectorserviceuri es la dirección URL del servicio de aplicaciones de Azure para su organización; por `https://fbconnector.azurewebsites.net` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-168">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span>

   <span data-ttu-id="ee2ba-169">El token de comprobación debe ser similar a una contraseña segura.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-169">The verify token should similar to a strong password.</span></span> <span data-ttu-id="ee2ba-170">Copie el token de verificación en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-170">Copy the verify token to a text file or other storage location.</span></span>

   ![Agregar el token de comprobación](../media/FBCimage33.png)

10. <span data-ttu-id="ee2ba-172">Pruebe y suscríbase al punto de conexión para la fuente.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-172">Test and subscribe to the endpoint for feed.</span></span>

    ![Probar y suscribirse al punto de conexión](../media/FBCimage34.png)

11. <span data-ttu-id="ee2ba-174">Agrega una dirección URL de privacidad, un icono de aplicación y un uso empresarial.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-174">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="ee2ba-175">Además, copia el identificador de la aplicación y el secreto de la aplicación en un archivo de texto u otra ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-175">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![Agregar una dirección URL de privacidad, un icono de aplicación y un uso empresarial](../media/FBCimage35.png)

12. <span data-ttu-id="ee2ba-177">Haz que la aplicación sea pública.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-177">Make the app public.</span></span>

    ![Hacer que la aplicación sea pública](../media/FBCimage36.png)

13. <span data-ttu-id="ee2ba-179">Agregar usuario al rol de administrador o evaluador.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-179">Add user to the admin or tester role.</span></span>

    ![Agregar usuario al rol de administrador o evaluador](../media/FBCimage37.png)

14. <span data-ttu-id="ee2ba-181">Agregue el **permiso Acceso al contenido público de la** página.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-181">Add the **Page Public Content Access** permission.</span></span>

    ![dd el permiso de acceso al contenido público de página](../media/FBCimage38.png)

15. <span data-ttu-id="ee2ba-183">Agregar permiso Administrar páginas.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-183">Add Manage Pages permission.</span></span>

    ![Permiso Para agregar páginas](../media/FBCimage39.png)

16. <span data-ttu-id="ee2ba-185">Obtén la aplicación revisada por Facebook.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-185">Get the application reviewed by Facebook.</span></span>

    ![Obtener la aplicación revisada por Facebook](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="ee2ba-187">Paso 4: Configurar la aplicación web del conector</span><span class="sxs-lookup"><span data-stu-id="ee2ba-187">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="ee2ba-188">Ve a (donde AzureAppResourceName es el nombre del recurso de la aplicación de `https://<AzureAppResourceName>.azurewebsites.net` Azure que llamaste en el paso 4).</span><span class="sxs-lookup"><span data-stu-id="ee2ba-188">Go to `https://<AzureAppResourceName>.azurewebsites.net` (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="ee2ba-189">Por ejemplo, si el nombre es **fbconnector**, vaya a `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="ee2ba-189">For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="ee2ba-190">La página principal de la aplicación tendrá el aspecto de la siguiente captura de pantalla:</span><span class="sxs-lookup"><span data-stu-id="ee2ba-190">The home page of the app will look like the following screenshot:</span></span>

   ![Ir a la aplicación web del conector](../media/FBCimage41.png)

2. <span data-ttu-id="ee2ba-192">Haga **clic en Configurar** para mostrar una página de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-192">Click **Configure** to display a sign in page.</span></span>

   ![Haga clic en Configurar para mostrar una página de inicio de sesión](../media/FBCimage42.png)

3. <span data-ttu-id="ee2ba-194">En el cuadro Id. de inquilino, escriba o pegue el id. de inquilino (que obtuvo en el paso 2).</span><span class="sxs-lookup"><span data-stu-id="ee2ba-194">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="ee2ba-195">En el cuadro de contraseña, escriba o pegue la APISecretKey (que  obtuvo en el paso 2) y, a continuación, haga clic en Establecer opciones de configuración para mostrar la página de detalles de configuración.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-195">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

    ![Inicie sesión con el identificador y la contraseña de su espacio empresarial y vaya a la página de detalles de configuración](../media/FBCimage43.png)

4. <span data-ttu-id="ee2ba-197">Escriba las siguientes opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="ee2ba-197">Enter the following configuration settings</span></span>

   - <span data-ttu-id="ee2ba-198">**Id. de aplicación de Facebook:** El identificador de la aplicación de Facebook que obtuvo en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-198">**Facebook application ID:** The app ID for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="ee2ba-199">**Secreto de aplicación de Facebook:** El secreto de aplicación para la aplicación de Facebook que obtuvo en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-199">**Facebook application secret:** The app secret for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="ee2ba-200">**Los webhooks de Facebook comprueban el token:** El token de comprobación que creó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-200">**Facebook webhooks verify token:** The verify token that you created in Step 3.</span></span>

   - <span data-ttu-id="ee2ba-201">**Id. de aplicación de AAD:** Identificador de aplicación de la aplicación de Azure Active Directory que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-201">**AAD application ID:** The application ID for the Azure Active Directory app that you created in Step 1.</span></span>

   - <span data-ttu-id="ee2ba-202">**Secreto de aplicación de AAD:** El valor del secreto APISecretKey que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-202">**AAD application secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="ee2ba-203">Haga **clic en Guardar** para guardar la configuración del conector.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-203">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="ee2ba-204">Paso 5: Configurar un conector de Facebook en el Centro de cumplimiento de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ee2ba-204">Step 5: Set up a Facebook connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="ee2ba-205">Vaya a conectores de datos y, a continuación, [https://compliance.microsoft.com](https://compliance.microsoft.com) haga clic en **Conectores** de datos en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-205">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="ee2ba-206">En la página **Conectores de datos** de **las páginas de Facebook Empresa,** haga clic **en Ver**.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-206">On the **Data connectors** page under **Facebook Business pages**, click **View**.</span></span>

3. <span data-ttu-id="ee2ba-207">En la página **Páginas empresariales de Facebook,** haga clic **en Agregar conector.**</span><span class="sxs-lookup"><span data-stu-id="ee2ba-207">On the **Facebook business pages** page, click **Add connector**.</span></span>

4. <span data-ttu-id="ee2ba-208">En la **página Términos de** servicio, haga clic **en Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="ee2ba-208">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="ee2ba-209">En la **página Agregar credenciales para la aplicación del** conector, escriba la siguiente información y, a continuación, haga clic en Validar **conexión.**</span><span class="sxs-lookup"><span data-stu-id="ee2ba-209">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Escribir las credenciales de la aplicación del conector](../media/TCimage38.png)

   - <span data-ttu-id="ee2ba-211">En el **cuadro** Nombre, escriba un nombre para el conector, como la página **de noticias de Facebook**.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-211">In the **Name** box, type a name for the connector, such as **Facebook news page**.</span></span>

   - <span data-ttu-id="ee2ba-212">En el **cuadro Dirección URL de** conexión, escriba o pegue la dirección URL del servicio de aplicaciones de Azure; por `https://fbconnector.azurewebsites.net` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-212">In the **Connection URL** box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   - <span data-ttu-id="ee2ba-213">En el **cuadro** Contraseña, escriba o pegue el valor de APISecretKey que agregó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-213">In the **Password** box, type or paste the value of the APISecretKey that you added in Step 2.</span></span>

   - <span data-ttu-id="ee2ba-214">En el **cuadro Id.** de aplicación de Azure, escriba o pegue el valor del identificador de aplicación (cliente) también llamado id. de aplicación de AAD que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-214">In the **Azure App ID** box, type or paste the value of the Application (client) ID also called as AAD Application ID that you created in Step 1.</span></span>

6. <span data-ttu-id="ee2ba-215">Una vez validada correctamente la conexión, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="ee2ba-215">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="ee2ba-216">En la **página Autorizar a Microsoft 365** para importar datos, vuelva a escribir o pegar APISecretKey y, a continuación, haga clic en Iniciar sesión en la aplicación **web.**</span><span class="sxs-lookup"><span data-stu-id="ee2ba-216">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click **Login web app**.</span></span>

8. <span data-ttu-id="ee2ba-217">En la página Configurar la aplicación del conector de **Facebook,** haga clic en Iniciar sesión con **Facebook** e inicie sesión con las credenciales de la cuenta de las páginas de Facebook Business de su organización.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-217">On the **Configure Facebook connector app** page, click **Login with Facebook** and log in using the credentials for the account for your organization's Facebook Business pages.</span></span> <span data-ttu-id="ee2ba-218">Asegúrese de que la cuenta de Facebook en la que inició sesión tiene asignado el rol de administrador de las páginas de Facebook Business de su organización.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-218">Make sure the Facebook account that you logged in to is assigned the admin role for your organization's Facebook Business pages.</span></span>

   ![Iniciar sesión con Facebook](../media/FBCimage50.png)

9. <span data-ttu-id="ee2ba-220">Se muestra una lista de las páginas empresariales administradas por la cuenta de Facebook en la que inició sesión.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-220">A list of the business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="ee2ba-221">Seleccione la página que desea archivar y, a continuación, haga clic **en Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="ee2ba-221">Select the page to archive and then click **Next**.</span></span>

   ![Seleccionar la página empresarial de la organización que desea archivar](../media/FBCimage52.png)

10. <span data-ttu-id="ee2ba-223">Haga **clic en** Continuar para salir de la configuración de la aplicación de servicio del conector.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-223">Click **Continue** to exit the setup of the connector service app.</span></span>

11. <span data-ttu-id="ee2ba-224">En la **página Establecer filtros,** puede aplicar un filtro para importar inicialmente elementos que tienen una antigüedad determinada.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-224">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="ee2ba-225">Seleccione una antigüedad y, a continuación, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-225">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="ee2ba-226">En la **página Elegir ubicación** de almacenamiento, escriba la dirección de correo electrónico del buzón de Microsoft 365 al que se importarán los elementos de Facebook y, a continuación, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="ee2ba-226">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Facebook items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="ee2ba-227">Haga **clic en Siguiente** para revisar la configuración del conector y, a continuación, haga clic en Finalizar para completar la configuración del conector. </span><span class="sxs-lookup"><span data-stu-id="ee2ba-227">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="ee2ba-228">En el Centro de cumplimiento, vaya a la  página **Conectores** de datos y haga clic en la pestaña Conectores para ver el progreso del proceso de importación.</span><span class="sxs-lookup"><span data-stu-id="ee2ba-228">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
