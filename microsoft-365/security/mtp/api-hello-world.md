---
title: Hola a todos sobre la API de REST de Microsoft 365 defender
description: Obtenga información sobre cómo crear una aplicación y usar un token para obtener acceso a las API de Microsoft 365 defender
keywords: App, token, Access, AAD, App, registro de aplicaciones, PowerShell, script, administrador global, permiso, Microsoft 365 defender
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
ms.openlocfilehash: b36a6acca5880a455a66b03b5355cdf1fb85b29b
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719315"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Hola a todos sobre la API de REST de Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="get-incidents-using-a-simple-powershell-script"></a>Obtener incidentes con un script de PowerShell simple

Este proyecto debe tardar de 5 a 10 minutos en completarse. Esta estimación de tiempo incluye el registro de la aplicación y la aplicación del código del script de ejemplo de PowerShell.

### <a name="register-an-app-in-azure-active-directory"></a>Registrar una aplicación en Azure Active Directory

1. Inicie sesión en [Azure](https://portal.azure.com) como un usuario con el rol de **administrador global** .

2. Navegue a registros de aplicaciones de **Azure Active Directory**  >    >  **nuevo registro**.

   ![Imagen de Microsoft Azure y navegación en el registro de la aplicación](../../media/atp-azure-new-app2.png)

3. En el formulario de registro, elija un nombre para la aplicación y, después, seleccione **registrar**. La selección de un URI de redireccionamiento es opcional. No necesitará uno para completar este ejemplo.

4. En la página de la aplicación, seleccione **permisos de API**  >  **Agregar** API de permisos  >  **mi organización usa** >, escriba **protección contra amenazas de Microsoft** y seleccione protección contra amenazas de **Microsoft**. La aplicación ahora puede tener acceso a Microsoft 365 defender.

   > [!TIP]
   > *Microsoft Threat Protection* es un nombre antiguo para Microsoft 365 defender y no aparecerá en la lista original. Debe empezar a escribir su nombre en el cuadro de texto para ver aparezca.
   ![Imagen de la selección de permisos de la API](../../media/apis-in-my-org-tab.PNG)

   - Elija **permisos de aplicación**  >  **Incident. Read. All** y seleccione **Agregar permisos**.

   ![Imagen de acceso a API y selección de API](../../media/request-api-permissions.PNG)

5. Seleccione **conceder consentimiento de administrador**. Cada vez que agregue un permiso, debe seleccionar **conceder consentimiento de administrador** para que surta efecto.

    ![Imagen de permisos de concesión](../../media/grant-consent.PNG)

6. Agregue un secreto a la aplicación. Seleccione **certificados & secretos**, agregue una descripción al secreto y, a continuación, seleccione **Agregar**.

    > [!TIP]
    > Después de seleccionar **Agregar**, seleccione **copiar el valor de secreto generado**. No podrá recuperar el valor secreto después de salir.

    ![Imagen de crear clave de aplicación](../../media/webapp-create-key2.png)

7. Registre el identificador de la aplicación y el identificador de inquilino en algún lugar seguro. Aparecen en **información general** en la página de la aplicación.

   ![Imagen del identificador de aplicación creado](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>Obtener un token con la aplicación y usar el token para obtener acceso a la API

Para obtener más información sobre los tokens de Azure Active Directory, vea el [tutorial de Azure ad](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

> [!IMPORTANT]
> Aunque el ejemplo de esta aplicación de demostración le anima a pegar el valor del secreto con fines de prueba, no debe **codificar secretos** en una aplicación que se ejecuta en producción. Un tercero puede usar su secreto para obtener acceso a los recursos. Puede ayudar a mantener la seguridad de los secretos de la aplicación mediante [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates). Para obtener un ejemplo práctico de cómo puede proteger su aplicación, consulte [Manage Secrets in your Server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).

1. Copie el script siguiente y péguelo en su editor de texto preferido. Guardar como **Get-Token.ps1**. También puede ejecutar el código tal y como está en PowerShell ISE, pero debe guardarlo, ya que tendremos que volver a ejecutarlo cuando use el script de recuperación de incidentes de la siguiente sección.

    Este script generará un token y lo guardará en la carpeta de trabajo con el nombre, *Latest-token.txt*.

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
1. Las siglas de *JWT* para *token web JSON*. El token descodificado contendrá varios elementos o notificaciones con formato JSON. Asegúrese de que la notificación de *roles* dentro del token descodificado contenga los permisos deseados.

    En la siguiente imagen, puede ver un token descodificado adquirido de una aplicación, con ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` y ```AdvancedHunting.Read.All``` permisos:

    ![Image jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a>Obtener una lista de incidentes recientes

El siguiente script usará **Get-Token.ps1** para obtener acceso a la API. A continuación, recupera una lista de los incidentes que se actualizaron por última vez en los últimos 48 horas y guarda la lista como un archivo JSON.

> [!IMPORTANT]
> Guarde este script en la misma carpeta que guardó **Get-Token.ps1**.

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

Ya ha terminado. Ha realizado correctamente:

- Se ha creado y registrado una aplicación.
- Permiso concedido para que la aplicación Lea las alertas.
- Conectado a la API.
- Se usó un script de PowerShell para devolver los incidentes actualizados en las últimas 48 horas.

## <a name="related-articles"></a>Artículos relacionados

- [Información general sobre las API de Microsoft 365 defender](api-overview.md)
- [Acceso a las API de Microsoft 365 defender](api-access.md)
- [Crear una aplicación para obtener acceso a Microsoft 365 defender sin un usuario](api-create-app-web.md)
- [Crear una aplicación para acceder a las API de Microsoft 365 defender en nombre de un usuario](api-create-app-user-context.md)
- [Crear una aplicación con acceso de socio multiinquilino a las API de Microsoft 365 defender](api-partner-access.md)
- [Administrar secretos en las aplicaciones de servidor con Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2,0 autorización para el inicio de sesión de usuario y el acceso a API](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
