---
title: Trabajar con resultados avanzados de consulta de búsqueda en Microsoft 365 Defender
description: Obtener el máximo partido de los resultados de consulta devueltos por la búsqueda avanzada en Microsoft 365 Defender
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, visualización, gráfico, filtros, desglose
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: eccf93b019baa240a46260a28f3f0bc109345dd4
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952601"
---
# <a name="work-with-advanced-hunting-query-results"></a>Trabajar con resultados avanzados de consulta de búsqueda

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Aunque puede crear [](advanced-hunting-overview.md) las consultas de búsqueda avanzadas para devolver información muy precisa, también puede trabajar con los resultados de la consulta para obtener más información e investigar actividades e indicadores específicos. Puede realizar las siguientes acciones en los resultados de la consulta:

- Ver resultados como una tabla o gráfico
- Exportar tablas y gráficos
- Profundizar en la información detallada de la entidad
- Ajustar las consultas directamente desde los resultados o aplicar filtros

## <a name="view-query-results-as-a-table-or-chart"></a>Ver resultados de consulta como tabla o gráfico
De forma predeterminada, la búsqueda avanzada muestra los resultados de la consulta como datos tabulares. También puede mostrar los mismos datos que un gráfico. La búsqueda avanzada admite las siguientes vistas:

| Tipo de vista | Descripción |
| -- | -- |
| **Table** | Muestra los resultados de la consulta en formato tabular |
| **Gráfico de columnas** | Representa una serie de elementos únicos en el eje X como barras verticales cuyas alturas representan valores numéricos de otro campo |
| **Gráfico de columnas apiladas** | Representa una serie de elementos únicos en el eje X como barras verticales apiladas cuyas alturas representan valores numéricos de uno o más campos |
| **Gráfico circular** | Representa los pies seccionales que representan elementos únicos. El tamaño de cada circular representa valores numéricos de otro campo. |
| **Gráfico de donas** | Representa arcos seccionales que representan elementos únicos. La longitud de cada arco representa valores numéricos de otro campo. |
| **Gráfico de líneas** | Traza valores numéricos para una serie de elementos únicos y conecta los valores trazados |
| **Gráfico de dispersión** | Traza valores numéricos para una serie de elementos únicos |
| **Gráfico de áreas** | Traza valores numéricos para una serie de elementos únicos y rellena las secciones debajo de los valores trazados |

### <a name="construct-queries-for-effective-charts"></a>Crear consultas para gráficos efectivos
Al representar gráficos, la búsqueda avanzada identifica automáticamente las columnas de interés y los valores numéricos que se agregan. Para obtener gráficos significativos, construya las consultas para devolver los valores específicos que desea ver visualizados. Estas son algunas consultas de ejemplo y los gráficos resultantes.

#### <a name="alerts-by-severity"></a>Alertas por gravedad
Use el `summarize` operador para obtener un recuento numérico de los valores que desea gráfico. La consulta siguiente usa el `summarize` operador para obtener el número de alertas por gravedad.

```kusto
AlertInfo
| summarize Total = count() by Severity
```
Al representar los resultados, un gráfico de columnas muestra cada valor de gravedad como una columna independiente:

![Imagen de resultados avanzados de consulta de búsqueda que se muestran como un gráfico de columnas Resultados de consulta para alertas por gravedad mostradas ](../../media/advanced-hunting-column-chart.jpg)
 *como gráfico de columnas*

#### <a name="alert-severity-by-operating-system"></a>Gravedad de alerta por sistema operativo
También puede usar el operador para `summarize` preparar los resultados de los valores de gráfico de varios campos. Por ejemplo, es posible que desee comprender cómo se distribuyen las gravedades de alerta entre sistemas operativos (SO). 

La consulta siguiente usa un operador para extraer información del sistema operativo de la tabla y, a continuación, usa para contar los valores `join` `DeviceInfo` de las columnas `summarize` `OSPlatform` `Severity` y:

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
Estos resultados se visualizan mejor con un gráfico de columnas apiladas:

![Imagen de resultados avanzados de consulta de búsqueda que se muestran como un gráfico apilado Resultados de consulta para alertas por sistema operativo y gravedad mostradas ](../../media/advanced-hunting-stacked-chart.jpg)
 *como un gráfico apilado*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>Correos electrónicos de suplantación de identidad (phishing) en los diez dominios de remitente principales
Si está trabajando con una lista de valores que no es finita, puede usar el operador para mostrar solo los valores con más `Top` instancias. Por ejemplo, para obtener los diez dominios de remitente con más correos electrónicos de suplantación de identidad, use la consulta siguiente:

```kusto
EmailEvents
| where ThreatTypes has "Phish" 
| summarize Count = count() by SenderFromDomain 
| top 10 by Count
```
Use la vista gráfico circular para mostrar de forma eficaz la distribución en los dominios superiores:

![Imagen de resultados avanzados de consulta de búsqueda que se muestran como gráfico circular gráfico circular que muestra la distribución de correos electrónicos de suplantación de identidad ](../../media/advanced-hunting-pie-chart.jpg)
 *(phishing) en los dominios principales del remitente*

#### <a name="file-activities-over-time"></a>Actividades de archivo con el tiempo
Con el operador con la función, puede comprobar si hay eventos que impliquen un indicador determinado a lo `summarize` largo del `bin()` tiempo. La consulta siguiente cuenta los eventos que implican el archivo en intervalos de 30 minutos para mostrar picos de `invoice.doc` actividad relacionados con ese archivo:

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
El siguiente gráfico de líneas resalta claramente los períodos de tiempo con más actividad que implica `invoice.doc` : 

![Imagen de resultados avanzados de consulta de búsqueda que se muestran como un gráfico de líneas Gráfico de líneas que muestra el número de eventos ](../../media/advanced-hunting-line-chart.jpg)
 *que implican un archivo a lo largo del tiempo*


## <a name="export-tables-and-charts"></a>Exportar tablas y gráficos
Después de ejecutar una consulta, **seleccione Exportar** para guardar los resultados en un archivo local. La vista elegida determina cómo se exportan los resultados:

- **Vista tabla:** los resultados de la consulta se exportan en forma tabular como un libro de Microsoft Excel
- **Cualquier gráfico:** los resultados de la consulta se exportan como una imagen JPEG del gráfico representado

## <a name="drill-down-from-query-results"></a>Profundizar en los resultados de la consulta
Para inspeccionar rápidamente un registro en los resultados de la consulta, seleccione la fila correspondiente para abrir el panel **Inspeccionar registro.** El panel proporciona la siguiente información basada en el registro seleccionado:

- **Activos:** vista resumida de los principales activos (buzones, dispositivos y usuarios) que se encuentran en el registro, enriquecidos con información disponible, como los niveles de riesgo y exposición
- **Árbol de procesos:** generado para registros con información del proceso y enriquecido mediante información contextual disponible; en general, las consultas que devuelven más columnas pueden dar como resultado árboles de proceso más enriquecidos.
- **Todos los detalles:** todos los valores de las columnas del registro  

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

Para refinar la consulta, seleccione los botones o de los valores que desea incluir o excluir y, a `+` `-` continuación, seleccione Ejecutar **consulta**.

![Imagen del filtro de búsqueda avanzada](../../media/advanced-hunting-filter.png)

Cuando aplica el filtro para modificar la consulta y, a continuación, ejecuta la consulta, los resultados se actualizan en consecuencia.

>[!NOTE]
>Es posible que algunas tablas de este artículo no estén disponibles en Microsoft Defender para endpoint. [Activa Microsoft 365 Defender para](m365d-enable.md) buscar amenazas con más orígenes de datos. Puede mover los flujos de trabajo de búsqueda avanzados de Microsoft Defender para endpoint a Microsoft 365 Defender siguiendo los pasos descritos en Migrar consultas avanzadas de búsqueda desde [Microsoft Defender para endpoint](advanced-hunting-migrate-from-mde.md).

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Introducción a las detecciones personalizadas](custom-detections-overview.md)
