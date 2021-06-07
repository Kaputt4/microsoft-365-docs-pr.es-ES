---
title: Microsoft 365 API de búsqueda avanzada de Defender
description: Obtenga información sobre cómo ejecutar consultas avanzadas de búsqueda con Microsoft 365 API avanzada de búsqueda de Defender
keywords: Búsqueda avanzada, API, api, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3ff62265783be846a95964164e372100fe1ef662
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769592"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>Microsoft 365 API de búsqueda avanzada de Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

[La búsqueda avanzada](advanced-hunting-overview.md) es una [](advanced-hunting-query-language.md) herramienta de búsqueda de amenazas que usa consultas especialmente construidas para examinar los últimos 30 días de datos de eventos en Microsoft 365 Defender. Puedes usar consultas avanzadas de búsqueda para inspeccionar actividad inusual, detectar posibles amenazas e incluso responder a ataques. La API de búsqueda avanzada le permite consultar programáticamente los datos de eventos.

## <a name="quotas-and-resource-allocation"></a>Cuotas y asignación de recursos

Las siguientes condiciones se relacionan con todas las consultas.

1. Las consultas exploran y devuelven datos de los últimos 30 días.
2. Los resultados pueden devolver hasta 100 000 filas.
3. Puede realizar hasta 15 llamadas por minuto por inquilino.
4. Las consultas se bloquean si el inquilino ha alcanzado el 100 % hasta después del siguiente ciclo de 15 minutos.
5. Si una sola solicitud se ejecuta durante más de 10 minutos, agotará el tiempo de espera y devolverá un error.
6. Un código de respuesta HTTP indica que ha alcanzado una cuota, ya sea por número de solicitudes enviadas o por tiempo `429` de ejecución asignado. Lea el cuerpo de la respuesta para comprender el límite que ha alcanzado. 

> [!NOTE]
> Todas las cuotas enumeradas anteriormente (por ejemplo, 15 llamadas por minuto) son por tamaño de espacio empresarial. Estas cuotas son las mínimas.

## <a name="permissions"></a>Permissions

Uno de los siguientes permisos es necesario para llamar a la API de búsqueda avanzada. Para obtener más información, incluido cómo elegir permisos, consulte [Access the Microsoft 365 Defender Protection API](api-access.md)

Tipo de permiso | Permiso | Nombre para mostrar de permisos
-|-|-
Aplicación | AdvancedHunting.Read.All | Ejecutar consultas avanzadas
Delegado (cuenta profesional o educativa) | AdvancedHunting.Read | Ejecutar consultas avanzadas

>[!Note]
> Al obtener un token con credenciales de usuario:
>
>- El usuario debe tener el rol de AD "Ver datos"
>- El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos.

## <a name="http-request"></a>Solicitud HTTP

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Encabezados de solicitud

Encabezado | Valor
-|-
Authorization | Portador {token} **Nota: obligatorio**
Content-Type | application/json

## <a name="request-body"></a>Cuerpo de la solicitud

En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:

Parámetro | Tipo | Descripción
-|-|-
Consulta | Texto | Consulta que se debe ejecutar. **Nota: obligatorio**

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devolverá `200 OK` y un _objeto QueryResponse_ en el cuerpo de la respuesta.

El objeto response contiene tres propiedades de nivel superior:

1. Estadísticas: diccionario de estadísticas de rendimiento de consulta.
2. Esquema: el esquema de la respuesta, una lista de Name-Type pares de cada columna.
3. Resultados: una lista de eventos de búsqueda avanzados.

## <a name="example"></a>Ejemplo:

En el siguiente ejemplo, un usuario envía la consulta siguiente y recibe un objeto de respuesta api que contiene `Stats` , `Schema` y `Results` .

### <a name="query"></a>Consulta

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a>Response (objeto)

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

## <a name="related-articles"></a>Artículos relacionados

- [Acceder a las API Microsoft 365 Defender](api-access.md)
- [Más información sobre los límites de api y las licencias](api-terms.md)
- [Comprender códigos de error](api-error-codes.md)
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
