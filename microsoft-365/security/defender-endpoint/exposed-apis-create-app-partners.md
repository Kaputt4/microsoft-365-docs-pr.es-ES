---
title: Acceso de asociados a través de api de Microsoft Defender para punto de conexión
ms.reviewer: ''
description: Obtenga información sobre cómo diseñar una aplicación web para obtener acceso mediante programación a Microsoft Defender para punto de conexión en nombre de los usuarios.
keywords: api, graph api, api admitidas, actor, alertas, dispositivo, usuario, dominio, ip, archivo, búsqueda avanzada, consulta
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 78eb829a936d5e07abde3ff46d90c71b5004e956
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67697833"
---
# <a name="partner-access-through-microsoft-defender-for-endpoint-apis"></a>Acceso de asociados a través de api de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:** 
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para Empresas](../defender-business/index.yml)

> [!IMPORTANT]
> Las funcionalidades avanzadas de búsqueda no se incluyen en Defender para empresas. Consulte [Comparar Microsoft Defender para Empresas con los planes 1 y 2 de Microsoft Defender para punto de conexión](../defender-business/compare-mdb-m365-plans.md#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2).


> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

En esta página se describe cómo crear una aplicación de Azure Active Directory (Azure AD) para obtener acceso mediante programación a Microsoft Defender para punto de conexión en nombre de los clientes.

Microsoft Defender para punto de conexión expone gran parte de sus datos y acciones a través de un conjunto de API mediante programación. Esas API le ayudarán a automatizar los flujos de trabajo e innovar en función de Microsoft Defender para punto de conexión funcionalidades. El acceso a la API requiere la autenticación de OAuth2.0. Para obtener más información, vea [Flujo de código de autorización de OAuth 2.0](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

En general, deberá realizar los pasos siguientes para usar las API:

- Cree una aplicación de Azure AD **multiinquilino** .
- Obtenga autorización (consentimiento) por parte del administrador del cliente para que la aplicación acceda a los recursos de Defender para punto de conexión que necesita.
- Obtenga un token de acceso mediante esta aplicación.
- Use el token para acceder a Microsoft Defender para punto de conexión API.

Los pasos siguientes le guiarán para crear una aplicación de Azure AD, obtener un token de acceso para Microsoft Defender para punto de conexión y validar el token.

## <a name="create-the-multi-tenant-app"></a>Creación de la aplicación multiinquilino

1. Inicie sesión en el [inquilino de Azure](https://portal.azure.com) con un usuario que tenga el rol **de administrador global** .

2. Vaya a **Azure Active Directory** \> **Registros de aplicaciones** \> **Nuevo registro**.

   :::image type="content" source="images/atp-azure-new-app2.png" alt-text="Panel de navegación al registro de aplicaciones" lightbox="images/atp-azure-new-app2.png":::

3. En el formulario de registro:

   - Elija un nombre para la aplicación.

   - Tipos de cuenta admitidos: cuentas en cualquier directorio organizativo.

   - URI de redirección: tipo: Web, URI: https://portal.azure.com

     :::image type="content" source="images/atp-api-new-app-partner.png" alt-text="Página de registro de aplicaciones asociadas de Microsoft Azure" lightbox="images/atp-api-new-app-partner.png":::

4. Permita que la aplicación acceda a Microsoft Defender para punto de conexión y asígnela con el conjunto mínimo de permisos necesarios para completar la integración.

   - En la página de la aplicación, seleccione **Permisos** \> de API **Agregar API de permisos** \> **Que mi organización usa** > escriba **WindowsDefenderATP** y seleccione en **WindowsDefenderATP**.

   - **Nota**: *WindowsDefenderATP* no aparece en la lista original. Empiece a escribir su nombre en el cuadro de texto para verlo aparecer.

     :::image type="content" source="images/add-permission.png" alt-text="La opción Agregar un permiso" lightbox="images/add-permission.png":::

### <a name="request-api-permissions"></a>Solicitar permisos de API

Para determinar qué permiso necesita, revise la sección **Permisos** de la API a la que está interesado llamar. Por ejemplo:

- Para [ejecutar consultas avanzadas](run-advanced-query-api.md), seleccione el permiso "Ejecutar consultas avanzadas".
- Para [aislar un dispositivo](isolate-machine.md), seleccione el permiso "Aislar máquina".

En el ejemplo siguiente usaremos el permiso **"Leer todas las alertas"** :

1. Elija **Permisos** \> de aplicación **Alert.Read.All** > seleccione Agregar **permisos**.

   :::image type="content" source="images/application-permissions.png" alt-text="La opción que permite agregar un permiso" lightbox="images/application-permissions.png":::

2. Seleccione **Conceder consentimiento**

   - **Nota**: Cada vez que agregue permiso, debe seleccionar en **Conceder consentimiento** para que el nuevo permiso surta efecto.

   :::image type="content" source="images/grant-consent.png" alt-text="La opción que permite conceder el consentimiento" lightbox="images/grant-consent.png":::

3. Agregue un secreto a la aplicación.

   - Seleccione **Certificados & secretos**, agregue la descripción al secreto y seleccione **Agregar**.

    **Importante**: Después de hacer clic en Agregar, **copie el valor de secreto generado**. ¡No podrás recuperarlo después de irte!

     :::image type="content" source="images/webapp-create-key2.png" alt-text="La clave de creación de la aplicación" lightbox="images/webapp-create-key2.png":::

4. Anote el identificador de la aplicación:

   - En la página de la aplicación, vaya a **Información general** y copie la siguiente información:

     :::image type="content" source="images/app-id.png" alt-text="Identificador de la aplicación de creación" lightbox="images/app-id.png":::

5. Agregue la aplicación al inquilino del cliente.

   Necesita que la aplicación se apruebe en cada inquilino de cliente en el que quiera usarlo. Esto se debe a que la aplicación interactúa con Microsoft Defender para punto de conexión aplicación en nombre del cliente.

   Un usuario con **administrador global** del inquilino del cliente debe seleccionar el vínculo de consentimiento y aprobar la aplicación.

   El vínculo de consentimiento tiene el siguiente formato:

   ```http
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   Donde 0000000000-0000-0000-0000-0000000000000 debe reemplazarse por el identificador de aplicación

   Después de hacer clic en el vínculo de consentimiento, inicie sesión con el administrador global del inquilino del cliente y dé su consentimiento a la aplicación.

   :::image type="content" source="images/app-consent-partner.png" alt-text="Botón Aceptar" lightbox="images/app-consent-partner.png":::

   Además, tendrá que pedir al cliente su identificador de inquilino y guardarlo para su uso futuro al adquirir el token.

6. **¡Hecho!** Ha registrado correctamente una aplicación. Consulte los ejemplos siguientes para la adquisición y validación de tokens.

## <a name="get-an-access-token-example"></a>Obtener un ejemplo de token de acceso

**Nota:** Para obtener el token de acceso en nombre del cliente, use el identificador de inquilino del cliente en las siguientes adquisiciones de tokens.

Para obtener más información sobre el token de AAD, consulte [el tutorial de AAD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

### <a name="using-powershell"></a>Con PowerShell

```powershell
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

### <a name="using-c"></a>Uso de C #

> El código siguiente se ha probado con Nuget Microsoft.Identity.Client.

> [!IMPORTANT]
> El paquete [NuGet Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory) y Autenticación de Azure AD Library (ADAL) han quedado en desuso. No se han agregado nuevas características desde el 30 de junio de 2020. Le recomendamos encarecidamente que actualice, consulte la [guía de migración](/azure/active-directory/develop/msal-migration) para obtener más detalles.

- Creación de una nueva aplicación de consola
- Instalación de NuGet [Microsoft.Identity.Client](https://www.nuget.org/packages/Microsoft.Identity.Client/)
- Agregue lo siguiente mediante

    ```console
    using Microsoft.Identity.Client;
    ```

- Copie o pegue el código siguiente en la aplicación (no olvide actualizar las tres variables: `tenantId`, `appId`y `appSecret`)

    ```csharp
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 
    const string authority = https://login.microsoftonline.com;
    const string audience = https://api.securitycenter.microsoft.com;

    IConfidentialClientApplication myApp = ConfidentialClientApplicationBuilder.Create(appId).WithClientSecret(appSecret).WithAuthority($"{authority}/{tenantId}").Build();

    List<string> scopes = new List<string>() { $"{audience}/.default" };

    AuthenticationResult authResult = myApp.AcquireTokenForClient(scopes).ExecuteAsync().GetAwaiter().GetResult();

    string token = authResult.AccessToken;
    ```

### <a name="using-python"></a>Uso de Python

Consulte [Obtención de un token mediante Python.](run-advanced-query-sample-python.md#get-token)

### <a name="using-curl"></a>Uso de Curl

> [!NOTE]
> El procedimiento siguiente supone que Curl para Windows ya está instalado en el equipo.

- Abrir una ventana de comandos
- Establecimiento de CLIENT_ID en el identificador de aplicación de Azure
- Establecimiento de CLIENT_SECRET en el secreto de aplicación de Azure
- Establezca TENANT_ID en el identificador de inquilino de Azure del cliente que quiere usar la aplicación para acceder a Microsoft Defender para punto de conexión aplicación.
- Ejecute el siguiente comando:

```curl
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Obtendrá una respuesta del formulario:

```console
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Validar el token

Comprobación de integridad para asegurarse de que tiene un token correcto:

- Copie o pegue en [JWT](https://jwt.ms) el token que obtiene en el paso anterior para descodificarlo.
- Validar que obtiene una notificación de "roles" con los permisos deseados
- En la captura de pantalla siguiente, puede ver un token descodificado adquirido de una aplicación con varios permisos para Microsoft Defender para punto de conexión:
- La notificación "tid" es el identificador de inquilino al que pertenece el token.

:::image type="content" source="images/webapp-decoded-token.png" alt-text="Página de validación de tokens" lightbox="images/webapp-decoded-token.png":::

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>Uso del token para acceder a Microsoft Defender para punto de conexión API

- Elija la API que desea usar. Para obtener más información, consulte [Api de Microsoft Defender para punto de conexión compatibles](exposed-apis-list.md).
- Establezca el encabezado Authorization en la solicitud Http que envíe a "Bearer {token}" (Bearer es el esquema de autorización)
- La hora de expiración del token es de 1 hora (puede enviar más de una solicitud con el mismo token)

- Ejemplo de envío de una solicitud para obtener una lista de alertas **mediante C#**

    ```csharp
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="see-also"></a>Vea también

- [API compatibles de Microsoft Defender para punto de conexión](exposed-apis-list.md)
- [Acceso a Microsoft Defender para punto de conexión en nombre de un usuario](exposed-apis-create-app-nativeapp.md)
