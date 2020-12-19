---
title: API de búsqueda avanzada de Microsoft 365 defender
description: Obtenga información sobre cómo ejecutar consultas de búsqueda avanzada mediante la API de búsqueda avanzada de Microsoft 365 defender
keywords: Búsqueda avanzada, API, API, MTP, M365 defender, Microsoft 365 defender
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
ms.openlocfilehash: e7cd9192ec25e01ed06b77cb2b39357cb9df79bd
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719385"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>API de búsqueda avanzada de Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Protección contra amenazas de Microsoft

> [!IMPORTANT]
> Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

La [búsqueda avanzada](advanced-hunting-overview.md) es una herramienta de búsqueda de amenazas que usa [consultas especialmente construidas](advanced-hunting-query-language.md) para examinar los últimos 30 días de los datos de eventos en Microsoft 365 defender. Puede usar consultas de búsqueda avanzada para inspeccionar actividades inusuales, detectar posibles amenazas e incluso responder a ataques. La API de búsqueda avanzada permite consultar mediante programación datos de eventos.

## <a name="quotas-and-resource-allocation"></a>Cuotas y asignación de recursos

Las siguientes condiciones están relacionadas con todas las consultas.

1. Las consultas exploran y devuelven datos de los últimos 30 días.
2. Los resultados pueden devolver hasta 100.000 filas.
3. Puede realizar hasta 10 llamadas por minuto por espacio empresarial.
4. Tiene 10 minutos de tiempo de ejecución por hora y por inquilino.
5. Tiene cuatro horas totales de día de tiempo de ejecución por inquilino.
6. Si se ejecuta una única solicitud durante más de 10 minutos, se agotará el tiempo de espera y se devolverá un error.
7. Un `429` código de respuesta HTTP indica que ha alcanzado una cuota, ya sea por el número de solicitudes enviadas o por el tiempo de ejecución asignado. El cuerpo de la respuesta incluirá el tiempo hasta que se restablezca la cuota que ha alcanzado.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a la API de búsqueda avanzada. Para obtener más información, incluido cómo elegir permisos, consulte [acceso a las API de protección de Microsoft 365 defender](api-access.md)

Tipo de permiso | Permiso | Nombre para mostrar del permiso
-|-|-
Aplicación | AdvancedHunting. Read. All | Ejecutar consultas avanzadas
Delegado (cuenta profesional o educativa) | AdvancedHunting. Read | Ejecutar consultas avanzadas

>[!Note]
> Al obtener un token con credenciales de usuario:
>
>- El usuario debe tener el rol de AD "ver datos"
>- El usuario debe tener acceso al dispositivo en función de la configuración del grupo de dispositivos.

## <a name="http-request"></a>Solicitud HTTP

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Encabezados de solicitud

Encabezado | Valor
-|-
Authorization | {Token} nota de portador **: obligatorio**
Content-Type | application/json

## <a name="request-body"></a>Cuerpo de la solicitud

En el cuerpo de la solicitud, proporcione un objeto JSON con los siguientes parámetros:

Parámetro | Tipo | Descripción
-|-|-
Consulta | Texto | La consulta que se va a ejecutar. **Nota: es necesario**

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devolverá `200 OK` y un objeto _QueryResponse_ en el cuerpo de la respuesta.

El objeto Response contiene tres propiedades de nivel superior:

1. Estadísticas: un diccionario de estadísticas de rendimiento de consultas.
2. Schema-el esquema de la respuesta, una lista de pares de Name-Type para cada columna.
3. Resultados: una lista de eventos de búsqueda avanzada.

## <a name="example"></a>Ejemplo

En el siguiente ejemplo, un usuario envía la consulta siguiente y recibe un objeto de respuesta de la API que contiene `Stats` , `Schema` y `Results` .

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

- [Acceso a las API de Microsoft 365 defender](api-access.md)
- [Obtenga información sobre los límites de API y las licencias](api-terms.md)
- [Descripción de los códigos de error](api-error-codes.md)
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
