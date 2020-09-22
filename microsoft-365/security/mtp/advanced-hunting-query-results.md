---
title: Trabajar con los resultados de la consulta de búsqueda avanzada en protección contra amenazas de Microsoft
description: Aprovechar al máximo la mayoría de los resultados de la consulta de búsqueda avanzada en la protección contra amenazas de Microsoft
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, Microsoft 365, protección contra amenazas de Microsoft, visualización, gráfico, filtros, explorar en profundidad
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
ms.openlocfilehash: d9650811a264992c20a1ed88939e06694373b25c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197708"
---
# <a name="work-with-advanced-hunting-query-results"></a>Trabajar con los resultados de la consulta de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Aunque puede crear consultas de [búsqueda avanzada](advanced-hunting-overview.md) para devolver información muy precisa, también puede trabajar con los resultados de la consulta para obtener más información e investigar actividades e indicadores específicos. Puede realizar las siguientes acciones en los resultados de la consulta:

- Ver los resultados como una tabla o un gráfico
- Exportar tablas y gráficos
- Profundizar en la información de la entidad detallada
- Ajustar las consultas directamente desde los resultados o aplicar filtros

## <a name="view-query-results-as-a-table-or-chart"></a>Ver los resultados de la consulta como una tabla o un gráfico
De forma predeterminada, la búsqueda avanzada muestra los resultados de la consulta como datos tabulares. También puede mostrar los mismos datos que un gráfico. La búsqueda avanzada es compatible con las siguientes vistas:

| Tipo de vista | Descripción |
| -- | -- |
| **Table** | Muestra los resultados de la consulta en formato de tabla. |
| **Gráfico de columnas** | Representa una serie de elementos únicos en el eje x como barras verticales cuyos altos representan valores numéricos de otro campo. |
| **Gráfico de columnas apiladas** | Representa una serie de elementos únicos en el eje x como barras verticales apiladas cuyos altos representan valores numéricos de uno o más campos. |
| **Gráfico circular** | Representa los gráficos circulares de sección que representan elementos únicos. El tamaño de cada gráfico circular representa valores numéricos de otro campo. |
| **Gráfico de anillos** | Representa arcos de sección que representan elementos únicos. La longitud de cada arco representa valores numéricos de otro campo. |
| **Gráfico de líneas** | Traza valores numéricos para una serie de elementos únicos y conecta los valores trazados. |
| **Gráfico de dispersión** | Traza valores numéricos para una serie de elementos únicos. |
| **Gráfico de área** | Traza valores numéricos para una serie de elementos únicos y rellena las secciones debajo de los valores representados. |

### <a name="construct-queries-for-effective-charts"></a>Crear consultas para gráficos efectivos
Al representar gráficos, la caza avanzada identifica automáticamente las columnas de interés y los valores numéricos que se van a agregar. Para obtener gráficos significativos, construya las consultas para devolver los valores específicos que desea ver visuales. A continuación se muestran algunas consultas de ejemplo y los gráficos resultantes.

#### <a name="alerts-by-severity"></a>Alertas por gravedad
Use el `summarize` operador para obtener un recuento numérico de los valores que desea representar en el gráfico. La siguiente consulta usa el `summarize` operador para obtener el número de alertas por gravedad.

```kusto
AlertInfo
| summarize Total = count() by Severity
```
Al representar los resultados, un gráfico de columnas muestra cada valor de gravedad como una columna independiente:

![Imagen de los resultados de la consulta de búsqueda avanzada mostrados como un gráfico ](../../media/advanced-hunting-column-chart.jpg)
 *de columnas resultados de consulta de alertas por gravedad mostrados como un gráfico de columnas*

#### <a name="alert-severity-by-operating-system"></a>Gravedad de la alerta por sistema operativo
También puede usar el `summarize` operador para preparar los resultados para representar gráficamente valores de varios campos. Por ejemplo, es posible que quiera comprender cómo se distribuyen las gravedades de las alertas entre sistemas operativos (SO). 

La siguiente consulta usa un `join` operador para extraer información del sistema operativo de la `DeviceInfo` tabla y, a continuación, usa `summarize` para contar los valores en las `OSPlatform` `Severity` columnas y:

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
Estos resultados se pueden visualizar mejor usando un gráfico de columnas apiladas:

![Imagen de los resultados de la consulta de búsqueda avanzada mostrados como ](../../media/advanced-hunting-stacked-chart.jpg)
 *resultado de una consulta de gráfico apilado para alertas por sistema operativo y gravedad mostradas como un gráfico apilado*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>Mensajes de suplantación de identidad en los diez principales dominios del remitente
Si está tratando con una lista de valores que no son finitos, puede usar el `Top` operador para representar solo los valores con la mayoría de las instancias. Por ejemplo, para obtener los diez principales dominios de remitentes con la mayoría de los correos electrónicos de suplantación de identidad, use la siguiente consulta:

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
Use la vista gráfico circular para mostrar de forma eficaz la distribución en los dominios superiores:

![Imagen de los resultados de la consulta de búsqueda avanzada mostrados como un gráfico circular gráfico circular ](../../media/advanced-hunting-pie-chart.jpg)
 *que muestra la distribución de mensajes de suplantación de identidad en los dominios principales del remitente*

#### <a name="file-activities-over-time"></a>Actividades de archivo a lo largo del tiempo
Mediante el `summarize` operador con la `bin()` función, puede comprobar si hay eventos que impliquen un indicador en particular a lo largo del tiempo. La consulta siguiente cuenta los eventos `invoice.doc` relacionados con el archivo en intervalos de 30 minutos para mostrar picos en la actividad relacionada con el archivo:

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
El gráfico de líneas siguiente destaca claramente los períodos de tiempo con más actividad, lo que implica `invoice.doc` : 

![Imagen de los resultados de la consulta de búsqueda avanzada mostrados como un gráfico de líneas del gráfico de líneas ](../../media/advanced-hunting-line-chart.jpg)
 *que muestra el número de eventos que implican un archivo a lo largo del tiempo*


## <a name="export-tables-and-charts"></a>Exportar tablas y gráficos
Después de ejecutar una consulta, seleccione **exportar** para guardar los resultados en un archivo local. La vista elegida determina cómo se exportarán los resultados:

- **Vista de tabla** : los resultados de la consulta se exportan en formato tabular como libro de Microsoft Excel
- **Cualquier gráfico** : los resultados de la consulta se exportan como una imagen JPEG del gráfico representado.

## <a name="drill-down-from-query-results"></a>Profundizar desde los resultados de la consulta
Para inspeccionar rápidamente un registro en los resultados de la consulta, seleccione la fila correspondiente para abrir el panel **inspeccionar registro** . El panel proporciona la siguiente información en función del registro seleccionado:

- **Activos** : Vista resumida de los activos principales (buzones de correo, dispositivos y usuarios) que se encuentran en el registro, enriquecido con información disponible, como los niveles de riesgo y exposición
- **Árbol de procesos** : generado para registros con información del proceso y enriquecido con información contextual disponible; en general, las consultas que devuelven más columnas pueden dar como resultado árboles de procesos más completos.
- **Todos los detalles** : todos los valores de las columnas del registro  

![Imagen del registro seleccionado con panel para inspeccionar el registro](../../media/mtp-ah/inspect-record.png)

Para ver más información acerca de una entidad específica en los resultados de la consulta, como un equipo, un archivo, un usuario, una dirección IP o una dirección URL, seleccione el identificador de entidad para abrir una página de perfil detallada para esa entidad.

## <a name="tweak-your-queries-from-the-results"></a>Modificar las consultas de los resultados
Haga clic con el botón derecho en un valor en el conjunto de resultados para mejorar la búsqueda rápidamente. Puede usar las opciones para:

- Buscar explícitamente el valor seleccionado (`==`)
- Excluir el valor seleccionado de la consulta (`!=`)
- Obtenga más operadores avanzados para agregar el valor a la consulta, como `contains`, `starts with` y `ends with` 

![Imagen del conjunto de resultados de caza avanzado](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>Filtrar los resultados de la consulta
Los filtros que aparecen a la derecha proporcionan un resumen del conjunto de resultados. Cada columna tiene una sección en la que se muestra una lista de los valores de la columna y el número de instancias.

Refine la consulta seleccionando los `+` `-` botones o de los valores que desea incluir o excluir y, a continuación, seleccionando **Ejecutar consulta**.

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
