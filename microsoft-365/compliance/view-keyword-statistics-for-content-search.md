---
title: Ver las estadísticas de palabras clave para resultados de búsqueda de contenido
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/30/2017
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 9701a024-c52e-43f0-b545-9a53478aec04
description: Obtenga información sobre cómo usar la característica Estadísticas de búsqueda para mostrar y comparar estadísticas de varias búsquedas de contenido en el Centro de seguridad & cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f12c51c47045996e450772c081bd26ef4a520b5f
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838703"
---
# <a name="view-keyword-statistics-for-content-search-results"></a>Ver las estadísticas de palabras clave para resultados de búsqueda de contenido

Después de crear y ejecutar una búsqueda de contenido, puede ver estadísticas sobre los resultados de búsqueda estimados. Esto incluye un resumen de los resultados de búsqueda (similar al resumen de los resultados de búsqueda estimados que se muestran en el panel de detalles), las estadísticas de consulta, como el número de ubicaciones de contenido con elementos que coinciden con la consulta de búsqueda y el nombre de las ubicaciones de contenido que tienen los elementos más correspondientes. Puede mostrar las estadísticas de una o más búsquedas de contenido. Esto le permite comparar rápidamente los resultados de varias búsquedas y tomar decisiones sobre la eficacia de las consultas de búsqueda.
  
Además, puede configurar búsquedas nuevas y existentes para devolver estadísticas para cada palabra clave de una consulta de búsqueda. Esto le permite comparar el número de resultados de cada palabra clave de una consulta y comparar las estadísticas de palabras clave de varias búsquedas.
  
También puede descargar estadísticas de búsqueda y de palabras clave en un archivo CSV. Así, una vez que abra el archivo con Excel podrá usar las opciones de filtrado y ordenación del programa para comparar los resultados, o preparar informes de los resultados de búsqueda.
  
## <a name="get-statistics-for-content-searches"></a>Obtener estadísticas para búsquedas de contenido

Para mostrar estadísticas de búsquedas de contenido:
  
1. En el Centro de cumplimiento de Microsoft 365, vaya **a Mostrar toda la búsqueda** de  >  **contenido**.

2. En la lista de búsquedas, seleccione dos o más búsquedas y, a continuación, haga clic en **Estadísticas de** búsqueda en la **página** desplegable Acciones masivas.
    
    ![Seleccione varias búsquedas y, a continuación, haga clic en Estadísticas de búsqueda](../media/1195c6c3-2e00-469d-8c29-85c1c7ebe6c7.png)
  
3. En la **página Estadísticas de búsqueda,** haga clic en uno de los vínculos siguientes para mostrar estadísticas sobre las búsquedas seleccionadas. 
    
    **Resumen**
    
    Esta página muestra estadísticas similares a las que se muestran en el panel de detalles de la **página Búsqueda de** contenido. Se muestran las estadísticas de todas las búsquedas seleccionadas. Tenga en cuenta que también puede volver a ejecutar las búsquedas seleccionadas de esta página para actualizar las estadísticas. 
    
    ![Resumen de las estadísticas de las búsquedas seleccionadas](../media/abb663eb-b3d6-4f4c-a99f-55d20b0848af.png)
  
    a.  Nombre de la búsqueda de contenido. Como se ha indicado anteriormente, puede mostrar y comparar estadísticas para varias búsquedas.
    
    b. Tipo de ubicación de contenido que se ha buscado. Cada fila muestra estadísticas de buzones, sitios y carpetas públicas de la búsqueda especificada.
    
    c. Número de ubicaciones de contenido que contienen elementos que coinciden con la consulta de búsqueda. Para los buzones, esta estadística también incluye el número de buzones de archivo que contienen elementos que coinciden con la consulta de búsqueda.
    
    d. El número total de elementos de todas las ubicaciones de contenido especificadas que coinciden con la consulta de búsqueda. Algunos ejemplos de tipos de elementos incluyen mensajes de correo electrónico, elementos de calendario y documentos. Si un elemento contiene varias instancias de una palabra clave que se está buscando, solo se cuenta una vez en el número total de elementos. Por ejemplo, si está buscando palabras "stock" o "fraud" y un mensaje de correo electrónico contiene tres instancias de la palabra "stock", solo se cuenta una vez en la columna **Elementos.** 
    
    e. Tamaño total de todos los elementos encontrados en la ubicación de contenido especificada que coinciden con la consulta de búsqueda. 
    
    **Queries**
    
    Esta página muestra estadísticas sobre la consulta de búsqueda.
    
    ![Estadísticas de consulta de búsqueda para las búsquedas seleccionadas](../media/dc817526-dfb9-43d3-a14c-4c58077eb7bb.png)
  
    a. Nombre de la búsqueda de contenido para la que la fila contiene estadísticas de consulta.
    
    b. Tipo de ubicación de contenido a la que se aplican las estadísticas de consulta.
    
    c. Esta columna indica a qué parte de la consulta de búsqueda se aplican las estadísticas. **Primary** indica toda la consulta de búsqueda. Si usa una lista de palabras clave al crear o editar una consulta de búsqueda, las estadísticas de cada componente de la consulta se incluyen en esta tabla. Vea la [sección Obtener estadísticas de palabras clave para búsquedas de](#get-keyword-statistics-for-content-searches) contenido en este artículo para obtener más información. 
    
    d. Esta columna contiene la consulta de búsqueda real que ejecuta la herramienta de búsqueda de contenido. Tenga en cuenta que la herramienta agrega automáticamente algunos componentes adicionales a la consulta que cree. 

    - Al buscar todo el contenido de los buzones (sin especificar palabras clave), la consulta de palabras clave real es para que se devuelvan  `size>=0` todos los elementos. 
    
     - Al buscar en sitios de SharePoint Online y OneDrive para la Empresa, se agregan los dos componentes siguientes:
    
          **NOT IsExternalContent:1:** excluye cualquier contenido de una organización local de SharePoint. 
    
          **NOT IsOneNotePage:1:** excluye todos los archivos de OneNote porque se trataría de duplicados de cualquier documento que coincida con la consulta de búsqueda. 

    
    e. Número de ubicaciones de contenido (especificadas por la columna ** Tipo de ubicación ** ) que contienen elementos que coinciden con la consulta de búsqueda que aparece en la **columna** Consulta. 
    
    f. Número de elementos (de la ubicación de contenido especificada) que coinciden con la consulta de búsqueda que aparece en la **columna** Consulta. Como se explicó anteriormente, si un elemento contiene varias instancias de una palabra clave que se está buscando, solo se cuenta una vez en esta columna. 
    
    g. Tamaño total de todos los elementos encontrados (en la ubicación de contenido especificada) que coinciden con la consulta de búsqueda de la **columna** Consulta. 
    
    **Ubicaciones principales**
    
    Esta página muestra estadísticas sobre el número de elementos que coinciden con la consulta de búsqueda en cada ubicación de contenido que se ha buscado. Se mostrarán las 1000 ubicaciones más importantes. Si ve estadísticas para varias búsquedas, se muestran las 1.000 ubicaciones principales de cada búsqueda. Tenga en cuenta que una ubicación de contenido no se incluye en esta página si no contiene ningún elemento que coincida con la consulta de búsqueda.
    
    ![Estadísticas sobre el número de elementos encontrados en las ubicaciones de contenido que se buscaron](../media/35a820b0-85d9-45d1-9a0c-c74bec803e67.png)
  
    a. Nombre de la ubicación de contenido.
    
    b. Tipo de ubicación de contenido a la que se aplican las estadísticas de ubicación.
    
    c. Hay columnas para cada búsqueda para la que se muestran las estadísticas. Esta columna muestra el número (y el tamaño total) de los elementos que coinciden con la consulta de búsqueda en cada ubicación de contenido. Tenga en cuenta que cuando se muestran estadísticas para varias búsquedas, la "NA" de esta columna indica que la ubicación de contenido no se incluyó en esa búsqueda. 

## <a name="get-keyword-statistics-for-content-searches"></a>Obtener estadísticas de palabras clave para búsquedas de contenido

Como se explicó anteriormente, la **página Consultas** muestra la consulta de búsqueda y el número (y tamaño) de los elementos que coinciden con la consulta. Si usa una lista de palabras clave al crear o editar una consulta de búsqueda, puede obtener estadísticas mejoradas que muestran cuántos elementos coinciden con cada palabra clave o frase de palabra clave. Esto puede ayudarle a identificar rápidamente qué partes de la consulta son las más (y menos) eficaces. Por ejemplo, si una palabra clave devuelve un gran número de elementos, puede optar por refinar la consulta de palabras clave para restringir los resultados de la búsqueda. Puede configurar una lista de palabras clave al crear o editar una búsqueda de contenido. 

Para crear una lista de palabras clave y ver estadísticas de palabras clave para una búsqueda de contenido:
  
1. En el Centro de cumplimiento de Microsoft 365, vaya **a Mostrar toda la búsqueda** de  >  **contenido**.
    
2. En la lista de búsquedas de contenido, haga clic y una búsqueda y, a continuación, haga clic **en Editar** icono ![ Editar ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .
    
3. Haga **clic en** Consulta y, a continuación, haga lo siguiente: 
    
    ![Haga clic en la casilla Mostrar lista de palabras clave y escriba una palabra clave en cada fila](../media/73ef46dd-3d5c-415d-b5e7-c3559caaafe2.png)
  
    a. Haga clic en **la casilla Mostrar lista** de palabras clave. 
    
    b. Escriba una palabra clave o fase de palabra clave en una fila de la tabla de palabras clave. Por ejemplo, escriba **presupuesto en** la primera fila y, a continuación, escriba **seguridad** en la segunda fila. 
    
4. Después de agregar las palabras clave que desea buscar y obtener estadísticas, haga clic en **Buscar** para ejecutar la búsqueda revisada. 
    
5. Cuando se complete la búsqueda, selecciónelo en la lista de **búsquedas** y, a continuación, haga clic en Estadísticas de búsqueda Botón ![ Estadísticas de búsqueda ](../media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png) . También puede mostrar y comparar estadísticas de palabras clave para varias búsquedas.
    
6. En la **página Estadísticas de búsqueda,** haga clic en **Consulta** para mostrar las estadísticas de palabras clave de las búsquedas seleccionadas. 
    
    ![Se muestran las estadísticas de cada palabra clave de las búsquedas seleccionadas](../media/e7910fa9-af93-4df9-92d0-e1e3e089e14f.png)
  
    Como se muestra en la captura de pantalla anterior, se muestran las estadísticas de cada palabra clave; esto incluye: 
    
    - Estadísticas de palabras clave para cada tipo de ubicación de contenido incluida en la búsqueda.
    
    - La consulta de búsqueda real para cada palabra clave, que incluye cualquier condición de la consulta de búsqueda. 
    
    - La consulta de búsqueda completa (identificada como **Principal** en la **columna Parte)** y las estadísticas de la consulta completa. Tenga en cuenta que estas son las mismas estadísticas que se muestran en la **página Resumen.** 

> [!NOTE]
> Para ayudar a reducir los problemas causados por listas de palabras clave grandes, ahora está limitado a un máximo de 20 filas en la lista de palabras clave de una consulta de búsqueda.
