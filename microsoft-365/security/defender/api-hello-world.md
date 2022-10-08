---
title: Hola mundo para Microsoft 365 Defender API REST
description: Obtenga información sobre cómo crear una aplicación y usar un token para acceder a las API de Microsoft 365 Defender
keywords: app, token, access, aad, app, application registration, powershell, script, global administrator, permission, microsoft 365 defender
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
ms.openlocfilehash: d94bd5353aecbf93ca59651878af7b6261e00d1d
ms.sourcegitcommit: 0380a7cd5adb710b80a0ed6fcd349199f1571080
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2022
ms.locfileid: "68332170"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Hola mundo para Microsoft 365 Defender API REST

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

## <a name="get-incidents-using-a-simple-powershell-script"></a>Obtención de incidentes mediante un script de PowerShell sencillo

Este proyecto tardará entre 5 y 10 minutos. Esta estimación de tiempo incluye el registro de la aplicación y la aplicación del código desde el script de ejemplo de PowerShell.

### <a name="register-an-app-in-azure-active-directory"></a>Registro de una aplicación en Azure Active Directory

1. Inicie sesión en [Azure](https://portal.azure.com) como usuario con el rol **Administrador global**.

2. Vaya a **Azure Active Directory** >  **Registros de aplicaciones** >  **Nuevo registro**.

   :::image type="content" source="../../media/atp-azure-new-app2.png" alt-text="La sección Nuevo registro del portal de Microsoft 365 Defender" lightbox="../../media/atp-azure-new-app2.png":::

3. En el formulario de registro, elija un nombre para la aplicación y, a continuación, seleccione **Registrar**. La selección de un URI de redireccionamiento es opcional. No necesitará uno para completar este ejemplo.

4. En la página de la aplicación, seleccione **Permisos** >  de API **Agregar API de permisos** > **Que mi organización usa** >, escriba **Microsoft Threat Protection** y seleccione **Microsoft Threat Protection**. La aplicación ahora puede acceder a Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection* es un nombre anterior para Microsoft 365 Defender y no aparecerá en la lista original. Debe empezar a escribir su nombre en el cuadro de texto para verlo aparecer.
   :::image type="content" source="../../media/apis-in-my-org-tab.PNG" alt-text="La sección de uso de LAS API en el portal de Microsoft 365 Defender" lightbox="../../media/apis-in-my-org-tab.PNG":::

   - Elija **Permisos** >  de aplicación **Incident.Read.All** y seleccione **Agregar permisos**.

     :::image type="content" source="../../media/request-api-permissions.PNG" alt-text="Panel de permisos de una aplicación en el portal de Microsoft 365 Defender" lightbox="../../media/request-api-permissions.PNG":::

5. Seleccione **Conceder consentimiento de administrador**. Cada vez que agregue un permiso, debe seleccionar **Conceder consentimiento del administrador** para que surta efecto.

    :::image type="content" source="../../media/grant-consent.PNG" alt-text="La sección Conceder consentimiento del administrador en el portal de Microsoft 365 Defender" lightbox="../../media/grant-consent.PNG":::

6. Agregue un secreto a la aplicación. Seleccione **Certificados & secretos**, agregue una descripción al secreto y, a continuación, seleccione **Agregar**.

    > [!TIP]
    > Después de seleccionar **Agregar**, seleccione **Copiar el valor de secreto generado**. No podrá recuperar el valor del secreto después de salir.

    :::image type="content" source="../../media/webapp-create-key2.png" alt-text="La sección agregar secreto en el portal de Microsoft 365 Defender" lightbox="../../media/webapp-create-key2.png":::
    

7. Registre el identificador de la aplicación y el identificador de inquilino en un lugar seguro. Se enumeran en **Información general** en la página de la aplicación.

   :::image type="content" source="../../media/app-and-tenant-ids.png" alt-text="La sección Información general del portal de Microsoft 365 Defender" lightbox="../../media/app-and-tenant-ids.png":::

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>Obtención de un token mediante la aplicación y uso del token para acceder a la API

Para obtener más información sobre los tokens de Azure Active Directory, consulte el [tutorial de Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

> [!IMPORTANT]
> Aunque el ejemplo de esta aplicación de demostración le anima a pegar el valor secreto con fines de prueba, **nunca debe codificar de forma rígida los secretos** en una aplicación que se ejecuta en producción. Un tercero podría usar el secreto para acceder a los recursos. Puede ayudar a proteger los secretos de la aplicación mediante [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates). Para obtener un ejemplo práctico de cómo proteger la aplicación, consulte [Administración de secretos en las aplicaciones de servidor con Azure Key Vault](/training/modules/manage-secrets-with-azure-key-vault/).

1. Copie el script siguiente y péguelo en el editor de texto que prefiera. Guarde como **Get-Token.ps1**. También puede ejecutar el código tal como está en PowerShell ISE, pero debe guardarlo, ya que tendremos que volver a ejecutarlo cuando usemos el script de captura de incidentes en la sección siguiente.

    Este script generará un token y lo guardará en la carpeta de trabajo bajo el nombre *,Latest-token.txt*.

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
1. *JWT* significa *JSON Web Token*. El token descodificado contendrá una serie de notificaciones o elementos con formato JSON. Asegúrese de que la notificación de *roles* dentro del token descodificado contiene los permisos deseados.

    En la imagen siguiente, puede ver un token descodificado adquirido de una aplicación, con ```Incidents.Read.All```permisos , ```Incidents.ReadWrite.All```y ```AdvancedHunting.Read.All``` :

    :::image type="content" source="../../media/api-jwt-ms.png" alt-text="La sección Token descodificado del portal de Microsoft 365 Defender" lightbox="../../media/api-jwt-ms.png":::

### <a name="get-a-list-of-recent-incidents"></a>Obtener una lista de incidentes recientes

El script siguiente usará **Get-Token.ps1** para acceder a la API. A continuación, recupera una lista de incidentes que se actualizaron por última vez en las últimas 48 horas y guarda la lista como un archivo JSON.

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
$url = "https://api.security.microsoft.com/api/incidents`?`$filter=lastUpdateTime+ge+$dateTime"

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

¡Ya has terminado! Ha realizado correctamente lo siguiente:

- Ha creado y registrado una aplicación.
- Se ha concedido permiso para que esa aplicación lea alertas.
- Conectado a la API.
- Se ha usado un script de PowerShell para devolver los incidentes actualizados en las últimas 48 horas.

## <a name="related-articles"></a>Artículos relacionados

- [Introducción a las API de Microsoft 365 Defender](api-overview.md)
- [Acceso a las API de Microsoft 365 Defender](api-access.md)
- [Creación de una aplicación para acceder a Microsoft 365 Defender sin un usuario](api-create-app-web.md)
- [Creación de una aplicación para acceder a Microsoft 365 Defender API en nombre de un usuario](api-create-app-user-context.md)
- [Creación de una aplicación con acceso de asociado multiinquilino a las API de Microsoft 365 Defender](api-partner-access.md)
- [Administración de secretos en las aplicaciones de servidor con Azure Key Vault](/training/modules/manage-secrets-with-azure-key-vault/)
- [Autorización de OAuth 2.0 para el inicio de sesión de usuario y el acceso a la API](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
