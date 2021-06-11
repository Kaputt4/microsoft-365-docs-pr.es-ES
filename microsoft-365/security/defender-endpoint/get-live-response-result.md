---
title: Obtener resultados de respuesta en directo
description: Obtenga información sobre cómo recuperar un resultado de comando de respuesta en directo específico por su índice.
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
ms.openlocfilehash: d58fc87d16bb58199c95933d85752008a08a0e81
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879786"
---
#  <a name="get-live-response-results"></a>Obtener resultados de respuesta en directo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Recupera un resultado de comando de respuesta en directo específico por su índice.

## <a name="limitations"></a>Limitaciones

1.  Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, vea [Get started](apis-intro.md).

| Tipo de permiso                    | Permiso           | Nombre para mostrar de permisos                   |
|------------------------------------|----------------------|-------------------------------------------|
| Aplicación                        | Machine.LiveResponse | Ejecutar respuesta en directo en un equipo específico |
| Delegado (cuenta profesional o educativa) | Machine.LiveResponse | Ejecutar respuesta en directo en un equipo específico |

## <a name="http-request"></a>Solicitud HTTP

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a>Encabezados de solicitud

| Nombre      | Tipo | Descripción               |
|---------------|----------|-------------------------------|
| Authorization | Cadena   | {token} de portador. Obligatorio. |

## <a name="request-body"></a>Cuerpo de la solicitud

En blanco

## <a name="response"></a>Respuesta

Si se realiza correctamente, este método devuelve 200, Ok código de respuesta con el objeto que contiene el vínculo al resultado del comando en la *propiedad value.* Este vínculo es válido durante 30 minutos y debe usarse inmediatamente para descargar el paquete en un almacenamiento local. Otra llamada puede volver a crear un vínculo expirado y no es necesario volver a ejecutar la respuesta en directo.

*Propiedades de transcripción de Runscript:*

| Propiedad  | Description                       |
|---------------|---------------------------------------|
| name          | Nombre de script ejecutado                  |
| exit_code     | Código de salida de script ejecutado             |
| script_output | Salida estándar de script ejecutada       |
| script_error  | Salida de error estándar de script ejecutada |

## <a name="example"></a>Ejemplo

**Solicitud**

Aquí tiene un ejemplo de la solicitud.

```HTTP
GET
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

**Respuesta**

Aquí tiene un ejemplo de la respuesta.

HTTP/1.1 200 Ok

Tipo de contenido: application/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

*Contenido del archivo:* 

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_error":""
}
```

## <a name="related-topics"></a>Temas relacionados

- [Obtener API de acción de máquina](get-machineaction-object.md)
- [Cancelar la acción del equipo](cancel-machine-action.md)
- [Ejecutar respuesta en directo](run-live-response.md) 
