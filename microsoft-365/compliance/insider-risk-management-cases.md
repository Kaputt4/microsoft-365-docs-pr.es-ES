---
title: Casos de administración de riesgos de Insider
description: Obtenga información sobre los casos de administración de riesgos de insider en Microsoft 365
keywords: Microsoft 365, administración de riesgos internos, administración de riesgos, cumplimiento
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 7712ce1ee4c28352861df17c0637a94d99fa2c8a
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226532"
---
# <a name="insider-risk-management-cases"></a>Casos de administración de riesgos de Insider

Los casos son el núcleo de la administración de riesgos de información interna y le permiten investigar profundamente y actuar en los problemas generados por los indicadores de riesgo definidos en sus directivas. Los casos se crean manualmente a partir de alertas en situaciones en las que es necesario realizar más acciones para solucionar un problema relacionado con el cumplimiento de un usuario. Cada caso está en el ámbito de un único usuario y se pueden agregar varias alertas para el usuario a un caso existente o a un nuevo caso. 

Después de investigar los detalles de un caso, puede tomar medidas mediante:

- enviar un aviso al usuario
- resolver el caso como benigno
- compartir el caso con la instancia de ServiceNow o con un destinatario de correo electrónico
- escalando el caso para una Advanced eDiscovery investigación

Consulte el vídeo Investigación y escalación de la administración de riesgos de [Insider](https://www.youtube.com/watch?v=UONUSmkRC8s) para obtener información general sobre cómo se investigan y administran los casos en la administración de riesgos de insider.

## <a name="cases-dashboard"></a>Panel de casos

El panel de casos de administración de riesgos **interno** permite ver y actuar en casos. Cada widget de informe del panel muestra información de los últimos 30 días.

- **Casos activos:** el número total de casos activos en investigación.
- **Casos de los últimos 30 días:** el número total de casos creados, ordenados por *estado Activo* *y* Cerrado.
- **Estadísticas:** tiempo promedio de los casos activos, enumerados en horas, días o meses.

La cola de casos enumera todos los casos activos y cerrados de la organización, además del estado actual de los siguientes atributos de caso:

- **Nombre de** caso: el nombre del caso, definido cuando se confirma una alerta y se crea el caso.  
- **Estado:** el estado del caso, *activo* o *cerrado*.
- **User:** el usuario del caso. Si la anonimización de nombres de usuario está habilitada, se muestra información anonimizada.
- **Caso de tiempo abierto:** el tiempo transcurrido desde que se abrió el caso.
- **Alertas totales de directiva:** número de coincidencias de directiva incluidas en el caso. Este número puede aumentar si se agregan nuevas alertas al caso.
- **Case last updated:** el tiempo transcurrido desde que se ha agregado una nota de caso o un cambio en el estado del caso.
- **Last updated by**: The name of the insider risk management analyst or researcher that last updated the case.

![Panel de casos de administración de riesgos de Insider](../media/insider-risk-cases-dashboard.png)

Use el control **Search** para buscar nombres de casos para texto específico y usar el filtro de casos para ordenar los casos por los atributos siguientes:

- Estado
- Tiempo de caso abierto, fecha de inicio y fecha de finalización
- Última actualización, fecha de inicio y fecha de finalización

## <a name="filter-cases"></a>Casos de filtro

Según el número y el tipo de directivas de administración de riesgos de insider activas de la organización, revisar una gran cola de casos puede ser un desafío. El uso de filtros de casos puede ayudar a los analistas e investigadores a ordenar los casos por varios atributos. Para filtrar alertas en el **panel Casos,** seleccione el control **Filtro.** Puede filtrar los casos por uno o varios atributos:

- **Estado:** seleccione uno o varios valores de estado para filtrar la lista de casos. Las opciones son *Active* y *Closed*.
- **Caso de hora abierto:** seleccione las fechas de inicio y finalización para cuando se abrió el caso.
- **Last updated**: Select the start and end dates for when the case was updated.

## <a name="investigate-a-case"></a>Investigar un caso

Una investigación más profunda sobre las alertas de administración de riesgos de insider es fundamental para tomar las medidas correctivas adecuadas. Los casos de administración de riesgos de Insider son la herramienta de administración central para profundizar en el historial de actividades de riesgo del usuario, los detalles de alerta, la secuencia de eventos de riesgo y para explorar el contenido y los mensajes expuestos a riesgos. Los analistas e investigadores de riesgos también usan casos para centralizar comentarios y notas de revisión y procesar la resolución de casos.

Seleccionar un caso abre las herramientas de administración de casos y permite a analistas y expertos profundizar en los detalles de los casos.

### <a name="case-overview"></a>Información general de casos

La **pestaña Información general** del caso resume los detalles del caso para los analistas e investigadores de riesgos. Incluye la siguiente información en el **área Acerca de este caso**

- **Estado:** el estado actual del caso, activo o cerrado.
- **Caso creado en**: La fecha y hora en que se creó el caso.
- **Puntuación de riesgo del usuario:** el nivel de riesgo calculado actual del usuario para el caso. Esta puntuación se calcula cada 24 horas y usa las puntuaciones de riesgo de alerta de todas las alertas activas asociadas al usuario.
- **Correo** electrónico: el alias de correo electrónico del usuario para el caso.
- **Organización o departamento:** la organización o el departamento al que está asignado el usuario.
- **Nombre del administrador:** el nombre del administrador del usuario.
- **Correo electrónico del** administrador: alias de correo electrónico del administrador del usuario.

La **pestaña Información general** del caso también incluye una sección **Alertas** que incluye la siguiente información acerca de las alertas de coincidencia de directivas asociadas con el caso:

- **Coincidencias de directiva:** el nombre de la directiva de administración de riesgos de insider asociada con las alertas de coincidencia para la actividad del usuario.
- **Estado:** Estado de la alerta.
- **Gravedad:** gravedad de la alerta.
- **Hora detectada:** el tiempo transcurrido desde que se generó la alerta.

![Detalles de casos de administración de riesgos de Insider](../media/insider-risk-case-details.png)

### <a name="alerts"></a>Alertas

La **pestaña** Alertas resume las alertas actuales incluidas en el caso. Se pueden agregar nuevas alertas a un caso existente y se agregarán a la cola de **alertas** a medida que estén asignadas. Los siguientes atributos de alerta se enumeran en la cola:

- Estado
- Gravedad
- Tiempo detectado

Seleccione una alerta de la cola para mostrar la **página Detalles de** alerta.

Use el control de búsqueda para buscar nombres de alerta para texto específico y usar el filtro de alertas para ordenar los casos por los atributos siguientes:

- Estado
- Gravedad
- Hora detectada, fecha de inicio y fecha de finalización

Use el control de filtro para filtrar alertas por varios atributos, incluidos:

- **Estado:** seleccione uno o más valores de estado para filtrar la lista de alertas. Las opciones son *Confirmada*, *Descartada*, *Falta por revisar*, y *Resuelta*.
- **Gravedad:** seleccione uno o más niveles de gravedad de riesgo de alerta para filtrar la lista de alertas. Las opciones son *Alta*, *Media*, y *Baja*.
- **Hora detectada:** seleccione las fechas de inicio y finalización para cuando se creó la alerta.
- **Directiva:** seleccione una o varias directivas para filtrar las alertas generadas por las directivas seleccionadas.

### <a name="user-activity"></a>Actividad de usuario

La pestaña de **Actividade del usuario** es una de las herramientas más eficaces para analizar los riesgos internos e investigar casos en la solución de administración de riesgos internos. Esta pestaña está estructurada para permitir la revisión rápida de un caso, incluida una escala de tiempo histórica de todas las alertas, detalles de alerta, la puntuación de riesgo actual para el usuario en el caso, la secuencia de eventos de riesgo y controles para tomar medidas eficaces para contener los riesgos en el caso.

![Actividad de usuario de administración de riesgos insider](../media/insider-risk-user-activities.png)

1. **Filtros de tiempo:** de forma predeterminada, los últimos seis meses de alertas confirmadas en el caso se muestran en el gráfico de actividad de usuario. Puede filtrar fácilmente la vista de gráfico seleccionando las pestañas *6 Meses,* *3 Meses* o *1* Mes en el gráfico de burbujas.
2. **Actividad y detalles de alerta de** riesgo: las actividades de riesgo se muestran visualmente como burbujas de color en el gráfico de actividades de usuario. Las burbujas se crean para diferentes categorías de riesgo y el tamaño de la burbuja es proporcional al número de actividades de riesgo para la categoría. Seleccione una burbuja para mostrar los detalles de cada actividad de riesgo. Los detalles incluyen:
    - **Fecha** de la actividad de riesgo.
    - La **categoría de actividad de riesgo**. Por ejemplo, *correos electrónicos* con datos adjuntos enviados fuera de la organización o Archivos descargados de SharePoint *Online*.
    - **Nivel de riesgo** de la alerta. Esta puntuación es la puntuación numérica para el nivel de gravedad del riesgo de alerta.
    - Número de eventos asociada a la alerta. También están disponibles vínculos a cada archivo o correo electrónico asociado con la actividad de riesgo.
3. **Secuencia de riesgos (versión preliminar):** el orden cronológico de las actividades de riesgo es un aspecto importante de la investigación de riesgos y la identificación de estas actividades relacionadas es una parte importante de la evaluación del riesgo general para su organización. Las actividades de alerta relacionadas se muestran con líneas de conexión para resaltar que estas actividades están asociadas a un área de riesgo mayor. Esta vista de actividades puede ayudar a los investigadores a "conectar los puntos" literalmente para las actividades de riesgo que podrían haber sido vistas como eventos aislados o aislados. Seleccione cualquier burbuja de la secuencia para mostrar los detalles de todas las actividades de riesgo asociadas. Los detalles incluyen:

    - **Nombre** de la secuencia.
    - **Fecha** o **Intervalo de fechas** de la secuencia.
    - **Puntuación de** riesgo para la secuencia. Esta puntuación es la puntuación numérica de la secuencia de los niveles combinados de gravedad del riesgo de alerta para cada actividad relacionada de la secuencia.
    - **Número de eventos asociados con cada alerta de la secuencia**. También están disponibles vínculos a cada archivo o correo electrónico asociado con cada actividad de riesgo.
    - **Mostrar actividades en secuencia**. Muestra la secuencia como una línea de resaltado en el gráfico de burbujas y expande los detalles de alerta para mostrar todas las alertas relacionadas en la secuencia.

4. **Leyenda de actividad de** riesgo: en la parte inferior del gráfico de actividad del usuario, una leyenda codificada por colores le ayuda a determinar rápidamente la categoría de riesgo para cada alerta.
5. **Cronología de** actividad de riesgo: se muestra la cronología completa de todas las alertas de riesgo asociadas con el caso, incluidos todos los detalles disponibles en la burbuja de alerta correspondiente.
6. **Acciones de caso:** las opciones para resolver el caso se encuentran en la barra de herramientas de acciones de caso. Puede resolver un caso, enviar un aviso de correo electrónico al usuario o escalar el caso para una investigación de datos o usuarios.

### <a name="activity-explorer-preview"></a>Explorador de actividades (versión preliminar)

> [!IMPORTANT]
> La pestaña Explorador de actividades está disponible en el área de administración de casos para los usuarios con eventos desencadenados después de que esta característica esté disponible en la organización.

La **pestaña Explorador de** actividades permite a los analistas de riesgos e investigadores revisar los detalles de actividad asociados con las alertas de riesgo. Por ejemplo, como parte de las acciones de administración de casos, es posible que los investigadores y analistas deba revisar todas las actividades de riesgo asociadas con el caso para obtener más detalles. Con el **explorador de actividades,** los revisores pueden revisar rápidamente una escala de tiempo de actividad de riesgo detectada e identificar y filtrar todas las actividades de riesgo asociadas con las alertas.

Para obtener más información sobre el explorador de actividades, consulte el artículo Alertas de administración de [riesgos de Insider.](insider-risk-management-alerts.md#activity-explorer-preview)

### <a name="content-explorer"></a>Explorador de contenido

La pestaña de **Explorador de contenido** permite a los analistas de riesgos y a los expertos revisar copias de todos los archivos y mensajes de correo electrónico individuales asociados con alertas de riesgo. Por ejemplo, si se crea una alerta cuando un usuario descarga cientos de archivos de SharePoint Online y la actividad desencadena una alerta de directiva, todos los archivos descargados de la alerta se capturan y copian en el caso de administración de riesgos de insider desde orígenes de almacenamiento originales.

El explorador de contenido es una herramienta eficaz con características básicas y avanzadas de búsqueda y filtrado. Para obtener más información sobre cómo usar el explorador de contenido, vea [Insider risk management Content explorer](insider-risk-management-content-explorer.md).

![Explorador de contenido de casos de administración de riesgos de Insider](../media/insider-risk-content-explorer.png)

### <a name="case-notes"></a>Notas de casos

La **pestaña Notas del** caso en el caso es donde los analistas de riesgos e investigadores comparten comentarios, comentarios e información sobre su trabajo para el caso. Las notas son adiciones permanentes a un caso y no se pueden modificar ni eliminar después de guardar la nota. Cuando se crea un caso a partir de una alerta, los comentarios escritos en el cuadro de diálogo **Confirmar alerta y crear casos de riesgo internas** se agregan automáticamente como nota de caso.

El panel de notas del caso muestra las notas del usuario que creó la nota y el tiempo transcurrido desde que se guardó la nota. Para buscar una palabra clave específica en el campo de texto de la nota de caso, use el botón **Buscar** en el panel de casos y escriba una palabra clave específica.

Para agregar una nota a un caso:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a Administración de **riesgos de Insider** y seleccione la **pestaña** Casos.
2. Seleccione un caso y, a continuación, seleccione la **pestaña Notas del caso.**
3. Seleccione **Agregar nota de caso**.
4. En el cuadro de diálogo Agregar **nota de caso,** escriba la nota para el caso. Seleccione **Guardar** para agregar la nota al caso o **seleccione Cancelar** cerrar sin guardar la nota en el caso.

### <a name="contributors"></a>Colaboradores

En la pestaña de **Colaboradores** activos se encuentra la opción de que los analistas de riesgos y los analistas de riesgos puedan agregar otros revisores al caso. De forma predeterminada, todos los usuarios asignados a **los analistas** de administración de riesgos insider y los roles de investigadores de administración de riesgos de **Insider** se enumeran como colaboradores para cada caso activo y cerrado. Solo los usuarios **asignados al rol Investigadores** de administración de riesgos de Insider tienen permiso para ver archivos y mensajes en el explorador de contenido.

El acceso temporal a un caso se puede conceder agregando un usuario como colaborador. Los colaboradores tienen todo el control de administración de casos en el caso específico excepto:

- Permiso para confirmar o descartar alertas
- Permiso para editar los colaboradores de los casos
- Permiso para ver archivos y mensajes en el explorador de contenido

Para agregar un colaborador a un caso:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a Administración de **riesgos de Insider** y seleccione la **pestaña** Casos.
2. Seleccione un caso y, a continuación, seleccione la **pestaña Colaboradores.**
3. Seleccione **Agregar colaborador**.
4. En el **cuadro de diálogo** Agregar colaborador, empiece a escribir el nombre del usuario que desea agregar y, a continuación, seleccione el usuario de la lista de usuarios sugerida. Esta lista se genera a partir del Azure Active Directory de la suscripción de inquilino.
5. Seleccione **Agregar** para agregar el usuario como colaborador o **seleccione Cancelar** cerrar el cuadro de diálogo sin agregarlo como colaborador.

## <a name="case-actions"></a>Acciones de casos

Los analistas e investigadores de riesgos pueden actuar en un caso en uno de varios métodos, según la gravedad del caso, el historial de riesgos del usuario y las directrices de riesgo de su organización. En algunas situaciones, es posible que deba escalar un caso a un usuario o una investigación de datos para colaborar con otras áreas de su organización y profundizar en las actividades de riesgo. La administración de riesgos de Insider está estrechamente integrada con otras Microsoft 365 de cumplimiento normativo para ayudarle con la administración de resolución integral.

### <a name="send-email-notice"></a>Enviar aviso de correo electrónico

En la mayoría de los casos, las acciones de usuario que crean alertas de riesgo de información interna son involuntarias o accidentales. Enviar un aviso de aviso al usuario por correo electrónico es un método eficaz para documentar la revisión y la acción de casos, y es un método para recordar a los usuarios las directivas corporativas o apuntarles a un aprendizaje de actualización. Los avisos se generan a partir de plantillas de [aviso que se crean](insider-risk-management-notices.md) para la infraestructura de administración de riesgos de insider.

Es importante recordar que enviar un aviso de correo electrónico a un usuario ***** no resuelve el caso como _Closed*. En algunos casos, es posible que desee dejar un caso abierto después de enviar un aviso a un usuario para buscar más actividades de riesgo sin abrir un nuevo caso. Si quiere resolver un caso después de enviar un aviso, debe seleccionar la opción **Resolver casos** como paso siguiente después de enviar un aviso.

Para enviar un aviso al usuario asignado a un caso:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a Administración de **riesgos de Insider** y seleccione la **pestaña** Casos.
2. Seleccione un caso y, a continuación, seleccione el **botón Enviar aviso de correo** electrónico en la barra de herramientas de acción caso.
3. En el **cuadro de diálogo** Enviar  aviso de correo electrónico, seleccione el control desplegable Elegir una plantilla de aviso para seleccionar la plantilla de aviso para el aviso. Esta selección rellena previamente los demás campos del aviso.
4. Revise los campos de aviso y actualice según corresponda. Los valores especificados aquí invalidarán los valores de la plantilla.
5. Seleccione **Enviar** para enviar el aviso al usuario o **seleccione Cancelar** cerrar el cuadro de diálogo sin enviar el aviso al usuario. Todos los avisos enviados se agregan a la cola de notas de caso en el panel **notas del** caso.

### <a name="escalate-for-investigation"></a>Remitir para investigación

Escala el caso para la investigación del usuario en situaciones en las que se necesita una revisión legal adicional para la actividad de riesgo del usuario. Esta extensión abre un nuevo caso de eDiscovery avanzado en su organización de Microsoft 365. eDiscovery avanzado proporciona un flujo de trabajo de un extremo a otro para conservar, recopilar, revisar, analizar y exportar contenido que responda a las investigaciones internas y externas de su organización. También permite que su equipo legal administre todo el flujo de trabajo de notificaciones de retención legal para comunicarse con los administradores implicados en un caso. Asignar un revisor como custodio en un caso de eDiscovery avanzado creado a partir de un caso de administración de riesgos internos ayuda a su equipo legal a tomar las medidas adecuadas y administrar la preservación del contenido. Para obtener más información sobre los casos de eDiscovery avanzado, consulte [Información general sobre la exhibición avanzada de documentos electrónicos en Microsoft 365](overview-ediscovery-20.md).

Para escalar un caso a una investigación de usuario:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a Administración de **riesgos de Insider** y seleccione la **pestaña** Casos.
2. Seleccione un caso y, a continuación, seleccione el botón **Escalar** para la investigación en la barra de herramientas de acción caso.
3. En el **cuadro de diálogo Escalar para** la investigación, escriba un nombre para la nueva investigación de usuario. Si es necesario, escriba notas sobre el caso y seleccione **Escalar**.
4. Revise los campos de aviso y actualice según corresponda. Los valores especificados aquí invalidarán los valores de la plantilla.
5. Seleccione **Confirmar** para crear el caso de investigación del usuario o **seleccione Cancelar** para cerrar el cuadro de diálogo sin crear un nuevo caso de investigación de usuario.

Después de que el caso de administración de riesgos de insider se haya escalado a un nuevo caso de investigación de usuario, puede revisar el nuevo caso en el área **eDiscovery** Advanced en el  >   Centro de cumplimiento de Microsoft 365.

### <a name="run-automated-tasks-with-power-automate-flows-for-the-case"></a>Ejecutar tareas automatizadas con Power Automate flujos para el caso

Con los flujos Power Automate recomendados, los investigadores y analistas de riesgos pueden tomar medidas rápidamente para:

- Solicitar información a RRHH o empresa sobre un usuario en un caso de riesgo interno
- Notificar al administrador cuando un usuario tiene una alerta de riesgo de información interna
- Crear un registro para un caso de administración de riesgos interno en ServiceNow
- Notificar a los usuarios cuando se agregan a una directiva de riesgo de insider

Para ejecutar, administrar o crear flujos de Power Automate para un caso de administración de riesgos interno:

1. Seleccione **Automatizar en** la barra de herramientas de acciones de caso. 
2. Elija el Power Automate para ejecutar y, a continuación, seleccione **Ejecutar flujo**. 
3. Una vez completado el flujo, seleccione **Listo**.

Para obtener más información sobre Power Automate para la administración de riesgos de insider, vea Introducción a la configuración de administración de riesgos [de insider](insider-risk-management-settings.md#power-automate-flows-preview).

### <a name="view-or-create-a-microsoft-teams-team-for-the-case"></a>Ver o crear un equipo Microsoft Teams para el caso

Cuando Microsoft Teams integración para la administración de riesgos de insider está habilitada en la configuración, un equipo de Microsoft Teams se crea automáticamente cada vez que se confirma una alerta y se crea un caso. Los investigadores y analistas de riesgos pueden abrir rápidamente Microsoft Teams y navegar directamente al equipo para un caso seleccionando Ver **Microsoft Teams** equipo en la barra de herramientas de acción de caso.

Para los casos abiertos antes de habilitar la integración de Microsoft Team, los investigadores y analistas de riesgos pueden crear un nuevo equipo de Microsoft Teams para un caso seleccionando Crear **Microsoft Teams** equipo en la barra de herramientas de acciones del caso.

Cuando se resuelve un caso, el equipo de Microsoft asociado se archivará automáticamente (oculto y convertido en de solo lectura).

Para obtener más información sobre Microsoft Teams para la administración de riesgos de insider, vea Introducción a la configuración de administración de riesgos [de insider](insider-risk-management-settings.md#microsoft-teams-preview).

### <a name="resolve-the-case"></a>Resolver el caso

Una vez que los analistas e investigadores de riesgos hayan completado su revisión e investigación, se puede resolver un caso para actuar en todas las alertas que se incluyen actualmente en el caso. La resolución de un caso agrega una clasificación de resolución, cambia el estado del caso a *Cerrado* y los motivos de la acción de resolución se agregan automáticamente a la cola de notas del caso en el panel notas **del** caso. Los casos se resuelven ya sea como:

- **Benigno:** clasificación de los casos en los que las alertas de coincidencia de directivas se evalúan como de bajo riesgo, no grave o falso positivo.
- **Infracción de directiva** confirmada: la clasificación de los casos en los que las alertas de coincidencia de directivas se evalúan como riesgosos, graves o el resultado de una intención malintencionada.

Para resolver un caso:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a Administración de **riesgos de Insider** y seleccione la **pestaña** Casos.
2. Seleccione un caso y, a continuación, seleccione el **botón Resolver caso** en la barra de herramientas de acción caso.
3. En el cuadro de diálogo Resolver **caso,** seleccione el control desplegable **Resolver como** para seleccionar la clasificación de resolución del caso. Las opciones son **Infracción de** directiva benigna **o Confirmada.**
4. En el cuadro de diálogo Resolver **caso,** escriba los motivos de la clasificación de resolución en el **campo de texto** Acción realizada.
5. Seleccione **Resolver** para cerrar el caso o **cancelar cerrar** el cuadro de diálogo sin resolver el caso.
