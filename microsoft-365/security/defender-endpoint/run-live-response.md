---
title: Ejecutar comandos de respuesta en directo en un dispositivo
description: Aprende a ejecutar una secuencia de comandos de respuesta en directo en un dispositivo.
keywords: apis, api de gráficos, api admitidas, carga en biblioteca
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 2a7daf18b1a1d791e7b92ded0a6b839bba1fd4c2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879765"
---
#  <a name="run-live-response-commands-on-a-device"></a>Ejecutar comandos de respuesta en directo en un dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Ejecuta una secuencia de comandos de respuesta en directo en un dispositivo

## <a name="limitations"></a>Limitaciones

1.  Las limitaciones de velocidad para esta API son 10 llamadas por minuto (las solicitudes adicionales se responden con HTTP 429).

2.  25 sesiones en ejecución simultánea (las solicitudes que superen el límite de limitación recibirán una respuesta "429 - Demasiadas solicitudes").

3.  Si el equipo no está disponible, la sesión se pondrá en cola durante un máximo de 3 días.

4.  Los tiempos de espera del comando RunScript se agotan después de 10 minutos.

5.  Cuando se produce un error en un comando de respuesta en directo, no se ejecutarán todas las acciones seguidas.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, vea [Get started](apis-intro.md).

| Tipo de permiso                    | Permiso           | Nombre para mostrar de permisos                   |
|------------------------------------|----------------------|-------------------------------------------|
| Aplicación                        | Machine.LiveResponse | Ejecutar respuesta en directo en un equipo específico |
| Delegado (cuenta profesional o educativa) | Machine.LiveResponse | Ejecutar respuesta en directo en un equipo específico |

## <a name="http-request"></a>Solicitud HTTP

```HTTP
POST
https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a>Encabezados de solicitud

| Nombre      | Tipo | Descripción                 |
|---------------|----------|---------------------------------|
| Authorization | Cadena   | Portador\<token>\. Obligatorio.   |
| Content-Type  | string   | application/json. Obligatorio. |

## <a name="request-body"></a>Cuerpo de la solicitud

| Parámetro | Tipo | Description                                                        |
|---------------|----------|------------------------------------------------------------------------|
| Comentario       | Cadena   | Comentario para asociarlo a la acción.                                 |
| Comandos      | Matriz    | Comandos que se ejecutarán. Los valores permitidos son PutFile, RunScript, GetFile. |

Comandos:

| Tipo de comando | Parámetros                                                                          | Description                                                                                                                      |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| PutFile      | Clave: FileName  <br><br>  Valor: \<file name\>                                                                          | Coloca un archivo de la biblioteca en el dispositivo. Los archivos se guardan en una carpeta de trabajo y se eliminan cuando el dispositivo se reinicia de forma predeterminada.
| RunScript    | Clave: ScriptName<br>Valor: \<Script from library\> <br><br> Clave: Args  <br> Valor: \<Script arguments\>                          | Ejecuta un script de la biblioteca en un dispositivo.    <br><br>  El parámetro Args se pasa al script. <br><br> Tiempo de espera después de 10 minutos.     
| GetFile      | Clave: Ruta de acceso <br> Valor: \<File path\>                                                        | Recopilar archivo de un dispositivo. NOTA: Las barras diagonales inversas en la ruta de acceso deben ser de escape.                                                                      |

## <a name="response"></a>Respuesta

-   Si se realiza correctamente, este método devuelve 200, Ok.
    Entidad Action. Si no se encontró el equipo con el identificador especificado: 404 No se encontró.

## <a name="example"></a>Ejemplo

**Solicitud**

Aquí tiene un ejemplo de la solicitud.

```HTTP

POST
https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```
**JSON**

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

**Respuesta**

Aquí tiene un ejemplo de la respuesta.

```HTTP
HTTP/1.1 200 Ok
```

Tipo de contenido: application/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}


```

## <a name="related-topics"></a>Temas relacionados
- [Obtener API de acción de máquina](get-machineaction-object.md)
- [Obtener resultado de respuesta en directo](get-live-response-result.md)
- [Cancelar la acción del equipo](cancel-machine-action.md)
