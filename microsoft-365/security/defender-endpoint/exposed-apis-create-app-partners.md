---
title: Crear una aplicación para tener acceso a Microsoft Defender para endpoint sin un usuario
ms.reviewer: ''
description: Aprende a diseñar una aplicación web para obtener acceso mediante programación a Microsoft Defender para endpoint sin un usuario.
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
ms.openlocfilehash: bc58241be69a1d8e1a78abc583b2c87dbef9cfa7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199429"
---
# <a name="partner-access-through-microsoft-defender-for-endpoint-apis"></a>Acceso de partners a través de Microsoft Defender para api de punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

En esta página se describe cómo crear una aplicación de Azure Active Directory (Azure AD) para obtener acceso mediante programación a Microsoft Defender para endpoint en nombre de los clientes.


Microsoft Defender para endpoint expone gran parte de sus datos y acciones a través de un conjunto de API programáticas. Estas API le ayudarán a automatizar los flujos de trabajo e innovar en función de las capacidades de Microsoft Defender para puntos de conexión. El acceso a la API requiere autenticación de OAuth2.0. Para obtener más información, vea Flujo de código de autorización de [OAuth 2.0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

En general, deberá seguir los pasos siguientes para usar las API:
- Crear una aplicación de Azure AD **multiinquilino.**
- Obtenga autorización(consentimiento) por parte del administrador del cliente para que la aplicación obtenga acceso a Defender para los recursos de extremo que necesita.
- Obtener un token de acceso con esta aplicación.
- Use el token para obtener acceso a Microsoft Defender para la API de punto de conexión.

Los siguientes pasos le guiarán sobre cómo crear una aplicación de Azure AD, obtener un token de acceso a Microsoft Defender para Endpoint y validar el token.

## <a name="create-the-multi-tenant-app"></a>Crear la aplicación multiinquilino

1. Inicie sesión en el inquilino [de Azure](https://portal.azure.com) con el usuario que tenga el rol **De administrador** global.

2. Vaya a **Azure Active Directory** App  >  **registrations** New  >  **registration**. 

   ![Imagen de Microsoft Azure y navegación al registro de aplicaciones](images/atp-azure-new-app2.png)

3. En el formulario de registro:

    - Elija un nombre para la aplicación.

    - Tipos de cuentas compatibles: cuentas en cualquier directorio de la organización.

    - URI de redireccionamiento: tipo: Web, URI: https://portal.azure.com

    ![Imagen del registro de aplicaciones asociadas de Microsoft Azure](images/atp-api-new-app-partner.png)


4. Permitir que la aplicación tenga acceso a Microsoft Defender para endpoint y asignarla con el conjunto mínimo de permisos necesarios para completar la integración.

   - En la página de la aplicación, seleccione Permisos de **API** Agregar API de permisos que mi organización usa  >    >   > tipo **WindowsDefenderATP** y seleccione **en WindowsDefenderATP**.

   - **Nota:** *WindowsDefenderATP* no aparece en la lista original. Comience a escribir su nombre en el cuadro de texto para verlo aparecer.

   ![agregar permiso](images/add-permission.png)
   
   ### <a name="request-api-permissions"></a>Solicitar permisos de API

   Para determinar qué permiso necesita, revise la sección **Permisos** de la API a la que está interesado llamar. Por ejemplo:

   - Para [ejecutar consultas avanzadas,](run-advanced-query-api.md)seleccione el permiso "Ejecutar consultas avanzadas"
   
   - Para [aislar un dispositivo,](isolate-machine.md)seleccione el permiso "Aislar máquina"

   En el siguiente ejemplo, usaremos el permiso **"Leer todas las** alertas":

   Elija **Permisos de aplicación**  >  **Alert.Read.All** > en Agregar **permisos**

   ![permisos de aplicación](images/application-permissions.png)


5. Seleccionar **Conceder consentimiento**

    - **Nota:** Cada vez que agregue permiso, debe seleccionar conceder **el consentimiento** para que el nuevo permiso suba a efecto.

    ![Imagen de concesión de permisos](images/grant-consent.png)

6. Agregue un secreto a la aplicación.

    - Seleccione **Certificados & secretos,** agregue una descripción al secreto y seleccione **Agregar**.

    **Importante:** Después de hacer clic en Agregar, **copie el valor secreto generado**. No podrás recuperarlo después de salir.

    ![Imagen de crear clave de aplicación](images/webapp-create-key2.png)

7. Anote el identificador de la aplicación:

   - En la página de la aplicación, vaya **a Información general** y copie la siguiente información:

   ![Imagen del identificador de aplicación creado](images/app-id.png)

8. Agregue la aplicación al inquilino del cliente.

    Necesita que la aplicación se apruebe en cada inquilino del cliente en el que tenga previsto usarlo. Esto se debe a que la aplicación interactúa con la aplicación de Microsoft Defender para endpoint en nombre del cliente.

    Un usuario con **administrador global** del inquilino del cliente debe seleccionar el vínculo de consentimiento y aprobar la aplicación.

    El vínculo de consentimiento es del formulario:

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    Donde 00000000-0000-0000-0000-000000000000000000 debe reemplazarse por su id. de aplicación

    Después de hacer clic en el vínculo de consentimiento, inicie sesión con el administrador global del inquilino del cliente y consiente la aplicación.

    ![Imagen de consentimiento](images/app-consent-partner.png)

    Además, deberá pedir al cliente su identificador de inquilino y guardarlo para usarlo en el futuro al adquirir el token.

- **¡Listo!** Ha registrado correctamente una aplicación. 
- Vea ejemplos a continuación para la adquisición y validación de tokens.

## <a name="get-an-access-token-example"></a>Obtenga un ejemplo de token de acceso:

**Nota:** Para obtener el token de acceso en nombre de su cliente, use el identificador de inquilino del cliente en las siguientes adquisiciones de tokens.

<br>Para obtener más información sobre el token de AAD, vea [tutorial de AAD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="using-powershell"></a>Mediante PowerShell

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
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

### <a name="using-c"></a>Usar C#:

>El código siguiente se ha probado con Nuget Microsoft.IdentityModel.Clients.ActiveDirectory

- Crear una nueva aplicación de consola
- Instalar NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)
- Agregar el siguiente uso

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

- Copie o pegue el código siguiente en la aplicación (no olvide actualizar las tres variables: ```tenantId, appId, appSecret``` )

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.microsoftonline.com";
    const string wdatpResourceId = "https://api.securitycenter.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="using-python"></a>Uso de Python

Consulte Obtener [token con Python](run-advanced-query-sample-python.md#get-token)

### <a name="using-curl"></a>Uso de Rizos

> [!NOTE]
> El siguiente procedimiento supone que Curl para Windows ya está instalado en el equipo

- Abrir una ventana de comandos
- Establecer CLIENT_ID en el identificador de aplicación de Azure
- Establecer CLIENT_SECRET en el secreto de aplicación de Azure
- Establezca TENANT_ID el identificador de inquilino de Azure del cliente que desea usar la aplicación para obtener acceso a la aplicación de Microsoft Defender para endpoint
- Ejecute el comando siguiente:

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Recibirá una respuesta del formulario:

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Validar el token

Comprobación de la cordura para asegurarse de que tiene un token correcto:
- Copiar y pegar en [JWT el](https://jwt.ms) token que obtienes en el paso anterior para descodificarlo
- Validar que obtiene una notificación de "roles" con los permisos deseados
- En la captura de pantalla siguiente, puedes ver un token descodificado adquirido de una aplicación con varios permisos para Microsoft Defender para endpoint:
- La notificación "tid" es el identificador de inquilino al que pertenece el token.

![Imagen de validación de tokens](images/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>Usar el token para obtener acceso a la API de Microsoft Defender para endpoint

- Elija la API que desea usar, para obtener más información, vea [Supported Microsoft Defender for Endpoint API](exposed-apis-list.md)
- Establezca el encabezado Authorization en la solicitud Http que envíe a "Bearer {token}" (El portador es el esquema de autorización)
- El tiempo de expiración del token es de 1 hora (puede enviar más de una solicitud con el mismo token)

- Ejemplo de envío de una solicitud para obtener una lista de alertas **mediante C#** 
    ```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="see-also"></a>Vea también
- [Compatible con Microsoft Defender para LAS API de punto de conexión](exposed-apis-list.md)
- [Access Microsoft Defender for Endpoint en nombre de un usuario](exposed-apis-create-app-nativeapp.md)
