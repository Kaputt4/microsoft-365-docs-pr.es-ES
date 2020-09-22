---
title: Hello World para la API de REST de protección contra amenazas de Microsoft
description: Obtenga información sobre cómo crear una aplicación y usar un token para acceder a las API de Microsoft Threat Protection
keywords: aplicación, token, Access, AAD, App, registro de la aplicación, PowerShell, script, administrador global, permiso
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
ms.openlocfilehash: cdf3f6a0c007763d2772233b1a299d59c931b2e5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201332"
---
# <a name="hello-world-for-microsoft-threat-protection-rest-api"></a>Hello World para la API de REST de protección contra amenazas de Microsoft 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft

>[!IMPORTANT] 
>Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="get-incidents-using-a-simple-powershell-script"></a>Obtener incidentes con un script de PowerShell simple

### <a name="how-long-it-takes-to-go-through-this-example"></a>¿Cuánto tiempo se tarda en completar este ejemplo?
Solo se llevan a cabo 5 minutos en dos pasos:
- Registro de la aplicación
- Usar ejemplos: solo requiere copiar o pegar un script de PowerShell corto

### <a name="do-i-need-a-permission-to-connect"></a>¿Necesito un permiso para conectarse?
Para la etapa de registro de aplicaciones, debe tener un rol de **administrador global** en el espacio empresarial de Azure Active Directory (Azure ad).

### <a name="step-1---create-an-app-in-azure-active-directory"></a>Paso 1: crear una aplicación en Azure Active Directory

1. Inicie sesión en [Azure](https://portal.azure.com) con su usuario de **administrador global** .

2. Navegue a registros de aplicaciones de **Azure Active Directory**  >  **App registrations**  >  **nuevo registro**. 

   ![Imagen de Microsoft Azure y navegación en el registro de la aplicación](../../media/atp-azure-new-app2.png)

3. En el formulario de registro, elija un nombre para la aplicación y, a continuación, seleccione **registrar**.

4. Permita que su aplicación tenga acceso a ATP de Microsoft defender y asígnele el permiso **leer todas las incidencias** :

   - En la página de la aplicación, seleccione **permisos de API**  >  **Agregar**API de permisos  >  **mi organización usa** > escriba **Microsoft Threat Protection** y seleccione en **protección contra amenazas de Microsoft**.

   >[!NOTE]
   >La protección contra amenazas de Microsoft no aparece en la lista original. Debe empezar a escribir su nombre en el cuadro de texto para ver aparezca.

   ![Imagen de acceso a API y selección de API](../../media/apis-in-my-org-tab.PNG)

   - Elija **permisos de aplicación**  >  **Incident. Read. All** > seleccione en **Agregar permisos**

   ![Imagen de acceso a API y selección de API](../../media/request-api-permissions.PNG)

   >[!IMPORTANT]
   >Debe seleccionar los permisos correspondientes. 

     Por ejemplo,

     - Para determinar qué permiso necesita, consulte la sección **permisos** en la API que le interesa llamar.

5. Seleccione **conceder consentimiento de administrador**

    - >[!NOTE]
      > Cada vez que agregue permisos, deberá seleccionar activar **concesión de consentimiento** para que el nuevo permiso surta efecto.

    ![Imagen de permisos de concesión](../../media/grant-consent.PNG)

6. Agregue un secreto a la aplicación.

    - Seleccione **certificados & secretos**, agregue Descripción al secreto y seleccione **Agregar**.

    >[!IMPORTANT]
    > Después de seleccionar **Agregar**, **copie el valor de secreto generado**. No podrá recuperar después de salir.

    ![Imagen de crear clave de aplicación](../../media/webapp-create-key2.png)

7. Anote el identificador de la aplicación y el identificador de su espacio empresarial:

   - En la página de la aplicación, vaya a **información general** y copie lo siguiente:

   ![Imagen del identificador de aplicación creado](../../media/app-and-tenant-ids.png)


Realiza! Ha registrado correctamente una aplicación.

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a>Paso 2: obtenga un token con la aplicación y use este token para obtener acceso a la API.

-   Copie el script siguiente en PowerShell ISE o en un editor de texto y guárdelo como "**Get-Token.ps1**"
-   Al ejecutar este script, se generará un token y se guardará en la carpeta de trabajo con el nombre "**Latest-token.txt**".

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$TenantId/oauth2/token"
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

-   Comprobación de la validez:<br>
Ejecute el script.<br>
En el explorador, vaya a: https://jwt.ms/ <br>
Copie el token (el contenido del archivo de Latest-token.txt).<br>
Pegar en el cuadro superior.<br>
Busque la sección "roles". Buscar el ```Incidents.Read.All``` rol.<br>
El ejemplo siguiente es de una aplicación que tiene ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` permisos y ```AdvancedHunting.Read.All``` .

![Image jwt.ms](../../media/api-jwt-ms.png)

### <a name="lets-get-the-incidents"></a>¡ Permite obtener los incidentes!

-   El siguiente script usará **Get-Token.ps1** para acceder a la API y se actualizarán los incidentes por última vez en pasadas 48 horas.
-   Guarde este script en la misma carpeta en la que guardó el script anterior **Get-Token.ps1**. 
-   La secuencia de comandos es un archivo JSON con los datos en la misma carpeta que los scripts.

```
# Returns Incidents last updated in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Incidents from the last 48 hours. Make sure you have incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# The URL contains the type of query and the time filter we created above
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results. 
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"     

Out-File -FilePath $outputJsonPath -InputObject $incidents 
```

Ya ha terminado. Acaba de realizar correctamente:
-   Creado y registrado y aplicación
-   Permiso concedido para que la aplicación Lea las alertas
-   Conectado a la API
-   Se usó un script de PowerShell para devolver los incidentes creados en las últimas 48 horas



## <a name="related-topic"></a>Tema relacionado
- [Acceso a las API de Microsoft Threat Protection](api-access.md)
- [Acceso a Microsoft Threat Protection con contexto de aplicación](api-create-app-web.md)
- [Acceso a Microsoft Threat Protection con contexto de usuario](api-create-app-user-context.md)
