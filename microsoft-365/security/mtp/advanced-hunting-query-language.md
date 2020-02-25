---
title: Conozca el lenguaje de consulta de la búsqueda avanzada de la Protección contra amenazas de Microsoft
description: Cree su primera consulta de búsqueda de amenazas y obtenga información sobre los operadores comunes y otros aspectos del lenguaje de consulta de búsqueda avanzada
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, idioma, aprendizaje, primera consulta, telemetría, eventos, telemetría, detecciones personalizadas, esquema, kusto, operadores, tipos de datos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: eda9b893057afd54a644f0091bf4e1b421bd5439
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42234699"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Conozca el lenguaje de consulta de búsqueda avanzada

**Se aplica a:**
- Protección contra amenazas de Microsoft



La búsqueda avanzada se basa en el [lenguaje de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/). Puede usar la sintaxis y los operadores Kusto para crear consultas que buscan información en el [esquema](advanced-hunting-schema-tables.md) específicamente estructurado para la búsqueda avanzada. Para entender mejor estos conceptos, ejecute la primera consulta.

## <a name="try-your-first-query"></a>Pruebe la primera consulta

En el Centro de seguridad de Microsoft 365, vaya a **Búsqueda** para ejecutar la primera consulta. Utilice el ejemplo siguiente:

```kusto
// Finds PowerShell execution events that could involve a download.
DeviceProcessEvents 
| where Timestamp > ago(7d)
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE") 
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
| project Timestamp, DeviceName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by Timestamp
```

Así se verá en la búsqueda avanzada.

![Imagen de la consulta de búsqueda avanzada de ATP de Microsoft Defender](../../media/advanced-hunting-query-example.png)

La consulta comienza con un breve comentario en el que se describe su función. Esto le ayudará si posteriormente decide guardar la consulta y compartirla con otras personas de su organización.

```kusto
// Finds PowerShell execution events that could involve a download.
DeviceProcessEvents
```

Generalmente, la consulta comienza con un nombre de tabla seguido de una serie de elementos precedidos por un operador de canalización (`|`). En este ejemplo, empezaremos introduciendo el nombre de la tabla `DeviceProcessEvents` y luego agregamos los elementos que sean necesarios, cada uno con su operador de canalización.

El primer elemento con canalización es un filtro de tiempo que abarca los siete días anteriores. Un intervalo de tiempo tan reducido como sea posible garantiza que las consultas funcionen bien, devuelvan resultados que se puedan administrar y no se agote el tiempo de espera.

```kusto
| where Timestamp > ago(7d)
```

El intervalo de tiempo va inmediatamente seguido de una búsqueda de archivos que representan la aplicación de PowerShell.

```kusto
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE")
```

A continuación, la consulta busca líneas de comandos que suelen usarse con PowerShell para descargar archivos.

```kusto
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
```

Ahora que la consulta identifica claramente los datos que desea localizar, agregue elementos que definen cómo son los resultados. `project` devuelve columnas específicas y `top` limita el número de resultados, logrando que los resultados tengan el formato correcto, sean lo suficientemente grandes y fáciles de procesar.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by Timestamp
```

Haga clic en **Ejecutar consulta** para ver los resultados. Puede expandir la vista de pantalla para poder centrarse en su consulta y en los resultados.

## <a name="learn-common-query-operators-for-advanced-hunting"></a>Conozca más operadores comunes de consulta para la búsqueda avanzada

Ahora que ha ejecutado la primera consulta y tiene una idea general de los componentes, es hora de retroceder un poco y aprender más sobre los aspectos básicos. El lenguaje de consulta Kusto que utiliza la búsqueda avanzada es compatible con una gama de operadores, entre ellos los siguientes operadores comunes.

| Operador | Descripción y uso |
|--|--|
| `where` | Filtra una tabla hasta llegar al subconjunto de filas que satisfacen un predicado. |
| `summarize` | Crea una tabla que agrega el contenido de la tabla de entrada. |
| `join` | Combina las filas de dos tablas para formar una nueva tabla mediante la coincidencia de los valores de la columna o columnas especificadas de cada tabla. |
| `count` | Devuelve el número de registros en el conjunto de registros de entrada. |
| `top` | Devuelve los primeros N registros ordenados según las columnas especificadas. |
| `limit` | Devuelve hasta el número de filas especificado. |
| `project` | Selecciona las columnas que desea incluir, cambia el nombre o elimina e inserta nuevas columnas calculadas. |
| `extend` | Crea columnas calculadas y las anexa al conjunto de resultados. |
| `makeset` |  Devuelve una matriz dinámica (JSON) del conjunto de valores distintivos que Expr toma en el grupo. |
| `find` | Busca las filas que coinciden con un predicado en un conjunto de tablas. |

Para ver un ejemplo dinámico de estos operadores, ejecútelos desde la sección **Comenzar** en la búsqueda avanzada.

## <a name="understand-data-types-and-their-query-syntax-implications"></a>Los tipos de datos y sus implicaciones de sintaxis de consulta

Los datos de las tablas de búsqueda avanzada se clasifican generalmente en los siguientes tipos de datos.

| Tipo de datos | Descripción e implicaciones de la consulta |
|--|--|
| `datetime` | Información sobre datos y hora que representan las marcas de tiempo del evento |
| `string` | Cadena de caracteres |
| `bool` | Verdadero o falso |
| `int` | Valor numérico de 32 bits  |
| `long` | Valor numérico de 64 bits |

## <a name="use-sample-queries"></a>Usar las consultas de ejemplo

La sección **Comenzar** ofrece algunas consultas sencillas con operadores de uso habitual. Pruebe a ejecutar estas consultas y realizar pequeñas modificaciones en ellas.

![Imagen de la ventana de búsqueda avanzada](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>Además de los ejemplos de consultas básicas, también puede acceder a [consultas compartidas](advanced-hunting-shared-queries.md) done encontrará escenarios específicos de búsqueda de amenazas. Explore las consultas compartidas en la parte izquierda de la página o en el repositorio de consultas de GitHub.

## <a name="access-query-language-documentation"></a>Acceso a documentación del lenguaje de consulta

Para más información sobre el lenguaje de consulta Kusto y los operadores compatibles, vaya a la [documentación del lenguaje de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/).

## <a name="related-topics"></a>Temas relacionados
- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
