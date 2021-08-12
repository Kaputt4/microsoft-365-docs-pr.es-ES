---
title: Flujo de trabajo de Teams en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Obtenga información sobre cómo conservar, recopilar, revisar y exportar contenido de Microsoft Teams en Advanced eDiscovery.
ms.openlocfilehash: e5e899b3ee6268c0214dbcfe6b53566072fc75ed045e728a0f7845f25354e552
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53841348"
---
# <a name="advanced-ediscovery-workflow-for-content-in-microsoft-teams-using-large-cases-preview"></a>Advanced eDiscovery flujo de trabajo de contenido en Microsoft Teams casos grandes (versión preliminar)

En este artículo se proporciona un conjunto completo de procedimientos, directrices y procedimientos recomendados para usar Advanced eDiscovery conservar, recopilar, revisar y exportar contenido de Microsoft Teams. El objetivo de este artículo es ayudarle a optimizar el flujo de trabajo de exhibición de documentos electrónicos para Teams contenido.

Hay cuatro categorías de contenido Teams que puede recopilar y procesar mediante Advanced eDiscovery:

- **Teams chats 1:1**. Mensajes de chat, publicaciones y datos adjuntos compartidos en una Teams conversación entre dos personas.  Teams chats 1:1 también se denominan *conversaciones*.

- **Teams chats de grupo**. Mensajes de chat, publicaciones y datos adjuntos compartidos en Teams conversación entre tres o más personas. También se *denominan chats de 1:N* o *conversaciones de grupo.*

- **Teams canales**. Mensajes de chat, publicaciones, respuestas y datos adjuntos compartidos en un Teams canal.

- **Canales Teams privados**. Mensajes, respuestas y datos adjuntos compartidos en un canal Teams privado.

## <a name="where-teams-content-is-stored"></a>Dónde Teams se almacena el contenido

Un requisito previo para administrar el contenido Teams en Advanced eDiscovery es comprender el tipo de contenido de Teams que puede recopilar, procesar y revisar en Advanced eDiscovery y dónde se almacena dicho contenido en Microsoft 365. En la tabla siguiente se Teams tipo de contenido y dónde se almacena cada uno.

||Ubicación de mensajes y publicaciones de chat  |Ubicación de archivos y datos adjuntos |
|:---------|:---------|:---------|
|Teams chats 1:1     |Los mensajes en chats 1:1 se almacenan en el Exchange Online de todos los participantes de chat. |Los archivos compartidos en un chat 1:1 se almacenan en la OneDrive para la Empresa de la persona que compartió el archivo. |
|Teams chats de grupo     |Los mensajes de los chats de grupo se almacenan en el Exchange Online de todos los participantes de chat. |Los archivos compartidos en chats de grupo se almacenan en la OneDrive para la Empresa de la persona que compartió el archivo. |
|Canales de Teams     |Todos los mensajes y publicaciones de canal se almacenan en el Exchange Online de correo asociado con el equipo.|Los archivos compartidos en un canal se almacenan en el sitio SharePoint online asociado con el equipo.           |
|Canales Teams privados     |Los mensajes enviados en un canal privado se almacenan Exchange Online buzones de todos los miembros del canal privado.|Los archivos compartidos en un canal privado se almacenan en un sitio SharePoint online asociado con el canal privado.|
||||

## <a name="create-a-case-for-teams-content"></a>Crear un caso para el Teams contenido

El primer paso para administrar Teams contenido en Advanced eDiscovery es crear un caso con el formato de caso grande que está optimizado para administrar Teams contenido. Estas son las ventajas de usar el formato de mayúsculas y minúsculas para Teams contenido:

- Compatibilidad con el subproceso de conversación, en el que los mensajes adicionales de la misma conversación que incluyen elementos dinámicos se recopilan y agregan automáticamente a conjuntos de revisión.

- Teams conversaciones de chat se agregan automáticamente a conjuntos de revisión como un archivo de transcripción HTML. Los datos adjuntos en la nube que se comparten en las conversaciones también se agregan al conjunto de revisión. Esto ayuda a dar contexto a las conversaciones con elementos dinámicos y reducir el número total de elementos producidos por el contenido basado en chat.

- Las colecciones de hasta 1 TB se pueden agregar a conjuntos de revisión, lo que le permite recopilar y cantidades grandes de Teams contenido en un caso.

Para obtener más información acerca del aumento de los límites de casos para casos grandes, vea [Usar casos grandes en Advanced eDiscovery](advanced-ediscovery-large-cases.md).

Para crear un caso grande:

1. Vaya a <https://compliance.microsoft.com> e inicie sesión.

2. En el panel de navegación izquierdo de la Centro de cumplimiento de Microsoft 365, haga clic en **eDiscovery > Advanced**.

3. En la **Advanced eDiscovery,** haga clic en la **pestaña Casos** y, a continuación, haga **clic en Crear un caso**.

   Se **muestra la página desplegable Nuevo** caso de exhibición de documentos electrónicos. La **sección Formato de** caso proporciona la opción de crear un caso grande.

   ![Opción de caso grande en la página Nuevo caso de exhibición de documentos electrónicos](..\media\AeDLargeCases1.png)

4. Después de asignar un nombre al caso, seleccione la **opción Caso grande** y, a continuación, haga clic en **Guardar** para crear el caso grande.

## <a name="add-teams-custodial-data-sources-and-preserve-teams-content"></a>Agregar Teams de datos con custodia y conservar Teams contenido  

El siguiente paso es identificar los usuarios que son los custodios de datos en la investigación y agregarlos y sus ubicaciones de contenido como custodios al caso que creaste en la sección anterior. Al agregar custodios, puede especificar su buzón y OneDrive cuenta como orígenes de datos de custodia. También puede especificar las Teams de contenido como orígenes de datos custodios para colocar rápidamente estas ubicaciones en retención legal para conservar el contenido durante la investigación. También facilita la recopilación de contenido y agregarlo a un conjunto de revisión.

Para agregar custodios a un caso y conservar orígenes de datos de custodia:

1. Vaya al Advanced eDiscovery que creó en la sección anterior y, a continuación, haga clic en **Orígenes de datos**.

2. En la **página Orígenes de datos,** haga clic **en Agregar origen de datos** Agregar  >  **nuevos custodios**.

3. En el **Asistente** para nuevo custodio, agregue uno o varios usuarios como custodios al caso escribiendo la primera parte del nombre o alias del usuario. Después de encontrar a la persona correcta, seleccione su nombre para agregarlo a la lista.  

4. Expanda cada custodio para ver los orígenes de datos principales que se han asociado automáticamente al custodio y para seleccionar otras ubicaciones para asociar al custodio.

   ![Orígenes de datos custodios](..\media\TeamsCustodialDataLocations1.png)

5. Siga estas directrices para agregar orígenes de datos de custodia Teams contenido. Haga **clic en** Editar para agregar una ubicación de datos.

   - **Buzones**. El buzón del custodio está seleccionado de forma predeterminada. Mantenga esta opción seleccionada para agregar (y conservar) chats 1:1, chats de grupo y chats de canal privado como datos de custodia.

   - **OneDrives**. La cuenta del administrador OneDrive está seleccionada de forma predeterminada. Mantenga esta opción seleccionada para agregar (y conservar) archivos compartidos en chats 1:1 y chats de grupo como datos de custodia.

   - **SharePoint**. Agregue el sitio SharePoint asociado con cualquier canal privado del que sea miembro el custodio para agregar (y conservar) como datos de custodia los archivos compartidos en el canal privado. Haga **clic en** Editar y, a continuación, agregue la dirección URL del sitio SharePoint asociado a un canal privado. Para obtener información sobre cómo localizar los canales privados de los que es miembro un usuario, vea [eDiscovery of private channels](/microsoftteams/ediscovery-investigation#ediscovery-of-private-channels).

   - **Microsoft Teams**. Agregue los equipos de los que el custodio es miembro para agregar (y conservar) como datos de custodia todos los mensajes de canal y todos los archivos compartidos a un canal Teams cliente. Al hacer clic **en Editar,** el buzón y el sitio asociados con cada equipo del que es miembro el custodio se muestran en una lista. Seleccione los equipos que desea asociar al custodio. Debe seleccionar el buzón y el sitio correspondientes para cada equipo.

   > [!NOTE]
   > También puede agregar el buzón y el sitio de Teams de los que los custodios no son miembros como una ubicación de datos de custodia. Para ello, haga clic en **Editar** junto **a Exchange** y **SharePoint** y, a continuación, agregue el buzón y la asociación de sitio con el equipo.

6. Después de agregar custodios y configurar los orígenes de datos de custodia, haga **clic** en Siguiente para mostrar la página **Configuración de** retención.

   Se muestra una lista de los custodios y la casilla de la columna Retención está seleccionada de forma predeterminada.  Esto indicaba que se colocará una retención en los orígenes de datos asociados con cada custodio. Deje estas casillas activadas para conservar estos datos.

7. En la **página Configuración de retención,** haga clic **en Siguiente** para revisar la configuración de los custodios. Haga **clic en** Enviar para agregar los custodios al caso.

Para obtener más información sobre cómo agregar y conservar orígenes de datos en Advanced eDiscovery caso, vea:

- [Agregar custodios a un Advanced eDiscovery caso](add-custodians-to-case.md)

- [Agregar orígenes de datos sin custodia a un Advanced eDiscovery caso](non-custodial-data-sources.md)

## <a name="collect-teams-content-and-add-to-review-set"></a>Recopilar Teams contenido y agregar al conjunto de revisión

Después de agregar custodios al caso y conservar el contenido en orígenes de datos de custodia, el siguiente paso del flujo de trabajo es buscar contenido que sea relevante Teams para la investigación y agregarlo a un conjunto de revisión para su revisión y análisis. Aunque es típico recopilar contenido de Teams junto con el contenido de otros servicios de Microsoft 365, como el correo electrónico en Exchange y los documentos de SharePoint, esta sección se centrará específicamente en recopilar contenido Teams en una colección. Puede crear colecciones adicionales que recopilan contenido que no Teams agregar a un conjunto de revisión.

Cuando recopila contenido Teams para un caso, hay dos pasos en el flujo de trabajo:

1. **Crear una colección borrador**.  El primer paso es crear una colección *borrador*, que es una estimación de los elementos que coinciden con los criterios de búsqueda. Puede ver información sobre los resultados que coinciden con la consulta de búsqueda, como el número total y el tamaño de los elementos encontrados, los distintos orígenes de datos donde se encontraron y las estadísticas sobre la consulta de búsqueda. También puede obtener una vista previa de un ejemplo de los elementos devueltos por la colección. Con estas estadísticas, puede cambiar la consulta de búsqueda y volver a ejecutar la colección borrador tantas veces como sea necesario para restringir los resultados hasta que esté satisfecho de que está recopilando el contenido relevante para su caso.

2. **Confirmar un borrador de colección en un conjunto de revisión**. Una vez que esté satisfecho con los resultados de una colección borrador, puede confirmar la colección en un conjunto de revisión. Al confirmar un borrador de colección, los elementos devueltos por la colección se agregan a un conjunto de revisión para su revisión, análisis y exportación.

También tiene la opción de no ejecutar una colección borrador y agregar los resultados de la colección directamente a un conjunto de revisión al crear y ejecutar la colección.

Para crear una colección de Teams contenido:

1. Vaya al Advanced eDiscovery caso al que agregó los custodios en la sección anterior y, a continuación, haga clic **en Colecciones**.

2. En la **página Colecciones,** seleccione **Nueva colección** Colección  >  **estándar**.

3. Escriba un nombre (obligatorio) y una descripción (opcional) para la colección.

4. En la **página Orígenes de** datos de custodia, haga clic en Seleccionar **custodios** para seleccionar los custodios que agregó al caso.

   La lista de los custodios de casos se muestra en la página desplegable Seleccionar **custodios.**

5. Seleccione uno o más custodios y, a continuación, haga clic **en Agregar**.

   Después de agregar custodios específicos a la colección, se muestra una lista de orígenes de datos específicos para cada custodio. Estos son los orígenes de datos que configuró al agregar el custodio al caso. Todos los orígenes de datos de custodia están seleccionados de forma predeterminada. Esto incluye cualquier Teams y canales privados que asoció con un custodio.

   Se recomienda hacer lo siguiente al recopilar Teams contenido:

   - Quite las cuentas de OneDrive del ámbito de la colección (anulando la selección de la casilla en la columna de OneDrive del custodio para cada custodio).  Esto evita la colección de archivos duplicados que se adjuntaban a chats de 1:1 y chats de grupo. Los datos adjuntos en la nube se recopilan automáticamente de cada conversación que se encuentra en la colección cuando se confirma el borrador de colección en el conjunto de revisión. Mediante este método (en lugar de buscar cuentas OneDrive como parte de la colección), los archivos adjuntos a 1:1 y los chats de grupo se agrupan en la conversación en la que se compartieron.

   - Anule la selección de la casilla en la **columna** Sitio adicional para quitar los SharePoint que contienen archivos compartidos en canales privados. Al hacerlo, se eliminan los archivos duplicados que se adjuntaban a conversaciones de canal privado porque los datos adjuntos en la nube adjuntos a conversaciones de canal privado se agregan automáticamente al conjunto de revisión cuando se confirma el borrador de colección y se agrupan en las conversaciones que se han compartido.

6. Si ha seguido anteriormente los pasos para agregar contenido Teams como orígenes de datos custodios, puede omitir este paso y seleccionar **Siguiente**. De lo  contrario, en la página Asistente para orígenes de datos sin custodia, puede elegir orígenes de datos no custodiales que contengan un contenido Teams que haya agregado al caso para buscar en la colección.

7. Si ha seguido anteriormente los pasos para agregar contenido Teams como orígenes de datos custodios, puede omitir este paso y seleccionar **Siguiente**. De lo contrario, en **la página Asistente para ubicaciones** adicionales, puede agregar otros orígenes de datos para buscar en la colección. Por ejemplo, puede agregar el buzón y el sitio para un equipo que no se agregó como origen de datos de custodia o no custodia. De lo contrario, **seleccione Siguiente** y omita este paso.

8. En la **página Asistente** para condiciones, configure la consulta de búsqueda para recopilar Teams contenido de los orígenes de datos que especificó en las páginas del asistente anteriores. Puede usar varias palabras clave y condiciones de búsqueda para restringir el ámbito de la colección. Para obtener más información, vea [Crear consultas de búsqueda para colecciones](building-search-queries.md).

   Para ayudar a garantizar la colección más completa de conversaciones de chat de Teams (incluidos  1:1, grupos, canales y chats privados) use la condición Tipo y seleccione la opción **Mensajes instantáneos.** También se recomienda incluir un intervalo de fechas o varias palabras clave para restringir el ámbito de la colección a los elementos relevantes para la investigación. Esta es una captura de pantalla de una consulta de ejemplo con las **opciones Tipo** **y** Fecha:

   ![Consulta para recopilar Teams contenido](..\media\TeamsConditionsQueryType.png)

9. En la **página Guardar** borrador o asistente para recopilar, realice una de las siguientes acciones en función de si desea crear una colección de borradores o confirmar la colección en un conjunto de revisión.

   ![Guardar colección borrador o confirmar colección](..\media\TeamsDraftCommitCollection.png)

   1. **Guardar colección como borrador**. Elija esta opción para crear una colección borrador. Como se explicó anteriormente, un borrador de colección no agrega los resultados de la colección a un conjunto de revisión. Devuelve una estimación de los resultados de búsqueda que coinciden con la consulta de búsqueda de los orígenes de datos en el ámbito de la colección. Esto le ofrece la oportunidad de ver [estadísticas e informes de colecciones[(collection-statistics-reports.md)] y editar y volver a ejecutar la colección borrador. Cuando esté satisfecho con el resultado de una colección borrador, puede confirmarlo en un conjunto de revisión. Para obtener más información, vea [Create a draft collection](create-draft-collection.md).

   2. **Recopilar elementos y agregarlos a un conjunto de revisión**. Elija esta opción para ejecutar la colección y, a continuación, agregue los resultados a un conjunto de revisión. Puede agregar la colección a un conjunto de revisión nuevo o existente. Las opciones para recopilar mensajes de Teams contextuales (también denominados subprocesos de *conversación)* y recopilar datos adjuntos en la nube se seleccionan de forma predeterminada y no se pueden no seleccionar. Estas opciones se aplican automáticamente debido al formato de mayúsculas y minúsculas que usó al crear inicialmente el nuevo caso para Teams contenido. Para obtener más información acerca de cómo confirmar colecciones en un conjunto de revisión, vea [Commit a draft collection to a review set](commit-draft-collection.md).

10. Cuando haya terminado de configurar la colección, envíe la colección para crear un borrador de colección o recopilar elementos y agregarlos a un conjunto de revisión.

   Cuando se completa el proceso de adición de la colección al conjunto de revisión, el valor de estado de la colección en la ficha **Colecciones** se establece en **Confirmado**.

## <a name="review-teams-content-in-a-review-set"></a>Revisar Teams contenido de un conjunto de revisión

Después de agregar colecciones de Teams contenido a un conjunto de revisión, el siguiente paso es revisar el contenido por su relevancia para la investigación y, si es necesario, agregarlo. Un requisito previo importante para revisar Teams contenido es comprender cómo Advanced eDiscovery procesos Teams conversaciones de chat y datos adjuntos al agregarlos a un conjunto de revisión. Este procesamiento de Teams de contenido da como resultado los siguientes tres aspectos:

- **[Agrupación](#grouping)**. Cómo se agrupan los mensajes, las publicaciones y las Teams las conversaciones se agrupan y se presentan en el conjunto de revisión. Esto también incluye datos adjuntos en las conversaciones de chat que se extraen y agrupan dentro de la conversación.

- **[Subprocesos de conversación de transcripción](#transcript-conversation-threading)**. Cómo Advanced eDiscovery determina qué contenido adicional de una conversación se recopila para proporcionar contexto alrededor de los elementos que coinciden con los criterios de la colección.

- **[Desduplicación](#deduplication-of-teams-content)**. Cómo Advanced eDiscovery controla el contenido Teams duplicado.

- **[Metadatos](#metadata-for-teams-content)**. Las propiedades de metadatos que Advanced eDiscovery a Teams contenido después de recopilarlo y agregarlo a un conjunto de revisión.

Comprender la agrupación, el subproceso de conversación, la desduplicación y Teams metadatos le ayudarán a optimizar la revisión y el análisis del Teams contenido. En esta sección también se incluyen sugerencias [para ver Teams contenido de un conjunto de revisión.](#tips-for-viewing-teams-content-in-a-review-set)

### <a name="grouping"></a>Agrupación

Cuando el contenido de Teams conversaciones de chat se agrega a un conjunto de revisión, los mensajes, las publicaciones y las respuestas de las conversaciones se agregan en archivos de transcripción HTML. Una sola conversación de chat puede tener varios archivos de transcripción. Una función importante de estos archivos de transcripción es presentar Teams contenido como conversaciones continuas y no como mensajes individuales (o independientes). Esto ayuda a proporciona contexto para los elementos que coinciden con los criterios de búsqueda de las colecciones en el paso anterior y reduce el número de elementos recopilados en el conjunto de revisión. Las transcripciones y los elementos asociados se pueden agrupar por *familia o* *conversación.* Los elementos de la misma familia tendrán el mismo valor para la propiedad de **metadatos FamilyId.** Los elementos de la misma conversación tendrán el mismo valor para la propiedad de metadatos **ConversationId.**

En la tabla siguiente se describe cómo los diferentes tipos de contenido Teams de chat se agrupan por familia y conversación.

| Teams de contenido|Grupo por familia  |Agrupar por conversación  |
|:---------|:---------|:---------|
|Teams 1:1 y chats en grupo   | Una transcripción y todos sus datos adjuntos y elementos extraídos comparten el mismo **FamilyId**. Cada transcripción tiene un **FamilyId único.** |Todos los archivos de transcripción y sus elementos de familia dentro de la misma conversación comparten el mismo **ConversationId**. Esto incluye los siguientes elementos:<br/><br/>  - Todos los elementos extraídos y los datos adjuntos de todas las transcripciones que comparten el mismo **ConversationId**. <br/> - Todas las transcripciones de la misma conversación de chat<br/> - Todas las copias de custodia de cada transcripción<br/> - Transcripciones de colecciones posteriores de la misma conversación de chat <br/><br/>  Para Teams 1:1 y conversaciones de chat en grupo, es posible que tenga varios archivos de transcripción, cada uno correspondiente a un período de tiempo diferente dentro de la conversación. Dado que estos archivos de transcripción son de la misma conversación con los mismos participantes, comparten el mismo **ConversationId**.|
|Teams chats de canal privado y canal privado    | Cada publicación y todas las respuestas y datos adjuntos se guardan en su propia transcripción. Esta transcripción y todos sus datos adjuntos y elementos extraídos comparten el mismo **FamilyId**.         |Cada publicación y sus datos adjuntos y elementos extraídos tienen un **ConversationId único.** Si hay colecciones posteriores o nuevas respuestas de la misma publicación, las transcripciones delta resultantes de dichas colecciones también tendrán el mismo **ConversationId**.|
||||

Use el control **Grupo** en la barra de comandos de un conjunto de revisión para ver Teams contenido agrupado por familia o conversación.

![Control de grupo en la barra de comandos](..\media\TeamsGroupControl.png)

- Seleccione **Datos adjuntos de familia** de grupo para ver Teams contenido agrupado por familia. Cada archivo de transcripción se muestra en una línea de la lista de elementos del conjunto de revisión. Los datos adjuntos se anidan en el elemento.

- Selecciona **Agrupar Teams o Yammer conversaciones para** ver Teams contenido agrupado por conversación. Cada conversación se muestra en una línea de la lista de elementos del conjunto de revisión. Los archivos de transcripción y los datos adjuntos se anidan en la conversación de nivel superior.

> [!NOTE]
> Los datos adjuntos en la nube se agrupan con las conversaciones en las que aparecen. Esta agrupación se realiza asignando el mismo **FamilyId** que el archivo de transcripción del mensaje al que se adjunta el archivo y el mismo **ConversationId** que la conversación en la que apareció el mensaje. Esto significa que se pueden agregar varias copias de datos adjuntos en la nube al conjunto de revisión si se adjuntaban a conversaciones diferentes.

#### <a name="viewing-transcript-files-for-conversations"></a>Visualización de archivos de transcripción para conversaciones

Al ver archivos de transcripción en un conjunto de revisión, algunos de los mensajes se resaltan en color púrpura. Los mensajes resaltados dependen de la copia de custodia de la transcripción que esté viendo. Por ejemplo, en un chat 1:1 entre User4 y User2, los mensajes publicados por User4 se resaltan en color púrpura al ver la transcripción recopilada desde el buzón de Usuario4. Al ver la transcripción de User2 de la misma conversación, los mensajes publicados por User2 se resaltan en color púrpura. Este comportamiento de resaltado se basa en la misma experiencia Teams cliente, donde las publicaciones de un usuario se resaltan en color púrpura en el Teams cliente.

Las capturas de pantalla siguientes muestran un ejemplo de conversación en el Teams cliente y el archivo de transcripción de la misma conversación en el conjunto de revisión. El resaltado púrpura en el archivo de transcripción indica que la transcripción se recopiló del buzón del usuario2.

##### <a name="conversation-in-teams-client"></a>Conversación en Teams cliente

![Conversación que se muestra en el archivo de transcripción del conjunto de revisión](..\media\TeamsClient1.png)

##### <a name="conversation-in-transcript-file"></a>Conversación en archivo de transcripción

![Misma conversación que se muestra en Teams cliente](..\media\TeamsTranscript1.png)

### <a name="transcript-conversation-threading"></a>Subprocesos de conversación de transcripción

La funcionalidad de subprocesos de conversación en formato de caso grande en Advanced eDiscovery ayuda a identificar contenido contextual relacionado con elementos que pueden ser relevantes para la investigación. Esta característica produce vistas de conversación distintas que incluyen mensajes de chat que preceden y siguen los elementos que coinciden con la consulta de búsqueda durante la colección. Esta funcionalidad le permite revisar de forma eficaz y rápida conversaciones de chat completas (llamadas conversaciones enhebradas) en Microsoft Teams. Como se explicó anteriormente, las conversaciones de chat se reconstruyen en archivos de transcripción HTML cuando Advanced eDiscovery agrega Teams contenido a un conjunto de revisión.

Esta es la lógica usada por Advanced eDiscovery para incluir mensajes adicionales y archivos de transcripción de respuestas que proporcionan contexto alrededor de los elementos que coinciden con la consulta de colección (denominada elementos dinámicos) que usó al recopilar Teams contenido. Los distintos comportamientos de subprocesos se basan en los tipos de chats y la consulta de búsqueda usada para recopilar los elementos dinámicos. Hay dos escenarios de colección comunes:

- Consultas que usan parámetros de búsqueda, como palabras clave y pares property:value

- Consultas que solo usan intervalos de fechas

| Teams de contenido|Consultas con parámetros de búsqueda  |Consultas con intervalos de fechas  |
|:---------|:---------|:---------|
|Teams 1:1 y chats en grupo   |Los mensajes que se publicaron 12 horas antes y 12 horas después de que los elementos con capacidad de respuesta se agrupan con el elemento dinámico en un único archivo de transcripción.   |Los mensajes de una ventana de 24 horas se agrupan en un único archivo de transcripción.|
|Teams chats de canal privado y canal privado    |Cada publicación que contiene elementos dinámicos y todas las respuestas correspondientes se agrupan en un único archivo de transcripción. |Cada publicación que contiene elementos dinámicos y todas las respuestas correspondientes se agrupan en un único archivo de transcripción.|
||||

### <a name="deduplication-of-teams-content"></a>Desduplicación de Teams contenido

En la siguiente lista se describe el comportamiento de desduplicación (y duplicación) al recopilar Teams contenido en un conjunto de opiniones.

- Cada archivo de transcripción agregado a un conjunto de revisión debe ser una asignación uno a uno al contenido almacenado en ubicaciones de datos. Esto significa Advanced eDiscovery no recopila ningún Teams contenido que ya se haya agregado al conjunto de revisión. Si un mensaje de chat ya se recopila en un conjunto de revisión, Advanced eDiscovery no agrega el mismo mensaje desde la misma ubicación de datos al conjunto de revisión en colecciones posteriores.

- Para chats de grupo y 1:1, las copias de mensajes se almacenan en el buzón de cada participante de la conversación. Las copias de la misma conversación que existen en los buzones de diferentes participantes se recopilan con metadatos diferentes. Como resultado, cada instancia de la conversación se trata como única y se lleva al conjunto de revisión en archivos de transcripción independientes. Por lo tanto, si todos los participantes de un chat de grupo o 1:1 se agregan como custodios en un caso y se incluyen en el ámbito de una colección, las copias de cada transcripción (para la misma conservación) se agregan al conjunto de opiniones y se agrupan junto con el mismo **ConversationId**. Cada una de estas copias está asociada con un custodio correspondiente. **Sugerencia:** La **columna Custodian** de la lista de conjunto de revisión identifica al custodio para el archivo de transcripción correspondiente.

- En colecciones posteriores de elementos de la misma conversación, solo el contenido delta que no se recogía anteriormente se agrega al conjunto de opiniones y se agrupa (compartiendo el mismo **ConversationId)** con las transcripciones recopiladas anteriormente de la misma conversación. Este es un ejemplo de este comportamiento:

   1. La colección A recopila mensajes en una conversación entre User1 y User2 y agrega al conjunto de opiniones.

   2. La colección B recopila mensajes de la misma conversación, pero hay nuevos mensajes entre User1 y User2 desde que se ha ejecutado la colección A.

   3. Solo los nuevos mensajes de la colección B se agregan al conjunto de revisión. Estos mensajes se agregan a un archivo de transcripción independiente, pero la nueva transcripción se agrupa con las transcripciones de la colección A por el mismo **ConversationId**.

   Este comportamiento se aplica a todos los tipos de Teams chats.

### <a name="metadata-for-teams-content"></a>Metadatos para Teams contenido

En conjuntos de revisión grandes con miles o millones de elementos, puede ser difícil restringir el ámbito de la revisión a Teams contenido. Para ayudarte a centrar tu opinión en Teams contenido, hay propiedades de metadatos específicas para Teams contenido. Puede usar estas propiedades para organizar las [](review-set-search.md) columnas de la lista de revisión y configurar filtros y consultas para optimizar la revisión de Teams contenido. Estas propiedades de metadatos también se incluyen al exportar Teams contenido de Advanced eDiscovery, para ayudarle a organizar y ver contenido después de la exportación o en herramientas de exhibición de documentos electrónicos de terceros.

En la tabla siguiente se describen las propiedades de metadatos Teams contenido.

|Metadata (propiedad)  |Description  |
|:---------|:---------|
|ContainsEditedMessage      | Indica si un archivo de transcripción contiene un mensaje editado. Los mensajes editados se identifican al ver el archivo de transcripción.|
|ConversationId|GUID que identifica la conversación a la que está asociado el elemento. Los archivos de transcripción y los datos adjuntos de la misma conversación tienen el mismo valor para esta propiedad.|
|Nombre de conversación     | El nombre de la conversación a la que está asociado el archivo de transcripción o los datos adjuntos. Para Teams 1:1 y los chats de grupo, el valor de esta propiedad es el UPN de todos los participantes de la conversación se concatenan. Por ejemplo, `User3 <User3@contoso.onmicrosoft.com>,User4 <User4@contoso.onmicrosoft.com>,User2 <User2@contoso.onmicrosoft.com>`. Teams chats de canal privado y canal privado usan el siguiente formato para el nombre de conversación: `<Team name>,<Channel name>` .Por ejemplo, `eDiscovery vNext, General`.          |
|ConversationType     | Indica el tipo de chat de equipo. Para Teams 1:1 y chats de grupo, el valor de esta propiedad es `Group` . Para Teams chats de canal privado y canal privado, el valor es `Channel` .|
|Fecha | Marca de tiempo del primer mensaje del archivo de transcripción.|
|FamilyId|GUID que identifica el archivo de transcripción de una conversación de chat. Los datos adjuntos tendrán el mismo valor para esta propiedad que el archivo de transcripción que contiene el mensaje al que se adjunta el archivo.|
|FileClass     |Indica ese tipo de contenido. Los elementos Teams chats tienen el valor `Conversation` . En cambio, Exchange mensajes de correo electrónico tienen el valor `Email` .|          |
|MessageKind     | La propiedad de tipo de mensaje. Teams contenido tiene el valor `microsoftteams , im` . |
|Destinatarios     | Una lista de todos los usuarios que recibieron un mensaje dentro de la conversación de transcripción.|
|TeamsChannelName     | Nombre Teams canal o nombre de canal privado de la transcripción.|
|||

Para obtener descripciones de otras Advanced eDiscovery metadatos, vea [Campos de metadatos de documento en Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).

## <a name="export-teams-content"></a>Exportar Teams contenido

Después de revisar y Teams contenido de un conjunto de revisión, puede exportar los archivos de transcripción que contienen contenido que responda a la investigación. No hay ninguna configuración de exportación específica para Teams contenido. Cada archivo de transcripción se exporta como un archivo de mensaje HTML. Este archivo también contiene etiquetas CDATA ocultas con todos los metadatos de los mensajes de chat individuales. Las propiedades de metadatos analizadas en la sección anterior se incluyen cuando Teams se exporta el contenido.  

Se hace referencia a cada archivo de transcripción en el archivo de carga y se puede encontrar mediante la ruta de acceso relativa en el Export_native_path del archivo de carga. Los archivos de transcripción se encuentran en la carpeta Conversaciones de la carpeta de exportación raíz.

## <a name="tips-for-viewing-teams-content-in-a-review-set"></a>Sugerencias para ver Teams contenido de un conjunto de revisión

Estos son algunos consejos y procedimientos recomendados para ver Teams contenido de un conjunto de revisión.

- Use el control **Personalizar columnas** de la barra de comandos para agregar y organizar columnas para optimizar la revisión de Teams contenido.

  ![Usar la página desplegable Editar columna para agregar, quitar y organizar columnas](..\media\EditReviewSetColumns.png)

   Puede agregar y quitar columnas que sean útiles para Teams contenido. También puede secuenciar el orden de las columnas arrastrándolas y soltándolas en la **página desplegable Editar** columna. También puede ordenar las columnas para agrupar Teams contenido con valores similares para la columna en la que se ordena.

- Las columnas útiles que le ayudarán a revisar Teams contenido incluyen **custodia,** **destinatarios** y **tipo de archivo** o tipo de **mensaje**.

- Use [filtros](review-set-search.md) para Teams propiedades relacionadas con el usuario para mostrar rápidamente Teams contenido. Hay filtros para la mayoría de las propiedades de metadatos descritas en la sección anterior.
