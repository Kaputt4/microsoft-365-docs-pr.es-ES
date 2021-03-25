---
title: Capturar alertas desde el inquilino del cliente de MSSP
description: Obtenga información sobre cómo capturar alertas de un inquilino de cliente
keywords: proveedor de servicios de seguridad administrados, mssp, configuración, integración
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ee2a5e1815dd552753ac7f3dee30df11ac4332e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076608"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a>Capturar alertas desde el inquilino del cliente de MSSP

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)

>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!NOTE]
>El MSSP toma esta acción.


Hay dos formas de capturar alertas:
- Uso del método SIEM
- Uso de API

## <a name="fetch-alerts-into-your-siem"></a>Capturar alertas en siem

Para capturar alertas en el sistema SIEM, deberá seguir los siguientes pasos:

Paso 1: Crear una aplicación de terceros

Paso 2: Obtener tokens de acceso y actualización desde el inquilino del cliente
 
Paso 3: permitir la aplicación en el Centro de seguridad de Microsoft Defender
 
### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a>Paso 1: Crear una aplicación en Azure Active Directory (Azure AD)
 
Deberá crear una aplicación y concederle permisos para capturar alertas desde el inquilino de Microsoft Defender para endpoint del cliente.

1. Inicie sesión en [Azure AD Portal](https://aad.portal.azure.com/).

2. Seleccione **Registros de aplicaciones de Azure Active Directory**  >  .
 
3. Haga clic **en Nuevo registro**.

4. Especifique los siguientes valores:

    - Nombre: \<Tenant_name\> Siem MSSP Connector (reemplace Tenant_name por el nombre para mostrar del espacio empresarial)
 
    - Tipos de cuentas compatibles: solo cuenta en este directorio de la organización 
    - URI de redireccionamiento: seleccione Web y escriba `https://<domain_name>/SiemMsspConnector` (reemplace <domain_name> por el nombre del inquilino)

5. Haga clic en **Registrar**. La aplicación se muestra en la lista de aplicaciones de su propiedad.

6. Seleccione la aplicación y, a continuación, haga clic **en Información general**.

7. Copie el valor del campo **Id. de aplicación (cliente)** en un lugar seguro, lo necesitará en el siguiente paso.

8. Seleccione **Certificados & secretos** en el nuevo panel de aplicaciones.

9. Haga **clic en Nuevo secreto de cliente**.

    - Descripción: escriba una descripción para la clave.
    - Expira: seleccionar **en 1 año**

 
10. Haga **clic en** Agregar , copie el valor del secreto de cliente en un lugar seguro, lo necesitará en el paso siguiente.
 

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a>Paso 2: Obtener tokens de acceso y actualización desde el inquilino del cliente
Esta sección le guía sobre cómo usar un script de PowerShell para obtener los tokens del inquilino del cliente. Este script usa la aplicación del paso anterior para obtener los tokens de acceso y actualización mediante el flujo de código de autorización de OAuth.

Después de proporcionar sus credenciales, deberá conceder el consentimiento a la aplicación para que la aplicación se aprovisione en el inquilino del cliente.


1. Cree una nueva carpeta y así mismo: `MsspTokensAcquisition` .

2. Descargue el [módulo LoginBrowser.psm1](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) y guárdelo en la `MsspTokensAcquisition` carpeta.

    >[!NOTE]
    >En la línea 30, reemplace `authorzationUrl` por `authorizationUrl` .

3. Cree un archivo con el siguiente contenido y guárdelo con el nombre `MsspTokensAcquisition.ps1` de la carpeta:
    ```
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

    Write-Host " -----------------------------------  TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " -----------------------------------  REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken 
    ```
4. Abra un símbolo del sistema de PowerShell con privilegios elevados en la `MsspTokensAcquisition` carpeta.

5. Ejecute el siguiente comando: `Set-ExecutionPolicy -ExecutionPolicy Bypass`

6. Escriba los siguientes comandos: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`
 
    - Reemplace \<client_id\> por el identificador de aplicación **(cliente)** que obtuvo del paso anterior.
    - Reemplace \<app_key\> por el secreto de **cliente** que creó a partir del paso anterior.
    - Reemplace \<customer_tenant_id\> por el identificador de inquilino del **cliente**. 
 

7. Se le pedirá que proporcione sus credenciales y consentimiento. Ignore el redireccionamiento de página.

8. En la ventana de PowerShell, recibirá un token de acceso y un token de actualización. Guarde el token de actualización para configurar el conector SIEM. 
 
### <a name="step-3-allow-your-application-on-microsoft-defender-security-center"></a>Paso 3: Permitir la aplicación en el Centro de seguridad de Microsoft Defender
Tendrás que permitir la aplicación que creaste en el Centro de seguridad de Microsoft Defender.
 
Deberá tener permiso Administrar configuración **del sistema del portal** para permitir la aplicación. De lo contrario, tendrá que solicitar al cliente que le permita la aplicación.

1. Vaya a `https://securitycenter.windows.com?tid=<customer_tenant_id>` (reemplace \<customer_tenant_id\> por el identificador de inquilino del cliente.

2. Haga clic **en**  >  **Configuración SIEM**. 

3. Seleccione la **pestaña MSSP.**

4. Escriba el **id. de** aplicación del primer paso y el identificador **de inquilino**.

5. Haga clic **en Autorizar aplicación**. 

 
Ahora puede descargar el archivo de configuración correspondiente para siem y conectarse a la API de Defender para endpoints. Para obtener más información, vea [Pull alerts to your SIEM tools](configure-siem.md).
 

- En el archivo de configuración de ArcSight / Archivo de propiedades de autenticación splunk, escriba la clave de la aplicación manualmente estableciendo el valor secreto.
- En lugar de adquirir un token de actualización en el portal, use el script del paso anterior para adquirir un token de actualización (o adquirirlo por otros medios).

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a>Capturar alertas desde el inquilino del cliente de MSSP mediante API
 
Para obtener información sobre cómo capturar alertas mediante la API de REST, vea [Extraer alertas mediante la API de REST](pull-alerts-using-rest-api.md).


## <a name="see-also"></a>Ver también
- [Conceder acceso de MSSP al portal](grant-mssp-access.md)
- [Obtener acceso al portal de clientes de MSSP](access-mssp-portal.md)
- [Configurar notificaciones de alertas](configure-mssp-notifications.md)
