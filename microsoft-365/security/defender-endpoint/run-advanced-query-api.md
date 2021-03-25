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
ms.technology: mde
ms.openlocfilehash: caf7a1bacfd726c560356d542bec3cf56c6b39d4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200202"
---
# <a name="advanced-hunting-api"></a>API de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a>Limitaciones
1. Solo puede ejecutar una consulta de datos de los últimos 30 días.
2. Los resultados incluirán un máximo de 100 000 filas.
3. El número de ejecuciones es limitado por inquilino:
   - Llamadas API: hasta 45 llamadas por minuto.
   - Tiempo de ejecución: 10 minutos de tiempo de ejecución cada hora y 3 horas de tiempo de ejecución al día.
4. El tiempo máximo de ejecución de una sola solicitud es de 10 minutos.
5. La respuesta 429 representará alcanzar el límite de cuota por número de solicitudes o por CPU. Lea el cuerpo de la respuesta para comprender qué límite se ha alcanzado. 

## <a name="permissions"></a>Permisos
Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)

Tipo de permiso |   Permiso  |   Nombre para mostrar de permisos
:---|:---|:---
Aplicación |   AdvancedQuery.Read.All |    'Ejecutar consultas avanzadas'
Delegado (cuenta profesional o educativa) | AdvancedQuery.Read | 'Ejecutar consultas avanzadas'

>[!Note]
> Al obtener un token con credenciales de usuario:
>- El usuario debe tener el rol de AD "Ver datos"
>- El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos (consulta Crear y administrar grupos [de dispositivos](machine-groups.md) para obtener más información)

## <a name="http-request"></a>Solicitud HTTP
```
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a>Encabezados de solicitud

Encabezado | Valor 
:---|:---
Authorization | Portador {token}. **Necesario**.
Content-Type    | application/json

## <a name="request-body"></a>Cuerpo de la solicitud
En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:

Parámetro | Tipo    | Descripción
:---|:---|:---
Consulta | Texto |  Consulta que se debe ejecutar. **Necesario**.

## <a name="response"></a>Respuesta
Si se ejecuta correctamente, este método devuelve 200 Ok y _el objeto QueryResponse_ en el cuerpo de la respuesta.


## <a name="example"></a>Ejemplo

Solicitud

Aquí tiene un ejemplo de la solicitud.

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

Respuesta

Aquí tiene un ejemplo de la respuesta.

>[!NOTE]
>El objeto de respuesta que se muestra aquí puede truncarse por brevedad. Todas las propiedades se devolverán desde una llamada real.

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

## <a name="related-topic"></a>Tema relacionado
- [Introducción a las API de Microsoft Defender para puntos de conexión](apis-intro.md)
- [Búsqueda avanzada desde portal](advanced-hunting-query-language.md)
- [Búsqueda avanzada con PowerShell](run-advanced-query-sample-powershell.md)
