---
title: Crear una colección de borrador
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Una colección de borradores es una búsqueda de exhibición de documentos electrónicos de orígenes de datos custodiales y no custodiales en un caso de eDiscovery (Premium) que devuelve una estimación de búsqueda que coincide con la consulta de búsqueda de la colección. Puede revisar las estadísticas de búsqueda, obtener una vista previa de un muestreo de elementos y revisar y volver a ejecutar la colección antes de confirmar los resultados en un conjunto de revisión.
ms.openlocfilehash: 248e95f928c818dfb4eb5b864c2d34304893281c
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64934893"
---
# <a name="create-a-draft-collection-in-ediscovery-premium"></a>Crear una colección de borradores en eDiscovery (Premium)

Después de identificar a los custodios y los orígenes de datos que no son custodios para el caso, está listo para identificar y localizar un conjunto de documentos que son pertinentes. Para ello, use la herramienta Colecciones para buscar contenido relevante en los orígenes de datos. Para ello, cree una colección que busque contenido en los orígenes de datos especificados que coincida con los criterios de búsqueda. Tiene la opción de crear una *colección de borradores*, que es una estimación de los elementos que se encuentran o puede crear una colección que agregue automáticamente los elementos a un conjunto de revisión. Al crear una colección de borradores, puede ver información sobre los resultados estimados que coincidían con la consulta de búsqueda, como el número total y el tamaño de los elementos encontrados, los distintos orígenes de datos donde se encontraron y las estadísticas sobre la consulta de búsqueda. También puede obtener una vista previa de un ejemplo de elementos devueltos por la colección. Con estas estadísticas, puede cambiar la consulta de búsqueda y volver a ejecutar la colección de borradores para restringir los resultados. Una vez que esté satisfecho con los resultados de la colección, puede confirmar la colección en un conjunto de revisión. Al confirmar una colección de borradores, los elementos devueltos por la colección se agregan a un conjunto de revisión para su revisión, análisis y exportación.

## <a name="before-you-create-a-draft-collection"></a>Antes de crear una colección de borradores

- Agregue custodios y orígenes de datos que no sean de custodia al caso antes de crear una colección de borradores. Esto es necesario para que pueda seleccionar los orígenes de datos al crear una colección de borradores. Para más información, vea:

  - [Agregar administradores a un caso](add-custodians-to-case.md)

  - [Agregar orígenes de datos que no son de Private a un caso](non-custodial-data-sources.md)

- Puede buscar orígenes de datos adicionales (los que no se han agregado al caso como ubicaciones de custodia o de no custodia) en un borrador de colección para ver el contenido que puede ser relevante para el caso. Estos orígenes de datos pueden incluir buzones de correo, sitios de SharePoint y Teams. Si esta situación es aplicable a su caso, compile una lista de estos orígenes de datos para poder agregarlos a la colección.

## <a name="create-a-draft-collection"></a>Crear una colección de borrador

1. En el portal de cumplimiento de Microsoft Purview, abra el caso de exhibición de documentos electrónicos (Premium) y, a continuación, seleccione la pestaña **Colecciones**.

2. En la página **Colecciones**, seleccione **Nueva** **colecciónStandard** > .

3. Escriba un nombre (obligatorio) y una descripción (opcional) para la colección. Una vez creada la colección, no puede cambiar el nombre, pero puede modificar la descripción.

4. En la página **Orígenes de datos custodiales** , realice una de las siguientes acciones para identificar los orígenes de datos custodiales de los que se va a recopilar contenido:

   - Haga clic en **Seleccionar custodios** para buscar en los custodios específicos que se agregaron al caso. Si usa esta opción, se muestra una lista de los custodios del caso. Seleccione uno o varios custodios. Después de seleccionar y agregar los custodios, también puede seleccionar los orígenes de datos específicos para buscar a cada custodio. Estos orígenes de datos que se muestran se especificaron cuando el custodio se agregó al caso.

   - Haga clic en el botón de alternancia **Seleccionar todo** para buscar en todos los custodios que se agregaron al caso. Al seleccionar esta opción, se buscan todos los orígenes de datos de todos los custodios.

5. En la página **Orígenes de datos sin custodia** , realice una de las siguientes acciones para identificar los orígenes de datos que no son de custodia de los que se va a recopilar contenido:

   - Haga clic en **Seleccionar orígenes de datos que no son de custodia** para seleccionar orígenes de datos específicos que no sean de custodia que se agregaron al caso. Si usa esta opción, se muestra una lista de orígenes de datos. Seleccione uno o varios de estos orígenes de datos.

   - Haga clic en el botón de alternancia **Seleccionar todo** para seleccionar todos los orígenes de datos que no sean de custodia que se agregaron al caso.

6. En la página **Orígenes de datos adicionales** , puede seleccionar otros buzones y sitios para buscar como parte de la colección. Estos tipos de orígenes de datos no se agregaron como ubicaciones de datos de custodia o no custodia en el caso. También tiene dos opciones al buscar orígenes de datos adicionales:

   - Para buscar en todas las ubicaciones de contenido un servicio específico (Exchange buzones, SharePoint y OneDrive sitios o Exchange carpetas públicas), haga clic en el botón de alternancia **Seleccionar todo** correspondiente en la columna **Estado**. Esta opción buscará en todas las ubicaciones de contenido del servicio seleccionado.

   - Para buscar una ubicación de contenido específica para un servicio, haga clic en el botón de alternancia **Seleccionar todo** correspondiente en la columna **Estado** y, a continuación, haga clic en **Usuarios, grupos o equipos** (para Exchange buzones) o **Elija sitios** para (SharePoint y OneDrive sitios) para buscar ubicaciones de contenido específicas.

7. En la página **Condiciones** , puede crear la consulta de búsqueda que se usa para recopilar elementos de los orígenes de datos que ha identificado en las páginas anteriores del asistente. Puede buscar palabras clave, pares property:value o usar una lista de palabras clave. También puede agregar varias condiciones de búsqueda para restringir el ámbito de la colección. Para obtener más información, consulte [Compilación de consultas de búsqueda para colecciones](building-search-queries.md).

8. En la página **Guardar como borrador o agregar para revisar conjunto** , seleccione **Guardar colección como borrador**.

   > [!NOTE]
   > La otra opción de esta página le permite recopilar elementos y agregarlos directamente a un conjunto de revisión. En lugar de crear una colección de borradores para la que pueda revisar las estadísticas y obtener una vista previa de un ejemplo de los resultados de la colección, esta opción omite ese proceso y agrega automáticamente la colección a un conjunto de revisión. Si selecciona la segunda opción para agregar la colección a un conjunto de revisión, tiene opciones adicionales que configurar, como recopilar subprocesos de conversación de chat completos en Microsoft Teams y Yammer y recopilar datos adjuntos en la nube (también *denominados datos adjuntos modernos*). Para obtener más información sobre esta configuración, consulte [Confirmación de una colección de borradores en un conjunto de revisión](commit-draft-collection.md).

9. En la página **Revisar la colección** , puede revisar y actualizar la configuración de recopilación que configuró en las páginas anteriores.

   - **Pestaña Resumen** : revise y modifique el nombre y la descripción de la colección, los criterios de búsqueda de recopilación, las ubicaciones de datos adicionales y el tipo de colección.

   - **Pestaña Orígenes** : revise y modifique los orígenes de datos custodios y no custodios de la colección.

10. Haga clic en **Enviar** para crear la colección de borradores. Se muestra una página que confirma que se creó la colección.

## <a name="what-happens-after-you-create-a-draft-collection"></a>¿Qué ocurre después de crear una colección de borradores?

Después de crear una colección de borradores, aparece en la página **Colecciones** en el caso y el estado muestra que está en curso. También se crea y muestra un trabajo denominado **Preparar la vista previa y las estimaciones de búsqueda** en la página **Trabajos** en el caso.

Durante el proceso de recopilación de borradores, eDiscovery (Premium) realiza una estimación de búsqueda mediante los criterios de búsqueda y los orígenes de datos especificados en la colección. eDiscovery (Premium) también prepara un muestreo de elementos que puede obtener una vista previa. Una vez completada la colección, se actualizan las siguientes columnas y los valores correspondientes de la página **Colección** :

![Estados de estado de una colección de borradores.](../media/DraftCollectionStatus.png)

- **Estado**: indica el estado y el tipo de colección. Un valor de **Estimated** indica que se ha completado una colección de borradores. Este mismo valor también indica que la colección es una colección de borradores y que no se ha agregado a un conjunto de revisión. Un valor de **Confirmado** en la columna **Estado** indica que la colección se ha agregado a un conjunto de revisión.

- **Estado de la estimación**: indica el estado de los resultados de búsqueda estimados y si las estimaciones y estadísticas de búsqueda están listas para su revisión. Un valor de **Correcto** indica que los resultados de la colección de borradores están listos para su revisión. Después de enviar por primera vez una colección de borradores, se muestra un valor de **En curso** para indicar que la colección sigue ejecutándose.

- **Estado de vista previa**: indica el estado de los elementos de ejemplo que puede obtener una vista previa. Un valor de **Correcto** indica que los elementos están listos para la versión preliminar. Después de enviar por primera vez una colección de borradores, se muestra un valor de **En curso** para indicar que la colección sigue ejecutándose.

## <a name="next-steps-after-a-draft-collection-is-complete"></a>Pasos siguientes una vez completada una colección de borradores

Una vez completada correctamente la colección de borradores, puede realizar varias tareas. Para realizar la mayoría de estas tareas, vaya a la pestaña **Colecciones** y haga clic en el nombre de la colección de borradores para mostrar la página de control flotante.

![Página de control flotante de una colección de borradores.](../media/DraftCollectionFlyoutPage.png)

Esta es una lista de cosas que puede hacer desde la página de control flotante de la colección:

- Seleccione la pestaña **Resumen** para ver información de resumen sobre la colección y los resultados de búsqueda estimados devueltos por la colección. Esto incluye el número total de elementos y el tamaño de los resultados de búsqueda estimados, el número de buzones y sitios que contienen los resultados de búsqueda y las condiciones de búsqueda (si se usan) que se usan para el ámbito de la colección.

- Seleccione la pestaña **Orígenes de datos** para ver una lista de custodios y orígenes de datos que no son de custodia) que se buscaron en la colección. Las ubicaciones de contenido adicionales que se buscaron se enumeran en **Ubicaciones** en la pestaña **Resumen** .

- Seleccione la pestaña **Buscar estadísticas** para ver las estadísticas sobre la colección. Esto incluye el número total y el tamaño de los elementos que se encuentran en cada servicio (por ejemplo, Exchange buzones o SharePoint sitios) y un informe de condición que muestra estadísticas sobre el número de elementos devueltos por distintos componentes de la consulta de búsqueda que usa la colección. Para obtener más información, consulte [Estadísticas e informes de recopilación](collection-statistics-reports.md).

- Haga clic en **Revisar ejemplo** (que se encuentra en la parte inferior de la página desplegable) para obtener una vista previa de un ejemplo de los elementos devueltos por la colección.

- Confirme la colección de borradores en un conjunto de revisión (haciendo clic en **AccionesEditar** >  colección). Esto significa que vuelve a ejecutar la colección (con la configuración actual) y agrega los elementos devueltos por la colección a un conjunto de revisión. Como se explicó anteriormente, también puede configurar opciones adicionales (como el subproceso de conversación y los datos adjuntos basados en la nube) al agregar la colección a un conjunto de revisión. Para obtener más información e instrucciones paso a paso, consulte [Confirmación de una colección de borradores en un conjunto de revisión](commit-draft-collection.md).

## <a name="manage-a-draft-collection"></a>Administración de una colección de borradores

Puede usar las opciones del menú **Acciones** de la página flotante de una colección de borradores para realizar varias tareas de administración.

![Opciones en el menú Acciones para la colección de borradores.](../media/DraftCollectionActionsMenu.png)

Estas son descripciones de las opciones de administración.

- **Editar colección**: cambie la configuración de la colección de borradores. Después de realizar cambios, puede volver a ejecutar la colección y actualizar las estimaciones y estadísticas de búsqueda. Como se explicó anteriormente, esta opción se usa para confirmar una colección de borradores en un conjunto de revisión.  

- **Eliminar colección**: elimine una colección de borradores. Tenga en cuenta que una vez confirmada una colección de borradores en un conjunto de revisión, no se puede eliminar.

- **Actualizar estimaciones**: vuelva a ejecutar la consulta (en los orígenes de datos) especificada en la colección de borradores para actualizar las estimaciones y estadísticas de búsqueda.

- **Exportar como informe**: exporta información sobre la colección de borradores a un archivo CSV que puede descargar en el equipo local. El informe de exportación contiene la siguiente información:

  - Identidad de cada ubicación de contenido que contiene elementos que coinciden con la consulta de búsqueda de la colección de borradores. Estas ubicaciones suelen ser buzones o sitios.
  
  - Número total de elementos en cada ubicación de contenido.
  
  - Tamaño total (en bytes) de los elementos de cada ubicación de contenido.

  - El servicio (por ejemplo, Exchange o SharePoint) en el que se encuentra la ubicación del contenido.

- **Copia de la colección**: cree una nueva colección de borradores copiando la configuración de una colección existente. Tiene que usar un nombre diferente para la nueva colección. También tiene la opción de modificar la configuración antes de enviar la nueva colección. Después de enviarla, se ejecuta la consulta de búsqueda y se generan nuevas estimaciones y estadísticas. Es una buena manera de crear rápidamente una colección de borradores adicional y, a continuación, modificar la configuración seleccionada según sea necesario, a la vez que conserva la información de la colección original. Esto también permite comparar fácilmente los resultados de dos colecciones similares.

> [!NOTE]
> Una vez confirmada una colección de borradores en un conjunto de revisión, solo puede copiar la colección y exportar un informe.
