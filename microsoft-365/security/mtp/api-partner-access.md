---
title: Acceso de partners a través de las API de Microsoft 365 Defender
description: Obtén información sobre cómo crear una aplicación para obtener acceso mediante programación a Microsoft 365 Defender en nombre de los usuarios.
keywords: partner, access, api, multi tenant, consent, access token, app
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
ms.openlocfilehash: 1e8db376db4533a1d3932b488a773472e5209c5a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922203"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a><span data-ttu-id="6a42e-104">Crear una aplicación con acceso de asociado a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a42e-104">Create an app with partner access to Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6a42e-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6a42e-105">**Applies to:**</span></span>

- <span data-ttu-id="6a42e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a42e-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a42e-107">Parte de la información está relacionada con el producto predefinido que puede modificarse considerablemente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="6a42e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6a42e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="6a42e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="6a42e-109">En esta página se describe cómo crear una aplicación de Azure Active Directory que tenga acceso mediante programación a Microsoft 365 Defender, en nombre de los usuarios de varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="6a42e-109">This page describes how to create an Azure Active Directory app that has programmatic access to Microsoft 365 Defender, on behalf of users across multiple tenants.</span></span> <span data-ttu-id="6a42e-110">Las aplicaciones multiinquilino son útiles para atender a grandes grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="6a42e-110">Multi-tenant apps are useful for serving large groups of users.</span></span>

<span data-ttu-id="6a42e-111">Si necesitas acceso mediante programación a Microsoft 365 Defender en nombre de un único usuario, consulta Crear una aplicación para tener acceso a las API de [Microsoft 365 Defender](api-create-app-user-context.md)en nombre de un usuario .</span><span class="sxs-lookup"><span data-stu-id="6a42e-111">If you need programmatic access to Microsoft 365 Defender on behalf of a single user, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md).</span></span> <span data-ttu-id="6a42e-112">Si necesitas acceso sin un usuario definido explícitamente (por ejemplo, si estás escribiendo una aplicación en segundo plano o un demonio), consulta Crear una aplicación para tener acceso a [Microsoft 365 Defender](api-create-app-web.md)sin un usuario .</span><span class="sxs-lookup"><span data-stu-id="6a42e-112">If you need access without a user explicitly defined (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="6a42e-113">Si no está seguro del tipo de acceso que necesita, vea [Introducción.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="6a42e-113">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="6a42e-114">Microsoft 365 Defender expone gran parte de sus datos y acciones a través de un conjunto de API programáticas.</span><span class="sxs-lookup"><span data-stu-id="6a42e-114">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="6a42e-115">Estas API le ayudan a automatizar flujos de trabajo y a usar las capacidades de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6a42e-115">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="6a42e-116">Este acceso a la API requiere autenticación de OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="6a42e-116">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="6a42e-117">Para obtener más información, vea Flujo de código de autorización de [OAuth 2.0](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="6a42e-117">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="6a42e-118">En general, deberá seguir los siguientes pasos para usar estas API:</span><span class="sxs-lookup"><span data-stu-id="6a42e-118">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="6a42e-119">Crear una aplicación de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="6a42e-119">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="6a42e-120">Obtener un token de acceso con esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="6a42e-120">Get an access token using this application.</span></span>
- <span data-ttu-id="6a42e-121">Use el token para obtener acceso a la API de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6a42e-121">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="6a42e-122">Dado que esta aplicación es multiinquilino, también necesitarás el consentimiento de [administrador](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) de cada inquilino en nombre de sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="6a42e-122">Since this app is multi-tenant, you'll also need [admin consent](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) from each tenant on behalf of its users.</span></span>

<span data-ttu-id="6a42e-123">En este artículo se explica cómo:</span><span class="sxs-lookup"><span data-stu-id="6a42e-123">This article explains how to:</span></span>

- <span data-ttu-id="6a42e-124">Crear una aplicación de Azure AD **multiinquilino**</span><span class="sxs-lookup"><span data-stu-id="6a42e-124">Create a **multi-tenant** Azure AD application</span></span>
- <span data-ttu-id="6a42e-125">Obtenga el consentimiento autorizado del administrador de usuarios para que la aplicación obtenga acceso al Microsoft 365 Defender que necesita.</span><span class="sxs-lookup"><span data-stu-id="6a42e-125">Get authorized consent from your user administrator for your application to access the Microsoft 365 Defender that resources it needs.</span></span>
- <span data-ttu-id="6a42e-126">Obtener un token de acceso a Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a42e-126">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="6a42e-127">Validar el token</span><span class="sxs-lookup"><span data-stu-id="6a42e-127">Validate the token</span></span>

<span data-ttu-id="6a42e-128">Microsoft 365 Defender expone gran parte de sus datos y acciones a través de un conjunto de API programáticas.</span><span class="sxs-lookup"><span data-stu-id="6a42e-128">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="6a42e-129">Estas API le ayudarán a automatizar los flujos de trabajo e innovar en función de las capacidades de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6a42e-129">Those APIs will help you automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="6a42e-130">El acceso a la API requiere autenticación de OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="6a42e-130">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="6a42e-131">Para obtener más información, vea Flujo de código de autorización de [OAuth 2.0](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="6a42e-131">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="6a42e-132">En general, deberá seguir los pasos siguientes para usar las API:</span><span class="sxs-lookup"><span data-stu-id="6a42e-132">In general, you’ll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="6a42e-133">Crear una aplicación de Azure AD **multiinquilino.**</span><span class="sxs-lookup"><span data-stu-id="6a42e-133">Create a **multi-tenant** Azure AD application.</span></span>
- <span data-ttu-id="6a42e-134">Obtenga autorización (consentimiento) del administrador de usuarios para que la aplicación obtenga acceso a los recursos de Microsoft 365 Defender que necesita.</span><span class="sxs-lookup"><span data-stu-id="6a42e-134">Get authorized (consent) by your user administrator for your application to access Microsoft 365 Defender resources it needs.</span></span>
- <span data-ttu-id="6a42e-135">Obtener un token de acceso con esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="6a42e-135">Get an access token using this application.</span></span>
- <span data-ttu-id="6a42e-136">Use el token para obtener acceso a la API de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6a42e-136">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="6a42e-137">Los siguientes pasos le guían sobre cómo crear una aplicación multiinquilino de Azure AD, obtener un token de acceso a Microsoft 365 Defender y validar el token.</span><span class="sxs-lookup"><span data-stu-id="6a42e-137">The following steps with guide you how to create a multi-tenant Azure AD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="6a42e-138">Crear la aplicación multiinquilino</span><span class="sxs-lookup"><span data-stu-id="6a42e-138">Create the multi-tenant app</span></span>

1. <span data-ttu-id="6a42e-139">Inicie sesión en [Azure](https://portal.azure.com) como usuario con el rol **Administrador** global.</span><span class="sxs-lookup"><span data-stu-id="6a42e-139">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="6a42e-140">Vaya a **Azure Active Directory** App  >  **registrations** New  >  **registration**.</span><span class="sxs-lookup"><span data-stu-id="6a42e-140">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Imagen de Microsoft Azure y navegación al registro de aplicaciones](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="6a42e-142">En el formulario de registro:</span><span class="sxs-lookup"><span data-stu-id="6a42e-142">In the registration form:</span></span>

   - <span data-ttu-id="6a42e-143">Elija un nombre para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6a42e-143">Choose a name for your application.</span></span>
   - <span data-ttu-id="6a42e-144">En **Tipos de cuentas compatibles,** seleccione Cuentas en cualquier directorio de la organización (cualquier directorio de Azure **AD) - Multitenant**.</span><span class="sxs-lookup"><span data-stu-id="6a42e-144">From **Supported account types**, select **Accounts in any organizational directory (Any Azure AD directory) - Multitenant**.</span></span>
   - <span data-ttu-id="6a42e-145">Rellene la sección **URI de** redireccionamiento.</span><span class="sxs-lookup"><span data-stu-id="6a42e-145">Fill out the **Redirect URI** section.</span></span> <span data-ttu-id="6a42e-146">Seleccione el **tipo Web** y dé al URI de redireccionamiento como **https://portal.azure.com** .</span><span class="sxs-lookup"><span data-stu-id="6a42e-146">Select type **Web** and give the redirect URI as **https://portal.azure.com**.</span></span>

   <span data-ttu-id="6a42e-147">Una vez que haya terminado de rellenar el formulario, seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="6a42e-147">After you're done filling out the form, select **Register**.</span></span>

   ![Imagen del formulario Registrar una aplicación](../..//media/atp-api-new-app-partner.png)

4. <span data-ttu-id="6a42e-149">En la página de la aplicación, seleccione **Permisos** de API Agregar API de permisos que mi organización usa  >    >   >, escriba Protección contra amenazas de Microsoft y seleccione **Protección contra** amenazas de Microsoft .</span><span class="sxs-lookup"><span data-stu-id="6a42e-149">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="6a42e-150">La aplicación ahora puede acceder a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6a42e-150">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="6a42e-151">*Microsoft Threat Protection* es un nombre antiguo de Microsoft 365 Defender y no aparecerá en la lista original.</span><span class="sxs-lookup"><span data-stu-id="6a42e-151">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="6a42e-152">Debe empezar a escribir su nombre en el cuadro de texto para verlo aparecer.</span><span class="sxs-lookup"><span data-stu-id="6a42e-152">You need to start writing its name in the text box to see it appear.</span></span>

   ![Imagen de selección de permisos de API](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="6a42e-154">Seleccione **Permisos de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="6a42e-154">Select **Application permissions**.</span></span> <span data-ttu-id="6a42e-155">Elija los permisos relevantes para su escenario (por ejemplo, **Incident.Read.All**) y, a continuación, **seleccione Agregar permisos**.</span><span class="sxs-lookup"><span data-stu-id="6a42e-155">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![Imagen de acceso a api y selección de API](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="6a42e-157">Debe seleccionar los permisos relevantes para su escenario.</span><span class="sxs-lookup"><span data-stu-id="6a42e-157">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="6a42e-158">*Leer todos los incidentes* es solo un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6a42e-158">*Read all incidents* is just an example.</span></span> <span data-ttu-id="6a42e-159">Para determinar qué permiso necesita, consulte la sección **Permisos** de la API a la que desea llamar.</span><span class="sxs-lookup"><span data-stu-id="6a42e-159">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="6a42e-160">Por ejemplo, para [ejecutar consultas avanzadas,](api-advanced-hunting.md)seleccione el permiso "Ejecutar consultas avanzadas"; para [aislar un dispositivo,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)seleccione el permiso "Aislar máquina".</span><span class="sxs-lookup"><span data-stu-id="6a42e-160">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="6a42e-161">Seleccione **Conceder consentimiento de administrador**.</span><span class="sxs-lookup"><span data-stu-id="6a42e-161">Select **Grant admin consent**.</span></span> <span data-ttu-id="6a42e-162">Cada vez que agregue un permiso, debe seleccionar Conceder consentimiento **de administrador** para que su efecto.</span><span class="sxs-lookup"><span data-stu-id="6a42e-162">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Imagen de concesión de permisos](../../media/grant-consent.PNG)

7. <span data-ttu-id="6a42e-164">Para agregar un secreto a la aplicación, seleccione Certificados **& secretos,** agregue una descripción al secreto y, a continuación, **seleccione Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6a42e-164">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="6a42e-165">Después de seleccionar **Agregar**, seleccione **copiar el valor secreto generado**.</span><span class="sxs-lookup"><span data-stu-id="6a42e-165">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="6a42e-166">No podrá recuperar el valor secreto después de salir.</span><span class="sxs-lookup"><span data-stu-id="6a42e-166">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Imagen de crear clave de aplicación](../../media/webapp-create-key2.png)

8. <span data-ttu-id="6a42e-168">Registre el identificador de la aplicación y el identificador de inquilino en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="6a42e-168">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="6a42e-169">Aparecen en Información **general en** la página de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6a42e-169">They're listed under **Overview** on your application page.</span></span>

   ![Imagen del identificador de aplicación creado](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="6a42e-171">Agregue la aplicación al inquilino del usuario.</span><span class="sxs-lookup"><span data-stu-id="6a42e-171">Add the application to your user's tenant.</span></span>

   <span data-ttu-id="6a42e-172">Dado que la aplicación interactúa con Microsoft 365 Defender en nombre de los usuarios, debe aprobarse para todos los inquilinos en los que tenga previsto usarlo.</span><span class="sxs-lookup"><span data-stu-id="6a42e-172">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

   <span data-ttu-id="6a42e-173">Un **administrador global** del inquilino del usuario debe ver el vínculo de consentimiento y aprobar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6a42e-173">A **Global Administrator** from your user's tenant needs to view the consent link and approve your application.</span></span>

   <span data-ttu-id="6a42e-174">El vínculo de consentimiento es del formulario:</span><span class="sxs-lookup"><span data-stu-id="6a42e-174">Consent link is of the form:</span></span>

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   <span data-ttu-id="6a42e-175">Los `00000000-0000-0000-0000-000000000000` dígitos deben reemplazarse por su id. de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6a42e-175">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>

   <span data-ttu-id="6a42e-176">Después de hacer clic en el vínculo de consentimiento, inicie sesión con el administrador global del inquilino del usuario y consiente la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6a42e-176">After clicking on the consent link, sign in with the Global Administrator of the user's tenant and consent the application.</span></span>

   ![Imagen de consentimiento](../../media/app-consent-partner.png)

   <span data-ttu-id="6a42e-178">También tendrás que pedir al usuario su identificador de inquilino.</span><span class="sxs-lookup"><span data-stu-id="6a42e-178">You'll also need to ask your user for their tenant ID.</span></span> <span data-ttu-id="6a42e-179">El identificador de inquilino es uno de los identificadores usados para adquirir tokens de acceso.</span><span class="sxs-lookup"><span data-stu-id="6a42e-179">The tenant ID is one of the identifiers used to acquire access tokens.</span></span>

- <span data-ttu-id="6a42e-180">**¡Listo!**</span><span class="sxs-lookup"><span data-stu-id="6a42e-180">**Done!**</span></span> <span data-ttu-id="6a42e-181">Ha registrado correctamente una aplicación.</span><span class="sxs-lookup"><span data-stu-id="6a42e-181">You've successfully registered an application!</span></span>
- <span data-ttu-id="6a42e-182">Vea ejemplos a continuación para la adquisición y validación de tokens.</span><span class="sxs-lookup"><span data-stu-id="6a42e-182">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="6a42e-183">Obtener un token de acceso</span><span class="sxs-lookup"><span data-stu-id="6a42e-183">Get an access token</span></span>

<span data-ttu-id="6a42e-184">Para obtener más información sobre los tokens de Azure AD, consulte el [tutorial de Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="6a42e-184">For more information on Azure AD tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a42e-185">Aunque los ejemplos de esta sección le animan a pegar  valores secretos con fines de prueba, nunca debe codificar los secretos en una aplicación que se ejecute en producción.</span><span class="sxs-lookup"><span data-stu-id="6a42e-185">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="6a42e-186">Un tercero podría usar el secreto para obtener acceso a los recursos.</span><span class="sxs-lookup"><span data-stu-id="6a42e-186">A third party could use your secret to access resources.</span></span> <span data-ttu-id="6a42e-187">Puedes ayudar a proteger los secretos de la aplicación con [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span><span class="sxs-lookup"><span data-stu-id="6a42e-187">You can help keep your app's secrets secure by using [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="6a42e-188">Para obtener un ejemplo práctico de cómo proteger la aplicación, consulta Administrar secretos en las aplicaciones de servidor [con Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span><span class="sxs-lookup"><span data-stu-id="6a42e-188">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

> [!TIP]
> <span data-ttu-id="6a42e-189">En los ejemplos siguientes, use el identificador de inquilino de un usuario para probar que el script funciona.</span><span class="sxs-lookup"><span data-stu-id="6a42e-189">In the following examples, use a user's tenant ID to test that the script is working.</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="6a42e-190">Obtener un token de acceso con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a42e-190">Get an access token using PowerShell</span></span>

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place!

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

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="6a42e-191">Obtener un token de acceso con C\#</span><span class="sxs-lookup"><span data-stu-id="6a42e-191">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="6a42e-192">El código siguiente se ha probado con Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="6a42e-192">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="6a42e-193">Crear una nueva aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="6a42e-193">Create a new console application.</span></span>
1. <span data-ttu-id="6a42e-194">Instalar NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="6a42e-194">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="6a42e-195">Agregue la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="6a42e-195">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="6a42e-196">Copie y pegue el siguiente código en la aplicación (no olvide actualizar las tres variables: `tenantId` , `clientId` , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="6a42e-196">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

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

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="6a42e-197">Obtener un token de acceso con Python</span><span class="sxs-lookup"><span data-stu-id="6a42e-197">Get an access token using Python</span></span>

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

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

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="6a42e-198">Obtener un token de acceso con el rizo</span><span class="sxs-lookup"><span data-stu-id="6a42e-198">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="6a42e-199">El rizo está preinstalado en Windows 10, versiones 1803 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="6a42e-199">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="6a42e-200">Para otras versiones de Windows, descarga e instala la herramienta directamente desde el [sitio web oficial de curl](https://curl.haxx.se/windows/).</span><span class="sxs-lookup"><span data-stu-id="6a42e-200">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="6a42e-201">Abra un símbolo del sistema y establezca CLIENT_ID en el identificador de la aplicación de Azure.</span><span class="sxs-lookup"><span data-stu-id="6a42e-201">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="6a42e-202">Establece CLIENT_SECRET en el secreto de la aplicación de Azure.</span><span class="sxs-lookup"><span data-stu-id="6a42e-202">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="6a42e-203">Establece TENANT_ID en el identificador de inquilino de Azure del usuario que desea usar la aplicación para tener acceso a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6a42e-203">Set TENANT_ID to the Azure tenant ID of the user that wants to use your app to access Microsoft 365 Defender.</span></span>
1. <span data-ttu-id="6a42e-204">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="6a42e-204">Run the following command:</span></span>

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="6a42e-205">Una respuesta correcta tendrá este aspecto:</span><span class="sxs-lookup"><span data-stu-id="6a42e-205">A successful response will look like this:</span></span>

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="6a42e-206">Validar el token</span><span class="sxs-lookup"><span data-stu-id="6a42e-206">Validate the token</span></span>

1. <span data-ttu-id="6a42e-207">Copie y pegue el token en el sitio web del validador de [tokens web JSON, JWT,](https://jwt.ms) para descodificarlo.</span><span class="sxs-lookup"><span data-stu-id="6a42e-207">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="6a42e-208">Asegúrese de que la notificación *de roles* dentro del token descodificado contiene los permisos deseados.</span><span class="sxs-lookup"><span data-stu-id="6a42e-208">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="6a42e-209">En la siguiente imagen, puedes ver un token descodificado adquirido desde una aplicación, con ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` y ```AdvancedHunting.Read.All``` permisos:</span><span class="sxs-lookup"><span data-stu-id="6a42e-209">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Imagen de validación de tokens](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="6a42e-211">Usar el token para obtener acceso a la API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a42e-211">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="6a42e-212">Elige la API que quieras usar (incidentes o búsqueda avanzada).</span><span class="sxs-lookup"><span data-stu-id="6a42e-212">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="6a42e-213">Para obtener más información, vea [Supported Microsoft 365 Defender API](api-supported.md).</span><span class="sxs-lookup"><span data-stu-id="6a42e-213">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="6a42e-214">En la solicitud http que está a punto de enviar, establezca el encabezado de autorización en , Bearer es el esquema de autorización `"Bearer" <token>` y el *token* es el token validado. </span><span class="sxs-lookup"><span data-stu-id="6a42e-214">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="6a42e-215">El token expirará en una hora.</span><span class="sxs-lookup"><span data-stu-id="6a42e-215">The token will expire within one hour.</span></span> <span data-ttu-id="6a42e-216">Puede enviar más de una solicitud durante este tiempo con el mismo token.</span><span class="sxs-lookup"><span data-stu-id="6a42e-216">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="6a42e-217">En el ejemplo siguiente se muestra cómo enviar una solicitud para obtener una lista de incidentes **mediante C#**.</span><span class="sxs-lookup"><span data-stu-id="6a42e-217">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="6a42e-218">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="6a42e-218">Related articles</span></span>

- [<span data-ttu-id="6a42e-219">Introducción a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a42e-219">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="6a42e-220">Obtener acceso a las API de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a42e-220">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="6a42e-221">Crear una aplicación "Hello world"</span><span class="sxs-lookup"><span data-stu-id="6a42e-221">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="6a42e-222">Crear una aplicación para tener acceso a Microsoft 365 Defender sin un usuario</span><span class="sxs-lookup"><span data-stu-id="6a42e-222">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="6a42e-223">Crear una aplicación para tener acceso a las API de Microsoft 365 Defender en nombre de un usuario</span><span class="sxs-lookup"><span data-stu-id="6a42e-223">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="6a42e-224">Más información sobre los límites de api y las licencias</span><span class="sxs-lookup"><span data-stu-id="6a42e-224">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="6a42e-225">Comprender códigos de error</span><span class="sxs-lookup"><span data-stu-id="6a42e-225">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="6a42e-226">Administrar secretos en las aplicaciones de servidor con Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="6a42e-226">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="6a42e-227">Autorización de OAuth 2.0 para el inicio de sesión de usuario y el acceso a la API</span><span class="sxs-lookup"><span data-stu-id="6a42e-227">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)