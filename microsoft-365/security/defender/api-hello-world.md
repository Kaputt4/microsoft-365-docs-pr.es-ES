---
title: Hello World para la API Microsoft 365 REST de Defender
description: Aprende a crear una aplicación y a usar un token para acceder a las API de Microsoft 365 Defender
keywords: app, token, access, aad, app, application registration, powershell, script, global administrator, permission, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ffdcf91da6b5def7d63e5fdb8ff51ddbdb1ec550
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072755"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Hello World para la API Microsoft 365 REST de Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

## <a name="get-incidents-using-a-simple-powershell-script"></a>Obtener incidentes con un script de PowerShell simple

Este proyecto debe tardar entre 5 y 10 minutos. Esta estimación de tiempo incluye registrar la aplicación y aplicar el código desde el script de ejemplo de PowerShell.

### <a name="register-an-app-in-azure-active-directory"></a>Registrar una aplicación en Azure Active Directory

1. Inicie sesión en [Azure](https://portal.azure.com) como usuario con el **rol De administrador** global.

2. Vaya a **Azure Active Directory**  >  **registros de aplicaciones** Nuevo  >  **registro**.

   ![Imagen de Microsoft Azure navegación al registro de aplicaciones](../../media/atp-azure-new-app2.png)

3. En el formulario de registro, elija un nombre para la aplicación y, a continuación, **seleccione Registrar**. Seleccionar un URI de redireccionamiento es opcional. No necesitará uno para completar este ejemplo.

4. En la página de la aplicación, seleccione Permisos de **API** Agregar API de permisos que mi organización usa  >    >   >, escriba **Protección contra amenazas de Microsoft** y seleccione **Protección contra amenazas de Microsoft**. La aplicación ahora puede acceder a Microsoft 365 Defender.

   > [!TIP]
   > *Protección contra amenazas de Microsoft* es un nombre antiguo de Microsoft 365 Defender y no aparecerá en la lista original. Debe empezar a escribir su nombre en el cuadro de texto para verlo aparecer.
   ![Imagen de selección de permisos de API](../../media/apis-in-my-org-tab.PNG)

   - Elija **Permisos de aplicación**  >  **Incident.Read.All** y seleccione Agregar **permisos**.

   ![Imagen de acceso a api y selección de API](../../media/request-api-permissions.PNG)

5. Seleccione **Conceder consentimiento de administrador**. Cada vez que agregue un permiso, debe seleccionar Conceder consentimiento **de administrador** para que su efecto.

    ![Imagen de concesión de permisos](../../media/grant-consent.PNG)

6. Agregue un secreto a la aplicación. Seleccione **Certificados & secretos,** agregue una descripción al secreto y, a continuación, **seleccione Agregar**.

    > [!TIP]
    > Después de seleccionar **Agregar**, seleccione **copiar el valor secreto generado**. No podrá recuperar el valor secreto después de salir.

    ![Imagen de crear clave de aplicación](../../media/webapp-create-key2.png)

7. Registre el identificador de la aplicación y el identificador de inquilino en un lugar seguro. Aparecen en Información **general en** la página de la aplicación.

   ![Imagen del identificador de aplicación creado](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>Obtener un token con la aplicación y usar el token para obtener acceso a la API

Para obtener más información sobre Azure Active Directory tokens, consulte el [tutorial de Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

> [!IMPORTANT]
> Aunque el ejemplo de esta aplicación de demostración te anima a  pegar el valor secreto con fines de prueba, nunca debes codificar los secretos en una aplicación que se ejecute en producción. Un tercero podría usar el secreto para obtener acceso a los recursos. Puedes ayudar a proteger los secretos de la aplicación con [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates). Para obtener un ejemplo práctico de cómo proteger la aplicación, consulta Administrar secretos en las aplicaciones de servidor [con Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).

1. Copie el script siguiente y péguelo en el editor de texto favorito. Guardar como **Get-Token.ps1**. También puede ejecutar el código tal como está en PowerShell ISE, pero debe guardarlo, ya que tendremos que volver a ejecutarlo cuando usemos el script de captura de incidentes en la siguiente sección.

    Este script generará un token y lo guardará en la carpeta de trabajo bajo el nombre, *Latest-token.txt*.

    ```PowerShell
    # This script gets the app context token and saves it to a file named "Latest-token.txt" under the current directory.
    # Paste in your tenant ID, client ID and app secret (App key).

    $tenantId = '' # Paste your directory (tenant) ID here
    $clientId = '' # Paste your application (client) ID here
    $appSecret = '' # # Paste your own app secret here to test, then store it in a safe place!

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

#### <a name="validate-the-token"></a>Validar el token

1. Copie y pegue el token que recibió en [JWT](https://jwt.ms) para descodificarlo.
1. *JWT* significa *token web JSON*. El token descodificado contendrá una serie de notificaciones o elementos con formato JSON. Asegúrese de que la notificación *de roles* dentro del token descodificado contiene los permisos deseados.

    En la siguiente imagen, puedes ver un token descodificado adquirido desde una aplicación, con ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` y ```AdvancedHunting.Read.All``` permisos:

    ![Imagen jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a>Obtener una lista de incidentes recientes

El script siguiente **usará** Get-Token.ps1para obtener acceso a la API. A continuación, recupera una lista de incidentes que se actualizaron por última vez en las últimas 48 horas y guarda la lista como un archivo JSON.

> [!IMPORTANT]
> Guarde este script en la misma carpeta que **guardóGet-Token.ps1**.

```PowerShell
# This script returns incidents last updated within the past 48 hours.

$token = ./Get-Token.ps1

# Get incidents from the past 48 hours.
# The script may appear to fail if you don't have any incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# This URL contains the type of query and the time filter we created above.
# Note that `$filter` does not refer to a local variable in our script --
# it's actually an OData operator and part of the API's syntax.
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the webrequest headers
$headers = @{
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the request and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results.
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get a string containing the execution time. We concatenate that string to the name 
# of the output file to avoid overwriting the file on consecutive runs of the script.
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"

Out-File -FilePath $outputJsonPath -InputObject $incidents
```

¡Ya ha terminado! Ha realizado correctamente lo siguiente:

- Creó y registró una aplicación.
- Se ha concedido permiso para que esa aplicación lea alertas.
- Conectado a la API.
- Se usó un script de PowerShell para devolver incidentes actualizados en las últimas 48 horas.

## <a name="related-articles"></a>Artículos relacionados

- [Microsoft 365 Introducción a las API de Defender](api-overview.md)
- [Acceder a las API Microsoft 365 Defender](api-access.md)
- [Crear una aplicación para acceder a Microsoft 365 Defender sin un usuario](api-create-app-web.md)
- [Crear una aplicación para obtener acceso a Microsoft 365 API de Defender en nombre de un usuario](api-create-app-user-context.md)
- [Crear una aplicación con acceso de asociado multiinquilino a Microsoft 365 API de Defender](api-partner-access.md)
- [Administrar secretos en las aplicaciones de servidor con Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/)
- [Autorización de OAuth 2.0 para el inicio de sesión de usuario y el acceso a la API](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)