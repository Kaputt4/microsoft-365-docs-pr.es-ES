---
title: Guía avanzada de la API de Python
ms.reviewer: ''
description: Obtenga información sobre cómo consultar con la API de Microsoft Defender para endpoint mediante Python, con ejemplos.
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
ms.technology: mde
ms.openlocfilehash: 78b6097ea9c3a83f35585f3b13fec4d9056ac25a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199722"
---
# <a name="advanced-hunting-using-python"></a><span data-ttu-id="af3fd-104">Búsqueda avanzada con Python</span><span class="sxs-lookup"><span data-stu-id="af3fd-104">Advanced Hunting using Python</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="af3fd-105">**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="af3fd-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="af3fd-106">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="af3fd-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="af3fd-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="af3fd-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="af3fd-108">Ejecute consultas avanzadas con Python, consulte [Advanced Hunting API](run-advanced-query-api.md).</span><span class="sxs-lookup"><span data-stu-id="af3fd-108">Run advanced queries using Python, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="af3fd-109">En esta sección, compartimos ejemplos de Python para recuperar un token y usarlo para ejecutar una consulta.</span><span class="sxs-lookup"><span data-stu-id="af3fd-109">In this section, we share Python samples to retrieve a token and use it to run a query.</span></span>

><span data-ttu-id="af3fd-110">**Requisito** previo: primero debes [crear una aplicación](apis-intro.md).</span><span class="sxs-lookup"><span data-stu-id="af3fd-110">**Prerequisite**: You first need to [create an app](apis-intro.md).</span></span>

## <a name="get-token"></a><span data-ttu-id="af3fd-111">Obtener token</span><span class="sxs-lookup"><span data-stu-id="af3fd-111">Get token</span></span>

- <span data-ttu-id="af3fd-112">Ejecute los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="af3fd-112">Run the following commands:</span></span>

```

import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.microsoftonline.com/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.microsoft.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]

```

<span data-ttu-id="af3fd-113">donde</span><span class="sxs-lookup"><span data-stu-id="af3fd-113">where</span></span>
- <span data-ttu-id="af3fd-114">tenantId: identificador del espacio empresarial en nombre del que desea ejecutar la consulta (es decir, la consulta se ejecutará en los datos de este espacio empresarial)</span><span class="sxs-lookup"><span data-stu-id="af3fd-114">tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="af3fd-115">appId: id. de la aplicación de Azure AD (la aplicación debe tener el permiso "Ejecutar consultas avanzadas" en Microsoft Defender para endpoint)</span><span class="sxs-lookup"><span data-stu-id="af3fd-115">appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Microsoft Defender for Endpoint)</span></span>
- <span data-ttu-id="af3fd-116">appSecret: secreto de la aplicación de Azure AD</span><span class="sxs-lookup"><span data-stu-id="af3fd-116">appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="af3fd-117">Ejecutar consulta</span><span class="sxs-lookup"><span data-stu-id="af3fd-117">Run query</span></span>

 <span data-ttu-id="af3fd-118">Ejecute la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="af3fd-118">Run the following query:</span></span>

```
query = 'RegistryEvents | limit 10' # Paste your own query here

url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
headers = { 
    'Content-Type' : 'application/json',
    'Accept' : 'application/json',
    'Authorization' : "Bearer " + aadToken
}

data = json.dumps({ 'Query' : query }).encode("utf-8")

req = urllib.request.Request(url, data, headers)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
schema = jsonResponse["Schema"]
results = jsonResponse["Results"]

```

- <span data-ttu-id="af3fd-119">schema contiene el esquema de los resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="af3fd-119">schema contains the schema of the results of your query</span></span>
- <span data-ttu-id="af3fd-120">los resultados contienen los resultados de la consulta</span><span class="sxs-lookup"><span data-stu-id="af3fd-120">results contain the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="af3fd-121">Consultas complejas</span><span class="sxs-lookup"><span data-stu-id="af3fd-121">Complex queries</span></span>

<span data-ttu-id="af3fd-122">Si desea ejecutar consultas complejas (o consultas de varias líneas), guarde la consulta en un archivo y, en lugar de la primera línea del ejemplo anterior, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="af3fd-122">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a><span data-ttu-id="af3fd-123">Trabajar con resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="af3fd-123">Work with query results</span></span>

<span data-ttu-id="af3fd-124">Ahora puede usar los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="af3fd-124">You can now use the query results.</span></span>

<span data-ttu-id="af3fd-125">Para recorrer en iteración los resultados, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="af3fd-125">To iterate over the results do the below:</span></span>

```
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result


```


<span data-ttu-id="af3fd-126">Para generar los resultados de la consulta en formato CSV en el archivo file1.csv haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="af3fd-126">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

<span data-ttu-id="af3fd-127">Para generar los resultados de la consulta en formato JSON en el archivo file1.jshaga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="af3fd-127">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```


## <a name="related-topic"></a><span data-ttu-id="af3fd-128">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="af3fd-128">Related topic</span></span>
- [<span data-ttu-id="af3fd-129">Microsoft Defender para api de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="af3fd-129">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="af3fd-130">API de Búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="af3fd-130">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="af3fd-131">Búsqueda avanzada con PowerShell</span><span class="sxs-lookup"><span data-stu-id="af3fd-131">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)
