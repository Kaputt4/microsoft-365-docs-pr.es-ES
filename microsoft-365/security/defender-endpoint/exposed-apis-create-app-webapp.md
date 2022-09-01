---
title: Creación de una aplicación para acceder a Microsoft Defender para punto de conexión sin un usuario
ms.reviewer: ''
description: Obtenga información sobre cómo diseñar una aplicación web para obtener acceso mediante programación a Microsoft Defender para punto de conexión sin un usuario.
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
ms.openlocfilehash: bd5c808ffef012f3c2cfefbb1bf664fe0e80babc
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67520091"
---
# <a name="create-an-app-to-access-microsoft-defender-for-endpoint-without-a-user"></a>Creación de una aplicación para acceder a Microsoft Defender para punto de conexión sin un usuario

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:** 
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para Empresas](../defender-business/index.yml)

> [!IMPORTANT]
> Las funcionalidades avanzadas de búsqueda no se incluyen en Defender para empresas. Consulte [Comparar Microsoft Defender para Empresas con los planes 1 y 2 de Microsoft Defender para punto de conexión](../defender-business/compare-mdb-m365-plans.md#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2).


> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

En esta página se describe cómo crear una aplicación para obtener acceso mediante programación a Defender for Endpoint sin un usuario. Si necesita acceso mediante programación a Defender para punto de conexión en nombre de un usuario, consulte [Obtención de acceso con el contexto de usuario](exposed-apis-create-app-nativeapp.md). Si no está seguro de qué acceso necesita, consulte [Introducción](apis-intro.md).

Microsoft Defender para punto de conexión expone gran parte de sus datos y acciones a través de un conjunto de API mediante programación. Esas API le ayudarán a automatizar los flujos de trabajo e innovar en función de las funcionalidades de Defender para punto de conexión. El acceso a la API requiere la autenticación de OAuth2.0. Para obtener más información, vea [Flujo de código de autorización de OAuth 2.0](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

En general, deberá realizar los pasos siguientes para usar las API:
- Cree una aplicación de Azure Active Directory (Azure AD).
- Obtenga un token de acceso mediante esta aplicación.
- Use el token para acceder a Defender for Endpoint API.

En este artículo se explica cómo crear una aplicación de Azure AD, obtener un token de acceso para Microsoft Defender para punto de conexión y validar el token.

## <a name="create-an-app"></a>Crear una aplicación

1. Inicie sesión en [Azure](https://portal.azure.com) con un usuario que tenga el rol **De administrador global** .

2. Vaya a **Azure Active Directory** \> **Registros de aplicaciones** \> **Nuevo registro**. 

    :::image type="content" source="images/atp-azure-new-app2.png" alt-text="Panel de registro de aplicaciones" lightbox="images/atp-azure-new-app2.png":::

3. En el formulario de registro, elija un nombre para la aplicación y, a continuación, seleccione **Registrar**.

4. Para permitir que la aplicación acceda a Defender para punto de conexión y asígnele el permiso **"Leer todas las alertas"** , en la página de la aplicación, seleccione **Permisos** \> de API Agregar API de **permisos** \> **que mi organización usa** >, escriba **WindowsDefenderATP** y, a continuación, seleccione **WindowsDefenderATP**.

   > [!NOTE]
   > *WindowsDefenderATP* no aparece en la lista original. Empiece a escribir su nombre en el cuadro de texto para verlo aparecer.

   :::image type="content" source="images/add-permission.png" alt-text="Panel Permisos de API" lightbox="images/add-permission.png":::

   Seleccione **Permisos** \> de aplicación **Alert.Read.All** y, a continuación, seleccione **Agregar permisos**.

   :::image type="content" source="images/application-permissions.png" alt-text="Panel de información de permisos de la aplicación" lightbox="images/application-permissions.png":::

     Debe seleccionar los permisos pertinentes. "Leer todas las alertas" es solo un ejemplo. Por ejemplo:

     - Para [ejecutar consultas avanzadas](run-advanced-query-api.md), seleccione el permiso "Ejecutar consultas avanzadas".
     - Para [aislar un dispositivo](isolate-machine.md), seleccione el permiso "Aislar máquina".
     - Para determinar qué permiso necesita, consulte la sección **Permisos** de la API a la que está interesado llamar.

5. Seleccione **Conceder consentimiento**.

     > [!NOTE]
     > Cada vez que agregue un permiso, debe seleccionar **Conceder consentimiento** para que el nuevo permiso surta efecto.

    :::image type="content" source="images/grant-consent.png" alt-text="Página Conceder permisos" lightbox="images/grant-consent.png":::

6. Para agregar un secreto a la aplicación, seleccione **Certificados & secretos**, agregue una descripción al secreto y, a continuación, seleccione **Agregar**.

    > [!NOTE]
    > Después de seleccionar **Agregar**, seleccione **Copiar el valor de secreto generado**. No podrá recuperar este valor después de salir.

      :::image type="content" source="images/webapp-create-key2.png" alt-text="La opción crear aplicación" lightbox="images/webapp-create-key2.png":::

7. Anote el identificador de la aplicación y el identificador de inquilino. En la página de la aplicación, vaya a **Información general** y copie lo siguiente.

   :::image type="content" source="images/app-and-tenant-ids.png" alt-text="Identificadores de inquilino y aplicación creados" lightbox="images/app-and-tenant-ids.png":::

8. **Solo para asociados Microsoft Defender para punto de conexión**. Establezca la aplicación en multiinquilino (disponible en todos los inquilinos después del consentimiento). Esto es **necesario** para aplicaciones de terceros (por ejemplo, si crea una aplicación destinada a ejecutarse en el inquilino de varios clientes). Esto **no es necesario** si crea un servicio que solo desea ejecutar en el inquilino (por ejemplo, si crea una aplicación para su propio uso que solo interactuará con sus propios datos). Para establecer que la aplicación sea multiinquilino:

    - Vaya a **Autenticación** y agregue `https://portal.azure.com` como uri de **redirección**.

    - En la parte inferior de la página, en **Tipos de cuenta admitidos**, seleccione el consentimiento **de la aplicación Cuentas en cualquier directorio organizativo** para la aplicación multiinquilino.

    Necesita que la aplicación se apruebe en cada inquilino en el que quiera usarlo. Esto se debe a que la aplicación interactúa con Defender para punto de conexión en nombre del cliente.

    Usted (o el cliente si está escribiendo una aplicación de terceros) debe seleccionar el vínculo de consentimiento y aprobar la aplicación. El consentimiento debe realizarse con un usuario que tenga privilegios administrativos en Active Directory.

    El vínculo de consentimiento se forma de la siguiente manera: 

    ```https
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    Donde 0000000000-0000-0000-0000-0000000000000 se reemplaza por el identificador de aplicación.


**¡Hecho!** Ha registrado correctamente una aplicación. Consulte los ejemplos siguientes para la adquisición y validación de tokens.

## <a name="get-an-access-token"></a>Obtener un token de acceso

Para más información sobre los tokens de Azure AD, consulte el [tutorial de Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

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
$token
```

### <a name="use-c"></a>Use C#:

El código siguiente se ha probado con NuGet Microsoft.Identity.Client 3.19.8.

> [!IMPORTANT]
> El paquete [NuGet Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory) y Autenticación de Azure AD Library (ADAL) han quedado en desuso. No se han agregado nuevas características desde el 30 de junio de 2020.   Le recomendamos encarecidamente que actualice, consulte la [guía de migración](/azure/active-directory/develop/msal-migration) para obtener más detalles.

1. Cree una nueva aplicación de consola.
1. Instale NuGet [Microsoft.Identity.Client](https://www.nuget.org/packages/Microsoft.Identity.Client/).
1. Agregue lo siguiente:

    ```csharp
    using Microsoft.Identity.Client;
    ```

1. Copie y pegue el código siguiente en la aplicación (no olvide actualizar las tres variables: ```tenantId, appId, appSecret```):

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
### <a name="use-python"></a>Uso de Python

Consulte [Obtención de token mediante Python](run-advanced-query-sample-python.md#get-token).

### <a name="use-curl"></a>Uso de Curl

> [!NOTE]
> En el procedimiento siguiente se supone que Curl para Windows ya está instalado en el equipo.

1. Abra un símbolo del sistema y establezca CLIENT_ID en el identificador de aplicación de Azure.
1. Establezca CLIENT_SECRET en el secreto de aplicación de Azure.
1. Establezca TENANT_ID en el identificador de inquilino de Azure del cliente que quiere usar la aplicación para acceder a Defender para punto de conexión.
1. Ejecute el comando siguiente:

    ```console
    curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
    ```
    
    Obtendrá una respuesta con el siguiente formato:
    
    ```console
    {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
    ```
    
## <a name="validate-the-token"></a>Validar el token

Asegúrese de que tiene el token correcto:

1. Copie y pegue el token que obtuvo en el paso anterior en [JWT](https://jwt.ms) para descodificarlo.

1. Valide que obtiene una notificación de "roles" con los permisos deseados.

   En la imagen siguiente, puede ver un token descodificado adquirido de una aplicación con permisos para todos los roles de Microsoft Defender para punto de conexión:

   :::image type="content" source="images/webapp-decoded-token.png" alt-text="La parte de detalles del token" lightbox="images/webapp-decoded-token.png":::

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>Uso del token para acceder a Microsoft Defender para punto de conexión API

1. Elija la API que desea usar. Para obtener más información, vea [Supported Defender for Endpoint API (Defender para API de punto de conexión admitido).](exposed-apis-list.md)
1. Establezca el encabezado de autorización en la solicitud http que envíe a "Bearer {token}" (Bearer es el esquema de autorización).
1. La hora de expiración del token es de una hora. Puede enviar más de una solicitud con el mismo token.

A continuación se muestra un ejemplo de envío de una solicitud para obtener una lista de alertas **mediante C#**:

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
