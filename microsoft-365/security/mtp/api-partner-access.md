---
title: Acceso de asociados mediante las API de Microsoft Threat Protection
description: Obtenga información sobre cómo crear una aplicación de AAD para obtener acceso mediante programación a la protección contra amenazas de Microsoft en nombre de sus clientes
keywords: asociado, acceso, API, multiempresa, consentimiento, token de acceso, aplicación
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
ms.openlocfilehash: ae9e5ae158c95ae52112f7bc16559559230a20e8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203712"
---
# <a name="partner-access-through-microsoft-threat-protection-apis"></a>Acceso de asociados mediante las API de Microsoft Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft

>[!IMPORTANT] 
>Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.


En esta página se describe cómo crear una aplicación de AAD para obtener acceso mediante programación a la protección contra amenazas de Microsoft en nombre de sus clientes.

Microsoft Threat Protection expone gran parte de sus datos y acciones a través de un conjunto de API de programación. Estas API le ayudarán a automatizar los flujos de trabajo y la innovación en función de las capacidades de Microsoft Threat Protection. El acceso a la API requiere la autenticación OAuth 2.0. Para obtener más información, vea [flujo de código de autorización de OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

En general, deberá realizar los siguientes pasos para usar las API:
- Cree una aplicación **de AAD multiinquilino** .
- Obtenga autorización (consentimiento) por parte del administrador del cliente para que su aplicación tenga acceso a los recursos de Microsoft Threat Protection que necesita.
- Obtenga un token de acceso con esta aplicación.
- Use el token para acceder a la API de Microsoft Threat Protection.

Los siguientes pasos, que le guían cómo crear una aplicación de AAD, obtener un token de acceso a la protección contra amenazas de Microsoft y validar el token.

## <a name="create-the-multi-tenant-app"></a>Crear la aplicación multiinquilino

1. Inicie sesión en su [inquilino de Azure](https://portal.azure.com) con un usuario que tenga un rol de **administrador global** .

2. Navegue a registros de aplicaciones de **Azure Active Directory**  >  **App registrations**  >  **nuevo registro**. 

   ![Imagen de Microsoft Azure y navegación en el registro de la aplicación](../../media/atp-azure-new-app2.png)

3. En el formulario de registro:

    - Elija un nombre para la aplicación.

    - Tipos de cuenta admitidos: cuentas en cualquier directorio de la organización.

    - URI de redireccionamiento-tipo: Web, URI: https://portal.azure.com

    ![Imagen del registro de la aplicación de socio de Microsoft Azure](../../media/atp-api-new-app-partner.png)


4. Permita que su aplicación tenga acceso a la protección contra amenazas de Microsoft y asígnela con el conjunto mínimo de permisos necesarios para completar la integración.

   - En la página de la aplicación, haga clic en **permisos de API**  >  **Agregar API de permisos**  >  **mi organización usa** > escriba **Microsoft Threat Protection** y haga clic en **protección contra amenazas de Microsoft**.

   >[!NOTE]
   >La protección contra amenazas de Microsoft no aparece en la lista original. Debe empezar a escribir su nombre en el cuadro de texto para ver aparezca.

   ![Imagen de acceso a API y selección de API](../../media/apis-in-my-org-tab.PNG)
   
   ### <a name="request-api-permissions"></a>Solicitar permisos de API

   Para determinar qué permiso necesita, consulte la sección **permisos** en la API que le interesa llamar. 

   En el siguiente ejemplo, usaremos el permiso **"leer todos los incidentes"** :

   Seleccione incidentes de permisos de la **aplicación**  >  **. Read. All** > haga clic en **Agregar permisos**

   ![Imagen de acceso a API y selección de API](../../media/request-api-permissions.PNG)


5. Haga clic en **conceder consentimiento**

    >[!NOTE]
    >Cada vez que agregue permisos, deberá hacer clic en **conceder consentimiento** para que el nuevo permiso surta efecto.

    ![Imagen de permisos de concesión](../../media/grant-consent.PNG)

6. Agregue un secreto a la aplicación.

    - Haga clic en **certificados & secretos**, agregue Descripción al secreto y haga clic en **Agregar**.

    >[!IMPORTANT]
    > Después de seleccionar **Agregar**, **copie el valor de secreto generado**. No podrá recuperar después de salir.

    ![Imagen de crear clave de aplicación](../../media/webapp-create-key2.png)

7. Anote el identificador de la aplicación:

   - En la página de la aplicación, vaya a **información general** y copie lo siguiente:

   ![Imagen del identificador de aplicación creado](../../media/app-id.png)

8. Agregue la aplicación al inquilino del cliente.

    Necesita que su aplicación esté aprobada en cada inquilino de cliente donde tenga previsto usarla. Esto se debe a que la aplicación interactúa con la aplicación de Microsoft Threat Protection en nombre de su cliente.

    Un usuario con **administrador global** del inquilino del cliente debe hacer clic en el vínculo de consentimiento y aprobar la aplicación.

    El vínculo de consentimiento tiene el siguiente formato:

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    Donde 00000000-0000-0000-0000-000000000000 debe reemplazarse con el identificador de la aplicación

    Después de hacer clic en el vínculo de consentimiento, inicie sesión con el administrador global del espacio empresarial del cliente y consienta la aplicación.

    ![Imagen de consentimiento](../../media/app-consent-partner.png)

    Además, tendrá que pedir al cliente su identificador de inquilino y guardarlo para usarlo en el futuro al adquirir el token.

- **Realiza!** Se ha registrado correctamente una aplicación. 
- Vea los siguientes ejemplos para la adquisición y validación de tokens.

## <a name="get-an-access-token-examples"></a>Obtener ejemplos de tokens de acceso:

>[!NOTE]
> Para obtener el token de acceso en nombre de su cliente, use el identificador de inquilino del cliente en las siguientes adquisiciones de token.

<br>Para obtener más información sobre el token de AAD, consulte el [tutorial de AAD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds) .

### <a name="using-powershell"></a>Mediante PowerShell

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

### <a name="using-c"></a>Mediante C#:

>El siguiente código se probó con Nuget Microsoft. IdentityModel. clients. ActiveDirectory

- Crear una nueva aplicación de consola
- Instalar Nuget [Microsoft. IdentityModel. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)
- Agregue lo siguiente con

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

- Copie/pegue el código siguiente en la aplicación (no olvide actualizar las 3 variables: ```tenantId, appId, appSecret``` )

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string mtpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(mtpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```



### <a name="using-curl"></a>Uso de rizo

> [!NOTE]
> El siguiente procedimiento supone que el doblez para Windows ya está instalado en el equipo

- Abrir una ventana de comandos
- Establecer CLIENT_ID en el identificador de la aplicación de Azure
- Establecer CLIENT_SECRET en el secreto de la aplicación de Azure
- Establecer TENANT_ID en el identificador de inquilino de Azure del cliente que desea usar la aplicación para acceder a la aplicación de protección contra amenazas de Microsoft
- Ejecute el siguiente comando:

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Obtendrá una respuesta del formulario:

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Validar el token

Comprobación de la validez para asegurarse de que obtuvo un token correcto:

- Copiar/pegar en [JWT](https://jwt.ms) el token que se obtiene en el paso anterior para poder descodificarlo
- Validar que obtiene una notificación de ' roles ' con los permisos deseados
- En la captura de pantalla siguiente, puede ver un token descodificado adquirido de una aplicación con varios permisos para la protección contra amenazas de Microsoft:
- La notificación "TID" es el identificador de inquilino al que pertenece el token.

![Imagen de validación de tokens](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-threat-protection-api"></a>Usar el token para acceder a la API de protección contra amenazas de Microsoft

- Elija la API que desea usar para obtener más información, consulte [API admitidas de Microsoft Threat Protection](api-supported.md)
- Establecer el encabezado Authorization en la solicitud HTTP que envía a "Bearer {token}" (Bearer es el esquema de autorización)
- La fecha de expiración del token es 1 hora (puede enviar más de una solicitud con el mismo token)

- Ejemplo de envío de una solicitud para obtener una lista de incidentes **con C#** 
    ```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="related-topics"></a>Temas relacionados 

- [Acceso a las API de Microsoft Threat Protection](api-access.md)
- [Acceso a Microsoft Threat Protection con contexto de aplicación](api-create-app-web.md)
- [Acceso a Microsoft Threat Protection con contexto de usuario](api-create-app-user-context.md)
