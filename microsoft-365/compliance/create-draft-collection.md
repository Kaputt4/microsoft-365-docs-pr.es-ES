---
title: Crear una colección de borradores
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
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Una colección borrador es una búsqueda de exhibición de documentos electrónicos de orígenes de datos con custodia y no custodia en un caso de exhibición de documentos electrónicos avanzada que devuelve una estimación de búsqueda que coincide con la consulta de búsqueda de la colección. Puede revisar las estadísticas de búsqueda, obtener una vista previa de un muestreo de elementos y revisar y volver a ejecutar la colección antes de confirmar los resultados en un conjunto de revisión.
ms.openlocfilehash: 18f018a5e00f355c3f320a963135e76ecc51f086
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838953"
---
# <a name="create-a-draft-collection-in-advanced-ediscovery"></a>Crear una colección borrador en eDiscovery avanzada

Después de identificar a los custodios y a los orígenes de datos que no son custodios para el caso, estará listo para identificar y localizar un conjunto de documentos relevantes. Para ello, use la herramienta Colecciones para buscar en los orígenes de datos contenido relevante. Para ello, cree una colección que busque en orígenes de datos especificados contenido que coincida con los criterios de búsqueda. Tiene la opción de crear una *colección* borrador , que es una estimación de los elementos que se encuentran o puede crear una colección que agrega automáticamente los elementos a un conjunto de revisión. Al crear una colección borrador, puede ver información sobre los resultados estimados que coinciden con la consulta de búsqueda, como el número total y el tamaño de los elementos encontrados, los distintos orígenes de datos donde se encontraron y las estadísticas sobre la consulta de búsqueda. También puede obtener una vista previa de un ejemplo de los elementos devueltos por la colección. Con estas estadísticas, puede cambiar la consulta de búsqueda y volver a ejecutar la colección de borradores para restringir los resultados. Una vez que esté satisfecho con los resultados de la colección, puede confirmar la colección en un conjunto de revisión. Al confirmar un borrador de colección, los elementos devueltos por la colección se agregan a un conjunto de revisión para su revisión, análisis y exportación.

## <a name="before-you-create-a-draft-collection"></a>Antes de crear una colección borrador

- Agregue custodios y orígenes de datos no custodiados al caso antes de crear una colección borrador. Esto es necesario para que pueda seleccionar los orígenes de datos al crear una colección de borradores. Para obtener más información, vea:

  - [Agregar administradores a un caso](add-custodians-to-case.md)

  - [Agregar orígenes de datos que no son de Private a un caso](non-custodial-data-sources.md)

- Puede buscar orígenes de datos adicionales (los que no se han agregado al caso como ubicaciones de custodia o no custodia) en un borrador de colección para obtener contenido que pueda ser relevante para el caso. Estos orígenes de datos pueden incluir buzones, sitios de SharePoint y Teams. Si esta situación es aplicable a su caso, compile una lista de estos orígenes de datos para que pueda agregarlos a la colección.

## <a name="create-a-draft-collection"></a>Crear una colección de borradores

1. En el Centro de cumplimiento de Microsoft 365, abra el caso eDiscovery avanzado y, a continuación, seleccione la **pestaña Colecciones.**

2. En la **página Colecciones,** seleccione **Nueva colección** Colección  >  **estándar**.

3. Escriba un nombre (obligatorio) y una descripción (opcional) para la colección. Después de crear la colección, no puede cambiar el nombre, pero puede modificar la descripción.

4. En la **página Orígenes de** datos custodiales, realice una de las siguientes acciones para identificar los orígenes de datos de custodia de los que se recopilará contenido:

   - Haga **clic en Seleccionar custodios** para buscar custodios específicos que se agregaron al caso. Si usa esta opción, se muestra una lista de los custodios de casos. Seleccione uno o más custodios. Después de seleccionar y agregar los custodios, también puede seleccionar los orígenes de datos específicos para buscar cada custodio. Estos orígenes de datos que se muestran se especificaron cuando se agregó el custodio al caso.

   - Haga clic en **el botón** de alternancia Seleccionar todo para buscar en todos los custodios que se agregaron al caso. Al seleccionar esta opción, se buscan todos los orígenes de datos de todos los custodios.

5. En la **página Orígenes** de datos sin custodia, realice una de las siguientes acciones para identificar los orígenes de datos que no son custodia para recopilar contenido de:

   - Haga **clic en Seleccionar orígenes** de datos no custodiales para seleccionar orígenes de datos no custodiales específicos que se agregaron al caso. Si usa esta opción, se mostrará una lista de orígenes de datos. Seleccione uno o varios de estos orígenes de datos.

   - Haga clic en **el botón** de alternancia Seleccionar todo para seleccionar todos los orígenes de datos que no son custodia que se agregaron al caso.

6. En la **página Orígenes de datos adicionales,** puede seleccionar otros buzones y sitios para buscar como parte de la colección. Estos tipos de orígenes de datos no se agregaron como ubicaciones de datos custodiales o no custodiales en el caso. También tiene dos opciones al buscar orígenes de datos adicionales:

   - Para buscar en todas las ubicaciones de contenido un servicio específico (buzones de Exchange, sitios de SharePoint y OneDrive o carpetas públicas de Exchange), haga clic en la alternancia **Seleccionar** todo correspondiente en la columna **Estado.** Esta opción buscará en todas las ubicaciones de contenido del servicio seleccionado.

   - Para buscar una ubicación de contenido  específica para un  servicio, haga clic en la alternancia Seleccionar todo  correspondiente en la columna Estado y, a continuación, haga clic en **Usuarios,** grupos o equipos (para buzones de Exchange) o Elegir sitios para (sitios de SharePoint y OneDrive) para buscar ubicaciones de contenido específicas.

7. En la **página Condiciones,** puede crear la consulta de búsqueda que se usa para recopilar elementos de los orígenes de datos que ha identificado en las páginas del asistente anteriores. Puede buscar palabras clave, pares property:value o usar una lista de palabras clave. También puede agregar varias condiciones de búsqueda para restringir el ámbito de la colección. Para obtener más información, vea [Crear consultas de búsqueda para colecciones](building-search-queries.md).

8. En la **página Guardar como borrador o agregar** a conjunto de revisión, seleccione **Guardar colección como borrador**.

   > [!NOTE]
   > La otra opción de esta página permite recopilar elementos y agregarlos directamente a un conjunto de revisión. En lugar de crear una colección borrador para la que pueda revisar estadísticas y obtener una vista previa de un ejemplo de los resultados de la colección, esta opción omite ese proceso y agrega automáticamente la colección a un conjunto de revisión. Si selecciona la segunda opción para agregar la colección a un conjunto de revisión, tendrá opciones adicionales que configurar, como recopilar subprocesos de conversación de chat completos en Microsoft Teams y Yammer y recopilar datos adjuntos de la nube (también denominados datos adjuntos modernos). Para obtener más información acerca de esta configuración, vea [Commit a draft collection to a review set](commit-draft-collection.md).

9. En la **página Revisar la colección,** puede revisar y actualizar la configuración de la colección que configuró en las páginas anteriores.

   - **Ficha Resumen:** revise y modifique el nombre y la descripción de la colección, los criterios de búsqueda de colección, las ubicaciones de datos adicionales y el tipo de colección.

   - **Ficha Orígenes:** revisar y modificar los orígenes de datos de custodia y no custodia de la colección.

10. Haga **clic en Enviar** para crear la colección borrador. Se muestra una página que confirma que se creó la colección.

## <a name="what-happens-after-you-create-a-draft-collection"></a>Qué sucede después de crear una colección de borradores

Después de crear una colección borrador, aparece en la página **Colecciones** en el caso y el estado muestra que está en curso. Un trabajo denominado **Preparación de la vista previa de** búsqueda y estimaciones también se crea y se muestra en la página **Trabajos** en el caso.

Durante el proceso de borrador de colección, eDiscovery avanzada realiza una estimación de búsqueda con los criterios de búsqueda y los orígenes de datos especificados en la colección. La exhibición de documentos electrónicos avanzada también prepara un muestreo de elementos que puede obtener una vista previa. Una vez completada la colección, se actualizan las siguientes columnas y valores correspondientes en la **página** Colección:

![Estados de estado de una colección borrador](../media/DraftCollectionStatus.png)

- **Status:** indica el estado y el tipo de colección. Un valor de **Estimated** indica que se ha completado una colección borrador. Este mismo valor también indica que la colección es un borrador de colección y que no se ha agregado a un conjunto de revisión. Un valor **de Committed** en la columna **Estado** indica que la colección se ha agregado a un conjunto de revisión.

- **Estado de** la estimación: indica el estado de los resultados de búsqueda estimados y si las estimaciones y estadísticas de búsqueda están listas para su revisión. Un valor de **Successful** indica que los resultados de la colección borrador están listos para su revisión. Después de enviar por primera vez un borrador de colección, se muestra un valor de **In progress** para indicar que la colección todavía se está ejecutando.

- **Estado de vista** previa: indica el estado de los elementos de ejemplo que puede obtener una vista previa. Un valor de **Successful** indica que los elementos están listos para la vista previa. Después de enviar por primera vez un borrador de colección, se muestra un valor de **In progress** para indicar que la colección todavía se está ejecutando.

## <a name="next-steps-after-a-draft-collection-is-complete"></a>Pasos siguientes después de completar un borrador de colección

Una vez completada correctamente el borrador de la colección, puede realizar varias tareas. Para realizar la mayoría de estas tareas, simplemente vaya a la pestaña **Colecciones** y haga clic en el nombre de la colección borrador para mostrar la página desplegable.

![Página desplegable de una colección de borradores](../media/DraftCollectionFlyoutPage.png)

Esta es una lista de las cosas que puede hacer desde la página desplegable de la colección:

- Seleccione la **pestaña** Resumen para ver información de resumen sobre la colección y los resultados de búsqueda estimados devueltos por la colección. Esto incluye el número total de elementos y el tamaño de los resultados de búsqueda estimados, el número de buzones y sitios que contienen los resultados de búsqueda y las condiciones de búsqueda (si se usan) usadas para el ámbito de la colección.

- Seleccione la **pestaña Orígenes de** datos para ver una lista de custodios y orígenes de datos no custodiados) que se buscaron en la colección. Las ubicaciones de contenido adicionales que se buscaron se enumeran **en Ubicaciones** en la **pestaña** Resumen.

- Seleccione la **pestaña Estadísticas de búsqueda** para ver estadísticas sobre la colección. Esto incluye el número total y el tamaño de los elementos encontrados en cada servicio (por ejemplo, buzones de Exchange o sitios de SharePoint) y un informe de condiciones que muestra estadísticas sobre el número de elementos devueltos por diferentes componentes de la consulta de búsqueda usada por la colección. Para obtener más información, vea [Collection statistics and reports](collection-statistics-reports.md).

- Haga **clic en Revisar ejemplo** (ubicado en la parte inferior de la página desplegable) para obtener una vista previa de una muestra de los elementos devueltos por la colección.

- Confirmar la colección borrador en un conjunto de revisión (haciendo clic en **Acciones**  >  **Editar colección**). Esto significa que se vuelve a ejecutar la colección (con la configuración actual) y se agregan los elementos devueltos por la colección a un conjunto de revisión. Como se explicó anteriormente, también puede configurar opciones adicionales (como subprocesos de conversación y datos adjuntos basados en la nube) al agregar la colección a un conjunto de opiniones. Para obtener más información e instrucciones paso a paso, vea [Commit a draft collection to a review set](commit-draft-collection.md).

## <a name="manage-a-draft-collection"></a>Administrar una colección de borradores

Puede usar las opciones del menú **Acciones** de la página desplegable de una colección de borradores para realizar varias tareas de administración.

![Opciones en el menú Acciones para la colección borrador](../media/DraftCollectionActionsMenu.png)

A continuación se descripciones de las opciones de administración.

- **Editar colección:** cambiar la configuración de la colección borrador. Después de realizar cambios, puede volver a ejecutar la colección y actualizar las estimaciones y estadísticas de búsqueda. Como se ha explicado anteriormente, se usa esta opción para confirmar un borrador de colección en un conjunto de revisión.  

- **Eliminar colección:** eliminar una colección borrador. Tenga en cuenta que una vez que un borrador de colección se confirma en un conjunto de revisión, no se puede eliminar.

- **Actualizar estimaciones:** vuelva a ejecutar la consulta (con los orígenes de datos) especificada en el borrador de colección para actualizar las estimaciones y estadísticas de búsqueda.

- **Exportar como informe:** exporta información sobre la colección borrador a un archivo CSV que puede descargar en el equipo local. El informe de exportación contiene la siguiente información:

  - La identidad de cada ubicación de contenido que contiene elementos que coinciden con la consulta de búsqueda de la colección borrador. Estas ubicaciones suelen ser buzones o sitios.
  
  - El número total de elementos en cada ubicación de contenido.
  
  - Tamaño total (en bytes) de los elementos de cada ubicación de contenido.

  - Servicio (como Exchange o SharePoint) en el que se encuentra la ubicación de contenido.

- **Copiar colección:** cree una nueva colección borrador copiando la configuración de una colección existente. Debe usar un nombre diferente para la nueva colección. También tiene la opción de modificar la configuración antes de enviar la nueva colección. Después de enviarla, se ejecuta la consulta de búsqueda y se generan nuevas estimaciones y estadísticas. Es una buena manera de crear rápidamente una colección de borradores adicional y, a continuación, modificar la configuración seleccionada según sea necesario mientras se conserva la información de la colección original. Esto también le permite comparar fácilmente los resultados de dos colecciones similares.

> [!NOTE]
> Después de que un borrador de colección se haya confirmado en un conjunto de revisión, solo puede copiar la colección y exportar un informe.
