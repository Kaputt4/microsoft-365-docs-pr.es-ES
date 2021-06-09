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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 0d44f59f69c590ecd8d61207de8784af3e32197d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844891"
---
# <a name="advanced-hunting-using-powershell"></a><span data-ttu-id="d3f85-104">Búsqueda avanzada de amenazas con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3f85-104">Advanced Hunting using PowerShell</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d3f85-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="d3f85-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="d3f85-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="d3f85-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d3f85-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="d3f85-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="d3f85-108">Ejecute consultas avanzadas con PowerShell, vea [Advanced Hunting API](run-advanced-query-api.md).</span><span class="sxs-lookup"><span data-stu-id="d3f85-108">Run advanced queries using PowerShell, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="d3f85-109">En esta sección, compartimos ejemplos de PowerShell para recuperar un token y usarlo para ejecutar una consulta.</span><span class="sxs-lookup"><span data-stu-id="d3f85-109">In this section, we share PowerShell samples to retrieve a token and use it to run a query.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d3f85-110">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="d3f85-110">Before you begin</span></span>
<span data-ttu-id="d3f85-111">Primero debes crear [una aplicación](apis-intro.md).</span><span class="sxs-lookup"><span data-stu-id="d3f85-111">You first need to [create an app](apis-intro.md).</span></span>

## <a name="preparation-instructions"></a><span data-ttu-id="d3f85-112">Instrucciones de preparación</span><span class="sxs-lookup"><span data-stu-id="d3f85-112">Preparation instructions</span></span>

- <span data-ttu-id="d3f85-113">Abra una ventana de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3f85-113">Open a PowerShell window.</span></span>
- <span data-ttu-id="d3f85-114">Si la directiva no le permite ejecutar los comandos de PowerShell, puede ejecutar el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="d3f85-114">If your policy does not allow you to run the PowerShell commands, you can run the below command:</span></span>
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

><span data-ttu-id="d3f85-115">Para obtener más información, consulte [documentación de PowerShell](/powershell/module/microsoft.powershell.security/set-executionpolicy)</span><span class="sxs-lookup"><span data-stu-id="d3f85-115">For more information, see [PowerShell documentation](/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

## <a name="get-token"></a><span data-ttu-id="d3f85-116">Obtener token</span><span class="sxs-lookup"><span data-stu-id="d3f85-116">Get token</span></span>

- <span data-ttu-id="d3f85-117">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="d3f85-117">Run the following:</span></span>

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

<span data-ttu-id="d3f85-118">donde</span><span class="sxs-lookup"><span data-stu-id="d3f85-118">where</span></span>
- <span data-ttu-id="d3f85-119">$tenantId: identificador del espacio empresarial en nombre del que desea ejecutar la consulta (es decir, la consulta se ejecutará en los datos de este inquilino)</span><span class="sxs-lookup"><span data-stu-id="d3f85-119">$tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="d3f85-120">$appId: id. de la aplicación de Azure AD (la aplicación debe tener permiso "Ejecutar consultas avanzadas" en Defender para endpoint)</span><span class="sxs-lookup"><span data-stu-id="d3f85-120">$appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Defender for Endpoint)</span></span>
- <span data-ttu-id="d3f85-121">$appSecret: secreto de la aplicación de Azure AD</span><span class="sxs-lookup"><span data-stu-id="d3f85-121">$appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="d3f85-122">Ejecutar consulta</span><span class="sxs-lookup"><span data-stu-id="d3f85-122">Run query</span></span>

<span data-ttu-id="d3f85-123">Ejecute la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="d3f85-123">Run the following query:</span></span>

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

- <span data-ttu-id="d3f85-124">$results los resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="d3f85-124">$results contain the results of your query</span></span>
- <span data-ttu-id="d3f85-125">$schema contiene el esquema de los resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="d3f85-125">$schema contains the schema of the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="d3f85-126">Consultas complejas</span><span class="sxs-lookup"><span data-stu-id="d3f85-126">Complex queries</span></span>

<span data-ttu-id="d3f85-127">Si desea ejecutar consultas complejas (o consultas de varias líneas), guarde la consulta en un archivo y, en lugar de la primera línea del ejemplo anterior, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3f85-127">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a><span data-ttu-id="d3f85-128">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="d3f85-128">Work with query results</span></span>

<span data-ttu-id="d3f85-129">Ahora puede usar los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="d3f85-129">You can now use the query results.</span></span>

<span data-ttu-id="d3f85-130">Para generar los resultados de la consulta en formato CSV en el archivo file1.csv haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3f85-130">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

<span data-ttu-id="d3f85-131">Para generar los resultados de la consulta en formato JSON en el archivo file1.jshaga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3f85-131">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a><span data-ttu-id="d3f85-132">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="d3f85-132">Related topic</span></span>
- [<span data-ttu-id="d3f85-133">Microsoft Defender para api de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d3f85-133">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="d3f85-134">API de Búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="d3f85-134">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="d3f85-135">Búsqueda avanzada de amenazas con Python</span><span class="sxs-lookup"><span data-stu-id="d3f85-135">Advanced Hunting using Python</span></span>](run-advanced-query-sample-python.md)
