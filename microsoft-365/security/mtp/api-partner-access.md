---
title: Acceso de asociados a través de las API de Microsoft 365 defender
description: Obtenga información sobre cómo crear una aplicación para obtener acceso mediante programación a Microsoft 365 defender en nombre de sus usuarios.
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
ms.openlocfilehash: 5de113c8f8419b3af2a287bd7ba7e41dc06b4121
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719445"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a>Crear una aplicación con el acceso de socio a las API de Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

En esta página se describe cómo crear una aplicación de Azure Active Directory que tenga acceso mediante programación a Microsoft 365 defender, en nombre de los usuarios en varios inquilinos. Las aplicaciones multiinquilino resultan útiles para dar servicio a grandes grupos de usuarios.

Si necesita obtener acceso mediante programación a Microsoft 365 defender en nombre de un único usuario, vea [crear una aplicación para obtener acceso a las API de microsoft 365 en nombre de un usuario](api-create-app-user-context.md). Si necesita acceso sin que un usuario se haya definido explícitamente (por ejemplo, si está escribiendo una aplicación de fondo o un daemon), vea [crear una aplicación para obtener acceso a Microsoft 365 defender sin un usuario](api-create-app-web.md). Si no está seguro de qué tipo de acceso necesita, consulte [Introducción](api-access.md).

Microsoft 365 defender expone gran parte de sus datos y acciones a través de un conjunto de API de programación. Estas API le ayudan a automatizar flujos de trabajo y a usar las capacidades de Microsoft 365 defender. Este acceso a la API requiere la autenticación OAuth 2.0. Para obtener más información, vea [flujo de código de autorización de OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

En general, deberá realizar los siguientes pasos para usar estas API:

- Cree una aplicación de Azure Active Directory (Azure AD).
- Obtenga un token de acceso con esta aplicación.
- Use el token para obtener acceso a la API de Microsoft 365 defender.

Dado que esta aplicación es multiinquilino, también necesitará el [consentimiento del administrador](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) de cada inquilino en nombre de sus usuarios.

En este artículo se explica cómo:

- Crear una aplicación de Azure AD **de varios inquilinos**
- Obtenga consentimiento autorizado del administrador de su usuario para que su aplicación tenga acceso a Microsoft 365 defender que los recursos que necesita.
- Obtener un token de acceso a Microsoft 365 defender
- Validar el token

Microsoft 365 defender expone gran parte de sus datos y acciones a través de un conjunto de API de programación. Estas API le ayudarán a automatizar los flujos de trabajo y la innovación en función de las capacidades de Microsoft 365 defender. El acceso a la API requiere la autenticación OAuth 2.0. Para obtener más información, vea [flujo de código de autorización de OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

En general, deberá realizar los siguientes pasos para usar las API:

- Cree una aplicación de Azure AD **para varios inquilinos** .
- Obtenga autorización (consentimiento) del administrador del usuario para que su aplicación tenga acceso a los recursos de Microsoft 365 defender que necesita.
- Obtenga un token de acceso con esta aplicación.
- Use el token para obtener acceso a la API de Microsoft 365 defender.

Los siguientes pasos, que le guían cómo crear una aplicación de Azure AD multiempresa, obtener un token de acceso a Microsoft 365 defender y validar el token.

## <a name="create-the-multi-tenant-app"></a>Crear la aplicación multiinquilino

1. Inicie sesión en [Azure](https://portal.azure.com) como un usuario con el rol de **administrador global** .

2. Navegue a registros de aplicaciones de **Azure Active Directory**  >    >  **nuevo registro**.

   ![Imagen de Microsoft Azure y navegación en el registro de la aplicación](../../media/atp-azure-new-app2.png)

3. En el formulario de registro:

   - Elija un nombre para la aplicación.
   - En **tipos de cuenta admitidos**, seleccione **cuentas en cualquier directorio de la organización (cualquier directorio de Azure ad)-multiinquilino**.
   - Rellene la sección **URI de redireccionamiento** . Seleccione tipo **Web** y asigne el URI de redireccionamiento como **https://portal.azure.com** .

   Cuando haya acabado de rellenar el formulario, seleccione **registrar**.

   ![Imagen del formulario para registrar una aplicación](../..//media/atp-api-new-app-partner.png)

4. En la página de la aplicación, seleccione **permisos de API**  >  **Agregar** API de permisos  >  **mi organización usa** >, escriba **protección contra amenazas de Microsoft** y seleccione protección contra amenazas de **Microsoft**. La aplicación ahora puede tener acceso a Microsoft 365 defender.

   > [!TIP]
   > *Microsoft Threat Protection* es un nombre antiguo para Microsoft 365 defender y no aparecerá en la lista original. Debe empezar a escribir su nombre en el cuadro de texto para ver aparezca.

   ![Imagen de la selección de permisos de la API](../../media/apis-in-my-org-tab.PNG)

5. Seleccione **permisos** de la aplicación. Elija los permisos relevantes para su escenario (por ejemplo, **Incident. Read. All**) y, a continuación, seleccione **Agregar permisos**.

   ![Imagen de acceso a API y selección de API](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > Debe seleccionar los permisos relevantes para su escenario. *Leer todos los incidentes* es solo un ejemplo. Para determinar qué permiso necesita, consulte la sección **permisos** en la API que quiera llamar.
    >
    > Por ejemplo, para [ejecutar consultas avanzadas](api-advanced-hunting.md), seleccione el permiso "ejecutar consultas avanzadas"; para [aislar un dispositivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), seleccione el permiso "aislar equipo".

6. Seleccione **conceder consentimiento de administrador**. Cada vez que agregue un permiso, debe seleccionar **conceder consentimiento de administrador** para que surta efecto.

    ![Imagen de permisos de concesión](../../media/grant-consent.PNG)

7. Para agregar un secreto a la aplicación, seleccione **certificados & secretos**, agregue una descripción al secreto y, a continuación, seleccione **Agregar**.

    > [!TIP]
    > Después de seleccionar **Agregar**, seleccione **copiar el valor de secreto generado**. No podrá recuperar el valor secreto después de salir.

    ![Imagen de crear clave de aplicación](../../media/webapp-create-key2.png)

8. Registre el identificador de la aplicación y el identificador de inquilino en algún lugar seguro. Aparecen en **información general** en la página de la aplicación.

   ![Imagen del identificador de aplicación creado](../../media/app-and-tenant-ids.png)

9. Agregue la aplicación al espacio empresarial del usuario.

   Como su aplicación interactúa con Microsoft 365 defender en nombre de sus usuarios, debe ser aprobado para cada inquilino en el que desee usarlo.

   Un **administrador global** del espacio empresarial del usuario necesita ver el vínculo de consentimiento y aprobar la aplicación.

   El vínculo de consentimiento tiene el siguiente formato:

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   Los dígitos `00000000-0000-0000-0000-000000000000` deben reemplazarse por el identificador de la aplicación.

   Después de hacer clic en el vínculo consentimiento, inicie sesión con el administrador global del espacio empresarial del usuario y dé su consentimiento a la aplicación.

   ![Imagen de consentimiento](../../media/app-consent-partner.png)

   También debe pedir al usuario su identificador de espacio empresarial. El identificador de inquilino es uno de los identificadores usados para adquirir tokens de acceso.

- **Realiza!** Ha registrado correctamente una aplicación.
- Vea los siguientes ejemplos para la adquisición y validación de tokens.

## <a name="get-an-access-token"></a>Obtener un token de acceso

Para obtener más información sobre los tokens de Azure AD, vea el [tutorial de Azure ad](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

> [!IMPORTANT]
> Aunque los ejemplos de esta sección le invitan a pegar los valores secretos con fines de prueba, **nunca debe codificar secretos** en una aplicación que se ejecuta en producción. Un tercero puede usar su secreto para obtener acceso a los recursos. Puede ayudar a mantener la seguridad de los secretos de la aplicación mediante [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates). Para obtener un ejemplo práctico de cómo puede proteger su aplicación, consulte [Manage Secrets in your Server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).

> [!TIP]
> En los ejemplos siguientes, use el identificador de inquilino de un usuario para comprobar que el script está funcionando.

### <a name="get-an-access-token-using-powershell"></a>Obtener un token de acceso con PowerShell

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

### <a name="get-an-access-token-using-c"></a>Obtener un token de acceso con C\#

> [!NOTE]
> El siguiente código se probó con Nuget Microsoft. IdentityModel. clients. ActiveDirectory 3.19.8.

1. Cree una nueva aplicación de consola.
1. Instale NuGet [Microsoft. IdentityModel. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).
1. Agregue la siguiente línea:

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Copie y pegue el siguiente código en la aplicación (no olvide actualizar las tres variables: `tenantId` , `clientId` `appSecret` ):

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

### <a name="get-an-access-token-using-python"></a>Obtener un token de acceso con Python

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

### <a name="get-an-access-token-using-curl"></a>Obtener un token de acceso con rizo

> [!NOTE]
> Doblez está preinstalado en Windows 10, versiones 1803 y posteriores. Para otras versiones de Windows, descargue e instale la herramienta directamente desde el [sitio web oficial de rizo](https://curl.haxx.se/windows/).

1. Abra un símbolo del sistema y establezca CLIENT_ID en el identificador de la aplicación de Azure.
1. Establezca CLIENT_SECRET en el secreto de la aplicación de Azure.
1. Establezca TENANT_ID el identificador de inquilino de Azure del usuario que quiera usar su aplicación para acceder a Microsoft 365 defender.
1. Ejecute el siguiente comando:

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Una respuesta correcta tendrá el siguiente aspecto:

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Validar el token

1. Copie y pegue el token en el [sitio web de validación de token Web de JSON, JWT,](https://jwt.ms) para descodificarlo.
1. Asegúrese de que la notificación de *roles* dentro del token descodificado contenga los permisos deseados.

En la siguiente imagen, puede ver un token descodificado adquirido de una aplicación, con ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` y ```AdvancedHunting.Read.All``` permisos:

![Imagen de validación de tokens](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Usar el token para obtener acceso a la API de Microsoft 365 defender

1. Elige la API que quieras usar (incidentes o búsqueda avanzada). Para obtener más información, consulte las [API admitidas de Microsoft 365 defender](api-supported.md).
2. En la solicitud HTTP que va a enviar, establezca el encabezado Authorization en `"Bearer" <token>` , el *portador* es el esquema de autorización y el *token* es su token validado.
3. El token expirará en una hora. Puede enviar más de una solicitud durante este tiempo con el mismo token.

En el ejemplo siguiente se muestra cómo enviar una solicitud para obtener una lista de incidentes **con C#**.

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Artículos relacionados

- [Información general sobre las API de Microsoft 365 defender](api-overview.md)
- [Acceso a las API de Microsoft 365 defender](api-access.md)
- [Crear una aplicación "Hello World"](api-hello-world.md)
- [Crear una aplicación para obtener acceso a Microsoft 365 defender sin un usuario](api-create-app-web.md)
- [Crear una aplicación para acceder a las API de Microsoft 365 defender en nombre de un usuario](api-create-app-user-context.md)
- [Obtenga información sobre los límites de API y las licencias](api-terms.md)
- [Descripción de los códigos de error](api-error-codes.md)
- [Administrar secretos en las aplicaciones de servidor con Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2,0 autorización para el inicio de sesión de usuario y el acceso a API](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
