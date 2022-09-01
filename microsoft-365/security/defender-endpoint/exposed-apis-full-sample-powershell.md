---
title: Búsqueda avanzada con la guía de la API de PowerShell
ms.reviewer: ''
description: Use estos ejemplos de código para consultar varias API de Microsoft Defender para punto de conexión.
keywords: apis, api admitidas, búsqueda avanzada, consulta
search.product: eADQiWindows 10XVcnh
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
ms.date: 04/27/2022
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: cad44fdbf07b784f6f18edb4d5eb59cd7cf46d80
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67520069"
---
# <a name="microsoft-defender-for-endpoint-apis-using-powershell"></a>API de Microsoft Defender para punto de conexión con PowerShell

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** 
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para Empresas](../defender-business/index.yml)

> [!IMPORTANT]
> Las funcionalidades avanzadas de búsqueda no se incluyen en Defender para empresas. Consulte [Comparar Microsoft Defender para Empresas con los planes 1 y 2 de Microsoft Defender para punto de conexión](../defender-business/compare-mdb-m365-plans.md#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2).

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)

Escenario completo con varias API de Microsoft Defender para punto de conexión.

En esta sección, compartimos ejemplos de PowerShell para 
- Recuperación de un token 
- Use el token para recuperar las alertas más recientes de Microsoft Defender para punto de conexión
- Para cada alerta, si la alerta tiene prioridad media o alta y sigue en curso, compruebe cuántas veces el dispositivo se ha conectado a una dirección URL sospechosa.

**Requisito previo**: primero debe [crear una aplicación](apis-intro.md).

## <a name="preparation-instructions"></a>Instrucciones de preparación

- Abra una ventana de PowerShell.
- Si la directiva no le permite ejecutar los comandos de PowerShell, puede ejecutar el siguiente comando:
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

Para obtener más información, consulte [la documentación de PowerShell](/powershell/module/microsoft.powershell.security/set-executionpolicy).

## <a name="get-token"></a>Obtener token

Ejecute lo siguiente:

- $tenantId: identificador del inquilino en nombre del que desea ejecutar la consulta (es decir, la consulta se ejecutará en los datos de este inquilino)
- $appId: Id. de la aplicación de AAD (la aplicación debe tener el permiso "Ejecutar consultas avanzadas" para Defender para punto de conexión)
- $appSecret: Secreto de la aplicación de Azure AD

- $suspiciousUrl: la dirección URL


```
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here
$suspiciousUrl = 'www.suspiciousUrl.com' # Paste your own URL here

$resourceAppIdUri = 'https://securitycenter.onmicrosoft.com/windowsatpservice'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$aadToken = $authResponse.access_token


#Get latest alert
$alertUrl = "https://api.securitycenter.microsoft.com/api/alerts?`$top=10"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$alertResponse = Invoke-WebRequest -Method Get -Uri $alertUrl -Headers $headers -ErrorAction Stop
$alerts =  ($alertResponse | ConvertFrom-Json).value

$machinesToInvestigate = New-Object System.Collections.ArrayList

Foreach($alert in $alerts)
{
    #echo $alert.id $alert.machineId    $alert.severity $alert.status

    $isSevereAlert = $alert.severity -in 'Medium', 'High'
    $isOpenAlert = $alert.status -in 'InProgress', 'New'
    if($isOpenAlert -and $isSevereAlert)
    {
        if (-not $machinesToInvestigate.Contains($alert.machineId))
        {
            $machinesToInvestigate.Add($alert.machineId) > $null
        }
    }
}

$commaSeparatedMachines = '"{0}"' -f ($machinesToInvestigate -join '","')

$query = "NetworkCommunicationEvents
| where MachineId in ($commaSeparatedMachines)
| where RemoteUrl  == `"$suspiciousUrl`"
| summarize ConnectionsCount = count() by MachineId"

$queryUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"

$queryBody = ConvertTo-Json -InputObject @{ 'Query' = $query }
$queryResponse = Invoke-WebRequest -Method Post -Uri $queryUrl -Headers $headers -Body $queryBody -ErrorAction Stop
$response =  ($queryResponse | ConvertFrom-Json).Results
$response
```


## <a name="see-also"></a>Vea también
- [API de Microsoft Defender para punto de conexión](apis-intro.md)
- [API de Búsqueda avanzada de amenazas](run-advanced-query-api.md)
- [Búsqueda avanzada de amenazas con Python](run-advanced-query-sample-python.md)
