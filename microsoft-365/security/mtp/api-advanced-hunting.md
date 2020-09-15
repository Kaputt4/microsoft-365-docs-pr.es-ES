---
title: API de búsqueda avanzada
description: Obtenga información sobre cómo ejecutar consultas de búsqueda avanzada mediante la API de protección contra amenazas de Microsoft
keywords: Búsqueda avanzada, API, API, MTP
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 92d5d2840963ae00ae0f03e3359f287371f770ee
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650552"
---
# <a name="advanced-hunting-apis"></a>API de búsqueda avanzada

**Se aplica a:**
- Protección contra amenazas de Microsoft

>[!IMPORTANT] 
>Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="limitations"></a>Limitaciones
1. Solo se puede ejecutar una consulta con datos de los últimos 30 días.
2. Los resultados incluirán un máximo de 100.000 filas.
3. El número de ejecuciones es limitado por espacio empresarial: hasta 15 llamadas por minuto, 15 minutos de tiempo de ejecución cada hora y 4 horas de tiempo de ejecución al día.
4. El tiempo de ejecución máximo de una única solicitud es de 10 minutos.

## <a name="permissions"></a>Permisos
Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [acceso a las API de Microsoft Threat Protection](api-access.md)

Tipo de permiso |   Permiso  |   Nombre para mostrar del permiso
:---|:---|:---
Aplicación |   AdvancedHunting. Read. All |  ' Ejecutar consultas avanzadas '
Delegado (cuenta profesional o educativa) | AdvancedHunting. Read | ' Ejecutar consultas avanzadas '

>[!Note]
> Al obtener un token con credenciales de usuario:
>- El usuario debe tener el rol de AD "ver datos"
>- El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos.

## <a name="http-request"></a>Solicitud HTTP
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Encabezados de solicitud

Encabezado | Valor 
:---|:---
Authorization | {Token} de portador. **Necesario**.
Content-Type    | application/json

## <a name="request-body"></a>Cuerpo de la solicitud
En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:

Parámetro | Tipo    | Description
:---|:---|:---
Consulta | Texto |  La consulta que se va a ejecutar. **Necesario**.

## <a name="response"></a>Respuesta
Si se ejecuta correctamente, este método devuelve 200 OK y el objeto _QueryResponse_ en el cuerpo de la respuesta. <br><br>

El objeto Response se divide en 3 partes (propiedades):<br>
1) ```Stats``` -Estadísticas de rendimiento de consultas.<br>
2) ```Schema``` -El esquema de la respuesta, una lista de pares de nombre-tipo para cada columna. <br>
3) ```Results``` -Una lista de eventos de búsqueda avanzada.

## <a name="example"></a>Ejemplo

Solicitud

Aquí tiene un ejemplo de la solicitud.


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

Respuesta

Aquí tiene un ejemplo de la respuesta.


```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
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
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}

```

## <a name="related-topic"></a>Tema relacionado
- [Acceso a las API de Microsoft Threat Protection](api-access.md)
