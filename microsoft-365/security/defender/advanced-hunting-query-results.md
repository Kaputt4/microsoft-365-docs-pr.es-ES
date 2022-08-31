---
title: Trabajar con resultados de consulta de búsqueda avanzada en Microsoft 365 Defender
description: Aprovechar al máximo los resultados de la consulta devueltos por la búsqueda avanzada en Microsoft 365 Defender
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, visualización, gráfico, filtros, exploración en profundidad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 451e45b60bbb8bc9ea552b616ccd230b5cf7caf6
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481710"
---
# <a name="work-with-advanced-hunting-query-results"></a>Trabajar con resultados de consulta de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Aunque puede crear consultas [de búsqueda avanzadas](advanced-hunting-overview.md) para devolver información precisa, también puede trabajar con los resultados de la consulta para obtener más información e investigar actividades e indicadores específicos. Puede realizar las siguientes acciones en los resultados de la consulta:

- Visualización de resultados como tabla o gráfico
- Exportar tablas y gráficos
- Explorar en profundidad la información detallada de la entidad
- Ajustar las consultas directamente desde los resultados

## <a name="view-query-results-as-a-table-or-chart"></a>Visualización de los resultados de la consulta como tabla o gráfico

De forma predeterminada, la búsqueda avanzada muestra los resultados de la consulta como datos tabulares. También puede mostrar los mismos datos que un gráfico. La búsqueda avanzada admite las siguientes vistas:

| Tipo de vista | Descripción |
|--|--|
| **Table** | Muestra los resultados de la consulta en formato tabular |
| **Gráfico de columnas** | Representa una serie de elementos únicos en el eje X como barras verticales cuyos altos representan valores numéricos de otro campo. |
| **Gráfico circular** | Representa los pasteles seccionales que representan elementos únicos. El tamaño de cada gráfico circular representa valores numéricos de otro campo. |
| **Gráfico de líneas** | Traza valores numéricos para una serie de elementos únicos y conecta los valores trazados |
| **Gráfico de dispersión** | Traza valores numéricos para una serie de elementos únicos |
| **Gráfico de áreas** | Traza valores numéricos para una serie de elementos únicos y rellena las secciones debajo de los valores trazados. |
| **Gráfico de áreas apiladas** | Traza valores numéricos para una serie de elementos únicos y apila las secciones rellenas debajo de los valores trazados.  |
| **Gráfico de tiempo** | Traza valores por recuento en una escala de tiempo lineal |

### <a name="construct-queries-for-effective-charts"></a>Construcción de consultas para gráficos efectivos

Al representar gráficos, la búsqueda avanzada identifica automáticamente las columnas de interés y los valores numéricos que se van a agregar. Para obtener gráficos significativos, construya las consultas para devolver los valores específicos que desea ver visualizados. Estas son algunas consultas de ejemplo y los gráficos resultantes.

#### <a name="alerts-by-severity"></a>Alertas por gravedad

Use el `summarize` operador para obtener un recuento numérico de los valores que desea trazar. En la consulta siguiente se usa el `summarize` operador para obtener el número de alertas por gravedad.

```kusto
AlertInfo
| summarize Total = count() by Severity
```

Al representar los resultados, un gráfico de columnas muestra cada valor de gravedad como una columna independiente:

:::image type="content" source="../../media/advanced-hunting-column-chart-new.png" alt-text="Ejemplo de un gráfico que muestra los resultados de búsqueda avanzada en el portal de Microsoft 365 Defender" lightbox="../../media/advanced-hunting-column-chart-new.png":::
*Resultados de consultas de alertas por gravedad mostradas como gráfico de columnas*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>Correos electrónicos de suplantación de identidad en los diez dominios principales del remitente

Si trabaja con una lista de valores que no son finitos, puede usar el `Top` operador para trazar solo los valores con la mayoría de las instancias. Por ejemplo, para obtener los 10 dominios de remitente principales con la mayoría de los correos electrónicos de phishing, use la consulta siguiente:

```kusto
EmailEvents
| where ThreatTypes has "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```

Use la vista de gráfico circular para mostrar de forma eficaz la distribución entre los dominios principales:

:::image type="content" source="../../media/advanced-hunting-pie-chart-new.png" alt-text="Gráfico circular que muestra los resultados de búsqueda avanzada en el portal de Microsoft 365 Defender" lightbox="../../media/advanced-hunting-pie-chart-new.png":::
*Gráfico circular que muestra la distribución de correos electrónicos de suplantación de identidad (phishing) entre los dominios principales del remitente*

#### <a name="file-activities-over-time"></a>Actividades de archivo a lo largo del tiempo
Con el `summarize` operador con la `bin()` función , puede comprobar si hay eventos que impliquen un indicador determinado a lo largo del tiempo. La consulta siguiente cuenta los eventos que implican el archivo `invoice.doc` a intervalos de 30 minutos para mostrar picos de actividad relacionados con ese archivo:

```kusto
CloudAppEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```

El gráfico de líneas siguiente resalta claramente los períodos de tiempo con más actividad relacionada con `invoice.doc`:

:::image type="content" source="../../media/line-chart-a.png" alt-text="Gráfico de líneas que muestra los resultados de búsqueda avanzada en el portal de Microsoft 365 Defender" lightbox="../../media/line-chart-a.png":::
*Gráfico de líneas que muestra el número de eventos que implican un archivo a lo largo del tiempo*

## <a name="export-tables-and-charts"></a>Exportar tablas y gráficos

Después de ejecutar una consulta, seleccione **Exportar** para guardar los resultados en el archivo local. La vista elegida determina cómo se exportan los resultados:

- **Vista de tabla**: los resultados de la consulta se exportan en formato tabular como un libro de Microsoft Excel
- **Cualquier gráfico**: los resultados de la consulta se exportan como una imagen JPEG del gráfico representado.

## <a name="drill-down-from-query-results"></a>Obtención de detalles de los resultados de la consulta

Para inspeccionar rápidamente un registro en los resultados de la consulta, seleccione la fila correspondiente para abrir el panel **Inspeccionar registro** . El panel proporciona la siguiente información en función del registro seleccionado:

- **Activos**: vista resumida de los principales recursos (buzones, dispositivos y usuarios) que se encuentran en el registro, enriquecidos con información disponible, como los niveles de riesgo y exposición.
- **Todos los detalles**: todos los valores de las columnas del registro

:::image type="content" source="../../media/results-inspect-record.png" alt-text="Registro seleccionado con panel para inspeccionar el registro en el portal de Microsoft 365 Defender" lightbox="../../media/results-inspect-record.png":::

Para ver más información sobre una entidad específica en los resultados de la consulta, como una máquina, un archivo, un usuario, una dirección IP o una dirección URL, seleccione el identificador de entidad para abrir una página de perfil detallada para esa entidad.

## <a name="tweak-your-queries-from-the-results"></a>Modificar las consultas de los resultados

Seleccione los tres puntos situados a la derecha de cualquier columna en el panel **Inspeccionar registro** . Puede usar las opciones para:

- Buscar explícitamente el valor seleccionado (`==`)
- Excluir el valor seleccionado de la consulta (`!=`)
- Obtenga operadores más avanzados para agregar el valor a la consulta, como `contains`, `starts with`y . `ends with`

:::image type="content" source="../../media/work-with-query-tweak-query.png" alt-text="El panel Tipo de acción de la página Inspeccionar registro del portal de Microsoft 365 Defender" lightbox="../../media/work-with-query-tweak-query.png":::

> [!NOTE]
> Es posible que algunas tablas de este artículo no estén disponibles en Microsoft Defender para punto de conexión. [Active Microsoft 365 Defender](m365d-enable.md) para buscar amenazas mediante más orígenes de datos. Para mover los flujos de trabajo de búsqueda avanzados de Microsoft Defender para punto de conexión a Microsoft 365 Defender, siga los pasos descritos en [Migración de consultas de búsqueda avanzadas desde Microsoft Defender para punto de conexión](advanced-hunting-migrate-from-mde.md) .

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Introducción a las detecciones personalizadas](custom-detections-overview.md)
