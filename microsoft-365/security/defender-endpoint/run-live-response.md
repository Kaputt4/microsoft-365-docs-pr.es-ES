---
title: Ejecución de comandos de respuesta en directo en un dispositivo
description: Obtenga información sobre cómo ejecutar una secuencia de comandos de respuesta dinámica en un dispositivo.
keywords: api, graph api, api admitidas, carga en la biblioteca
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: 4ef4a02be76d24d99b77272f751b646fa526827e
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68628057"
---
# <a name="run-live-response-commands-on-a-device"></a>Ejecución de comandos de respuesta en directo en un dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)


[!include[Prerelease information](../../includes/prerelease.md)]

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Ejecuta una secuencia de comandos de respuesta dinámica en un dispositivo.

## <a name="limitations"></a>Limitaciones

1. Las limitaciones de velocidad de esta API son de 10 llamadas por minuto (las solicitudes adicionales se responden con HTTP 429).

2. 25 sesiones en ejecución simultánea (las solicitudes que superen el límite de limitación recibirán una respuesta "429 - Demasiadas solicitudes").

3. Si la máquina no está disponible, la sesión se pondrá en cola durante un máximo de 3 días.

4. Tiempos de espera del comando RunScript después de 10 minutos.

5. Los comandos de respuesta dinámica no se pueden poner en cola y solo se pueden ejecutar de uno en uno.

6. Si la máquina que intenta ejecutar esta llamada API está en un grupo de dispositivos RBAC que no tiene asignado un nivel de corrección automatizado, deberá habilitar al menos el nivel de corrección mínimo para un grupo de dispositivos determinado.
    > [!NOTE]
    > La creación de grupos de dispositivos se admite en El plan 1 y el plan 2 de Defender para punto de conexión.  

7. Se pueden ejecutar varios comandos de respuesta dinámica en una sola llamada API. Sin embargo, cuando se produce un error en un comando de respuesta dinámica, no se ejecutarán todas las acciones posteriores.

## <a name="minimum-requirements"></a>Requisitos mínimos

Antes de iniciar una sesión en un dispositivo, asegúrese de cumplir los siguientes requisitos:

- **Compruebe que está ejecutando una versión compatible de Windows**.

  Los dispositivos deben ejecutar una de las siguientes versiones de Windows

  - **Windows 11**
  
  - **Windows 10**
    - [Versión 1909](/windows/whats-new/whats-new-windows-10-version-1909) o posterior
    - [Versión 1903](/windows/whats-new/whats-new-windows-10-version-1903) con [KB4515384](https://support.microsoft.com/help/4515384/windows-10-update-kb4515384)
    - [Versión 1809 (RS 5)](/windows/whats-new/whats-new-windows-10-version-1809) [con KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)
    - [Versión 1803 (RS 4)](/windows/whats-new/whats-new-windows-10-version-1803) con [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)
    - [Versión 1709 (RS 3)](/windows/whats-new/whats-new-windows-10-version-1709) con [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)

  - **Windows Server 2019: solo aplicable para la versión preliminar pública**
    - Versión 1903 o (con [KB4515384](https://support.microsoft.com/help/4515384/windows-10-update-kb4515384)) posterior
    - Versión 1809 (con [KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818))
    
  - **Windows Server 2022**

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para más información, incluido cómo elegir permisos, consulte [Introducción](apis-intro.md).

|Tipo de permiso|Permiso|Nombre para mostrar del permiso|
|---|---|---|
|Application|Machine.LiveResponse|Ejecución de una respuesta en directo en una máquina específica|
|Delegado (cuenta profesional o educativa)|Machine.LiveResponse|Ejecución de una respuesta en directo en una máquina específica|

## <a name="http-request"></a>Solicitud HTTP

```HTTP
POST https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a>Encabezados de solicitud

|Nombre|Tipo|Descripción|
|---|---|---|
|Authorization|Cadena|Portador\<token>\. Obligatorio.|
|Content-Type|string|application/json. Required.|

## <a name="request-body"></a>Cuerpo de la solicitud

|Parámetro|Tipo|Descripción|
|---|---|---|
|Comentario|Cadena|Comentario que se va a asociar a la acción.|
|Comandos|Matriz|Comandos que se van a ejecutar. Los valores permitidos son PutFile, RunScript y GetFile.|

## <a name="commands"></a>Comandos

|Tipo de comando|Parámetros|Description|
|---|---|---|
|PutFile|Clave: FileName <p> Valor: \<file name\>|Coloca un archivo de la biblioteca en el dispositivo. Los archivos se guardan en una carpeta de trabajo y se eliminan cuando el dispositivo se reinicia de forma predeterminada.
|Runscript|Clave: ScriptName <br> Valor: \<Script from library\> <p> Clave: Args <br> Valor: \<Script arguments\>|Ejecuta un script desde la biblioteca en un dispositivo. <p>  El parámetro Args se pasa al script. <p> Tiempos de espera después de 10 minutos.|
|GetFile|Clave: Ruta de acceso <br> Valor: \<File path\>|Recopilar archivo de un dispositivo. NOTA: Las barras diagonales inversas en la ruta de acceso deben tener escape.|

## <a name="response"></a>Respuesta

- Si se ejecuta correctamente, este método devuelve 201 Created.

  Entidad Action. Si no se encontró la máquina con el identificador especificado: 404 No encontrado.

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

Aquí tiene un ejemplo de la solicitud.

```HTTP
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

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

### <a name="response-example"></a>Ejemplo de respuesta

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

- [Obtención de la API de acción de la máquina](get-machineaction-object.md)
- [Obtener resultado de respuesta en directo](get-live-response-result.md)
- [Cancelar acción de máquina](cancel-machine-action.md)
