---
title: Estadística e informes de colecciones
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo obtener acceso y usar estadísticas e informes para borradores de colecciones y colecciones que se han confirmado en un conjunto de revisión en Advanced eDiscovery.
ms.openlocfilehash: 5edbd4a3b7212e027c777ed6ce5284f4e9cf595c
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838964"
---
# <a name="collection-statistics-and-reports-in-advanced-ediscovery"></a>Estadísticas e informes de colección en Advanced eDiscovery

Después de crear una colección borrador, puede ver estadísticas de los elementos recuperados, como las ubicaciones de contenido que contienen la mayoría de los elementos que coinciden con los criterios de búsqueda y el número de elementos devueltos por la consulta de búsqueda. También puede obtener una vista previa de un subconjunto de los resultados.

Cuando haya identificado el conjunto de documentos que desea examinar, puede agregar los resultados de búsqueda a un conjunto de revisión para recopilar y procesar.

## <a name="statistics-and-reports-for-draft-collections"></a>Estadísticas e informes para borradores de colecciones

En esta sección se describen las estadísticas disponibles para las colecciones de borradores. Estas estadísticas están disponibles en la **pestaña Estadísticas de búsqueda** de la página desplegable de una colección de borradores.

### <a name="collection-estimates"></a>Estimaciones de colección

En esta sección se muestra un resumen gráfico de los elementos estimados devueltos por la colección. Esto indica el número de elementos que coinciden con los criterios de búsqueda de la colección. Esta información le ofrece una idea sobre el número estimado de elementos devueltos por la colección.

![Estimaciones de colección para una colección borrador](../media/AeDCollectionEstimates.png)

- **Elementos estimados por ubicaciones:** el número total de elementos estimados devueltos por la colección. También se muestra el número específico de elementos ubicados en buzones de correo y ubicados en sitios.

- **Ubicaciones estimadas con aciertos:** el número total de ubicaciones de contenido que contienen elementos devueltos por la colección. También se muestra el número específico de ubicaciones de buzones y sitios.

- **Volumen de datos por ubicación (en MB):** tamaño total de todos los elementos estimados devueltos por la colección. También se muestra el tamaño específico de los elementos de buzón y los elementos del sitio.

### <a name="condition-report"></a>Informe de condiciones

En esta sección se muestran estadísticas sobre la consulta de búsqueda de colección y el número de elementos estimados que coinciden con diferentes partes de la consulta de búsqueda. Puede usar estas estadísticas para analizar el número de elementos que coinciden con cada componente de la consulta de búsqueda. Esto puede ayudarle a refinar los criterios de búsqueda de la colección y, si es necesario, restringir el ámbito de la colección.

- **Tipo de ubicación:** tipo de ubicación de contenido a la que se aplican las estadísticas de consulta. El valor de **Exchange** indica una ubicación de buzón; un valor de **SharePoint** indica una ubicación del sitio.

- **Parte:** la parte de la consulta de búsqueda a la que se aplican las estadísticas. **Primary** indica toda la consulta de búsqueda. **Palabra** clave indica que las estadísticas de la fila son para una palabra clave específica. Si usa una lista de palabras clave cuando para la consulta de búsqueda de la colección, las estadísticas de cada componente de la consulta se incluyen en esta tabla.

- **Condición:** el componente real (palabra clave o condición) de la consulta de búsqueda que se ha ejecutado para la colección borrador que devuelve las estadísticas mostradas en la fila correspondiente.

- **Ubicaciones con** aciertos: el número de ubicaciones de contenido (especificadas por la columna **Tipo** de ubicación) que contienen elementos que coinciden con la consulta principal o de palabra clave enumerada en la **columna Condición.**

- **Elementos:** el número de elementos (desde la ubicación de contenido especificada) que coinciden con la consulta enumerada en la **columna Condición.** Como se explicó anteriormente, si un elemento contiene varias instancias de una palabra clave que se está buscando, solo se cuenta una vez en esta columna.

- **Tamaño (MB):** tamaño total de todos los elementos encontrados (en la ubicación de contenido especificada) que coinciden con la consulta de búsqueda en la **columna Condición.**

### <a name="top-locations"></a>Ubicaciones principales

En esta sección se muestran estadísticas sobre las ubicaciones de contenido específicas con la mayoría de los elementos devueltos por la colección.

- El nombre de la ubicación (la dirección de correo electrónico de los buzones y la dirección URL de los sitios).

- Tipo de ubicación (un buzón o sitio).

- Número estimado de elementos en la ubicación de contenido devuelta por la colección.

- Tamaño total de los elementos estimados en cada ubicación de contenido.

## <a name="statistics-and-reports-for-committed-collections"></a>Estadísticas e informes para colecciones comprometidas

En esta sección se describen las estadísticas disponibles después de confirmar una colección en un conjunto de revisión, incluido el número real de elementos agregados al conjunto de revisión. Estas estadísticas (además de la información del conjunto de carga) proporcionan información histórica sobre el contenido agregado a un caso.

Después de confirmar una colección en un conjunto de revisión, se muestran las siguientes pestañas en la página desplegable de la conexión comprometida. Cada una de estas pestañas contiene diferentes tipos de información sobre la colección.

![Pestañas en la página desplegable de la colección comprometida](../media/CommittedCollectionFlyoutPage.png)

### <a name="collection-contents"></a>Contenido de la colección

Esta sección de **la pestaña** Resumen contiene estadísticas y otra información sobre los elementos que se recopilaron de los orígenes de datos de la colección y se agregaron al conjunto de revisión.

- **Total de elementos extraídos**. El número total de elementos agregados al conjunto de revisión. Este número indica la suma de elementos primarios y elementos secundarios agregados al conjunto de revisión.

  > [!TIP]
  > Mantenga el cursor sobre las barras de elementos primarios o secundarios para mostrar el número total de elementos primarios o secundarios.

- **Elementos primarios**. El número de elementos devueltos por la colección que se usó para recopilar los elementos que se agregaron al conjunto de revisión. Este número corresponde (y es igual a) el número estimado de elementos que se muestra en la sección **Parámetros de colección.** El número de elementos primarios que recopila información que se usó para recopilar los elementos que se agregaron al conjunto de revisión.
 
   Un elemento primario puede contener varios elementos secundarios. Por ejemplo, un mensaje de correo electrónico es un elemento primario si contiene un archivo adjunto o tiene datos adjuntos en la nube. En este caso, el archivo adjunto o el destino de los datos adjuntos en la nube se consideran elementos secundarios. Al confirmar una colección, los elementos primarios y los elementos secundarios correspondientes se agregan al conjunto de revisión como elementos o archivos individuales.

- **Elementos secundarios**. Número de elementos secundarios agregados al conjunto de revisión. Los elementos secundarios son datos adjuntos u otras partes de un elemento primario. Los elementos secundarios incluyen archivos adjuntos, datos adjuntos en la nube, imágenes y firmas de correo electrónico. Cuando se confirma una colección en un conjunto de revisión, los elementos secundarios se extraen, indizan y se agregan al conjunto de revisión como archivos individuales.

- **Elementos únicos**. Número de elementos únicos agregados al conjunto de revisión. Los elementos únicos son exclusivos del conjunto de revisión. Todos los elementos son únicos cuando se agrega la primera colección a un nuevo conjunto de revisión porque no había elementos anteriores en el conjunto de revisión.

- **Elementos duplicados identificados**. Número de elementos de la colección que no se agregaron al conjunto de revisión porque ya existe el mismo elemento en el conjunto de revisión. Las estadísticas sobre elementos duplicados pueden ayudar a explicar las diferencias entre el número de elementos estimados de una colección borrador y el número real de elementos agregados al conjunto de revisión.

### <a name="indexing"></a>Indización

La **sección Indización** de la pestaña **Resumen** de un conjunto de revisión confirmado contiene información de indización sobre los elementos agregados al conjunto de revisión.

**Nuevos elementos indizados**. El número de elementos que se indexó recientemente antes de que se agregaron al conjunto de revisión. Un ejemplo de un elemento recién indizado son elementos secundarios que se extraen de un elemento primario y luego se indizan antes de agregarlos al conjunto de revisión. Además, los elementos que no se encuentran en orígenes de datos  de custodia y ubicaciones de contenido no custodial que aparecen en la pestaña Orígenes de datos en el caso se indizan antes de agregarlos a la revisión. Por ejemplo, los elementos recién indizados incluirían elementos recopilados de ubicaciones adicionales.

**Elementos indizados actualizados**. El número de elementos parcialmente indizados que se indizaron correctamente y se agregaron al conjunto de revisión. Esto indizaría parcialmente los elementos de la pestaña  Ubicaciones de contenido custodial y no custodial Orígenes de datos que se indizaron correctamente cuando la colección se confirmaba en el conjunto de revisión.

**Errores de indización**. El número de elementos parcialmente indizados que no se pudieron indizar antes de que se agregaron al conjunto de revisión. Estos elementos pueden requerir corrección de errores.

### <a name="collection-parameters"></a>Parámetros de colección

En esta sección se muestra la información de la colección que se usó para recopilar los elementos que se agregaron al conjunto de revisión. Esta pestaña muestra información similar a la información de la **pestaña Estadísticas de** búsqueda. En esta sección se proporciona una instantánea rápida de la consulta de búsqueda usada por la colección, las ubicaciones de contenido que se buscaron y los resultados estimados de la colección. Como se explicó anteriormente, el número de elementos estimados en esta sección sería igual al número de elementos primarios que se muestran en la sección **Contenido de la** colección.

### <a name="search-statistics-tab"></a>Pestaña Estadísticas de búsqueda

Las estadísticas mostradas en la **pestaña Estadísticas de** búsqueda son las mismas estadísticas de la última vez que se ejecutaba un borrador de colección. Esto incluye estimaciones de colección, informe de condiciones y ubicaciones principales. Esta información se conserva de la colección borrador para referencia histórica y se puede comparar con la colección real que se ha confirmado en el conjunto de revisión.

## <a name="differences-between-draft-collection-estimates-and-the-actual-committed-collection"></a>Diferencias entre las estimaciones de borrador de colección y la colección comprometida real

Al ejecutar un borrador de colección, se muestra una estimación del número de elementos  (y su  tamaño total) que cumplen los criterios de colección en la pestaña Resumen y en la sección Estimaciones de colección de la pestaña **Estadísticas de** búsqueda. Después de confirmar un borrador de colección en un conjunto de revisión, el número real de elementos (y su tamaño total) agregados al conjunto de revisión suelen ser diferentes de las estimaciones. En la mayoría de los casos, se agregan más elementos al conjunto de revisión de los estimados desde la colección borrador. En la siguiente lista se describen los motivos más comunes de estas diferencias y sugerencias para identificarlas:

- **Elementos secundarios**. Elementos secundarios que se extraen de sus elementos primarios y se agregan como archivos individuales. El número de elementos secundarios puede aumentar significativamente el número de elementos que se agregan realmente al conjunto de revisión. En general, el número de  elementos primarios  identificados en la sección Contenido de la colección de la ficha Resumen de una colección comprometida debe ser igual al número de elementos estimados de la colección borrador.

- **Elementos duplicados**. No se agregarán los elementos de la colección borrador que ya se hayan agregado al conjunto de revisión de una colección anterior. Como se explicó anteriormente, el número de elementos duplicados de la colección se muestra en la sección **Contenido** de la colección de la **ficha** Resumen.

- **Opciones de configuración de colección**. Al confirmar un borrador de colección en un conjunto de revisión, debe tener la opción de incluir subprocesos de conversación, datos adjuntos en la nube y versiones de documentos. Cualquiera de estos elementos que se agregan al conjunto de revisión no se incluye en las estimaciones de la colección borrador. Solo se identifican y recopilan cuando se confirma la colección. Seleccionar estas opciones probablemente aumentará el número de elementos agregados al conjunto de revisión. 

    Por ejemplo, varias versiones de SharePoint documentos no se incluyen en la estimación de la colección borrador. Pero si selecciona la opción para incluir todas las versiones del documento al exportar los resultados de búsqueda, lo que aumentará el número real (y el tamaño total) de los elementos agregados al conjunto de opiniones. 

    Para obtener más información acerca de estas opciones, vea [Commit a draft collection to a review set](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set-in-advanced-ediscovery). 

Estos son otros motivos por los que los resultados estimados de una colección de borrador pueden ser diferentes que los resultados confirmados reales.

- **La forma en que se calculan los resultados de las colecciones de borradores**. Una estimación de los resultados de búsqueda devueltos por una colección borrador es solo esa, una estimación (y no un recuento real) de los elementos que cumplen los criterios de consulta de colección. Para compilar la estimación de elementos de correo electrónico, se solicita una lista de los IDs de mensaje que cumplen los criterios de búsqueda de la base Exchange datos. Pero cuando se confirma la colección en un conjunto de revisión, la colección se vuelve a ejecutar y los mensajes reales se recuperan de la base Exchange datos. Por lo tanto, pueden producirse diferencias debido a la forma en que se determina el número estimado de elementos y el número real de elementos.

- **Cambios que ocurren entre el momento en que se estiman y confirman colecciones de borradores**. Cuando se confirma un borrador de colección en un conjunto de revisión, la búsqueda se vuelve a ejecutar para recopilar los elementos más recientes del índice de búsqueda que cumplen los criterios de búsqueda. Es posible que se crearon, enviaron o eliminaron elementos adicionales que cumplen los criterios de búsqueda en el tiempo entre la última ejecución de la colección borrador y el momento en que la colección borrador se confirma en un conjunto de revisión. También es posible que los elementos que estaban en el índice de búsqueda cuando se calcularon los resultados de la colección de borradores ya no estén ahí porque se purgaron de un origen de datos antes de confirmar la colección. Una forma de mitigar este problema es especificar un intervalo de fechas para una colección. Otra forma es colocar una retención en las ubicaciones de contenido para que los elementos se conserven y no se puedan purgar.

- **Elementos sin indizar**. Si la colección borrador incluía la búsqueda en todos los buzones de Exchange o en todos los sitios de SharePoint, solo se agregarán al conjunto de revisión elementos sin indizar de ubicaciones de contenido que contengan elementos que coincidan con los criterios de la colección. En otras palabras, si no se encuentra ningún resultado en un buzón o sitio, los elementos no indexados de ese buzón o sitio no se agregarán al conjunto de revisión. Sin embargo, los elementos sin indizar de todas las ubicaciones de contenido (incluso aquellos que no contienen elementos que coincidan con la consulta de colección) se incluirán en los resultados estimados de la colección.

    Como alternativa, si el borrador de colección incluía ubicaciones de contenido específicas  (lo que significa que se exportarán los buzones o sitios específicos que se especifican en la página Ubicaciones adicionales del asistente para borrador de colección), los elementos no indexados (que no se excluyen por los criterios de colección) de las ubicaciones de contenido especificadas en la búsqueda. En este caso, el número estimado de elementos sin indexar y el número de elementos sin indexar que se agregan al conjunto de revisión debe ser el mismo.
