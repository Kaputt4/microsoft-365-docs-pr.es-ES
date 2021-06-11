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
#  <a name="run-live-response-commands-on-a-device"></a><span data-ttu-id="b3fa1-104">Ejecutar comandos de respuesta en directo en un dispositivo</span><span class="sxs-lookup"><span data-stu-id="b3fa1-104">Run live response commands on a device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b3fa1-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b3fa1-105">**Applies to:**</span></span>
- [<span data-ttu-id="b3fa1-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b3fa1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="b3fa1-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="b3fa1-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b3fa1-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="b3fa1-109">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="b3fa1-109">API description</span></span>

<span data-ttu-id="b3fa1-110">Ejecuta una secuencia de comandos de respuesta en directo en un dispositivo</span><span class="sxs-lookup"><span data-stu-id="b3fa1-110">Runs a sequence of live response commands on a device</span></span>

## <a name="limitations"></a><span data-ttu-id="b3fa1-111">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="b3fa1-111">Limitations</span></span>

1.  <span data-ttu-id="b3fa1-112">Las limitaciones de velocidad para esta API son 10 llamadas por minuto (las solicitudes adicionales se responden con HTTP 429).</span><span class="sxs-lookup"><span data-stu-id="b3fa1-112">Rate limitations for this API are 10 calls per minute (additional requests are responded with HTTP 429).</span></span>

2.  <span data-ttu-id="b3fa1-113">25 sesiones en ejecución simultánea (las solicitudes que superen el límite de limitación recibirán una respuesta "429 - Demasiadas solicitudes").</span><span class="sxs-lookup"><span data-stu-id="b3fa1-113">25 concurrently running sessions (requests exceeding the throttling limit will receive a "429 - Too many requests" response).</span></span>

3.  <span data-ttu-id="b3fa1-114">Si el equipo no está disponible, la sesión se pondrá en cola durante un máximo de 3 días.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-114">If the machine is not available, the session will be queued for up to 3 days.</span></span>

4.  <span data-ttu-id="b3fa1-115">Los tiempos de espera del comando RunScript se agotan después de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-115">RunScript command timeouts after 10 minutes.</span></span>

5.  <span data-ttu-id="b3fa1-116">Cuando se produce un error en un comando de respuesta en directo, no se ejecutarán todas las acciones seguidas.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-116">When a live response command fails all followed actions will not be executed.</span></span>

## <a name="permissions"></a><span data-ttu-id="b3fa1-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="b3fa1-117">Permissions</span></span>

<span data-ttu-id="b3fa1-118">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b3fa1-119">Para obtener más información, incluido cómo elegir permisos, vea [Get started](apis-intro.md).</span><span class="sxs-lookup"><span data-stu-id="b3fa1-119">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="b3fa1-120">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="b3fa1-120">Permission type</span></span>                    | <span data-ttu-id="b3fa1-121">Permiso</span><span class="sxs-lookup"><span data-stu-id="b3fa1-121">Permission</span></span>           | <span data-ttu-id="b3fa1-122">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="b3fa1-122">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="b3fa1-123">Aplicación</span><span class="sxs-lookup"><span data-stu-id="b3fa1-123">Application</span></span>                        | <span data-ttu-id="b3fa1-124">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="b3fa1-124">Machine.LiveResponse</span></span> | <span data-ttu-id="b3fa1-125">Ejecutar respuesta en directo en un equipo específico</span><span class="sxs-lookup"><span data-stu-id="b3fa1-125">Run live response on a specific machine</span></span> |
| <span data-ttu-id="b3fa1-126">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="b3fa1-126">Delegated (work or school account)</span></span> | <span data-ttu-id="b3fa1-127">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="b3fa1-127">Machine.LiveResponse</span></span> | <span data-ttu-id="b3fa1-128">Ejecutar respuesta en directo en un equipo específico</span><span class="sxs-lookup"><span data-stu-id="b3fa1-128">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="b3fa1-129">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="b3fa1-129">HTTP request</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a><span data-ttu-id="b3fa1-130">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="b3fa1-130">Request headers</span></span>

| <span data-ttu-id="b3fa1-131">Nombre</span><span class="sxs-lookup"><span data-stu-id="b3fa1-131">Name</span></span>      | <span data-ttu-id="b3fa1-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="b3fa1-132">Type</span></span> | <span data-ttu-id="b3fa1-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3fa1-133">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="b3fa1-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="b3fa1-134">Authorization</span></span> | <span data-ttu-id="b3fa1-135">Cadena</span><span class="sxs-lookup"><span data-stu-id="b3fa1-135">String</span></span>   | <span data-ttu-id="b3fa1-136">Portador\<token>\.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-136">Bearer\<token>\.</span></span> <span data-ttu-id="b3fa1-137">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-137">Required.</span></span>   |
| <span data-ttu-id="b3fa1-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="b3fa1-138">Content-Type</span></span>  | <span data-ttu-id="b3fa1-139">string</span><span class="sxs-lookup"><span data-stu-id="b3fa1-139">string</span></span>   | <span data-ttu-id="b3fa1-p104">application/json. Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-p104">application/json. Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="b3fa1-142">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="b3fa1-142">Request body</span></span>

| <span data-ttu-id="b3fa1-143">Parámetro</span><span class="sxs-lookup"><span data-stu-id="b3fa1-143">Parameter</span></span> | <span data-ttu-id="b3fa1-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="b3fa1-144">Type</span></span> | <span data-ttu-id="b3fa1-145">Description</span><span class="sxs-lookup"><span data-stu-id="b3fa1-145">Description</span></span>                                                        |
|---------------|----------|------------------------------------------------------------------------|
| <span data-ttu-id="b3fa1-146">Comentario</span><span class="sxs-lookup"><span data-stu-id="b3fa1-146">Comment</span></span>       | <span data-ttu-id="b3fa1-147">Cadena</span><span class="sxs-lookup"><span data-stu-id="b3fa1-147">String</span></span>   | <span data-ttu-id="b3fa1-148">Comentario para asociarlo a la acción.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-148">Comment to associate with the action.</span></span>                                 |
| <span data-ttu-id="b3fa1-149">Comandos</span><span class="sxs-lookup"><span data-stu-id="b3fa1-149">Commands</span></span>      | <span data-ttu-id="b3fa1-150">Matriz</span><span class="sxs-lookup"><span data-stu-id="b3fa1-150">Array</span></span>    | <span data-ttu-id="b3fa1-151">Comandos que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-151">Commands to run.</span></span> <span data-ttu-id="b3fa1-152">Los valores permitidos son PutFile, RunScript, GetFile.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-152">Allowed values are PutFile, RunScript, GetFile.</span></span> |

<span data-ttu-id="b3fa1-153">Comandos:</span><span class="sxs-lookup"><span data-stu-id="b3fa1-153">Commands:</span></span>

| <span data-ttu-id="b3fa1-154">Tipo de comando</span><span class="sxs-lookup"><span data-stu-id="b3fa1-154">Command Type</span></span> | <span data-ttu-id="b3fa1-155">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b3fa1-155">Parameters</span></span>                                                                          | <span data-ttu-id="b3fa1-156">Description</span><span class="sxs-lookup"><span data-stu-id="b3fa1-156">Description</span></span>                                                                                                                      |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b3fa1-157">PutFile</span><span class="sxs-lookup"><span data-stu-id="b3fa1-157">PutFile</span></span>      | <span data-ttu-id="b3fa1-158">Clave: FileName</span><span class="sxs-lookup"><span data-stu-id="b3fa1-158">Key: FileName</span></span>  <br><br>  <span data-ttu-id="b3fa1-159">Valor: \<file name\></span><span class="sxs-lookup"><span data-stu-id="b3fa1-159">Value: \<file name\></span></span>                                                                          | <span data-ttu-id="b3fa1-160">Coloca un archivo de la biblioteca en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-160">Puts a file from the library to the device.</span></span> <span data-ttu-id="b3fa1-161">Los archivos se guardan en una carpeta de trabajo y se eliminan cuando el dispositivo se reinicia de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-161">Files are saved in a working folder and are deleted when the device restarts by default.</span></span>
| <span data-ttu-id="b3fa1-162">RunScript</span><span class="sxs-lookup"><span data-stu-id="b3fa1-162">RunScript</span></span>    | <span data-ttu-id="b3fa1-163">Clave: ScriptName</span><span class="sxs-lookup"><span data-stu-id="b3fa1-163">Key: ScriptName</span></span><br><span data-ttu-id="b3fa1-164">Valor: \<Script from library\></span><span class="sxs-lookup"><span data-stu-id="b3fa1-164">Value: \<Script from library\></span></span> <br><br> <span data-ttu-id="b3fa1-165">Clave: Args</span><span class="sxs-lookup"><span data-stu-id="b3fa1-165">Key: Args</span></span>  <br> <span data-ttu-id="b3fa1-166">Valor: \<Script arguments\></span><span class="sxs-lookup"><span data-stu-id="b3fa1-166">Value: \<Script arguments\></span></span>                          | <span data-ttu-id="b3fa1-167">Ejecuta un script de la biblioteca en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-167">Runs a script from the library on a device.</span></span>    <br><br>  <span data-ttu-id="b3fa1-168">El parámetro Args se pasa al script.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-168">The Args parameter is passed to your script.</span></span> <br><br> <span data-ttu-id="b3fa1-169">Tiempo de espera después de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-169">Timeouts after 10 minutes.</span></span>     
| <span data-ttu-id="b3fa1-170">GetFile</span><span class="sxs-lookup"><span data-stu-id="b3fa1-170">GetFile</span></span>      | <span data-ttu-id="b3fa1-171">Clave: Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="b3fa1-171">Key: Path</span></span> <br> <span data-ttu-id="b3fa1-172">Valor: \<File path\></span><span class="sxs-lookup"><span data-stu-id="b3fa1-172">Value: \<File path\></span></span>                                                        | <span data-ttu-id="b3fa1-173">Recopilar archivo de un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-173">Collect file from a device.</span></span> <span data-ttu-id="b3fa1-174">NOTA: Las barras diagonales inversas en la ruta de acceso deben ser de escape.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-174">NOTE: Backslashes in path must be escaped.</span></span>                                                                      |

## <a name="response"></a><span data-ttu-id="b3fa1-175">Respuesta</span><span class="sxs-lookup"><span data-stu-id="b3fa1-175">Response</span></span>

-   <span data-ttu-id="b3fa1-176">Si se realiza correctamente, este método devuelve 200, Ok.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-176">If successful, this method returns 200, Ok.</span></span>
    <span data-ttu-id="b3fa1-177">Entidad Action.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-177">Action entity.</span></span> <span data-ttu-id="b3fa1-178">Si no se encontró el equipo con el identificador especificado: 404 No se encontró.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-178">If machine with the specified ID was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="b3fa1-179">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b3fa1-179">Example</span></span>

<span data-ttu-id="b3fa1-180">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="b3fa1-180">**Request**</span></span>

<span data-ttu-id="b3fa1-181">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-181">Here is an example of the request.</span></span>

```HTTP

POST
https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```
<span data-ttu-id="b3fa1-182">**JSON**</span><span class="sxs-lookup"><span data-stu-id="b3fa1-182">**JSON**</span></span>

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

<span data-ttu-id="b3fa1-183">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="b3fa1-183">**Response**</span></span>

<span data-ttu-id="b3fa1-184">Aquí tiene un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="b3fa1-184">Here is an example of the response.</span></span>

```HTTP
HTTP/1.1 200 Ok
```

<span data-ttu-id="b3fa1-185">Tipo de contenido: application/json</span><span class="sxs-lookup"><span data-stu-id="b3fa1-185">Content-type: application/json</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="b3fa1-186">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b3fa1-186">Related topics</span></span>
- [<span data-ttu-id="b3fa1-187">Obtener API de acción de máquina</span><span class="sxs-lookup"><span data-stu-id="b3fa1-187">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="b3fa1-188">Obtener resultado de respuesta en directo</span><span class="sxs-lookup"><span data-stu-id="b3fa1-188">Get live response result</span></span>](get-live-response-result.md)
- [<span data-ttu-id="b3fa1-189">Cancelar la acción del equipo</span><span class="sxs-lookup"><span data-stu-id="b3fa1-189">Cancel machine action</span></span>](cancel-machine-action.md)
