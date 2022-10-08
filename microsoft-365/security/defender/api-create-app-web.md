---
title: Creación de una aplicación para acceder a Microsoft 365 Defender sin un usuario
description: Obtenga información sobre cómo crear una aplicación para acceder a Microsoft 365 Defender sin un usuario.
keywords: app, access, api, create
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.custom: api
ms.openlocfilehash: 168d935aeb534251f19d32fc9d83377731b1d1ee
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68067078"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a>Creación de una aplicación para acceder a Microsoft 365 Defender sin un usuario

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

En esta página se describe cómo crear una aplicación para obtener acceso mediante programación a Microsoft 365 Defender sin un usuario definido, por ejemplo, si está creando un demonio o un servicio en segundo plano.

Si necesita acceso mediante programación a Microsoft 365 Defender en nombre de uno o varios usuarios, consulte [Creación de una aplicación para acceder a Microsoft 365 Defender API en nombre de un usuario](api-create-app-user-context.md) y [Creación de una aplicación con acceso de asociado a Microsoft 365 Defender API](api-partner-access.md). Si no está seguro del tipo de acceso que necesita, consulte [Introducción](api-access.md).

Microsoft 365 Defender expone gran parte de sus datos y acciones a través de un conjunto de API mediante programación. Esas API le ayudan a automatizar flujos de trabajo y a usar las funcionalidades de Microsoft 365 Defender. Este acceso a la API requiere la autenticación de OAuth2.0. Para obtener más información, vea [Flujo de código de autorización de OAuth 2.0](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

En general, deberá realizar los pasos siguientes para usar estas API:

- Cree una aplicación de Azure Active Directory (Azure AD).
- Obtenga un token de acceso mediante esta aplicación.
- Use el token para acceder a Microsoft 365 Defender API.

En este artículo se explica cómo:

- Crear una aplicación Azure AD
- Obtención de un token de acceso para Microsoft 365 Defender
- Valide el token.

## <a name="create-an-app"></a>Crear una aplicación

1. Inicie sesión en [Azure](https://portal.azure.com) como usuario con el rol **Administrador global** .

2. Vaya a **Azure Active Directory** >  **Registros de aplicaciones** >  **Nuevo registro**.

   :::image type="content" source="../../media/atp-azure-new-app2.png" alt-text="Pestaña Nuevo registro en el portal de Microsoft 365 Defender" lightbox="../../media/atp-azure-new-app2.png":::

3. En el formulario, elija un nombre para la aplicación y, a continuación, seleccione **Registrar**.

4. En la página de la aplicación, seleccione **Permisos** >  de API **Agregar API de permisos** > **Que mi organización usa** >, escriba **Microsoft Threat Protection** y seleccione **Microsoft Threat Protection**. La aplicación ahora puede acceder a Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection* es un nombre anterior para Microsoft 365 Defender y no aparecerá en la lista original. Debe empezar a escribir su nombre en el cuadro de texto para verlo aparecer.

   :::image type="content" source="../../media/apis-in-my-org-tab.PNG" alt-text="Pestaña Uso de LAS API de la organización en el portal de Microsoft 365 Defender" lightbox="../../media/apis-in-my-org-tab.PNG":::

5. Seleccione **Permisos de aplicación**. Elija los permisos pertinentes para el escenario (por ejemplo, **Incident.Read.All**) y, a continuación, seleccione **Agregar permisos**.

   :::image type="content" source="../../media/request-api-permissions.PNG" alt-text="Panel de permisos de la aplicación en el portal de Microsoft 365 Defender" lightbox="../../media/request-api-permissions.PNG":::

    > [!NOTE]
    > Debe seleccionar los permisos pertinentes para el escenario. *Leer todos los incidentes* es solo un ejemplo. Para determinar qué permiso necesita, consulte la sección **Permisos** de la API a la que desea llamar.
    >
    > Por ejemplo, para [ejecutar consultas avanzadas](api-advanced-hunting.md), seleccione el permiso "Ejecutar consultas avanzadas"; Para [aislar un dispositivo](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), seleccione el permiso "Aislar máquina".

6. Seleccione **Conceder consentimiento de administrador**. Cada vez que agregue un permiso, debe seleccionar **Conceder consentimiento del administrador** para que surta efecto.

    :::image type="content" source="../../media/grant-consent.PNG" alt-text="Panel relacionado con la concesión de consentimiento en el portal de Microsoft 365 Defender" lightbox="../../media/grant-consent.PNG":::

7. Para agregar un secreto a la aplicación, seleccione **Certificados & secretos**, agregue una descripción al secreto y, a continuación, seleccione **Agregar**.

    > [!TIP]
    > Después de seleccionar **Agregar**, seleccione **Copiar el valor de secreto generado**. No podrá recuperar el valor del secreto después de salir.

    :::image type="content" source="../../media/defender-endpoint/webapp-create-key2.png" alt-text="Panel Crear aplicación en el portal de Microsoft 365 Defender" lightbox="../../media/defender-endpoint/webapp-create-key2.png":::

8. Registre el identificador de la aplicación y el identificador de inquilino en un lugar seguro. Se enumeran en **Información general** en la página de la aplicación.

   :::image type="content" source="../../media/app-and-tenant-ids.png" alt-text="Panel Información general del portal de Microsoft 365 Defender" lightbox="../../media/app-and-tenant-ids.png":::

9. **Solo para asociados de Microsoft 365 Defender**: [siga estas instrucciones](./api-partner-access.md) para el acceso de asociados a través de las API de Microsoft 365 Defender, establezca la aplicación como multiinquilino, de modo que pueda estar disponible en todos los inquilinos una vez que reciba el consentimiento del administrador. El acceso de asociados es **necesario** para aplicaciones de terceros, por ejemplo, si crea una aplicación destinada a ejecutarse en varios inquilinos de clientes. No es **necesario** si crea un servicio que solo desea ejecutar en el inquilino, como una aplicación para su propio uso que solo interactuará con sus propios datos. Para establecer la aplicación como multiinquilino:

    - Vaya a **Autenticación** y agregue https://portal.azure.com como uri de **redirección**.

    - En la parte inferior de la página, en **Tipos de cuenta admitidos**, seleccione el consentimiento **de la aplicación Cuentas en cualquier directorio organizativo** para la aplicación multiinquilino.

    Dado que la aplicación interactúa con Microsoft 365 Defender en nombre de los usuarios, debe aprobarse para cada inquilino en el que quiera usarlo.

    El administrador global de Active Directory para cada inquilino debe seleccionar el vínculo de consentimiento y aprobar la aplicación.

    El vínculo de consentimiento tiene la siguiente estructura:

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    Los dígitos `00000000-0000-0000-0000-000000000000` se deben reemplazar por el identificador de aplicación.  

**¡Hecho!** Ha registrado correctamente una aplicación. Consulte los ejemplos siguientes para la adquisición y validación de tokens.

## <a name="get-an-access-token"></a>Obtener un token de acceso

Para obtener más información sobre los tokens de Azure Active Directory, consulte el [tutorial de Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

> [!IMPORTANT]
> Aunque los ejemplos de esta sección le animan a pegar valores secretos con fines de prueba, **nunca debe codificar de forma rígida los secretos** en una aplicación que se ejecuta en producción. Un tercero podría usar el secreto para acceder a los recursos. Puede ayudar a proteger los secretos de la aplicación mediante [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates). Para obtener un ejemplo práctico de cómo proteger la aplicación, consulte [Administración de secretos en las aplicaciones de servidor con Azure Key Vault](/training/modules/manage-secrets-with-azure-key-vault/).

### <a name="get-an-access-token-using-powershell"></a>Obtención de un token de acceso mediante PowerShell

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

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

### <a name="get-an-access-token-using-c"></a>Obtención de un token de acceso mediante C\#

> [!NOTE]
> El código siguiente se ha probado con Nuget Microsoft.Identity.Client 3.19.8.

> [!IMPORTANT]
> El paquete [NuGet Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory) y Autenticación de Azure AD Library (ADAL) han quedado en desuso. No se han agregado nuevas características desde el 30 de junio de 2020.   Le recomendamos encarecidamente que actualice, consulte la [guía de migración](/azure/active-directory/develop/msal-migration) para obtener más detalles.

1. Cree una nueva aplicación de consola.

1. Instale NuGet [Microsoft.Identity.Client](https://www.nuget.org/packages/Microsoft.Identity.Client/).

1. Agregue la línea siguiente:

    ```C#
    using Microsoft.Identity.Client;
    ```

1. Copie y pegue el código siguiente en la aplicación (no olvide actualizar las tres variables: `tenantId`, `clientId`, `appSecret`):

    ```C#
    csharp
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

### <a name="get-an-access-token-using-python"></a>Obtención de un token de acceso mediante Python

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.security.microsoft.com'

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

### <a name="get-an-access-token-using-curl"></a>Obtención de un token de acceso mediante curl

> [!NOTE]
> Curl está preinstalado en Windows 10, versiones 1803 y posteriores. Para otras versiones de Windows, descargue e instale la herramienta directamente desde el [sitio web oficial de curl](https://curl.haxx.se/windows/).

1. Abra un símbolo del sistema y establezca CLIENT_ID en el identificador de aplicación de Azure.

1. Establezca CLIENT_SECRET en el secreto de aplicación de Azure.

1. Establezca TENANT_ID en el identificador de inquilino de Azure del cliente que quiere usar la aplicación para acceder a Microsoft 365 Defender.

1. Ejecute el comando siguiente:

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   Una respuesta correcta tendrá el siguiente aspecto:

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a>Validar el token

1. Copie y pegue el token en el [sitio web de validador de token web JSON, JWT,](https://jwt.ms) para descodificarlo.

1. Asegúrese de que la notificación de *roles* dentro del token descodificado contiene los permisos deseados.

   En la imagen siguiente, puede ver un token descodificado adquirido de una aplicación, con `Incidents.Read.All`permisos , `Incidents.ReadWrite.All`y `AdvancedHunting.Read.All` :

   :::image type="content" source="../../media/defender-endpoint/webapp-decoded-token.png" alt-text="Panel Token descodificado del portal de Microsoft 365 Defender" lightbox="../../media/defender-endpoint/webapp-decoded-token.png":::

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Uso del token para acceder a la API de Microsoft 365 Defender

1. Elija la API que desea usar (incidentes o búsqueda avanzada). Para obtener más información, consulte [API de Microsoft 365 Defender compatibles](api-supported.md).

2. En la solicitud HTTP que va a enviar, establezca el encabezado `"Bearer" <token>`de autorización en , *Bearer* es el esquema de autorización y el *token* es el token validado.

3. El token expirará en una hora. Puede enviar más de una solicitud durante este tiempo con el mismo token.

En el ejemplo siguiente se muestra cómo enviar una solicitud para obtener una lista de incidentes **mediante C#**.

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Artículos relacionados

- [Introducción a las API de Microsoft 365 Defender](api-overview.md)
- [Acceso a las API de Microsoft 365 Defender](api-access.md)
- [Creación de una aplicación "Hola mundo"](api-hello-world.md)
- [Creación de una aplicación para acceder a Microsoft 365 Defender API en nombre de un usuario](api-create-app-user-context.md)
- [Creación de una aplicación con acceso de asociado multiinquilino a las API de Microsoft 365 Defender](api-partner-access.md)
- [Más información sobre los límites de API y las licencias](api-terms.md)
- [Descripción de los códigos de error](api-error-codes.md)
- [Administración de secretos en las aplicaciones de servidor con Azure Key Vault](/training/modules/manage-secrets-with-azure-key-vault/)
- [Autorización de OAuth 2.0 para el inicio de sesión de usuario y el acceso a la API](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
