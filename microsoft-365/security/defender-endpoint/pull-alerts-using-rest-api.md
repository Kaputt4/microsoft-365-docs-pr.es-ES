---
title: Extraer Microsoft Defender para detecciones de puntos de conexión mediante la API de REST
description: Obtenga información sobre cómo llamar a un punto de conexión de la API de Microsoft Defender para endpoints para extraer detecciones en formato JSON mediante la API de REST de SIEM.
keywords: detecciones, detecciones de extracción, api de reposo, solicitud, respuesta
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
ms.openlocfilehash: a7d13da6abfb2cd6c829b6fd04fdf94de8cd20b8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186874"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a>Extraer Microsoft Defender para detecciones de puntos de conexión con la API de REST de SIEM

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

>[!Note]
>- [Microsoft Defender para alerta de](alerts.md) extremo se compone de una o más detecciones.
>- [Microsoft Defender para la detección de](api-portal-mapping.md) puntos de conexión se compone del evento sospechoso que se produjo en el dispositivo y sus detalles de alerta relacionados.
>-La API de alertas de punto de conexión de Microsoft Defender es la API más reciente para el consumo de alertas y contiene una lista detallada de pruebas relacionadas para cada alerta. Para obtener más información, vea [Alert methods and properties y](alerts.md) List [alerts](get-alerts.md).

Microsoft Defender para endpoint admite el protocolo OAuth 2.0 para extraer detecciones de la API.

En general, el protocolo OAuth 2.0 admite cuatro tipos de flujos:
- Flujo de concesión de autorización
- Flujo implícito
- Flujo de credenciales de cliente
- Flujo de propietario de recursos

Para obtener más información acerca de las especificaciones de OAuth, vea el sitio [web de OAuth](http://www.oauth.net).

Microsoft Defender para  endpoint admite  el flujo de concesión de autorización y el flujo de credenciales de cliente para obtener acceso a las detecciones de extracción, con Azure Active Directory (AAD) como servidor de autorización.

El _flujo de concesión de_ autorización usa credenciales de usuario para obtener un código de autorización, que luego se usa para obtener un token de acceso.

El _flujo de credenciales de cliente_ usa credenciales de cliente para autenticarse en la dirección URL del punto de conexión de Microsoft Defender para extremo. Este flujo es adecuado para escenarios en los que un cliente de OAuth crea solicitudes a una API que no requiere credenciales de usuario.

Use el siguiente método en la API de Microsoft Defender para Endpoint para extraer detecciones en formato JSON.

>[!NOTE]
>El Centro de seguridad de Microsoft Defender combina detecciones de alertas similares en una sola alerta. Esta API extrae detecciones de alertas en su forma sin procesar en función de los parámetros de consulta que establezca, lo que le permite aplicar su propia agrupación y filtrado. 

## <a name="before-you-begin"></a>Antes de empezar
- Antes de llamar al extremo de Microsoft Defender para endpoint para extraer detecciones, deberá habilitar la aplicación de integración SIEM en Azure Active Directory (AAD). Para obtener más información, vea [Enable SIEM integration in Microsoft Defender for Endpoint](enable-siem-integration.md).

- Anote los siguientes valores en su registro de aplicaciones de Azure ya que los necesitará para configurar el flujo de OAuth en su aplicación de servicio o demonio:
  - Identificador de la aplicación (exclusivo de la aplicación)
  - Clave de aplicación o secreto (exclusivo de la aplicación)
  - El punto de conexión del token de OAuth 2.0 de su aplicación
    - Para ver este valor, haga clic en **Ver puntos de conexión** en la parte inferior del Portal de administración de Azure, en la página de su aplicación. El punto de conexión será algo similar a `https://login.microsoftonline.com/{tenantId}/oauth2/token`.

## <a name="get-an-access-token"></a>Obtener un token de acceso
Antes de crear llamadas al punto de conexión, deberá obtener un token de acceso.

Usarás el token de acceso para obtener acceso al recurso protegido, que es detecciones en Microsoft Defender para endpoint.

Para obtener un token de acceso, deberá realizar una solicitud POST al punto de conexión de emisión de tokens. Esta es una solicitud de ejemplo:

```http

POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```
La respuesta incluirá un acceso token e información de expiración.

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```
Ahora puede usar el valor en el campo *access_token* en una solicitud a la API de Defender for Endpoint.

## <a name="request"></a>Solicitud
Con un token de acceso, la aplicación puede realizar solicitudes autenticadas a la API de Microsoft Defender para endpoints. Su aplicación debe anexar el token de acceso al encabezado de autorización de cada solicitud.

### <a name="request-syntax"></a>Sintaxis de solicitud
Método | URI de solicitud
:---|:---|
GET| Use el URI aplicable para su región. <br><br> **Para la UE**: `https://wdatp-alertexporter-eu.windows.com/api/alerts` </br> **Para EE. UU.**: `https://wdatp-alertexporter-us.windows.com/api/alerts` <br> **Para Reino Unido**: `https://wdatp-alertexporter-uk.windows.com/api/alerts` 

### <a name="request-header"></a>Encabezado de solicitud
Encabezado | Tipo | Descripción|
:--|:--|:--
Authorization | string | Necesario. El token de acceso de Azure AD con el formato **Bearer** &lt; *token* &gt; . |

### <a name="request-parameters"></a>Parámetros de la solicitud

Use parámetros de consulta opcionales para especificar y controlar la cantidad de datos devueltos en una respuesta. Si llama a este método sin parámetros, la respuesta contiene todas las alertas de la organización en las últimas 2 horas.

Nombre | Valor| Descripción
:---|:---|:---
sinceTimeUtc | DateTime | Define las alertas de límite de tiempo inferior de las que se recuperan, según el campo: <br> `LastProcessedTimeUtc` <br> El intervalo de tiempo será: de la hora sinceTimeUtc a la hora actual. <br><br> **NOTA:** Cuando no se especifica, se recuperan todas las alertas generadas en las últimas dos horas.
untilTimeUtc | DateTime | Define las alertas enlazadas de tiempo superior que se recuperan. <br> El intervalo de tiempo será: de `sinceTimeUtc` vez en `untilTimeUtc` cuando. <br><br> **NOTA**: Cuando no se especifica, el valor predeterminado será la hora actual.
ago | string | Extrae alertas en el siguiente intervalo de tiempo: `(current_time - ago)` de vez en `current_time` cuando. <br><br> El valor debe establecerse según **el formato de duración ISO 8601** <br> Ejemplo: `ago=PT10M` extraerá las alertas recibidas en los últimos 10 minutos.
límite | Entero | Define el número de alertas que se recuperarán. Las alertas más recientes se recuperarán en función del número definido.<br><br> **NOTA**: Cuando no se especifique, se recuperarán todas las alertas disponibles en el intervalo de tiempo.
machinegroups | string | Especifica los grupos de dispositivos de los que extraer alertas. <br><br> **NOTA:** Cuando no se especifica, se recuperarán las alertas de todos los grupos de dispositivos. <br><br> Ejemplo: <br><br> ```https://wdatp-alertexporter-eu.securitycenter.windows.com/api/Alerts/?machinegroups=UKMachines&machinegroups=FranceMachines```
DeviceCreatedMachineTags | string | Etiqueta de dispositivo única del Registro.
CloudCreatedMachineTags | string | Etiquetas de dispositivo creadas en el Centro de seguridad de Microsoft Defender.

### <a name="request-example"></a>Ejemplo de solicitud
En el ejemplo siguiente se muestra cómo recuperar todas las detecciones de la organización.

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

En el siguiente ejemplo se muestra una solicitud para obtener las últimas 20 detecciones desde 2016-09-12 a las 00:00:00.

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a>Respuesta
El valor devuelto es una matriz de objetos de alerta en formato JSON.

Este es un valor devuelto de ejemplo:

```json 
[
{        
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a>Ejemplos de código
### <a name="get-access-token"></a>Obtener token de acceso
En los ejemplos de código siguientes se muestra cómo obtener un token de acceso para llamar a la API SIEM de Microsoft Defender para endpoint.

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials" | cut -d "{" -f2 | cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]} | cut -d "\"" -f2 | cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a>Usar token para conectarse al extremo de detecciones
Los ejemplos de código siguientes muestran cómo usar un token de acceso para llamar a la API SIEM de Defender for Endpoint para obtener alertas.

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

#Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results.  This works for SIEM API:
$alerts =  $response.Content | ConvertFrom-Json | ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw | ConvertFrom-Json | Select-Object -ExpandProperty value | Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token" | cut -d "[" -f2 | cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a>Códigos de error
La API de REST de Microsoft Defender para endpoint devuelve los siguientes códigos de error causados por una solicitud no válida.

Código de error HTTP | Descripción
:---|:---
401 | Solicitud malformada o token no válido.
403 | Excepción no autorizada: el administrador de inquilinos no administra ninguno de los dominios o se elimina el estado del espacio empresarial.
500 | Error en el servicio.

## <a name="related-topics"></a>Temas relacionados
- [Habilitar la integración de SIEM en Microsoft Defender para endpoint](enable-siem-integration.md)
- [Configurar ArcSight para extraer Microsoft Defender para detecciones de puntos de conexión](configure-arcsight.md)
- [Extraer detecciones a las herramientas SIEM](configure-siem.md)
- [Campos de Microsoft Defender para detección de puntos de conexión](api-portal-mapping.md)
- [Solucionar problemas de integración de herramientas SIEM](troubleshoot-siem.md)
