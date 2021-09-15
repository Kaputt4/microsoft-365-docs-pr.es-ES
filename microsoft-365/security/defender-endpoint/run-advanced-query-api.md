---
title: API de Búsqueda avanzada de amenazas
ms.reviewer: ''
description: Aprenda a usar la API de búsqueda avanzada para ejecutar consultas avanzadas en Microsoft Defender para endpoint. Descubra las limitaciones y vea un ejemplo.
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
ms.openlocfilehash: f85c4cd8cf5d657e4043aae80da8b3dae989a29d
ms.sourcegitcommit: f88a0ec621e7d9bc5f376eeaf70c8a9800711f88
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2021
ms.locfileid: "59356627"
---
# <a name="advanced-hunting-api"></a>API de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a>Limitaciones

1. Solo puede ejecutar una consulta de datos de los últimos 30 días.

2. Los resultados incluirán un máximo de 100 000 filas.

3. El número de ejecuciones es limitado por inquilino:
   - Llamadas API: hasta 45 llamadas por minuto, hasta 1500 llamadas por hora.
   - Tiempo de ejecución: 10 minutos de tiempo de ejecución cada hora y 3 horas de tiempo de ejecución al día.

4. El tiempo máximo de ejecución de una sola solicitud es de 10 minutos.

5. La respuesta 429 representará alcanzar el límite de cuota por número de solicitudes o por CPU. Lea el cuerpo de la respuesta para comprender qué límite se ha alcanzado.

6. El tamaño máximo del resultado de la consulta de una sola solicitud no puede superar los 124 MB. Si se supera, HTTP 400 Bad Request con el mensaje "La ejecución de la consulta ha excedido el tamaño de resultado permitido. Optimizar la consulta limitando la cantidad de resultados e intentarlo de nuevo" aparecerá.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar de permisos
:---|:---|:---
Aplicación|AdvancedQuery.Read.All|'Ejecutar consultas avanzadas'
Delegado (cuenta profesional o educativa)|AdvancedQuery.Read|'Ejecutar consultas avanzadas'

> [!NOTE]
> Al obtener un token con credenciales de usuario:
>
> - El usuario debe tener el rol de AD "Ver datos"
> - El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)

## <a name="http-request"></a>Solicitud HTTP

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a>Encabezados de solicitud

Encabezado|Valor
:---|:---
Authorization|Portador {token}. **Necesario**.
Content-Type|application/json

## <a name="request-body"></a>Cuerpo de la solicitud

En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:

Parámetro|Tipo|Descripción
:---|:---|:---
Consulta|Texto|Consulta que se debe ejecutar. **Necesario**.

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve 200 Ok y _el objeto QueryResponse_ en el cuerpo de la respuesta.

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

Aquí tiene un ejemplo de la solicitud.

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents
|where InitiatingProcessFileName =~ 'powershell.exe'
|where ProcessCommandLine contains 'appdata'
|project Timestamp, FileName, InitiatingProcessFileName, DeviceId
|limit 2"
}
```

### <a name="response-example"></a>Ejemplo de respuesta

Aquí tiene un ejemplo de la respuesta.

> [!NOTE]
> El objeto de respuesta que se muestra aquí puede truncarse por brevedad. Todas las propiedades se devolverán desde una llamada real.

```json
{
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topics"></a>Temas relacionados

- [Introducción a las API de Microsoft Defender para puntos de conexión](apis-intro.md)
- [Búsqueda avanzada desde portal](advanced-hunting-query-language.md)
- [Búsqueda avanzada de amenazas con PowerShell](run-advanced-query-sample-powershell.md)
