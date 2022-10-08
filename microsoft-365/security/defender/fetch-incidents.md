---
title: Capturar incidentes relacionados con Microsoft 365 Defender
description: Obtenga información sobre cómo capturar incidentes de Microsoft 365 Defender de un inquilino de cliente
keywords: proveedor de servicios de seguridad administrados, mssp, configure, integration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m65-security-compliance
- tier3
ms.topic: article
ms.custom: api
ms.openlocfilehash: bdd3065b7d0699ae90d7e1ec9799fd176af508b3
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68072709"
---
# <a name="fetch-microsoft-365-defender-incidents"></a>Capturar incidentes relacionados con Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!NOTE]
> Esta acción la realiza el MSSP.

Hay dos maneras de capturar alertas:

- Uso del método SIEM
- Uso de API

## <a name="fetch-incidents-into-your-siem"></a>Captura de incidentes en siem

Para capturar incidentes en el sistema SIEM, deberá realizar los pasos siguientes:

- Paso 1: Creación de una aplicación de terceros
- Paso 2: Obtención de tokens de acceso y actualización desde el inquilino del cliente
- Paso 3: permitir la aplicación en Microsoft 365 Defender

### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a>Paso 1: Creación de una aplicación en Azure Active Directory (Azure AD)

Tendrá que crear una aplicación y concederle permisos para capturar alertas del inquilino Microsoft 365 Defender del cliente.

1. Inicie sesión en el [portal de Azure AD](https://aad.portal.azure.com/).

2. Seleccione **Azure Active Directory** \> **Registros de aplicaciones**.

3. Haga clic en **Nuevo registro**.

4. Especifique los valores siguientes:

    - Nombre: \<Tenant_name\> Conector SIEM MSSP (reemplace Tenant_name por el nombre para mostrar del inquilino)

    - Tipos de cuenta admitidos: solo cuenta en este directorio organizativo
    - URI de redirección: seleccione Web y escriba `https://<domain_name>/SiemMsspConnector`(reemplace <domain_name> por el nombre del inquilino)

5. Haga clic en **Registrar**. La aplicación se muestra en la lista de aplicaciones de su propiedad.

6. Seleccione la aplicación y haga clic en **Información general**.

7. Copie el valor del campo **Id. de aplicación (cliente)** en un lugar seguro, lo necesitará en el paso siguiente.

8. Seleccione **Certificado & secretos** en el nuevo panel de aplicación.

9. Haga clic en **Nuevo secreto de cliente**.

    - Descripción: escriba una descripción para la clave.
    - Expira: Seleccionar **en 1 año**

10. Haga clic en **Agregar**, copie el valor del secreto de cliente en un lugar seguro, lo necesitará en el paso siguiente.

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a>Paso 2: Obtención de tokens de acceso y actualización desde el inquilino del cliente

Esta sección le guía sobre cómo usar un script de PowerShell para obtener los tokens del inquilino del cliente. Este script usa la aplicación del paso anterior para obtener los tokens de acceso y actualización mediante el flujo de código de autorización de OAuth.

Después de proporcionar sus credenciales, tendrá que conceder consentimiento a la aplicación para que la aplicación se aprovisione en el inquilino del cliente.

1. Cree una nueva carpeta y asígnele el nombre : `MsspTokensAcquisition`.

2. Descargue el [módulo LoginBrowser.psm1](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) y guárdelo en la `MsspTokensAcquisition` carpeta .

    > [!NOTE]
    > En la línea 30, reemplace por `authorzationUrl` `authorizationUrl`.

3. Cree un archivo con el siguiente contenido y guárdelo con el nombre `MsspTokensAcquisition.ps1` en la carpeta :

    ```powershell
    param (
        [Parameter(Mandatory=$true)][string]$clientId,
        [Parameter(Mandatory=$true)][string]$secret,
        [Parameter(Mandatory=$true)][string]$tenantId
    )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

    # Load our Login Browser Function
    Import-Module .\LoginBrowser.psm1

    # Configuration parameters
    $login = "https://login.microsoftonline.com"
    $redirectUri = "https://SiemMsspConnector"
    $resourceId = "https://graph.windows.net"

    Write-Host 'Prompt the user for his credentials, to get an authorization code'
    $authorizationUrl = ("{0}/{1}/oauth2/authorize?prompt=select_account&response_type=code&client_id={2}&redirect_uri={3}&resource={4}" -f
                        $login, $tenantId, $clientId, $redirectUri, $resourceId)
    Write-Host "authorzationUrl: $authorizationUrl"

    # Fake a proper endpoint for the Redirect URI
    $code = LoginBrowser $authorizationUrl $redirectUri

    # Acquire token using the authorization code

    $Body = @{
        grant_type = 'authorization_code'
        client_id = $clientId
        code = $code
        redirect_uri = $redirectUri
        resource = $resourceId
        client_secret = $secret
    }

    $tokenEndpoint = "$login/$tenantId/oauth2/token?"
    $Response = Invoke-RestMethod -Method Post -Uri $tokenEndpoint -Body $Body
    $token = $Response.access_token
    $refreshToken= $Response.refresh_token

    Write-Host " ----------------------------------- TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " ----------------------------------- REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken
    ```
4. Abra un símbolo del sistema de PowerShell con privilegios elevados en la `MsspTokensAcquisition` carpeta .

5. Ejecute el siguiente comando: `Set-ExecutionPolicy -ExecutionPolicy Bypass`

6. Escriba los siguientes comandos: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`

    - Reemplace por \<client_id\> el **identificador de aplicación (cliente)** que obtuvo del paso anterior.
    - Reemplace por \<app_key\> el **secreto de cliente** que creó en el paso anterior.
    - Reemplace por \<customer_tenant_id\> el **identificador de inquilino** del cliente.

7. Se le pedirá que proporcione sus credenciales y su consentimiento. Omita el redireccionamiento de la página.

8. En la ventana de PowerShell, recibirá un token de acceso y un token de actualización. Guarde el token de actualización para configurar el conector SIEM.

### <a name="step-3-allow-your-application-on-microsoft-365-defender"></a>Paso 3: Permitir la aplicación en Microsoft 365 Defender

Tendrá que permitir la aplicación que creó en Microsoft 365 Defender.

Tendrá que tener permiso administrar la **configuración del sistema del portal** para permitir la aplicación. De lo contrario, deberá solicitar al cliente que le permita la aplicación.

1. Vaya a `https://security.microsoft.com?tid=<customer_tenant_id>` (reemplace por \<customer_tenant_id\> el identificador de inquilino del cliente.

2. Haga clic en API de **puntos de conexión** \>  \> **de configuración** \> **SIEM**.

3. Seleccione la pestaña **MSSP** .

4. Escriba el **identificador de aplicación** del primer paso y el **identificador de inquilino**.

5. Haga clic en **Autorizar aplicación**.

Ahora puede descargar el archivo de configuración correspondiente para SIEM y conectarse a la API de Microsoft 365 Defender. Para obtener más información, consulte [Extracción de alertas en las herramientas SIEM](../defender-endpoint/configure-siem.md).

- En el archivo de configuración de ArcSight o en el archivo de propiedades de autenticación de Splunk, escriba la clave de aplicación manualmente estableciendo el valor del secreto.
- En lugar de adquirir un token de actualización en el portal, use el script del paso anterior para adquirir un token de actualización (o adquirirlo por otros medios).

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a>Captura de alertas del inquilino del cliente de MSSP mediante las API

Para obtener información sobre cómo capturar alertas mediante la API REST, consulte [Extracción de alertas mediante la API REST](../defender-endpoint/pull-alerts-using-rest-api.md).
