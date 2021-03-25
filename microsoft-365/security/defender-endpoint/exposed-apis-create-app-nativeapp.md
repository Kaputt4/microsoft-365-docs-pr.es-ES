---
title: Usar Microsoft Defender para las API de punto de conexión
ms.reviewer: ''
description: Aprende a diseñar una aplicación nativa de Windows para obtener acceso mediante programación a Microsoft Defender para endpoint sin un usuario.
keywords: apis, api de gráfico, api admitidas, actor, alertas, dispositivo, usuario, dominio, ip, archivo, búsqueda avanzada, consulta
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 5e59ff75a7933cf52af857f1a41b0925aa7bb47a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198946"
---
# <a name="use-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="f8498-104">Usar Microsoft Defender para las API de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="f8498-104">Use Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f8498-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f8498-105">**Applies to:**</span></span>
- [<span data-ttu-id="f8498-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="f8498-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="f8498-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="f8498-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f8498-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="f8498-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="f8498-109">En esta página se describe cómo crear una aplicación para obtener acceso mediante programación a Defender for Endpoint en nombre de un usuario.</span><span class="sxs-lookup"><span data-stu-id="f8498-109">This page describes how to create an application to get programmatic access to Defender for Endpoint on behalf of a user.</span></span>

<span data-ttu-id="f8498-110">Si necesita acceso mediante programación a Microsoft Defender para Endpoint sin un usuario, consulte [Access Microsoft Defender for Endpoint with application context](exposed-apis-create-app-webapp.md).</span><span class="sxs-lookup"><span data-stu-id="f8498-110">If you need programmatic access Microsoft Defender for Endpoint without a user, refer to [Access Microsoft Defender for Endpoint with application context](exposed-apis-create-app-webapp.md).</span></span>

<span data-ttu-id="f8498-111">Si no está seguro de qué acceso necesita, lea la [página Introducción](apis-intro.md).</span><span class="sxs-lookup"><span data-stu-id="f8498-111">If you are not sure which access you need, read the [Introduction page](apis-intro.md).</span></span>

<span data-ttu-id="f8498-112">Microsoft Defender para endpoint expone gran parte de sus datos y acciones a través de un conjunto de API programáticas.</span><span class="sxs-lookup"><span data-stu-id="f8498-112">Microsoft Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="f8498-113">Estas API te permitirán automatizar los flujos de trabajo e innovar en función de las capacidades de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="f8498-113">Those APIs will enable you to automate work flows and innovate based on Microsoft Defender for Endpoint capabilities.</span></span> <span data-ttu-id="f8498-114">El acceso a la API requiere autenticación de OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="f8498-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="f8498-115">Para obtener más información, vea Flujo de código de autorización de [OAuth 2.0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="f8498-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="f8498-116">En general, deberá seguir los pasos siguientes para usar las API:</span><span class="sxs-lookup"><span data-stu-id="f8498-116">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="f8498-117">Crear una aplicación de AAD</span><span class="sxs-lookup"><span data-stu-id="f8498-117">Create an AAD application</span></span>
- <span data-ttu-id="f8498-118">Obtener un token de acceso con esta aplicación</span><span class="sxs-lookup"><span data-stu-id="f8498-118">Get an access token using this application</span></span>
- <span data-ttu-id="f8498-119">Usar el token para obtener acceso a la API de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f8498-119">Use the token to access Defender for Endpoint API</span></span>

<span data-ttu-id="f8498-120">En esta página se explica cómo crear una aplicación de AAD, obtener un token de acceso a Microsoft Defender para Endpoint y validar el token.</span><span class="sxs-lookup"><span data-stu-id="f8498-120">This page explains how to create an AAD application, get an access token to Microsoft Defender for Endpoint and validate the token.</span></span>

>[!NOTE]
> <span data-ttu-id="f8498-121">Al obtener acceso a la API de Microsoft Defender para endpoint en nombre de un usuario, necesitará el permiso de aplicación y el permiso de usuario correctos.</span><span class="sxs-lookup"><span data-stu-id="f8498-121">When accessing Microsoft Defender for Endpoint API on behalf of a user, you will need the correct Application permission and user permission.</span></span>
> <span data-ttu-id="f8498-122">Si no está familiarizado con los permisos de usuario en Microsoft Defender para endpoint, consulte [Manage portal access using role-based access control](rbac.md).</span><span class="sxs-lookup"><span data-stu-id="f8498-122">If you are not familiar with user permissions on Microsoft Defender for Endpoint, see [Manage portal access using role-based access control](rbac.md).</span></span>

>[!TIP]
> <span data-ttu-id="f8498-123">Si tiene permiso para realizar una acción en el portal, tiene permiso para realizar la acción en la API.</span><span class="sxs-lookup"><span data-stu-id="f8498-123">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="f8498-124">Crear una aplicación</span><span class="sxs-lookup"><span data-stu-id="f8498-124">Create an app</span></span>

1. <span data-ttu-id="f8498-125">Inicie sesión en [Azure](https://portal.azure.com) con una cuenta de usuario que tenga el rol **Administrador global.**</span><span class="sxs-lookup"><span data-stu-id="f8498-125">Log on to [Azure](https://portal.azure.com) with a user account that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="f8498-126">Vaya a **Azure Active Directory** App  >  **registrations** New  >  **registration**.</span><span class="sxs-lookup"><span data-stu-id="f8498-126">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Imagen de Microsoft Azure y navegación al registro de aplicaciones](images/atp-azure-new-app2.png)

3. <span data-ttu-id="f8498-128">Cuando aparezca la página **Registrar una aplicación**, escriba la información de registro de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="f8498-128">When the **Register an application** page appears, enter your application's registration information:</span></span>

   - <span data-ttu-id="f8498-129">**Nombre**: escriba un nombre significativo para la aplicación, que se mostrará a los usuarios de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f8498-129">**Name** - Enter a meaningful application name that will be displayed to users of the app.</span></span>
   - <span data-ttu-id="f8498-130">**Tipos de cuentas compatibles**: seleccione qué cuentas desea que admita la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f8498-130">**Supported account types** - Select which accounts you would like your application to support.</span></span>

       | <span data-ttu-id="f8498-131">Tipos de cuenta admitidos</span><span class="sxs-lookup"><span data-stu-id="f8498-131">Supported account types</span></span> | <span data-ttu-id="f8498-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8498-132">Description</span></span> |
       |-------------------------|-------------|
       | <span data-ttu-id="f8498-133">**Solo las cuentas de este directorio organizativo**</span><span class="sxs-lookup"><span data-stu-id="f8498-133">**Accounts in this organizational directory only**</span></span> | <span data-ttu-id="f8498-134">Seleccione esta opción si va a crear una aplicación de línea de negocio (LOB).</span><span class="sxs-lookup"><span data-stu-id="f8498-134">Select this option if you're building a line-of-business (LOB) application.</span></span> <span data-ttu-id="f8498-135">Esta opción no está disponible si no va a registrar la aplicación en un directorio.</span><span class="sxs-lookup"><span data-stu-id="f8498-135">This option is not available if you're not registering the application in a directory.</span></span><br><br><span data-ttu-id="f8498-136">Esta opción se asigna solo a un único inquilino de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f8498-136">This option maps to Azure AD only single-tenant.</span></span><br><br><span data-ttu-id="f8498-137">Esta es la opción predeterminada a menos que registre la aplicación fuera de un directorio.</span><span class="sxs-lookup"><span data-stu-id="f8498-137">This is the default option unless you're registering the app outside of a directory.</span></span> <span data-ttu-id="f8498-138">En los casos en los que la aplicación se registra fuera de un directorio, el valor predeterminado son las cuentas personales de Microsoft y cuentas multiinquilino de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f8498-138">In cases where the app is registered outside of a directory, the default is Azure AD multi-tenant and personal Microsoft accounts.</span></span> |
       | <span data-ttu-id="f8498-139">**Cuentas en cualquier directorio organizativo**</span><span class="sxs-lookup"><span data-stu-id="f8498-139">**Accounts in any organizational directory**</span></span> | <span data-ttu-id="f8498-140">Seleccione esta opción si desea tener como destino todos los clientes de negocios y del sector educativo.</span><span class="sxs-lookup"><span data-stu-id="f8498-140">Select this option if you would like to target all business and educational customers.</span></span><br><br><span data-ttu-id="f8498-141">Esta opción se asigna a un multiinquilino de solo Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f8498-141">This option maps to an Azure AD only multi-tenant.</span></span><br><br><span data-ttu-id="f8498-142">Si ha registrado la aplicación como solo para un único inquilino de Azure AD, puede actualizarla para que sea de multiinquilino de Azure AD y que vuelva a serlo para un solo inquilino mediante la hoja **Autenticación**.</span><span class="sxs-lookup"><span data-stu-id="f8498-142">If you registered the app as Azure AD only single-tenant, you can update it to be Azure AD multi-tenant and back to single-tenant through the **Authentication** blade.</span></span> |
       | <span data-ttu-id="f8498-143">**Cuentas en cualquier directorio organizativo y cuentas personales de Microsoft**</span><span class="sxs-lookup"><span data-stu-id="f8498-143">**Accounts in any organizational directory and personal Microsoft accounts**</span></span> | <span data-ttu-id="f8498-144">Seleccione esta opción para establecer como destino el mayor conjunto posible de clientes.</span><span class="sxs-lookup"><span data-stu-id="f8498-144">Select this option to target the widest set of customers.</span></span><br><br><span data-ttu-id="f8498-145">Esta opción asigna cuentas personales de Microsoft y cuentas multiinquilinos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f8498-145">This option maps to Azure AD multi-tenant and personal Microsoft accounts.</span></span><br><br><span data-ttu-id="f8498-146">Si registró la aplicación como cuentas multiinquilino de Azure AD y cuentas personales de Microsoft, no puede cambiar esto en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="f8498-146">If you registered the app as Azure AD multi-tenant and personal Microsoft accounts, you cannot change this in the UI.</span></span> <span data-ttu-id="f8498-147">En su lugar, debe usar el editor de manifiestos de aplicación para cambiar los tipos de cuenta admitidos.</span><span class="sxs-lookup"><span data-stu-id="f8498-147">Instead, you must use the application manifest editor to change the supported account types.</span></span> |

   - <span data-ttu-id="f8498-148">**URI de redirección (opcional)**: seleccione el tipo de aplicación que se va a crear, **Web** o **Cliente público (móvil y escritorio)** y, a continuación, escriba el identificador URI de redireccionamiento (o la dirección URL de respuesta) para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f8498-148">**Redirect URI (optional)** - Select the type of app you're building, **Web** or **Public client (mobile & desktop)**, and then enter the redirect URI (or reply URL) for your application.</span></span>
       - <span data-ttu-id="f8498-149">Para aplicaciones web, proporcione la dirección URL base de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f8498-149">For web applications, provide the base URL of your app.</span></span> <span data-ttu-id="f8498-150">Por ejemplo, `http://localhost:31544` podría ser la dirección URL de una aplicación web que se ejecuta en la máquina local.</span><span class="sxs-lookup"><span data-stu-id="f8498-150">For example, `http://localhost:31544` might be the URL for a web app running on your local machine.</span></span> <span data-ttu-id="f8498-151">Los usuarios utilizan esta dirección URL para iniciar sesión en una aplicación cliente web.</span><span class="sxs-lookup"><span data-stu-id="f8498-151">Users would use this URL to sign in to a web client application.</span></span>
       - <span data-ttu-id="f8498-152">Para aplicaciones cliente públicas, proporcione el identificador URI que utiliza Azure AD para devolver las respuestas de los tokens.</span><span class="sxs-lookup"><span data-stu-id="f8498-152">For public client applications, provide the URI used by Azure AD to return token responses.</span></span> <span data-ttu-id="f8498-153">Escriba un valor específico para la aplicación, como `myapp://auth`.</span><span class="sxs-lookup"><span data-stu-id="f8498-153">Enter a value specific to your application, such as `myapp://auth`.</span></span>

     <span data-ttu-id="f8498-154">Si desea ejemplos específicos de aplicaciones web o aplicaciones nativas, visite nuestras [guías de inicio rápido](/azure/active-directory/develop/#quickstarts).</span><span class="sxs-lookup"><span data-stu-id="f8498-154">To see specific examples for web applications or native applications, check out our [quickstarts](/azure/active-directory/develop/#quickstarts).</span></span>

     <span data-ttu-id="f8498-155">Cuando termine, seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="f8498-155">When finished, select **Register**.</span></span>

4. <span data-ttu-id="f8498-156">Permitir que la aplicación tenga acceso a Microsoft Defender para endpoint y asignarle el permiso "Leer alertas":</span><span class="sxs-lookup"><span data-stu-id="f8498-156">Allow your Application to access Microsoft Defender for Endpoint and assign it 'Read alerts' permission:</span></span>

    - <span data-ttu-id="f8498-157">En la página de la aplicación, seleccione Permisos de **API** Agregar API de permisos que mi organización usa  >    >   > tipo **WindowsDefenderATP** y seleccione **en WindowsDefenderATP**.</span><span class="sxs-lookup"><span data-stu-id="f8498-157">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** > type **WindowsDefenderATP** and select on **WindowsDefenderATP**.</span></span>

    - <span data-ttu-id="f8498-158">**Nota:** *WindowsDefenderATP* no aparece en la lista original.</span><span class="sxs-lookup"><span data-stu-id="f8498-158">**Note**: *WindowsDefenderATP* does not appear in the original list.</span></span> <span data-ttu-id="f8498-159">Comience a escribir su nombre en el cuadro de texto para verlo aparecer.</span><span class="sxs-lookup"><span data-stu-id="f8498-159">Start writing its name in the text box to see it appear.</span></span>

      ![agregar permiso](images/add-permission.png)

    - <span data-ttu-id="f8498-161">Elija **Permisos delegados**  >  **Alert.Read >** **seleccione Agregar permisos**</span><span class="sxs-lookup"><span data-stu-id="f8498-161">Choose **Delegated permissions** > **Alert.Read** > select **Add permissions**</span></span>

      ![permisos de aplicación](images/application-permissions-public-client.png)

    - <span data-ttu-id="f8498-163">**Nota importante:** Seleccione los permisos relevantes.</span><span class="sxs-lookup"><span data-stu-id="f8498-163">**Important note**: Select the relevant permissions.</span></span> <span data-ttu-id="f8498-164">Las alertas de lectura solo son un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f8498-164">Read alerts is only an example.</span></span>

      <span data-ttu-id="f8498-165">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="f8498-165">For instance,</span></span>

      - <span data-ttu-id="f8498-166">Para [ejecutar consultas avanzadas,](run-advanced-query-api.md)seleccione el permiso "Ejecutar consultas avanzadas"</span><span class="sxs-lookup"><span data-stu-id="f8498-166">To [run advanced queries](run-advanced-query-api.md), select 'Run advanced queries' permission</span></span>
      - <span data-ttu-id="f8498-167">Para [aislar un dispositivo,](isolate-machine.md)seleccione el permiso "Aislar máquina"</span><span class="sxs-lookup"><span data-stu-id="f8498-167">To [isolate a device](isolate-machine.md), select 'Isolate machine' permission</span></span>
      - <span data-ttu-id="f8498-168">Para determinar qué permiso necesita, vea la **sección Permisos** en la API a la que está interesado llamar.</span><span class="sxs-lookup"><span data-stu-id="f8498-168">To determine which permission you need, view the **Permissions** section in the API you are interested to call.</span></span>

    - <span data-ttu-id="f8498-169">Seleccionar **Conceder consentimiento**</span><span class="sxs-lookup"><span data-stu-id="f8498-169">Select **Grant consent**</span></span>

      <span data-ttu-id="f8498-170">**Nota:** Cada vez que agregue permiso, debe seleccionar conceder **el consentimiento** para que el nuevo permiso suba a efecto.</span><span class="sxs-lookup"><span data-stu-id="f8498-170">**Note**: Every time you add permission you must select on **Grant consent** for the new permission to take effect.</span></span>

      ![Imagen de concesión de permisos](images/grant-consent.png)

6. <span data-ttu-id="f8498-172">Anote el identificador de la aplicación y el identificador de inquilino:</span><span class="sxs-lookup"><span data-stu-id="f8498-172">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="f8498-173">En la página de la aplicación, vaya **a Información general** y copie la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="f8498-173">On your application page, go to **Overview** and copy the following information:</span></span>

   ![Imagen del identificador de aplicación creado](images/app-and-tenant-ids.png)


## <a name="get-an-access-token"></a><span data-ttu-id="f8498-175">Obtener un token de acceso</span><span class="sxs-lookup"><span data-stu-id="f8498-175">Get an access token</span></span>

<span data-ttu-id="f8498-176">Para obtener más información sobre los tokens de AAD, consulte [Tutorial de Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="f8498-176">For more information on AAD tokens, see [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span></span>

### <a name="using-c"></a><span data-ttu-id="f8498-177">Uso de C #</span><span class="sxs-lookup"><span data-stu-id="f8498-177">Using C#</span></span>

- <span data-ttu-id="f8498-178">Copie o pegue la clase siguiente en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f8498-178">Copy/Paste the below class in your application.</span></span>
- <span data-ttu-id="f8498-179">Usa **el método AcquireUserTokenAsync** con el identificador de aplicación, el identificador de inquilino, el nombre de usuario y la contraseña para adquirir un token.</span><span class="sxs-lookup"><span data-stu-id="f8498-179">Use **AcquireUserTokenAsync** method with your application ID, tenant ID, user name, and password to acquire a token.</span></span>

    ```csharp
    namespace WindowsDefenderATP
    {
        using System.Net.Http;
        using System.Text;
        using System.Threading.Tasks;
        using Newtonsoft.Json.Linq;

        public static class WindowsDefenderATPUtils
        {
            private const string Authority = "https://login.microsoftonline.com";

            private const string WdatpResourceId = "https://api.securitycenter.microsoft.com";

            public static async Task<string> AcquireUserTokenAsync(string username, string password, string appId, string tenantId)
            {
                using (var httpClient = new HttpClient())
                {
                    var urlEncodedBody = $"resource={WdatpResourceId}&client_id={appId}&grant_type=password&username={username}&password={password}";

                    var stringContent = new StringContent(urlEncodedBody, Encoding.UTF8, "application/x-www-form-urlencoded");

                    using (var response = await httpClient.PostAsync($"{Authority}/{tenantId}/oauth2/token", stringContent).ConfigureAwait(false))
                    {
                        response.EnsureSuccessStatusCode();

                        var json = await response.Content.ReadAsStringAsync().ConfigureAwait(false);

                        var jObject = JObject.Parse(json);

                        return jObject["access_token"].Value<string>();
                    }
                }
            }
        }
    }
    ```

## <a name="validate-the-token"></a><span data-ttu-id="f8498-180">Validar el token</span><span class="sxs-lookup"><span data-stu-id="f8498-180">Validate the token</span></span>

<span data-ttu-id="f8498-181">Compruebe para asegurarse de que tiene un token correcto:</span><span class="sxs-lookup"><span data-stu-id="f8498-181">Verify to make sure you got a correct token:</span></span>
- <span data-ttu-id="f8498-182">Copiar y pegar en [JWT el](https://jwt.ms) token que obtuvo en el paso anterior para descodificarlo</span><span class="sxs-lookup"><span data-stu-id="f8498-182">Copy/paste into [JWT](https://jwt.ms) the token you got in the previous step in order to decode it</span></span>
- <span data-ttu-id="f8498-183">Validar que obtienes una notificación "scp" con los permisos de aplicación deseados</span><span class="sxs-lookup"><span data-stu-id="f8498-183">Validate you get a 'scp' claim with the desired app permissions</span></span>
- <span data-ttu-id="f8498-184">En la siguiente captura de pantalla, puedes ver un token descodificado adquirido desde la aplicación en el tutorial:</span><span class="sxs-lookup"><span data-stu-id="f8498-184">In the screenshot below you can see a decoded token acquired from the app in the tutorial:</span></span>

![Imagen de validación de tokens](images/nativeapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a><span data-ttu-id="f8498-186">Usar el token para obtener acceso a la API de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="f8498-186">Use the token to access Microsoft Defender for Endpoint API</span></span>

- <span data-ttu-id="f8498-187">Elija la API que desea usar: Compatible [con Microsoft Defender para las API de punto de conexión](exposed-apis-list.md)</span><span class="sxs-lookup"><span data-stu-id="f8498-187">Choose the API you want to use - [Supported Microsoft Defender for Endpoint APIs](exposed-apis-list.md)</span></span>
- <span data-ttu-id="f8498-188">Establezca el encabezado Authorization en la solicitud HTTP que envíe a "Bearer {token}" (El portador es el esquema de autorización)</span><span class="sxs-lookup"><span data-stu-id="f8498-188">Set the Authorization header in the HTTP request you send to "Bearer {token}" (Bearer is the Authorization scheme)</span></span>
- <span data-ttu-id="f8498-189">El tiempo de expiración del token es de 1 hora (puede enviar más de una solicitud con el mismo token)</span><span class="sxs-lookup"><span data-stu-id="f8498-189">The Expiration time of the token is 1 hour (you can send more than one request with the same token)</span></span>

- <span data-ttu-id="f8498-190">Ejemplo de envío de una solicitud para obtener una lista de alertas **mediante C#**</span><span class="sxs-lookup"><span data-stu-id="f8498-190">Example of sending a request to get a list of alerts **using C#**</span></span> 

    ```csharp
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="see-also"></a><span data-ttu-id="f8498-191">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8498-191">See also</span></span>
- [<span data-ttu-id="f8498-192">Microsoft Defender para api de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="f8498-192">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="f8498-193">Access Microsoft Defender for Endpoint with application context</span><span class="sxs-lookup"><span data-stu-id="f8498-193">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
