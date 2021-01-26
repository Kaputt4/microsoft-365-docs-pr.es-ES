---
title: Casos de administración de riesgos de Insider
description: Más información sobre los casos de administración de riesgos de Insider en Microsoft 365
keywords: Microsoft 365, administración de riesgos interno, administración de riesgos, cumplimiento
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
ms.openlocfilehash: feabf3083b0ff1d182884c66fc2b2fd890275a0a
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976217"
---
# <a name="insider-risk-management-cases"></a>Casos de administración de riesgos de Insider

Los casos son el núcleo de la administración de riesgos internas y le permiten investigar en profundidad y actuar en los problemas generados por indicadores de riesgo definidos en sus directivas. Los casos se crean manualmente a partir de alertas en situaciones en las que se necesitan más acciones para solucionar un problema relacionado con el cumplimiento de un usuario. Cada caso está en el ámbito de un solo usuario y se pueden agregar varias alertas para el usuario a un caso existente o a un nuevo caso. 

Después de investigar los detalles de un caso, puede tomar medidas:

- enviar un aviso al usuario
- resolver el caso como benigno
- compartir el caso con la instancia de ServiceNow o con un destinatario de correo electrónico
- escalar el caso para una investigación de eDiscovery avanzado

## <a name="cases-dashboard"></a>Panel casos

El panel de casos de administración de **riesgos interno** le permite ver y actuar en casos. Cada widget de informe del panel muestra información de los últimos 30 días.

- **Casos activos:** el número total de casos activos que se están investigando.
- **Casos de los últimos 30 días:** el número total de casos creados, ordenados por *estado activo* *y* cerrado.
- **Estadísticas:** tiempo promedio de los casos activos, enumerados en horas, días o meses.

La cola de casos enumera todos los casos activos y cerrados de su organización, además del estado actual de los siguientes atributos de caso:

- **Nombre de** caso: nombre del caso, definido cuando se confirma una alerta y se crea el caso.  
- **Estado:** el estado del caso, ya sea *Activo* o *Cerrado.*
- **Usuario:** el usuario del caso. Si está habilitada la anonimización de nombres de usuario, se muestra información anonimizada.
- **Caso de hora** abierto: el tiempo transcurrido desde que se abrió el caso.
- **Total de alertas de directiva:** el número de coincidencias de directiva incluidas en el caso. Este número puede aumentar si se agregan nuevas alertas al caso.
- **Last updated**: The time that has passed since there has been an added case note or change in the case state.
- **Last updated by**: The name of the insider risk management analyst or researcher that last updated the case.

![Panel de casos de administración de riesgos de Insider](../media/insider-risk-cases-dashboard.png)

Use el control **de** búsqueda para buscar nombres de casos para texto específico y usar el filtro de mayúsculas y minúsculas para ordenar los casos por los atributos siguientes:

- Estado
- Caso de hora abierto, fecha de inicio y fecha de finalización
- Última actualización, fecha de inicio y fecha de finalización

## <a name="filter-cases"></a>Filtrar casos

Según el número y el tipo de directivas de administración de riesgos internas activas de la organización, revisar una gran cola de casos puede ser complicado. El uso de filtros de casos puede ayudar a los analistas e investigadores a ordenar los casos por varios atributos. Para filtrar alertas en el **panel Casos,** seleccione el control **Filtro.** Puede filtrar los casos por uno o más atributos:

- **Estado:** seleccione uno o más valores de estado para filtrar la lista de casos. Las opciones son *Active* y *Closed*.
- **Caso de hora abierto:** seleccione las fechas de inicio y finalización para cuando se abrió el caso.
- **Last updated**: Select the start and end dates for when the case was updated.

## <a name="investigate-a-case"></a>Investigar un caso

Una investigación más profunda de las alertas de administración de riesgos interno es fundamental para tomar las medidas correctivas adecuadas. Los casos de administración de riesgos de Insider son la herramienta de administración central para profundizar en el historial de actividades de riesgo de los usuarios y los detalles de alertas, y para explorar el contenido y los mensajes expuestos a riesgos. Los analistas e investigadores de riesgos también usan casos para centralizar los comentarios y notas de revisión y procesar la resolución de casos.

La selección de un caso abre las herramientas de administración de casos y permite a los analistas e investigadores profundizar en los detalles de los casos.

### <a name="case-overview"></a>Información general sobre casos

La **pestaña Información general sobre** casos resume la actividad de alerta y el historial de nivel de riesgo del caso. 

- El  widget Alertas muestra las coincidencias de directiva para el caso, incluido el estado de la alerta, la gravedad del riesgo de alerta y cuándo se detectó la alerta. 
- El **gráfico de historial de nivel** de riesgo muestra el nivel de riesgo de usuario en los últimos 30 días. El gráfico de líneas permite a los analistas e investigadores ver rápidamente la tendencia en el riesgo general de los usuarios a lo largo del tiempo. 
- El **widget Contenido de actividad** de riesgo resume los tipos de datos y contenido contenidos en las alertas agregadas al caso. Este widget ofrece una vista completa de todos los datos y el contenido establecido en riesgo en el caso.

El **panel de detalles del** caso está disponible en todas las pestañas de administración de casos y resume los detalles del caso para analistas de riesgos e investigadores. Incluye las siguientes áreas:

- **Nombre de** caso: nombre del caso, con el prefijo de un número de secuencia de caso generado automáticamente y el nombre del riesgo asociado con la plantilla de directiva con la que coincide la primera alerta confirmada. 
- **Estado del** caso: el estado actual del caso, ya sea *Activo* o *Cerrado.*
- **Puntuación de riesgo del usuario:** el nivel de riesgo calculado actual del usuario para el caso. Esta puntuación se calcula cada 24 horas y usa las puntuaciones de riesgo de alerta de todas las alertas activas asociadas al usuario.
- **Alertas confirmadas:** lista de alertas para el usuario confirmadas para el caso.
- **Contenido relacionado:** lista de contenido, ordenada por tipos y orígenes de contenido. Por ejemplo, para el contenido de alertas de casos en SharePoint Online, es posible que vea nombres de archivo o carpetas que están asociados con la actividad de riesgo para alertas en el caso.

![Detalles de casos de administración de riesgos de Insider](../media/insider-risk-case-details.png)

### <a name="alerts"></a>Alertas

La **pestaña** Alertas resume las alertas actuales incluidas en el caso. Se pueden agregar nuevas alertas a un caso existente y se agregarán a la cola de **alertas** a medida que se asignen. Los siguientes atributos de alerta se enumeran en la cola:

- Estado
- Severity
- Tiempo detectado

Seleccione una alerta de la cola para mostrar la página De **detalles de** alerta.

Use el control de búsqueda para buscar nombres de alerta para texto específico y usar el filtro de alertas para ordenar los casos por los atributos siguientes:

- Estado
- Severity
- Hora detectada, fecha de inicio y fecha de finalización

Use el control de filtro para filtrar alertas por varios atributos, incluidos:

- **Estado:** seleccione uno o más valores de estado para filtrar la lista de alertas. Las opciones son *Confirmado,* *Descartado,* *Necesita revisión* y *Resuelto.*
- **Gravedad:** seleccione uno o más niveles de gravedad de riesgo de alerta para filtrar la lista de alertas. Las opciones son *Alta,* *Media* y *Baja.*
- **Hora detectada:** seleccione las fechas de inicio y finalización para cuando se creó la alerta.
- **Directiva:** seleccione una o más directivas para filtrar las alertas generadas por las directivas seleccionadas.

### <a name="user-activity"></a>Actividad de usuario

La **pestaña Actividad del** usuario es una de las herramientas más eficaces para el análisis de riesgos internos y la investigación de casos en la solución de administración de riesgos internos. Esta pestaña está estructurada para permitir la revisión rápida de un caso, incluida una escala de tiempo histórica de todas las alertas, todos los detalles de alertas, la puntuación de riesgo actual para el usuario en el caso y los controles para tomar medidas eficaces para contener los riesgos en el caso.

![Actividad de usuario de administración de riesgos de Insider](../media/insider-risk-user-activities.png)

1. **Filtros de fecha y** hora de la ventana: de forma predeterminada, los últimos seis meses de alertas confirmadas en el caso se muestran en el gráfico de actividad de usuario. Puedes filtrar fácilmente la vista de gráfico con los controles deslizantes en ambos extremos de la ventana del gráfico o definiendo fechas de inicio y finalización específicas en el control de filtro de gráfico.
2. **Actividad y detalles de alertas de** riesgo: las actividades de riesgo se muestran visualmente como burbujas de color en el gráfico actividad del usuario. Las burbujas se crean para diferentes categorías de riesgo y el tamaño de la burbuja es proporcional al número de actividades de riesgo de la categoría. Seleccione una burbuja para mostrar los detalles de cada actividad de riesgo. Entre los detalles se incluyen:
    - **Fecha** de la actividad de riesgo.
    - La **categoría de actividad de riesgo**. Por ejemplo, correo electrónico con datos adjuntos *enviados fuera* de la organización o archivos descargados *de SharePoint Online*.
    - **Puntuación de** riesgo de la alerta. Esta puntuación es la puntuación numérica para el nivel de gravedad de riesgo de alerta.
    - Número de eventos asociados a la alerta. También están disponibles vínculos a cada archivo o correo electrónico asociado con la actividad de riesgo.
3. **Leyenda de actividad de** riesgo: en la parte inferior del gráfico de actividad de usuario, una leyenda codificada por colores le ayuda a determinar rápidamente la categoría de riesgo de cada alerta.
4. **Cronómetro de** actividad de riesgo: se muestra el crono de todas las alertas de riesgo asociadas con el caso, incluidos todos los detalles disponibles en la burbuja de alerta correspondiente.
5. **Acciones de caso:** las opciones para resolver el caso se encuentran en la barra de herramientas de acciones de caso. Puede resolver un caso, enviar un aviso por correo electrónico al usuario o escalar el caso para una investigación de datos o usuarios.

### <a name="activity-explorer-preview"></a>Explorador de actividades (versión preliminar)

>[!IMPORTANT]
>La pestaña Explorador de actividades está disponible en el área de administración de casos para los usuarios con eventos desencadenados después de que esta característica esté disponible en la organización.

La **pestaña Explorador de** actividades permite a los analistas e investigadores de riesgos revisar los detalles de actividad asociados con las alertas de riesgo. Por ejemplo, como parte de las acciones de administración de casos, es posible que los investigadores y analistas deba revisar todas las actividades de riesgo asociadas con el caso para obtener más detalles. Con el **Explorador de actividades,** los revisores pueden revisar rápidamente una escala de tiempo de actividad de riesgo detectada e identificar y filtrar todas las actividades de riesgo asociadas con las alertas.

Para obtener más información sobre el Explorador de actividades, consulta el artículo de alertas de administración [de riesgos de Insider.](insider-risk-management-alerts.md#activity-explorer-preview)

### <a name="content-explorer"></a>Explorador de contenido

La **pestaña Explorador de contenido** permite a los analistas e investigadores de riesgos revisar copias de todos los archivos individuales y mensajes de correo electrónico asociados con alertas de riesgo. Por ejemplo, si se crea una alerta cuando un usuario descarga cientos de archivos desde SharePoint Online y la actividad desencadena una alerta de directiva, todos los archivos descargados de la alerta se capturan y copian en el caso de administración de riesgos de Insider desde orígenes de almacenamiento originales.

El Explorador de contenido es una herramienta eficaz con características básicas y avanzadas de búsqueda y filtrado. Para obtener más información sobre cómo usar el Explorador de contenido, vea El Explorador de contenido de administración de riesgos [de Insider.](insider-risk-management-content-explorer.md)

![Explorador de contenido de casos de administración de riesgos de Insider](../media/insider-risk-content-explorer.png)

### <a name="case-notes"></a>Notas del caso

La **pestaña Notas del** caso en el caso es donde analistas de riesgos e investigadores comparten comentarios, comentarios e información sobre su trabajo para el caso. Las notas son adiciones permanentes a un caso y no se pueden editar ni eliminar después de guardar la nota. Cuando se crea un caso a partir  de una alerta, los comentarios introducidos en el cuadro de diálogo Confirmar alerta y crear casos de riesgo interno se agregan automáticamente como nota de caso.

El panel de notas del caso muestra las notas del usuario que creó la nota y el tiempo transcurrido desde que se guardó la nota. Para buscar una palabra clave específica en  el campo de texto de nota de caso, use el botón Buscar en el panel de casos y escriba una palabra clave específica.

Para agregar una nota a un caso:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione la **pestaña Casos.**
2. Seleccione un caso y, a continuación, seleccione la **pestaña Notas del caso.**
3. Seleccione **Agregar nota de caso.**
4. En el **cuadro de diálogo** Agregar nota de caso, escriba la nota para el caso. Seleccione **Guardar** para agregar la nota al caso o **seleccione** Cancelar cerrar sin guardar la nota en el caso.

### <a name="contributors"></a>Colaboradores

La **pestaña Colaboradores** en el caso es donde los analistas de riesgos y los investigadores pueden agregar otros revisores al caso. De forma predeterminada, todos los usuarios asignados a los roles Analistas de administración de riesgos de **Insider** e Investigadores de administración de riesgos de **Insider** aparecen como colaboradores para cada caso activo y cerrado.

Todos los casos de administración de riesgos internos deben administrarse con controles de acceso adecuados para mantener la confidencialidad e integridad de la investigación. Para ayudar a mantener el control de acceso de los casos, a los usuarios se les asigna uno de los dos tipos de acceso a los casos:

- **Acceso permanente:** el acceso permanente se concede automáticamente a los usuarios con los roles Analistas de administración de riesgos de **Insider** e Investigadores de administración de riesgos de **Insider** cuando se crea el caso a partir de una alerta. El acceso permanente concede control total del caso durante la duración del caso y concede la capacidad de agregar otros colaboradores de casos.
- **Acceso temporal:** solo los colaboradores que tienen acceso permanente al caso conceden acceso temporal a los usuarios. Normalmente, este nivel de acceso se concede al usuario que necesita agregar notas a un caso. Los colaboradores con acceso temporal tienen control de administración de casos excepto:
    - Permiso para confirmar o descartar alertas
    - Permiso para editar los colaboradores para casos
    - Permiso para ver archivos y mensajes en el Explorador de contenido

Para agregar un colaborador a un caso:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione la **pestaña Casos.**
2. Seleccione un caso y, a continuación, seleccione la **pestaña Colaboradores.**
3. Seleccione **Agregar colaborador.**
4. En el **cuadro de diálogo** Agregar colaborador, empiece a escribir el nombre del usuario que desea agregar y, a continuación, seleccione el usuario de la lista de usuarios sugerida. Esta lista se genera a partir de Azure Active Directory de la suscripción de inquilino.
5. Seleccione **Agregar** para agregar el usuario como colaborador o seleccione Cancelar **cerrar** el cuadro de diálogo sin agregar el usuario como colaborador.

## <a name="case-actions"></a>Acciones case

Los analistas e investigadores de riesgos pueden tomar medidas en un caso en uno de varios métodos, según la gravedad del caso, el historial de riesgos del usuario y las directrices de riesgo de su organización. En algunas situaciones, es posible que deba escalar un caso a un usuario o una investigación de datos para colaborar con otras áreas de su organización y profundizar en las actividades de riesgo. La administración de riesgos de Insider está estrechamente integrada con otras soluciones de cumplimiento de Microsoft 365 para ayudarle con la administración de resolución de un extremo a otro.

### <a name="send-email-notice"></a>Enviar aviso de correo electrónico

En la mayoría de los casos, las acciones del usuario que crean alertas de riesgo interno son involuntarias o accidentales. Enviar un aviso al usuario por correo electrónico es un método eficaz para documentar la revisión de casos y la acción, y es un método para recordar a los usuarios las directivas corporativas o señalarles que actualicen el aprendizaje. Los avisos se generan a [partir de plantillas de aviso que se crean](insider-risk-management-notices.md) para la infraestructura de administración de riesgos interno.

Es importante recordar que enviar un aviso de correo electrónico a un usuario *_*_* no _ resuelve el caso como _Closed*. En algunos casos, es posible que desee dejar un caso abierto después de enviar un aviso a un usuario para buscar más actividades de riesgo sin abrir un nuevo caso. Si desea resolver un caso después de enviar un aviso, debe seleccionar **Resolver** caso como paso siguiente después de enviar un aviso.

Para enviar un aviso al usuario asignado a un caso:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione la **pestaña Casos.**
2. Seleccione un caso y, a continuación, seleccione el botón **Enviar aviso de** correo electrónico en la barra de herramientas de acciones del caso.
3. En el **cuadro de diálogo** Enviar  aviso por correo electrónico, seleccione el control desplegable Elegir una plantilla de aviso para seleccionar la plantilla de aviso para el aviso. Esta selección rellena previamente los demás campos del aviso.
4. Revise los campos de aviso y actualice según corresponda. Los valores especificados aquí invalidarán los valores de la plantilla.
5. Seleccione **Enviar** para enviar el aviso  al usuario o cancelar el cuadro de diálogo sin enviar el aviso al usuario. Todos los avisos enviados se agregan a la cola de notas del caso en el panel **de notas del** caso.

### <a name="escalate-for-investigation"></a>Escalar para investigación

Escalar el caso para la investigación de usuarios en situaciones en las que se necesite una revisión legal adicional para la actividad de riesgo del usuario. Esta escalación abre un nuevo caso de eDiscovery avanzado en su organización de Microsoft 365. EDiscovery avanzado proporciona un flujo de trabajo completo para conservar, recopilar, revisar, analizar y exportar contenido que responde a las investigaciones legales internas y externas de su organización. También permite al equipo legal administrar todo el flujo de trabajo de notificación de retención legal para comunicarse con los administradores implicados en un caso. La asignación de un revisor como administrador en un caso de eDiscovery avanzado creado a partir de un caso de administración de riesgos interno ayuda a su equipo legal a tomar las medidas adecuadas y administrar la conservación de contenido. Para obtener más información sobre los casos de eDiscovery avanzado, vea Información general sobre [eDiscovery avanzado en Microsoft 365.](overview-ediscovery-20.md)

Para escalar un caso a una investigación de usuario:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione la **pestaña Casos.**
2. Seleccione un caso y, a continuación, seleccione el botón **Escalar** para investigación en la barra de herramientas de acciones del caso.
3. En el **cuadro de diálogo Escalar** para investigación, escriba un nombre para la nueva investigación de usuarios. Si es necesario, escriba notas sobre el caso y seleccione **Escalar**.
4. Revise los campos de aviso y actualice según corresponda. Los valores especificados aquí invalidarán los valores de la plantilla.
5. Seleccione **Confirmar** para crear el caso de investigación de usuario o **cancelar** para cerrar el cuadro de diálogo sin crear un nuevo caso de investigación de usuario.

Una vez que el caso de administración de riesgos interno se ha escalado a un nuevo caso de investigación de usuario, puede revisar el nuevo caso en el área de exhibición avanzada de documentos electrónicos en el Centro de cumplimiento de  >   Microsoft 365.

### <a name="run-automated-tasks-with-power-automate-flows-for-the-case"></a>Ejecutar tareas automatizadas con flujos de Power Automate para el caso

Con los flujos recomendados de Power Automate, los investigadores de riesgos y analistas pueden tomar medidas rápidamente para:

- Solicitar información de recursos humanos o empresariales sobre un usuario en un caso de riesgo interno
- Notificar al administrador cuando un usuario tiene una alerta de riesgo interno
- Agregar un aviso de calendario para hacer un seguimiento en un caso de riesgo interno
- Crear un registro para un caso de administración de riesgos interno en ServiceNow

Para ejecutar, administrar o crear flujos de Power Automate para un caso de administración de riesgos interno:

1. Seleccione **Automatizar en la** barra de herramientas de acciones de casos. 
2. Elija el flujo de Power Automate que desea ejecutar y, a continuación, **seleccione Ejecutar flujo.** 
3. Una vez completado el flujo, seleccione **Listo.**

Para obtener más información sobre los flujos de Power Automate para la administración de riesgos interno, consulte Introducción a la configuración de administración de [riesgos de Insider.](insider-risk-management-settings.md#power-automate-flows-preview)

### <a name="view-or-create-a-microsoft-teams-team-for-the-case"></a>Ver o crear un equipo de Microsoft Teams para el caso

Cuando se habilita la integración de Microsoft Teams para la administración de riesgos interno en la configuración, se crea automáticamente un equipo de Microsoft Teams cada vez que se confirma una alerta y se crea un caso. Los analistas y los investigadores de riesgos pueden abrir rápidamente Microsoft Teams y navegar directamente al equipo en busca de un caso seleccionando Ver equipo de **Microsoft Teams** en la barra de herramientas de acciones del caso.

Para los casos abiertos antes de habilitar la integración de Microsoft Team, los investigadores de riesgos y analistas pueden crear un nuevo equipo de Microsoft Teams para un caso seleccionando Crear equipo de **Microsoft Teams** en la barra de herramientas de acciones del caso.

Cuando se resuelve un caso, microsoft team asociado se archivará automáticamente (oculto y se volverá a solo lectura).

Para obtener más información sobre Microsoft Teams para la administración de riesgos de insider, consulte Introducción a la configuración de administración [de riesgos de Insider.](insider-risk-management-settings.md#microsoft-teams-preview)

### <a name="share-the-case"></a>Compartir el caso

Compartir un caso de administración de riesgos interno permite a los investigadores de riesgos y analistas colaborar fácilmente con otras partes interesadas de cumplimiento de la organización. Puede compartir rápidamente un vínculo a un caso de administración de riesgos internos con partes interesadas externas desde el área de administración de casos. Para obtener acceso al caso de administración de riesgos interno desde el vínculo, las partes interesadas deben incluirse en cualquiera de los grupos de roles de administración de riesgos de Insider.

>[!NOTE]
>Gracias por sus comentarios y soporte técnico durante la vista previa del conector ServiceNow. Hemos decidido finalizar la versión preliminar del conector ServiceNow y dejar de admitir la administración de riesgos de Insider el 30 de noviembre de 2020. Estamos evaluando activamente métodos alternativos para proporcionar a los clientes la integración de ServiceNow en la administración de riesgos interno.

Están disponibles las siguientes opciones de uso compartido:

- **ServiceNow:** después de configurar el conector ServiceNow de Microsoft 365 para su organización de Microsoft 365, puede compartir fácilmente un vínculo al caso, abrir un incidente o solicitar un cambio con su organización ServiceNow. Para compartir el caso con ServiceNow, seleccione **Compartir**  >  **ServiceNow** en la acción de caso. La integración de ServiceNow con la administración de riesgos de Insider incluye la siguiente información de casos y acciones:
    - **Nombre de** la tarea: el nombre de la nueva tarea ServiceNow.
    - **Descripción de** la tarea: descripción de la nueva tarea ServiceNow. Este campo de descripción editable incluye automáticamente un vínculo al caso de administración de riesgos de Insider.
    - **Tipo de** tarea: el tipo de tarea para la nueva tarea ServiceNow, ya sea *incidente* o solicitud *de cambio*.
    - **Prioridad:** la prioridad de la nueva tarea ServiceNow, ya sea *Planeación,* Baja, *Moderada,* *Alta* o *Crítica.*
    - **Fecha de vencimiento:** la fecha solicitada para completar la tarea ServiceNow.

![Uso compartido de la administración de riesgos de Insider con ServiceNow](../media/insider-risk-share-servicenow.png)

- **Correo** electrónico: comparte un vínculo al caso de administración de riesgos de Insider en un correo electrónico. Puede elegir cualquier cliente de correo electrónico configurado localmente con esta opción de uso compartido. Para compartir el vínculo de caso con correo electrónico, seleccione **Compartir**  >  **correo electrónico** en la barra de herramientas de acciones del caso.
- **Vínculo Copiar:** copia un vínculo al caso de administración de riesgos de Insider en el Portapapeles. Para copiar el vínculo de caso en el Portapapeles, **seleccione** el vínculo Compartir copia en la barra de herramientas de acciones de  >   caso.

### <a name="resolve-the-case"></a>Resolver el caso

Una vez que los analistas e investigadores de riesgos hayan completado su revisión e investigación, se puede resolver un caso para actuar en todas las alertas incluidas actualmente en el caso. La resolución de un caso agrega una clasificación de resolución, cambia el estado del caso a *Cerrado* y los motivos de la acción de resolución se agregan automáticamente a la cola de notas del caso en el panel de notas **del** caso. Los casos se resuelven como:

- **Benigno:** la clasificación para los casos en los que las alertas de coincidencia de directivas se evalúan como de riesgo bajo, no grave o falso positivo.
- **Infracción de directiva** confirmada: la clasificación para los casos en los que las alertas de coincidencia de directiva se evalúan como arriesgadas, graves o el resultado de una intención malintencionada.

Para resolver un caso:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione la **pestaña Casos.**
2. Seleccione un caso y, a continuación, seleccione el botón Resolver **caso** en la barra de herramientas de acciones de caso.
3. En el cuadro de diálogo Resolver **caso,** seleccione el control Resolver **como** desplegable para seleccionar la clasificación de resolución del caso. Las opciones son **Infracción de** directiva benigna **o confirmada.**
4. En el cuadro de diálogo Resolver **caso,** escriba los motivos de la clasificación de resolución en el **campo de** texto Acción realizada.
5. Seleccione **Resolver** para cerrar el caso o **cancelar** el cuadro de diálogo sin resolver el caso.
