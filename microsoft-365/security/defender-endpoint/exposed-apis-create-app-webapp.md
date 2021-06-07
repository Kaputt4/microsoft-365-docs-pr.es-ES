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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 4742a32fd899f41d4e7772c52415891cdd8895bf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769526"
---
# <a name="create-an-app-to-access-microsoft-defender-for-endpoint-without-a-user"></a>Crear una aplicación para tener acceso a Microsoft Defender para endpoint sin un usuario

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

En esta página se describe cómo crear una aplicación para obtener acceso mediante programación a Defender for Endpoint sin un usuario. Si necesita acceso mediante programación a Defender for Endpoint en nombre de un usuario, vea [Obtener acceso con contexto de usuario](exposed-apis-create-app-nativeapp.md). Si no está seguro de qué acceso necesita, vea [Introducción.](apis-intro.md)

Microsoft Defender para endpoint expone gran parte de sus datos y acciones a través de un conjunto de API programáticas. Estas API le ayudarán a automatizar los flujos de trabajo e innovar en función de las capacidades de Defender para endpoints. El acceso a la API requiere autenticación de OAuth2.0. Para obtener más información, vea Código de autorización [de OAuth 2.0 Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

En general, deberá seguir los pasos siguientes para usar las API:
- Crear una aplicación Azure Active Directory (Azure AD).
- Obtener un token de acceso con esta aplicación.
- Use el token para obtener acceso a la API de Defender for Endpoint.

En este artículo se explica cómo crear una aplicación de Azure AD, obtener un token de acceso a Microsoft Defender para Endpoint y validar el token.

## <a name="create-an-app"></a>Crear una aplicación

1. Inicie sesión en [Azure](https://portal.azure.com) con un usuario que tenga el rol **De administrador** global.

2. Vaya a **Azure Active Directory**  >  **registros de aplicaciones** Nuevo  >  **registro**. 

   ![Imagen de Microsoft Azure navegación al registro de aplicaciones](images/atp-azure-new-app2.png)

3. En el formulario de registro, elija un nombre para la aplicación y, a continuación, **seleccione Registrar**.

4. Para habilitar la aplicación para tener acceso a Defender for Endpoint y asignarle el permiso **"Leer** todas las **alertas",** en la página de la aplicación, seleccione Permisos de api Agregar api de permisos que mi organización usa >, escriba WindowsDefenderATP y, a continuación,  >    >   **seleccione WindowsDefenderATP**. 

   > [!NOTE]
   > *WindowsDefenderATP* no aparece en la lista original. Comience a escribir su nombre en el cuadro de texto para verlo aparecer.

   ![agregar permiso](images/add-permission.png)

   - Seleccione **Permisos de aplicación**  >  **Alert.Read.All** y, a continuación, seleccione Agregar **permisos**.

   ![permiso de la aplicación](images/application-permissions.png)

     Debe seleccionar los permisos pertinentes. "Leer todas las alertas" es solo un ejemplo. Por ejemplo:

     - Para [ejecutar consultas avanzadas,](run-advanced-query-api.md)seleccione el permiso "Ejecutar consultas avanzadas".
     - Para [aislar un dispositivo,](isolate-machine.md)seleccione el permiso "Aislar máquina".
     - Para determinar qué permiso necesita, consulte la sección **Permisos** de la API a la que le interesa llamar.

5. Seleccione **Conceder consentimiento**.

     > [!NOTE]
     > Cada vez que agregue un permiso, debe seleccionar Conceder **consentimiento** para que el nuevo permiso suba a efecto.

    ![Conceder permisos](images/grant-consent.png)

6. Para agregar un secreto a la aplicación, seleccione Certificados **& secretos,** agregue una descripción al secreto y, a continuación, **seleccione Agregar**.

    > [!NOTE]
    > Después de seleccionar **Agregar**, seleccione **copiar el valor secreto generado**. No podrá recuperar este valor después de salir.

    ![Imagen de crear clave de aplicación](images/webapp-create-key2.png)

7. Anote el identificador de aplicación y el identificador de inquilino. En la página de la aplicación, vaya a **Información general** y copie lo siguiente.

   ![Imagen del identificador de aplicación creado](images/app-and-tenant-ids.png)

8. **Solo para Microsoft Defender para socios de punto de conexión**. Establece la aplicación para que sea multiinquilino (disponible en todos los inquilinos después del consentimiento). Esto es **necesario para** aplicaciones de terceros (por ejemplo, si creas una aplicación destinada a ejecutarse en el inquilino de varios clientes). Esto no **es** necesario si crea un servicio que desea ejecutar solo en el espacio empresarial (por ejemplo, si crea una aplicación para su propio uso que solo interactuará con sus propios datos). Para establecer la aplicación como multiinquilino:

    - Vaya a **Autenticación** y agregue `https://portal.azure.com` como uri de **redireccionamiento**.

    - En la parte inferior de la página, en **Tipos** de cuenta admitidos, seleccione el consentimiento **cuentas** en cualquier aplicación de directorio de la organización para la aplicación multiinquilino.

    Necesita que la aplicación se apruebe en cada inquilino en el que tenga previsto usarlo. Esto se debe a que la aplicación interactúa con Defender for Endpoint en nombre del cliente.

    Tú (o tu cliente si estás escribiendo una aplicación de terceros) debes seleccionar el vínculo de consentimiento y aprobar la aplicación. El consentimiento debe realizarse con un usuario que tenga privilegios administrativos en Active Directory.

    El vínculo de consentimiento se forma de la siguiente manera: 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    Donde 00000000-0000-0000-0000-0000000000000000000000000000000000000000000000000000000000000000000000000000 se reemplaza por el identificador de aplicación.


**¡Listo!** Ha registrado correctamente una aplicación. Vea ejemplos a continuación para la adquisición y validación de tokens.

## <a name="get-an-access-token"></a>Obtener un token de acceso

Para obtener más información sobre los tokens de Azure AD, consulte el [tutorial de Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

### <a name="use-powershell"></a>Usar PowerShell

```powershell
# This script acquires the App Context Token and stores it in the variable $token for later use in the script.
# Paste your Tenant ID, App ID, and App Secret (App key) into the indicated quotes below.

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
```

### <a name="use-c"></a>Use C#:

El siguiente código se ha probado con NuGet Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.

1. Crear una nueva aplicación de consola.
1. Instale NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).
1. Agregue lo siguiente:

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Copie y pegue el siguiente código en la aplicación (no olvide actualizar las tres variables: ```tenantId, appId, appSecret``` ):

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


### <a name="use-python"></a>Usar Python

Consulta [Obtener token con Python](run-advanced-query-sample-python.md#get-token).

### <a name="use-curl"></a>Usar El rizo

> [!NOTE]
> En el siguiente procedimiento se presupone que El Windows ya está instalado en el equipo.

1. Abra un símbolo del sistema y establezca CLIENT_ID en el identificador de la aplicación de Azure.
1. Establece CLIENT_SECRET en el secreto de la aplicación de Azure.
1. Establece TENANT_ID en el identificador de inquilino de Azure del cliente que desea usar la aplicación para tener acceso a Defender for Endpoint.
1. Ejecute el siguiente comando:

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Recibirá una respuesta con el siguiente formulario:

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Validar el token

Asegúrese de que obtuvo el token correcto:

1. Copie y pegue el token que obtuvo en el paso anterior en [JWT](https://jwt.ms) para descodificarlo.
1. Validar que obtiene una notificación de "roles" con los permisos deseados
1. En la siguiente imagen, puedes ver un token descodificado adquirido desde una aplicación con permisos para todos los roles de Microsoft Defender para endpoint:

![Imagen de validación de tokens](images/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>Usar el token para obtener acceso a la API de Microsoft Defender para endpoint

1. Elija la API que desea usar. Para obtener más información, vea [Supported Defender for Endpoint API](exposed-apis-list.md).
1. Establezca el encabezado de autorización en la solicitud http que envíe a "Bearer {token}" (Bearer es el esquema de autorización).
1. El tiempo de expiración del token es de una hora. Puede enviar más de una solicitud con el mismo token.

A continuación se muestra un ejemplo de envío de una solicitud para obtener una lista de **alertas mediante C#**: 
```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="see-also"></a>Consulte también
- [API compatibles de Microsoft Defender para punto de conexión](exposed-apis-list.md)
- [Access Microsoft Defender for Endpoint en nombre de un usuario](exposed-apis-create-app-nativeapp.md)
