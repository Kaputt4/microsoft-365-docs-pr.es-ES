---
title: Búsqueda avanzada con conceptos básicos de api de PowerShell
ms.reviewer: ''
description: Obtenga información básica sobre cómo consultar la API de Microsoft Defender para endpoints con PowerShell.
keywords: apis, api admitidas, búsqueda avanzada, consulta
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 89ff7984e009f022984f4004a0195176c68a9bad
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194026"
---
# <a name="advanced-hunting-using-powershell"></a>Búsqueda avanzada de amenazas con PowerShell

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Ejecute consultas avanzadas con PowerShell, vea [Advanced Hunting API](run-advanced-query-api.md).

En esta sección, compartimos ejemplos de PowerShell para recuperar un token y usarlo para ejecutar una consulta.

## <a name="before-you-begin"></a>Antes de empezar
Primero debes crear [una aplicación](apis-intro.md).

## <a name="preparation-instructions"></a>Instrucciones de preparación

- Abra una ventana de PowerShell.
- Si la directiva no le permite ejecutar los comandos de PowerShell, puede ejecutar el siguiente comando:
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

>Para obtener más información, consulte [documentación de PowerShell](/powershell/module/microsoft.powershell.security/set-executionpolicy)

## <a name="get-token"></a>Obtener token

- Ejecute el siguiente comando:

```
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

donde
- $tenantId: identificador del espacio empresarial en nombre del que desea ejecutar la consulta (es decir, la consulta se ejecutará en los datos de este inquilino)
- $appId: id. de la aplicación de Azure AD (la aplicación debe tener permiso "Ejecutar consultas avanzadas" en Defender para endpoint)
- $appSecret: secreto de la aplicación de Azure AD

## <a name="run-query"></a>Ejecutar consulta

Ejecute la siguiente consulta:

```
$query = 'RegistryEvents | limit 10' # Paste your own query here

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

- $results los resultados de la consulta
- $schema contiene el esquema de los resultados de la consulta

### <a name="complex-queries"></a>Consultas complejas

Si desea ejecutar consultas complejas (o consultas de varias líneas), guarde la consulta en un archivo y, en lugar de la primera línea del ejemplo anterior, ejecute el comando siguiente:

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a>Trabajar con resultados de consulta

Ahora puede usar los resultados de la consulta.

Para generar los resultados de la consulta en formato CSV en el archivo file1.csv haga lo siguiente:

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

Para generar los resultados de la consulta en formato JSON en file file1.json, haga lo siguiente:

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a>Tema relacionado
- [Microsoft Defender para api de punto de conexión](apis-intro.md)
- [API de Búsqueda avanzada de amenazas](run-advanced-query-api.md)
- [Búsqueda avanzada de amenazas con Python](run-advanced-query-sample-python.md)
