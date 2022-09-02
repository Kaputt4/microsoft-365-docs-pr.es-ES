---
title: Obtención de resultados de respuesta en directo
description: Obtenga información sobre cómo recuperar un resultado de comando de respuesta dinámica específico por su índice.
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
ms.collection: m365-security-compliance
ms.topic: article
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: 4ea317cc7bcc60162b67e4c01baecb7a2f5c8ced
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67523586"
---
# <a name="get-live-response-results"></a>Obtención de resultados de respuesta en directo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Recupera un resultado de comando de respuesta dinámica específico por su índice.

## <a name="limitations"></a>Limitaciones

1. Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.

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
Application|Machine.Read.All|''Leer todos los perfiles de máquina''
Application|"Machine.ReadWrite.All|"Leer y escribir toda la información de la máquina"
|Delegado (cuenta profesional o educativa)|Machine.LiveResponse|Ejecución de una respuesta en directo en una máquina específica|

## <a name="http-request"></a>Solicitud HTTP

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a>Encabezados de solicitud

|Nombre|Tipo|Descripción|
|---|---|---|
|Authorization|Cadena|{token} de portador. Obligatorio.|

## <a name="request-body"></a>Cuerpo de solicitud

En blanco

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve el código de respuesta 200, Ok con el objeto que contiene el vínculo al comando da como resultado la propiedad *value* . Este vínculo es válido durante 30 minutos y debe usarse inmediatamente para descargar el paquete en un almacenamiento local. Otra llamada puede volver a crear un vínculo expirado y no es necesario volver a ejecutar la respuesta en directo.

*Propiedades de transcripción de Runscript:*

|Propiedad|Descripción|
|---|---|
|script_name|Nombre del script ejecutado|
|exit_code|Código de salida del script ejecutado|
|script_output|Salida estándar del script ejecutado|
|script_errors|Salida de error estándar del script ejecutado|

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

Aquí tiene un ejemplo de la solicitud.

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

### <a name="response-example"></a>Ejemplo de respuesta

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
    "script_errors":""
}
```

## <a name="related-topics"></a>Temas relacionados

- [Obtención de la API de acción de la máquina](get-machineaction-object.md)
- [Cancelar acción de máquina](cancel-machine-action.md)
- [Ejecutar respuesta directa](run-live-response.md) 
