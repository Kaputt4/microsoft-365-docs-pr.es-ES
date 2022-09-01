---
title: Hola mundo para Microsoft Defender para punto de conexión API
ms.reviewer: ''
description: Cree una llamada de API de estilo "Hola mundo" al Microsoft Defender para punto de conexión API.
keywords: apis, api admitidas, búsqueda avanzada, consulta, atp de Microsoft Defender, microsoft defender para punto de conexión
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
ms.openlocfilehash: a240f647e1e1cead26bab384e112e14a26dea2d3
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67499000"
---
# <a name="microsoft-defender-for-endpoint-api---hello-world"></a>API de Microsoft Defender para punto de conexión: Hola mundo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)


>¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="get-alerts-using-a-simple-powershell-script"></a>Obtención de alertas mediante un script de PowerShell sencillo

### <a name="how-long-it-takes-to-go-through-this-example"></a>¿Cuánto tiempo se tarda en pasar por este ejemplo?

Solo tarda 5 minutos en realizarse en dos pasos:

- Registro de la aplicación
- Ejemplos de uso: solo se requiere copiar y pegar un script corto de PowerShell

### <a name="do-i-need-a-permission-to-connect"></a>¿Necesito un permiso para conectarme?

Para la fase de registro de aplicaciones, debe tener un rol **de Administrador global** en el inquilino de Azure Active Directory (Azure AD).

### <a name="step-1---create-an-app-in-azure-active-directory"></a>Paso 1: Creación de una aplicación en Azure Active Directory

1. Inicie sesión en [Azure](https://portal.azure.com) con **el usuario Administrador global**.

2. Vaya a **Azure Active Directory** \> **Registros de aplicaciones** \> **Nuevo registro**.

   :::image type="content" source="images/atp-azure-new-app2.png" alt-text="La opción Registros de aplicaciones en el panel Administrar del portal de Azure Active Directory"  lightbox="images/atp-azure-new-app2.png":::

3. En el formulario de registro, elija un nombre para la aplicación y, a continuación, haga clic en **Registrar**.

4. Permita que la aplicación acceda a Defender para punto de conexión y asígnele el permiso **"Leer todas las alertas"** :

   - En la página de la aplicación, haga clic en **Permisos** \> de API **Agregar API de permisos** \> **Que mi organización usa** > escriba **WindowsDefenderATP** y haga clic en **WindowsDefenderATP**.

     > [!NOTE]
     > WindowsDefenderATP no aparece en la lista original. Debe empezar a escribir su nombre en el cuadro de texto para verlo aparecer.

     :::image type="content" source="images/add-permission.png" alt-text="La opción Permisos de API en el panel Administrar del portal de Azure Active Directory" lightbox="images/add-permission.png":::

   - Elija **Permisos** \> de aplicación **Alert.Read.All** > Haga clic en **Agregar permisos**.

     :::image type="content" source="images/application-permissions.png" alt-text="El tipo de permiso y los paneles de configuración de la página Solicitar permisos de API" lightbox="images/application-permissions.png":::

     > [!IMPORTANT]
     > Debe seleccionar los permisos pertinentes. "Leer todas las alertas" es solo un ejemplo.

     Por ejemplo:

     - Para [ejecutar consultas avanzadas](run-advanced-query-api.md), seleccione el permiso "Ejecutar consultas avanzadas".
     - Para [aislar una máquina](isolate-machine.md), seleccione el permiso "Aislar máquina".
     - Para determinar qué permiso necesita, consulte la sección **Permisos** de la API a la que está interesado llamar.

5. Haga clic en **Conceder consentimiento**.

   > [!NOTE]
   > Cada vez que agregue permiso, debe hacer clic en **Conceder consentimiento** para que el nuevo permiso surta efecto.

   :::image type="content" source="images/grant-consent.png" alt-text="Opción de consentimiento de concesión de permisos en el portal de Azure Active Directory" lightbox="images/grant-consent.png":::

6. Agregue un secreto a la aplicación.

    Haga clic en **Certificados & secretos**, agregue la descripción al secreto y haga clic en **Agregar**.

    > [!IMPORTANT]
    > Después de hacer clic en Agregar, **copie el valor de secreto generado**. ¡No podrás recuperarlo después de irte!

    :::image type="content" source="images/webapp-create-key2.png" alt-text="El elemento de menú Certificados & secretos en el panel Administrar del portal de Azure Active Directory" lightbox="images/webapp-create-key2.png":::

7. Anote el identificador de la aplicación y el identificador de inquilino.

   En la página de la aplicación, vaya a **Información general** y copie lo siguiente:

   :::image type="content" source="images/app-and-tenant-ids.png" alt-text="Panel de detalles de la aplicación en el elemento de menú Información general del portal de Azure Active Directory" lightbox="images/app-and-tenant-ids.png":::

¡Listo! Ha registrado correctamente una aplicación.

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a>Paso 2: Obtener un token mediante la aplicación y usar este token para acceder a la API.

- Copie el script siguiente en PowerShell ISE o en un editor de texto y guárdelo como **Get-Token.ps1**.
- La ejecución de este script generará un token y lo guardará en la carpeta de trabajo con el nombre **Latest-token.txt**.

   ```powershell
   # That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
   # Paste below your Tenant ID, App ID and App Secret (App key).

   $tenantId = '' ### Paste your tenant ID here
   $appId = '' ### Paste your Application ID here
   $appSecret = '' ### Paste your Application secret here

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

- Comprobación de integridad:
  - Ejecute el script.
  - En el explorador, vaya a: <https://jwt.ms/>.
  - Copie el token (el contenido del archivo Latest-token.txt).
  - Pegue en el cuadro superior.
  - Busque la sección "roles". Busque el rol _Alert.Read.All_ .

  :::image type="content" source="images/api-jwt-ms.png" alt-text="Panel Token descodificado para jwt.ms" lightbox="images/api-jwt-ms.png":::

### <a name="lets-get-the-alerts"></a>¡Vamos a obtener las alertas!

- El script siguiente usará **Get-Token.ps1** para acceder a la API y obtendrá las alertas de las últimas 48 horas.
- Guarde este script en la misma carpeta en la que guardó el script anterior **Get-Token.ps1**.
- El script crea dos archivos (json y csv) con los datos en la misma carpeta que los scripts.

  ```powershell
  # Returns Alerts created in the past 48 hours.

  $token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

  # Get Alert from the last 48 hours. Make sure you have alerts in that time frame.
  $dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

  # The URL contains the type of query and the time filter we create above
  # Read more about other query options and filters at   Https://TBD- add the documentation link
  $url = "https://api.securitycenter.microsoft.com/api/alerts?`$filter=alertCreationTime ge $dateTime"

  # Set the WebRequest headers
  $headers = @{
      'Content-Type' = 'application/json'
      Accept = 'application/json'
      Authorization = "Bearer $token"
  }

  # Send the webrequest and get the results.
  $response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

  # Extract the alerts from the results.
  $alerts =  ($response | ConvertFrom-Json).value | ConvertTo-Json

  # Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
  $dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

  # Save the result as json and as csv
  $outputJsonPath = "./Latest Alerts $dateTimeForFileName.json"
  $outputCsvPath = "./Latest Alerts $dateTimeForFileName.csv"

  Out-File -FilePath $outputJsonPath -InputObject $alerts
  ($alerts | ConvertFrom-Json) | Export-CSV $outputCsvPath -NoTypeInformation
  ```

¡Ya has terminado! Acaba de tener éxito:

- Creación y registro y aplicación
- Se ha concedido permiso para que esa aplicación lea alertas.
- Conexión de la API
- Se ha usado un script de PowerShell para devolver las alertas creadas en las últimas 48 horas.

## <a name="related-topic"></a>Tema relacionado

- [API de Microsoft Defender para punto de conexión](exposed-apis-list.md)
- [Acceso a Microsoft Defender para punto de conexión con contexto de aplicación](exposed-apis-create-app-webapp.md)
- [Acceso a Microsoft Defender para punto de conexión con el contexto de usuario](exposed-apis-create-app-nativeapp.md)
