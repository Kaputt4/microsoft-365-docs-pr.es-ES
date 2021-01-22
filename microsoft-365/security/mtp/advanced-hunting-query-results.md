---
title: Trabajar con resultados de consulta de búsqueda avanzada en Microsoft 365 Defender
description: Obtener el máximo partido de los resultados de la consulta devueltos por la búsqueda avanzada en Microsoft 365 Defender
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, microsoft 365, Protección contra amenazas de Microsoft, visualización, gráfico, filtros, exploración en profundidad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 462ba35f584b45bbfeb0d8a3de3b118ba1c9e17c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932327"
---
# <a name="work-with-advanced-hunting-query-results"></a>Trabajar con resultados de consulta de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Aunque puede crear [](advanced-hunting-overview.md) consultas de búsqueda avanzada para devolver información muy precisa, también puede trabajar con los resultados de la consulta para obtener más información e investigar actividades e indicadores específicos. Puede realizar las siguientes acciones en los resultados de la consulta:

- Ver resultados como una tabla o gráfico
- Exportar tablas y gráficos
- Explorar en profundidad la información detallada de la entidad
- Retocar las consultas directamente desde los resultados o aplicar filtros

## <a name="view-query-results-as-a-table-or-chart"></a>Ver los resultados de la consulta como una tabla o un gráfico
De forma predeterminada, la búsqueda avanzada muestra los resultados de la consulta como datos tabulares. También puede mostrar los mismos datos que un gráfico. La búsqueda avanzada admite las siguientes vistas:

| Tipo de vista | Descripción |
| -- | -- |
| **Table** | Muestra los resultados de la consulta en formato tabular |
| **Gráfico de columnas** | Representa una serie de elementos únicos en el eje X como barras verticales cuyos altos representan valores numéricos de otro campo |
| **Gráfico de columnas apiladas** | Representa una serie de elementos únicos en el eje X como barras verticales apiladas cuyos altos representan valores numéricos de uno o más campos |
| **Gráfico circular** | Representa los pies de sección que representan elementos únicos. El tamaño de cada gráfico circular representa valores numéricos de otro campo. |
| **Gráfico de donas** | Representa arcos de sección que representan elementos únicos. La longitud de cada arco representa valores numéricos de otro campo. |
| **Gráfico de líneas** | Traza valores numéricos para una serie de elementos únicos y conecta los valores trazados |
| **Gráfico de dispersión** | Traza valores numéricos para una serie de elementos únicos |
| **Gráfico de áreas** | Traza los valores numéricos de una serie de elementos únicos y rellena las secciones debajo de los valores trazados |

### <a name="construct-queries-for-effective-charts"></a>Crear consultas para gráficos efectivos
Al representar gráficos, la búsqueda avanzada identifica automáticamente las columnas de interés y los valores numéricos que se agregan. Para obtener gráficos significativos, cree las consultas para devolver los valores específicos que desea ver visualizados. Estas son algunas consultas de ejemplo y los gráficos resultantes.

#### <a name="alerts-by-severity"></a>Alertas por gravedad
Use el `summarize` operador para obtener un recuento numérico de los valores que desea gráficos. La consulta siguiente usa el `summarize` operador para obtener el número de alertas por gravedad.

```kusto
AlertInfo
| summarize Total = count() by Severity
```
Al representar los resultados, un gráfico de columnas muestra cada valor de gravedad como una columna independiente:

![Imagen de resultados de consulta de búsqueda avanzada que se muestran como un gráfico de columnas Resultados de consulta para alertas por gravedad mostradas ](../../media/advanced-hunting-column-chart.jpg)
 *como un gráfico de columnas*

#### <a name="alert-severity-by-operating-system"></a>Gravedad de alerta por sistema operativo
También puede usar el operador `summarize` para preparar los resultados de los gráficos de valores de varios campos. Por ejemplo, es posible que quieras comprender cómo se distribuyen las gravedades de alerta entre sistemas operativos (SO). 

La consulta siguiente usa un operador para extraer información del sistema operativo de la tabla y, a continuación, usa para contar los valores de `join` las columnas y las `DeviceInfo` `summarize` `OSPlatform` `Severity` columnas:

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
Estos resultados se visualizan mejor con un gráfico de columnas apiladas:

![Imagen de resultados de consulta de búsqueda avanzada que se muestran como un gráfico apilado Resultados de consulta para alertas por sistema operativo y gravedad mostradas ](../../media/advanced-hunting-stacked-chart.jpg)
 *como un gráfico apilado*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>Mensajes de correo electrónico de suplantación de identidad (phishing) en los diez principales dominios de remitente
Si está trabajando con una lista de valores que no es finita, puede usar el operador para crear un gráfico solo de los valores con `Top` la mayoría de las instancias. Por ejemplo, para obtener los diez dominios de remitente con más correos electrónicos de suplantación de identidad( phishing), use la siguiente consulta:

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
Use la vista de gráfico circular para mostrar de forma eficaz la distribución entre los dominios principales:

![Imagen de los resultados de la consulta de búsqueda avanzada que se muestra como gráfico circular con una distribución de correos electrónicos de suplantación de identidad ](../../media/advanced-hunting-pie-chart.jpg)
 *entre los principales dominios de remitentes*

#### <a name="file-activities-over-time"></a>Actividades de archivos a lo largo del tiempo
Si usas el operador con la función, puedes comprobar si hay eventos `summarize` relacionados con un indicador determinado a lo largo del `bin()` tiempo. La consulta siguiente cuenta los eventos relacionados con el archivo en intervalos de 30 minutos para mostrar picos de `invoice.doc` actividad relacionados con ese archivo:

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
El siguiente gráfico de líneas resalta claramente los períodos de tiempo con más actividad que `invoice.doc` implica: 

![Imagen de los resultados de la consulta de búsqueda avanzada que se muestra como un gráfico de líneas del gráfico de líneas que muestra el número de eventos relacionados ](../../media/advanced-hunting-line-chart.jpg)
 *con un archivo a lo largo del tiempo*


## <a name="export-tables-and-charts"></a>Exportar tablas y gráficos
Después de ejecutar una consulta, **seleccione Exportar** para guardar los resultados en un archivo local. La vista elegida determina cómo se exportan los resultados:

- **Vista de tabla:** los resultados de la consulta se exportan en formato tabular como un libro de Microsoft Excel
- **Cualquier gráfico:** los resultados de la consulta se exportan como una imagen JPEG del gráfico representado

## <a name="drill-down-from-query-results"></a>Explorar en profundidad los resultados de la consulta
Para inspeccionar rápidamente un registro en los resultados de la consulta, seleccione la fila correspondiente para abrir el panel **Inspeccionar registro.** El panel proporciona la siguiente información en función del registro seleccionado:

- **Activos:** vista resumida de los activos principales (buzones, dispositivos y usuarios) que se encuentran en el registro, enriquecida con la información disponible, como los niveles de riesgo y exposición.
- **Árbol de procesos:** generado para registros con información de procesos y enriquecido mediante información contextual disponible; En general, las consultas que devuelven más columnas pueden dar como resultado árboles de proceso más enriquecidos.
- **Todos los** detalles: todos los valores de las columnas del registro  

![Imagen del registro seleccionado con panel para inspeccionar el registro](../../media/mtp-ah/inspect-record.png)

Para ver más información sobre una entidad específica en los resultados de la consulta, como una máquina, un archivo, un usuario, una dirección IP o una dirección URL, seleccione el identificador de entidad para abrir una página de perfil detallada para esa entidad.

## <a name="tweak-your-queries-from-the-results"></a>Modificar las consultas de los resultados
Haga clic con el botón derecho en un valor en el conjunto de resultados para mejorar la búsqueda rápidamente. Puede usar las opciones para:

- Buscar explícitamente el valor seleccionado (`==`)
- Excluir el valor seleccionado de la consulta (`!=`)
- Obtenga más operadores avanzados para agregar el valor a la consulta, como `contains`, `starts with` y `ends with` 

![Imagen del conjunto de resultados de búsqueda avanzada](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>Filtrar los resultados de la consulta
Los filtros que aparecen a la derecha proporcionan un resumen del conjunto de resultados. Cada columna tiene una sección en la que se muestra una lista de los valores de la columna y el número de instancias.

Para refinar la consulta, seleccione los botones o los valores que desee incluir o excluir y, a `+` `-` continuación, seleccione Ejecutar **consulta.**

![Imagen del filtro de búsqueda avanzada](../../media/advanced-hunting-filter.png)

Cuando aplica el filtro para modificar la consulta y, a continuación, ejecuta la consulta, los resultados se actualizan en consecuencia.

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Introducción a las detecciones personalizadas](custom-detections-overview.md)
