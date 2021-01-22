---
title: Crear una aplicación para acceder a Microsoft 365 Defender sin un usuario
description: Obtenga información sobre cómo crear una aplicación para acceder a Microsoft 365 Defender sin un usuario.
keywords: aplicación, acceso, api, crear
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
ms.openlocfilehash: f438189b4ba9fb66124650782b3de2ee34dfee64
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928443"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a>Crear una aplicación para acceder a Microsoft 365 Defender sin un usuario

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información está relacionada con el producto de versión preliminar que puede modificarse considerablemente antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

En esta página se describe cómo crear una aplicación para obtener acceso mediante programación a Microsoft 365 Defender sin un usuario definido, por ejemplo, si está creando un demonio o un servicio en segundo plano.

Si necesita acceso mediante programación a Microsoft 365 Defender en nombre de uno o más usuarios, vea Crear una aplicación para obtener acceso a las API de [Microsoft 365 Defender](api-create-app-user-context.md) en nombre de un usuario y Crear una aplicación con acceso de asociado a las API de [Microsoft 365 Defender.](api-partner-access.md) Si no está seguro del tipo de acceso que necesita, vea [Introducción.](api-access.md)

Microsoft 365 Defender expone gran parte de sus datos y acciones a través de un conjunto de API mediante programación. Estas API le ayudan a automatizar flujos de trabajo y a usar las capacidades de Microsoft 365 Defender. Este acceso a la API requiere la autenticación OAuth2.0. Para obtener más información, vea [OAuth 2.0 Flujo de código de autorización.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

En general, deberá seguir los pasos siguientes para usar estas API:

- Cree una aplicación de Azure Active Directory (Azure AD).
- Obtenga un token de acceso con esta aplicación.
- Use el token para obtener acceso a la API de Microsoft 365 Defender.

En este artículo se explica cómo:

- Crear una aplicación de Azure AD
- Obtener un token de acceso a Microsoft 365 Defender
- Valide el token.

## <a name="create-an-app"></a>Crear una aplicación

1. Inicie sesión en [Azure](https://portal.azure.com) como usuario con el rol **de administrador** global.

2. Vaya a **Registros de aplicaciones de Azure Active Directory** Nuevo  >    >  **registro.**

   ![Imagen de Microsoft Azure y navegación al registro de aplicaciones](../../media/atp-azure-new-app2.png)

3. En el formulario, elija un nombre para la aplicación y, a continuación, **seleccione Registrar**.

4. En la página de la aplicación, seleccione Permisos de **API** Agregar API de permisos que mi organización usa >, escriba Protección contra amenazas de Microsoft y  >    >   seleccione Protección **contra amenazas de Microsoft.**  La aplicación ahora puede acceder a Microsoft 365 Defender.

   > [!TIP]
   > *La Protección contra amenazas* de Microsoft es un nombre anterior de Microsoft 365 Defender y no aparecerá en la lista original. Debe empezar a escribir su nombre en el cuadro de texto para que aparezca.

   ![Imagen de selección de permisos de API](../../media/apis-in-my-org-tab.PNG)

5. Seleccione **Permisos de aplicación.** Elija los permisos relevantes para su escenario (por ejemplo, **Incident.Read.All**) y, a continuación, **seleccione Agregar permisos.**

   ![Imagen de acceso api y selección de API](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > Debe seleccionar los permisos relevantes para su escenario. *Leer todos los incidentes* es solo un ejemplo. Para determinar qué permiso necesita, consulte la **sección Permisos** de la API a la que desea llamar.
    >
    > Por ejemplo, para [ejecutar consultas avanzadas,](api-advanced-hunting.md)seleccione el permiso "Ejecutar consultas avanzadas"; para [aislar un dispositivo,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)seleccione el permiso "Aislar máquina".

6. Seleccione **Conceder consentimiento de administrador.** Cada vez que agregue un permiso, debe seleccionar Conceder consentimiento **de administrador** para que su efecto.

    ![Imagen de Concesión de permisos](../../media/grant-consent.PNG)

7. Para agregar un secreto a la aplicación, seleccione Certificados **& secretos,** agregue una descripción al secreto y, a continuación, **seleccione Agregar**.

    > [!TIP]
    > Después de seleccionar **Agregar**, seleccione **copiar el valor secreto generado.** No podrá recuperar el valor secreto después de salir.

    ![Imagen de crear clave de aplicación](../../media/webapp-create-key2.png)

8. Registre el id. de aplicación y el id. de espacio empresarial en algún lugar seguro. Aparecen en Información **general en** la página de la aplicación.

   ![Imagen del id. de aplicación creado](../../media/app-and-tenant-ids.png)

9. Solo para partners de Microsoft [](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access) **365 Defender:** siga estas instrucciones para el acceso de asociados a través de las API de Microsoft 365 Defender, establezca la aplicación como multiinquilino para que pueda estar disponible en todos los inquilinos una vez que reciba el consentimiento del administrador. El acceso de **partners es** necesario para aplicaciones de terceros, por ejemplo, si creas una aplicación que está pensada para ejecutarse en los inquilinos de varios clientes. No es **necesario si** crea un servicio que desea ejecutar solo en su espacio empresarial, como una aplicación para su propio uso que solo interactuará con sus propios datos. Para establecer la aplicación como multiinquilino:

    - Vaya a **Autenticación** y agregue https://portal.azure.com como uri de **redireccionamiento.**

    - En la parte inferior de la página,  **en** Tipos de cuenta admitidos, seleccione las cuentas en cualquier consentimiento de aplicación de directorio de la organización para la aplicación multiinquilino.

    Dado que la aplicación interactúa con Microsoft 365 Defender en nombre de los usuarios, debe aprobarse para todos los inquilinos en los que se va a usar.

    El administrador global de Active Directory para cada inquilino debe seleccionar el vínculo de consentimiento y aprobar la aplicación.

    El vínculo de consentimiento tiene la siguiente estructura:

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    Los `00000000-0000-0000-0000-000000000000` dígitos deben reemplazarse por su id. de aplicación.  

**¡Listo!** Ha registrado correctamente una aplicación. Consulta los ejemplos siguientes para la adquisición y validación de tokens.

## <a name="get-an-access-token"></a>Obtener un token de acceso

Para obtener más información sobre los tokens de Azure Active Directory, vea el [tutorial de Azure AD.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

> [!IMPORTANT]
> Aunque los ejemplos de esta sección le animan a pegar  valores secretos con fines de prueba, nunca debe codificar secretos en una aplicación que se ejecuta en producción. Un tercero podría usar su secreto para obtener acceso a los recursos. Puede ayudar a proteger los secretos de la aplicación con [Azure Key Vault.](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates) Para obtener un ejemplo práctico de cómo proteger la aplicación, vea Administrar secretos en las aplicaciones [de servidor con Azure Key Vault.](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)

### <a name="get-an-access-token-using-powershell"></a>Obtener un token de acceso con PowerShell

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

### <a name="get-an-access-token-using-c"></a>Obtener un token de acceso con C\#

> [!NOTE]
> El código siguiente se probó con Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.

1. Cree una nueva aplicación de consola.

1. Instale NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).

1. Agregue la siguiente línea:

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Copie y pegue el siguiente código en la aplicación (no olvide actualizar las tres variables: `tenantId` `clientId` , `appSecret` ):

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

### <a name="get-an-access-token-using-curl"></a>Obtener un token de acceso mediante el bucle

> [!NOTE]
> El arroba está preinstalado en Windows 10, versiones 1803 y posteriores. Para otras versiones de Windows, descargue e instale la herramienta directamente desde el [sitio web oficial de esta herramienta.](https://curl.haxx.se/windows/)

1. Abra un símbolo del sistema y establezca CLIENT_ID el identificador de la aplicación de Azure.

1. Establezca CLIENT_SECRET en el secreto de aplicación de Azure.

1. Establece TENANT_ID el identificador de inquilino de Azure del cliente que desea usar la aplicación para acceder a Microsoft 365 Defender.

1. Ejecute el siguiente comando:

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   Una respuesta correcta tendrá este aspecto:

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a>Validar el token

1. Copie y pegue el token en el sitio web del validador de [tokens web JSON, JWT,](https://jwt.ms) para descodificarlo.

1. Asegúrese de que la *notificación de roles* dentro del token descodificado contiene los permisos deseados.

   En la siguiente imagen, puede ver un token descodificado adquirido desde una aplicación, con `Incidents.Read.All` `Incidents.ReadWrite.All` , y `AdvancedHunting.Read.All` permisos:

   ![Imagen de validación de token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Usar el token para obtener acceso a la API de Microsoft 365 Defender

1. Elija la API que desea usar (incidentes o búsqueda avanzada). Para obtener más información, vea las API compatibles de [Microsoft 365 Defender.](api-supported.md)

2. En la solicitud http que va a enviar, establezca el encabezado de autorización en , Bearer es el esquema de autorización y el token es `"Bearer" <token>` el token validado.  

3. El token expirará en una hora. Puede enviar más de una solicitud durante este tiempo con el mismo token.

En el ejemplo siguiente se muestra cómo enviar una solicitud para obtener una lista de incidentes **con C#**.

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Artículos relacionados

- [Introducción a las API de Microsoft 365 Defender](api-overview.md)
- [Obtener acceso a las API de Microsoft 365 Defender](api-access.md)
- [Crear una aplicación "Hola a todos"](api-hello-world.md)
- [Crear una aplicación para acceder a las API de Microsoft 365 Defender en nombre de un usuario](api-create-app-user-context.md)
- [Crear una aplicación con acceso de asociado multiinquilino a las API de Microsoft 365 Defender](api-partner-access.md)
- [Más información sobre los límites de la API y las licencias](api-terms.md)
- [Comprender los códigos de error](api-error-codes.md)
- [Administrar secretos en las aplicaciones de servidor con Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [Autorización de OAuth 2.0 para el inicio de sesión del usuario y el acceso a la API](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
