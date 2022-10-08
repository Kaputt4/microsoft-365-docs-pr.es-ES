---
title: Guía de búsqueda avanzada con API de Python
ms.reviewer: ''
description: Obtenga información sobre cómo consultar mediante la API de Microsoft Defender para punto de conexión, mediante Python, con ejemplos.
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
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: db5e7ee445a15b98d0b871c397c3dd84a9b0e510
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68226084"
---
# <a name="advanced-hunting-using-python"></a>Búsqueda avanzada de amenazas con Python

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** 
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Ejecute consultas avanzadas con Python, consulte [Advanced Hunting API](run-advanced-query-api.md).

En esta sección, compartimos ejemplos de Python para recuperar un token y usarlo para ejecutar una consulta.

> **Requisito previo**: primero debe [crear una aplicación](apis-intro.md).

## <a name="get-token"></a>Obtener token

- Ejecute los comandos siguientes:

```python
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

Dónde

- tenantId: identificador del inquilino en nombre del que desea ejecutar la consulta (es decir, la consulta se ejecutará en los datos de este inquilino).
- appId: identificador de la aplicación de Azure AD (la aplicación debe tener el permiso "Ejecutar consultas avanzadas" para Microsoft Defender para punto de conexión)
- appSecret: secreto de la aplicación de Azure AD

## <a name="run-query"></a>Ejecutar consulta

 Ejecute la consulta siguiente:

```python
query = 'DeviceRegistryEvents | limit 10' # Paste your own query here

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

- esquema contiene el esquema de los resultados de la consulta
- los resultados contienen los resultados de la consulta

### <a name="complex-queries"></a>Consultas complejas

Si desea ejecutar consultas complejas (o consultas multilínea), guarde la consulta en un archivo y, en lugar de la primera línea del ejemplo anterior, ejecute el siguiente comando:

```python
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a>Trabajar con resultados de consulta

Ahora puede usar los resultados de la consulta.

Para recorrer en iteración los resultados, haga lo siguiente:

```python
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result
```

Para generar los resultados de la consulta en formato CSV en el archivo file1.csv haga lo siguiente:

```python
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

Para generar los resultados de la consulta en formato JSON en el archivo file1.json, haga lo siguiente:

```python
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```

## <a name="related-topic"></a>Tema relacionado

- [API de Microsoft Defender para punto de conexión](apis-intro.md)
- [API de Búsqueda avanzada de amenazas](run-advanced-query-api.md)
- [Búsqueda avanzada de amenazas con PowerShell](run-advanced-query-sample-powershell.md)
