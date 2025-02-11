---
title: Búsqueda avanzada con conceptos básicos de la API de PowerShell
ms.reviewer: ''
description: Obtenga información sobre los conceptos básicos de la consulta de la API de Microsoft Defender para punto de conexión mediante PowerShell.
keywords: apis, api admitidas, búsqueda avanzada, consulta
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: b4fc422194aca1615c8a1b365ea7b9b34a67551c
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68644447"
---
# <a name="advanced-hunting-using-powershell"></a>Búsqueda avanzada de amenazas con PowerShell

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** 
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Ejecute consultas avanzadas con PowerShell, consulte [Advanced Hunting API( API de búsqueda avanzada](run-advanced-query-api.md)).

En esta sección, compartimos ejemplos de PowerShell para recuperar un token y usarlo para ejecutar una consulta.

## <a name="before-you-begin"></a>Antes de empezar
Primero debe [crear una aplicación](apis-intro.md).

## <a name="preparation-instructions"></a>Instrucciones de preparación

- Abra una ventana de PowerShell.

- Si la directiva no le permite ejecutar los comandos de PowerShell, puede ejecutar el siguiente comando:

  ```powershell
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

Para obtener más información, consulte [la documentación de PowerShell](/powershell/module/microsoft.powershell.security/set-executionpolicy).

## <a name="get-token"></a>Obtener token

- Ejecute el siguiente comando:

```powershell
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$body = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$response = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $body -ErrorAction Stop
$aadToken = $response.access_token
```

Dónde
- $tenantId: identificador del inquilino en nombre del que desea ejecutar la consulta (es decir, la consulta se ejecutará en los datos de este inquilino)
- $appId: identificador de la aplicación de Azure AD (la aplicación debe tener el permiso "Ejecutar consultas avanzadas" en Defender para punto de conexión)
- $appSecret: Secreto de la aplicación de Azure AD

## <a name="run-query"></a>Ejecutar consulta

Ejecute la consulta siguiente:

```powershell
$query = 'DeviceRegistryEvents | limit 10' # Paste your own query here

$url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$body = ConvertTo-Json -InputObject @{ 'Query' = $query }
$webResponse = Invoke-WebRequest -Method Post -Uri $url -Headers $headers -Body $body -ErrorAction Stop
$response =  $webResponse | ConvertFrom-Json
$results = $response.Results
$schema = $response.Schema
```

- $results contienen los resultados de la consulta
- $schema contiene el esquema de los resultados de la consulta

### <a name="complex-queries"></a>Consultas complejas

Si desea ejecutar consultas complejas (o consultas multilínea), guarde la consulta en un archivo y, en lugar de la primera línea del ejemplo anterior, ejecute el siguiente comando:

```powershell
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a>Trabajar con resultados de consulta

Ahora puede usar los resultados de la consulta.

Para generar los resultados de la consulta en formato CSV en file1.csv de archivos, ejecute el siguiente comando:

```powershell
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

Para generar los resultados de la consulta en formato JSON en el archivo file1.json, ejecute el siguiente comando:

```powershell
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a>Tema relacionado
- [API de Microsoft Defender para punto de conexión](apis-intro.md)
- [API de Búsqueda avanzada de amenazas](run-advanced-query-api.md)
- [Búsqueda avanzada de amenazas con Python](run-advanced-query-sample-python.md)
