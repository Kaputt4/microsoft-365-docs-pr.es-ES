---
title: Microsoft 365 Defender API de búsqueda avanzada
description: Aprenda a ejecutar consultas de búsqueda avanzadas mediante la API de búsqueda avanzada de Microsoft 365 Defender
keywords: Búsqueda avanzada, API, API, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.custom: api
ms.openlocfilehash: d01cdacc40b58eb940b2773606221b4fdbe18728
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823198"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>Microsoft 365 Defender API de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

[La búsqueda avanzada](advanced-hunting-overview.md) es una herramienta de búsqueda de amenazas que usa [consultas especialmente construidas](advanced-hunting-query-language.md) para examinar los últimos 30 días de datos de eventos en Microsoft 365 Defender. Puede usar consultas de búsqueda avanzadas para inspeccionar actividades inusuales, detectar posibles amenazas e incluso responder a ataques. La API de búsqueda avanzada permite consultar datos de eventos mediante programación.

## <a name="quotas-and-resource-allocation"></a>Cuotas y asignación de recursos

Las condiciones siguientes se relacionan con todas las consultas.

1. Las consultas exploran y devuelven datos de los últimos 30 días.
2. Los resultados pueden devolver hasta 100 000 filas.
3. Puede realizar hasta 45 llamadas por minuto por inquilino.
4. Las consultas se bloquean si el inquilino ha alcanzado el 100 % hasta después del siguiente ciclo de 15 minutos.
5. Si una sola solicitud se ejecuta durante más de 10 minutos, se agota el tiempo de espera y se devuelve un error.
6. Un `429` código de respuesta HTTP indica que ha alcanzado una cuota, ya sea por número de solicitudes enviadas o por tiempo de ejecución asignado. Lea el cuerpo de la respuesta para comprender el límite que ha alcanzado. 

> [!NOTE]
> Todas las cuotas enumeradas anteriormente (por ejemplo, 15 llamadas por minuto) son por tamaño de inquilino. Estas cuotas son el mínimo.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a la API de búsqueda avanzada. Para obtener más información, incluido cómo elegir permisos, consulte [Acceso a las API de Microsoft 365 Defender Protection](api-access.md).

Tipo de permiso | Permiso | Nombre para mostrar del permiso
-|-|-
Aplicación | AdvancedHunting.Read.All| Ejecución de consultas avanzadas
Delegado (cuenta profesional o educativa) | AdvancedHunting.Read | Ejecución de consultas avanzadas

>[!Note]
> Al obtener un token con credenciales de usuario:
>
>- El usuario debe tener el rol de AD "Ver datos".
>- El usuario debe tener acceso al dispositivo, en función de la configuración del grupo de dispositivos.

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

En el cuerpo de la solicitud, proporcione un objeto JSON con los parámetros siguientes:

Parámetro | Tipo | Descripción
-|-|-
Query | Texto | Consulta que se va a ejecutar. **Nota: obligatorio**

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devolverá `200 OK`y un objeto _QueryResponse_ en el cuerpo de la respuesta.

El objeto de respuesta contiene tres propiedades de nivel superior:

1. Estadísticas: diccionario de estadísticas de rendimiento de consultas.
2. Esquema: esquema de la respuesta, una lista de pares de Name-Type para cada columna.
3. Resultados: una lista de eventos de búsqueda avanzada.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, un usuario envía la consulta siguiente y recibe un objeto de respuesta de API que contiene `Stats`, `Schema`y `Results`.

### <a name="query"></a>Query

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a>Objeto Response

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

- [Acceso a las API de Microsoft 365 Defender](api-access.md)
- [Más información sobre los límites de API y las licencias](api-terms.md)
- [Descripción de los códigos de error](api-error-codes.md)
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
