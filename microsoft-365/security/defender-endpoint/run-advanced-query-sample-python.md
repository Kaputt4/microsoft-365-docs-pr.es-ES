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
# <a name="advanced-hunting-using-python"></a>Búsqueda avanzada con Python

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Ejecute consultas avanzadas con Python, consulte [Advanced Hunting API](run-advanced-query-api.md).

En esta sección, compartimos ejemplos de Python para recuperar un token y usarlo para ejecutar una consulta.

>**Requisito** previo: primero debes [crear una aplicación](apis-intro.md).

## <a name="get-token"></a>Obtener token

- Ejecute los comandos siguientes:

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

donde
- tenantId: identificador del espacio empresarial en nombre del que desea ejecutar la consulta (es decir, la consulta se ejecutará en los datos de este espacio empresarial)
- appId: id. de la aplicación de Azure AD (la aplicación debe tener el permiso "Ejecutar consultas avanzadas" en Microsoft Defender para endpoint)
- appSecret: secreto de la aplicación de Azure AD

## <a name="run-query"></a>Ejecutar consulta

 Ejecute la siguiente consulta:

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

- schema contiene el esquema de los resultados de la consulta
- los resultados contienen los resultados de la consulta

### <a name="complex-queries"></a>Consultas complejas

Si desea ejecutar consultas complejas (o consultas de varias líneas), guarde la consulta en un archivo y, en lugar de la primera línea del ejemplo anterior, ejecute el comando siguiente:

```
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a>Trabajar con resultados de consulta

Ahora puede usar los resultados de la consulta.

Para recorrer en iteración los resultados, haga lo siguiente:

```
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result


```


Para generar los resultados de la consulta en formato CSV en el archivo file1.csv haga lo siguiente:

```
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

Para generar los resultados de la consulta en formato JSON en el archivo file1.jshaga lo siguiente:

```
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```


## <a name="related-topic"></a>Tema relacionado
- [Microsoft Defender para api de punto de conexión](apis-intro.md)
- [API de Búsqueda avanzada de amenazas](run-advanced-query-api.md)
- [Búsqueda avanzada con PowerShell](run-advanced-query-sample-powershell.md)
