---
title: Ver estadísticas de resultados de búsqueda de exhibición de documentos electrónicos
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.search: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo usar la característica de estadísticas de búsqueda para mostrar estadísticas de búsquedas de contenido y búsquedas asociadas con un caso de exhibición de documentos electrónicos principales en el centro de Microsoft 365 cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e543c89b91560520a4e4bf31feb8471c91da4a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311153"
---
# <a name="view-statistics-for-ediscovery-search-results"></a>Ver estadísticas de resultados de búsqueda de exhibición de documentos electrónicos

Después de crear y ejecutar una búsqueda de contenido o una búsqueda asociada con un caso de exhibición de documentos electrónicos principal, puede ver estadísticas sobre los resultados de búsqueda estimados. Esto incluye un resumen de los resultados de búsqueda (similar al resumen de los resultados de búsqueda estimados que se muestran en la página desplegable de búsqueda), las estadísticas de consulta, como el número de ubicaciones de contenido con elementos que coinciden con la consulta de búsqueda y la identidad de las ubicaciones de contenido que tienen los elementos más correspondientes.
  
Además, puede usar la lista de palabras clave para configurar una búsqueda para devolver estadísticas para cada palabra clave de una consulta de búsqueda. Esto le permite comparar el número de resultados devueltos por cada palabra clave de una consulta.
  
También puede descargar estadísticas de búsqueda en un archivo CSV. Así, una vez que abra el archivo con Excel podrá usar las opciones de filtrado y ordenación del programa para comparar los resultados, o preparar informes de los resultados de búsqueda.
  
## <a name="get-statistics-for-searches"></a>Obtener estadísticas para búsquedas

Para mostrar estadísticas de una búsqueda de contenido o una búsqueda asociada a un caso de exhibición de documentos electrónicos principal.:
  
1. En el centro Microsoft 365 cumplimiento, haga clic **en Mostrar todo** y, a continuación, realice una de las siguientes acciones:

   - Haga **clic en Búsqueda de** contenido y, a continuación, seleccione una búsqueda para mostrar la página desplegable.

     O

   - Haga **clic en eDiscovery** Core , seleccione un caso y, a continuación, seleccione una búsqueda en la pestaña  >  Búsquedas para mostrar la página desplegable. 

2. En la página desplegable de la búsqueda seleccionada, haga clic en la **pestaña Estadísticas de** búsqueda.
  
   ![Ficha Estadísticas de búsqueda](../media/SearchStatistics1.png)

La **pestaña Estadísticas de** búsqueda contiene las siguientes secciones que contienen diferentes tipos de estadísticas sobre la búsqueda.

### <a name="search-content"></a>Contenido de búsqueda

En esta sección se muestra un resumen gráfico de los elementos estimados devueltos por la búsqueda. Esto indica el número de elementos que coinciden con los criterios de búsqueda. Esta información le ofrece una idea sobre el número estimado de elementos devueltos por la búsqueda.

![Estimaciones de búsqueda para una búsqueda](../media/SearchContentReport.png)

- **Elementos estimados por ubicaciones:** el número total de elementos estimados devueltos por la búsqueda. También se muestra el número específico de elementos ubicados en buzones de correo y ubicados en sitios.

- **Ubicaciones estimadas con aciertos:** el número total de ubicaciones de contenido que contienen elementos devueltos por la búsqueda. También se muestra el número específico de ubicaciones de buzones y sitios.

- **Volumen de datos por ubicación (en MB):** tamaño total de todos los elementos estimados devueltos por la búsqueda. También se muestra el tamaño específico de los elementos de buzón y los elementos del sitio.

### <a name="condition-report"></a>Informe de condiciones

En esta sección se muestran estadísticas sobre la consulta de búsqueda y el número de elementos estimados que coinciden con distintas partes de la consulta de búsqueda. Puede usar estas estadísticas para analizar el número de elementos que coinciden con cada componente de la consulta de búsqueda. Esto puede ayudarle a refinar los criterios de búsqueda y, si es necesario, restringir el ámbito del ámbito. También puede descargar una copia de este informe en formato CSV.

![Informe de condiciones](../media/SearchContentReportNoKeywordList.png)

- **Tipo de ubicación:** tipo de ubicación de contenido a la que se aplican las estadísticas de consulta. El valor de **Exchange** indica una ubicación de buzón; un valor de **SharePoint** indica una ubicación del sitio.

- **Parte:** la parte de la consulta de búsqueda a la que se aplican las estadísticas. **Primary** indica toda la consulta de búsqueda. **Palabra** clave indica que las estadísticas de la fila son para una palabra clave específica. Si usa una lista de palabras clave para la consulta de búsqueda, las estadísticas de cada componente de la consulta se incluyen en esta tabla. Para obtener más información, vea [Get keyword statistics for searches](#get-keyword-statistics-for-searches).

- **Condición:** el componente real (palabra clave o condición) de la consulta de búsqueda que devuelve las estadísticas mostradas en la fila correspondiente.

- **Ubicaciones con** aciertos: el número de ubicaciones de contenido (especificadas por la columna **Tipo** de ubicación) que contienen elementos que coinciden con la consulta principal o de palabra clave enumerada en la **columna Condición.**

- **Elementos:** el número de elementos (desde la ubicación de contenido especificada) que coinciden con la consulta enumerada en la **columna Condición.** Como se explicó anteriormente, si un elemento contiene varias instancias de una palabra clave que se está buscando, solo se cuenta una vez en esta columna.

- **Tamaño (MB):** tamaño total de todos los elementos encontrados (en la ubicación de contenido especificada) que coinciden con la consulta de búsqueda en la **columna Condición.**

### <a name="top-locations"></a>Ubicaciones principales

En esta sección se muestran estadísticas sobre las ubicaciones de contenido específicas con la mayoría de los elementos devueltos por la búsqueda. Se mostrarán las 1000 ubicaciones más importantes. También puede descargar una copia de este informe en formato CSV.

- El nombre de la ubicación (la dirección de correo electrónico de los buzones y la dirección URL de los sitios).

- Tipo de ubicación (un buzón o sitio).

- Número estimado de elementos en la ubicación de contenido devuelta por la búsqueda.

- Tamaño total de los elementos estimados en cada ubicación de contenido.

## <a name="get-keyword-statistics-for-searches"></a>Obtener estadísticas de palabras clave para búsquedas

Como se explicó anteriormente, la sección **Informe de condiciones** muestra la consulta de búsqueda y el número (y tamaño) de los elementos que coinciden con la consulta. Si usa una lista de palabras clave al crear o editar una consulta de búsqueda, puede obtener estadísticas mejoradas que muestran cuántos elementos coinciden con cada palabra clave o frase de palabra clave. Esto puede ayudarle a identificar rápidamente qué partes de la consulta son las más (y menos) eficaces. Por ejemplo, si una palabra clave devuelve un gran número de elementos, puede optar por refinar la consulta de palabras clave para restringir los resultados de la búsqueda.

Para crear una lista de palabras clave y ver estadísticas de palabras clave para una búsqueda:
  
1. En el Microsoft 365 de cumplimiento, cree una nueva búsqueda de contenido o una búsqueda asociada con un caso de exhibición de documentos electrónicos principal.

2. En la **página Condiciones** del asistente para búsqueda. active la casilla **Mostrar lista de palabras clave.**

   ![Casilla mostrar lista de palabras clave](../media/SearchKeywordsList1.png)

3. Escriba una palabra clave o fase de palabra clave en una fila de la tabla de palabras clave. Por ejemplo, escriba **presupuesto en** la primera fila, escriba **seguridad** en la segunda fila y escriba **FY2021** en la tercera fila.

   ![Escriba hasta 20 palabras clave o frases de palabras clave en la lista](../media/SearchKeywordsList2.png)

   > [!NOTE]
   > Para ayudar a reducir los problemas causados por listas de palabras clave grandes, está limitado a un máximo de 20 filas en la lista de palabras clave de una consulta de búsqueda.

4. Después de agregar las palabras clave a la lista en la que desea buscar y obtener estadísticas, ejecute la búsqueda.

5. Cuando se complete la búsqueda, selecciónelo para mostrar la página desplegable.

6. En la **pestaña Estadísticas de búsqueda,** haga clic en el **informe Condición** para mostrar las estadísticas de palabras clave de la búsqueda.

    ![Se muestran las estadísticas de cada palabra clave](../media/SearchKeywordsList3.png)
  
    Como se muestra en la captura de pantalla anterior, se muestran las estadísticas de cada palabra clave; esto incluye:

    - Estadísticas de palabras clave para cada tipo de ubicación de contenido incluida en la búsqueda.

    - Número de elementos de buzón sin indizar.

    - La consulta de búsqueda real y los resultados de cada palabra clave (identificada como **Palabra** clave en la **columna Parte),** que incluye cualquier condición de la consulta de búsqueda.

    - La consulta de búsqueda completa (identificada como **Principal** en la **columna Parte)** y las estadísticas de la consulta completa para cada tipo de ubicación. Tenga en cuenta que estas son las mismas estadísticas que se muestran en la **pestaña** Resumen.
