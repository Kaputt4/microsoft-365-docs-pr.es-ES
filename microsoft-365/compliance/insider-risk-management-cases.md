---
title: Casos de administración de riesgos internos
description: Más información sobre los casos de administración de riesgos internos en Microsoft Purview
keywords: Microsoft 365, Microsoft Purview, riesgo interno, administración de riesgos, cumplimiento
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- tier1
- purview-compliance
ms.custom: admindeeplinkCOMPLIANCE
ms.openlocfilehash: 254fb4f17331be8b688463599dea86b9f3748ca8
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68634638"
---
# <a name="insider-risk-management-cases"></a>Casos de administración de riesgos internos

>[!IMPORTANT]
>Administración de riesgos internos de Microsoft Purview correlaciona varias señales para identificar posibles riesgos internos malintencionados o involuntarios, como el robo de IP, la pérdida de datos y las infracciones de seguridad. La administración de riesgos internos permite a los clientes crear directivas para administrar la seguridad y el cumplimiento. Creados con privacidad por diseño, los usuarios se seudonimizan de forma predeterminada y los controles de acceso basados en roles y los registros de auditoría están en su lugar para ayudar a garantizar la privacidad del nivel de usuario.

Los casos son el núcleo de la gestión de riesgos internos y le permiten investigar y actuar en profundidad sobre los problemas generados por los indicadores de riesgo definidos en sus políticas. Los casos se crean manualmente a partir de alertas en situaciones en las que se necesita más acción para solucionar un problema relacionado con el cumplimiento para un usuario. Cada caso se limita a un único usuario y se pueden agregar varias alertas para el usuario a un caso existente o a un caso nuevo.

Después de investigar los detalles de un caso, puede tomar medidas mediante:

- enviar al usuario un aviso
- resolver el caso como benigno
- compartir el caso con la instancia de ServiceNow o con un destinatario de correo electrónico
- escalar el caso de una investigación de eDiscovery (Premium)

Consulte el [vídeo Investigación y escalación de la administración de riesgos](https://www.youtube.com/watch?v=UONUSmkRC8s) internos para obtener información general sobre cómo se investigan y administran los casos en la administración de riesgos internos.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="cases-dashboard"></a>Panel Casos

El **panel casos** de administración de riesgos internos le permite ver y actuar en casos. Cada widget de informe del panel muestra información de los últimos 30 días.

- **Casos activos**: el número total de casos activos que se están investigando.
- **Casos de los últimos 30 días**: el número total de casos creados, ordenados por estado *Activo* y *Cerrado* .
- **Estadísticas**: tiempo medio de los casos activos, enumerados en horas, días o meses.

En la cola de casos se enumeran todos los casos activos y cerrados de su organización, además del estado actual de los siguientes atributos de caso:

- **Nombre** de caso: nombre del caso, definido cuando se confirma una alerta y se crea el caso.  
- **Estado**: estado del caso, *activo* o *cerrado*.
- **Usuario**: el usuario del caso. Si se habilita la anonimización de nombres de usuario, se muestra información anónima.
- **Mayúsculas y minúsculas abiertas**: el tiempo transcurrido desde que se abrió el caso.
- **Total de alertas de directiva**: el número de coincidencias de directivas incluidas en el caso. Este número puede aumentar si se agregan nuevas alertas al caso.
- **Caso actualizado por última vez**: el tiempo transcurrido desde que se ha agregado una nota de caso o un cambio en el estado del caso.
- **Última actualización por**: el nombre del analista o investigador de administración de riesgos internos que actualizó por última vez el caso.

![Panel casos de administración de riesgos internos.](../media/insider-risk-cases-dashboard.png)

Use el control **Buscar** para buscar nombres de mayúsculas y minúsculas en texto específico y use el filtro de mayúsculas y minúsculas para ordenar casos por los siguientes atributos:

- Estado
- Tiempo de caso abierto, fecha de inicio y fecha de finalización
- Última actualización, fecha de inicio y fecha de finalización

## <a name="filter-cases"></a>Casos de filtro

En función del número y el tipo de directivas de administración de riesgos internos activas de su organización, la revisión de una gran cola de casos puede ser complicado. El uso de filtros de casos puede ayudar a los analistas e investigadores a ordenar casos por varios atributos. Para filtrar alertas en el **panel Casos**, seleccione el control **Filtro** . Puede filtrar los casos por uno o varios atributos:

- **Estado**: seleccione uno o varios valores de estado para filtrar la lista de casos. Las opciones son *Active* y *Closed*.
- **Mayúsculas** y minúsculas abiertas: seleccione las fechas de inicio y finalización para cuando se abrió el caso.
- **Última actualización**: seleccione las fechas de inicio y finalización para cuando se actualizó el caso.

## <a name="investigate-a-case"></a>Investigación de un caso

Una investigación más profunda de las alertas de administración de riesgos internos es fundamental para tomar las medidas correctivas adecuadas. Los casos de administración de riesgos internos son la herramienta de administración central para profundizar en el historial de actividades de riesgo del usuario, los detalles de las alertas, la secuencia de eventos de riesgo y explorar el contenido y los mensajes expuestos a los riesgos. Los analistas e investigadores de riesgo también usan casos para centralizar comentarios y notas de revisión y procesar la resolución de casos.

Seleccionar un caso abre las herramientas de administración de casos y permite a analistas y expertos profundizar en los detalles de los casos.

### <a name="case-overview"></a>Información general de casos

En la pestaña **Información general del caso** se resumen los detalles del caso para analistas e investigadores de riesgo. Incluye la siguiente información en el área **Acerca de este caso**

- **Estado**: estado actual del caso, activo o cerrado.
- **Caso creado en**: fecha y hora en que se creó el caso.
- **Puntuación de riesgo del usuario**: el nivel de riesgo calculado actual del usuario para el caso. Esta puntuación se calcula cada 24 horas y usa puntuaciones de riesgo de alerta de todas las alertas activas asociadas al usuario.
- **Email**: alias de correo electrónico del usuario para el caso.
- **Organización o departamento**: la organización o el departamento al que está asignado el usuario.
- **Nombre del administrador**: nombre del administrador del usuario.
- **Correo electrónico del administrador**: alias de correo electrónico del administrador del usuario.

![Detalles del caso de administración de riesgos internos.](../media/insider-risk-case-details.png)

La pestaña **Información general del caso** también incluye una sección **Alertas** que incluye la siguiente información sobre las alertas de coincidencia de directivas asociadas al caso:

- **Coincidencias de directivas**: el nombre de la directiva de administración de riesgos internos asociada a las alertas de coincidencia para la actividad del usuario.
- **Estado**: estado de la alerta.
- **Gravedad**: gravedad de la alerta.
- **Tiempo detectado**: tiempo transcurrido desde que se generó la alerta.

### <a name="alerts"></a>Alertas

La pestaña **Alertas** resume las alertas actuales incluidas en el caso. Se pueden agregar nuevas alertas a un caso existente y se agregarán a la cola **de alertas** a medida que se asignen. Los siguientes atributos de alerta aparecen en la cola:

- Estado
- Severity
- Tiempo detectado

Seleccione una alerta de la cola para mostrar la página **Detalles** de la alerta.

Use el control de búsqueda para buscar en nombres de alerta texto específico y usar el filtro de alertas para ordenar casos por los siguientes atributos:

- Estado
- Severity
- Hora detectada, fecha de inicio y fecha de finalización

Use el control de filtro para filtrar las alertas por varios atributos, entre los que se incluyen:

- **Estado**: seleccione uno o varios valores de estado para filtrar la lista de alertas. Las opciones son *Confirmada*, *Descartada*, *Falta por revisar*, y *Resuelta*.
- **Gravedad**: seleccione uno o varios niveles de gravedad de riesgo de alerta para filtrar la lista de alertas. Las opciones son *Alta*, *Media*, y *Baja*.
- **Hora detectada**: seleccione las fechas de inicio y finalización para cuando se creó la alerta.
- **Directiva**: seleccione una o varias directivas para filtrar las alertas generadas por las directivas seleccionadas.

### <a name="user-activity"></a>Actividad de usuario

La pestaña **Actividad de usuario** permite a los analistas e investigadores de riesgo revisar los detalles de la actividad y usar una representación visual de todas las actividades asociadas a alertas y casos de riesgo. Por ejemplo, como parte del proceso de evaluación de prioridades de alertas, es posible que los analistas tengan que revisar todas las actividades de riesgo asociadas al caso para obtener más detalles. En los casos, los investigadores de riesgo pueden revisar los detalles de la actividad del usuario y el gráfico de burbujas para ayudar a comprender el ámbito general de las actividades asociadas al caso. Para obtener más información sobre el gráfico De actividad de usuario, consulte el artículo [Actividades de administración de riesgos de Insider](insider-risk-management-activities.md#user-activity) .

### <a name="activity-explorer-preview"></a>Explorador de actividad (versión preliminar)

La pestaña **Explorador de actividad** permite a los analistas e investigadores de riesgo revisar los detalles de la actividad asociados a las alertas de riesgo. Por ejemplo, como parte de las acciones de administración de casos, es posible que los investigadores y analistas necesiten revisar todas las actividades de riesgo asociadas al caso para obtener más detalles. Con el **Explorador de actividades**, los revisores pueden revisar rápidamente una escala de tiempo de la actividad de riesgo detectada e identificar y filtrar todas las actividades de riesgo asociadas a alertas.

Para obtener más información sobre el Explorador de actividades, consulte el artículo [Actividades de administración de riesgos de Insider](insider-risk-management-activities.md#activity-explorer) .

### <a name="forensic-evidence-preview"></a>Pruebas forenses (versión preliminar)

La pestaña **Pruebas forenses (versión preliminar)** permite a los investigadores de riesgo revisar las capturas visuales asociadas a las actividades de riesgo incluidas en los casos. Por ejemplo, como parte de las acciones de administración de casos, es posible que los investigadores necesiten ayudar a aclarar el contexto de la actividad del usuario que se está revisando. Ver los clips reales de la actividad puede ayudar al investigador a determinar si la actividad del usuario es potencialmente arriesgada y puede provocar un incidente de seguridad.

Para obtener más información sobre las pruebas forenses, consulte el artículo [Información sobre las pruebas forenses de administración de riesgos internos](/microsoft-365/compliance/insider-risk-management-forensic-evidence) .

### <a name="content-explorer"></a>Explorador de contenido

La pestaña **Explorador de contenido** permite a los investigadores de riesgo revisar copias de todos los archivos individuales y mensajes de correo electrónico asociados a alertas de riesgo. Por ejemplo, si se crea una alerta cuando un usuario descarga cientos de archivos de SharePoint Online y la actividad desencadena una alerta de directiva, todos los archivos descargados para la alerta se capturan y copian en el caso de administración de riesgos internos de orígenes de almacenamiento originales.

El Explorador de contenido es una herramienta eficaz con características básicas y avanzadas de búsqueda y filtrado. Para obtener más información sobre el uso del Explorador de contenido, consulte [Explorador de contenido de administración de riesgos internos](insider-risk-management-content-explorer.md).

![Explorador de contenido de casos de administración de riesgos internos.](../media/insider-risk-content-explorer.png)

### <a name="case-notes"></a>Notas del caso

La pestaña **Notas** del caso en el caso es donde analistas e investigadores de riesgo comparten comentarios, comentarios e información sobre su trabajo para el caso. Las notas son adiciones permanentes a un caso y no se pueden editar ni eliminar después de guardar la nota. Cuando se crea un caso a partir de una alerta, los comentarios escritos en el cuadro de diálogo **Confirmar alerta y crear casos de riesgo internas** se agregan automáticamente como nota de caso.

El panel de notas del caso muestra las notas del usuario que creó la nota y el tiempo transcurrido desde que se guardó la nota. Para buscar en el campo de texto de la nota de caso una palabra clave específica, use el botón **Buscar** en el panel del caso y escriba una palabra clave específica.

Para agregar una nota a un caso:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos** internos y seleccione la pestaña **Casos**.
2. Seleccione un caso y, a continuación, seleccione la pestaña **Notas del caso** .
3. Seleccione **Agregar nota de caso**.
4. En el cuadro de diálogo **Agregar nota de caso** , escriba la nota para el caso. Seleccione **Guardar** para agregar la nota al caso o seleccione **Cancelar** cierre sin guardar la nota en el caso.

### <a name="contributors"></a>Colaboradores

En la pestaña de **Colaboradores** activos se encuentra la opción de que los analistas de riesgos y los analistas de riesgos puedan agregar otros revisores al caso. De forma predeterminada, todos los usuarios **asignados a los roles Insider Risk Management Analysts** y **Insider Risk Management Investigators** se enumeran como colaboradores para cada caso activo y cerrado. Solo los usuarios **asignados al rol Insider Risk Management Investigators** tienen permiso para ver archivos y mensajes en el Explorador de contenido.

Se puede conceder acceso temporal a un caso agregando un usuario como colaborador. Los colaboradores tienen todo el control de administración de casos en el caso específico, excepto:

- Permiso para confirmar o descartar alertas
- Permiso para editar los colaboradores de los casos
- Permiso para ver archivos y mensajes en el Explorador de contenido

Para agregar un colaborador a un caso:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos** internos y seleccione la pestaña **Casos**.
2. Seleccione un caso y, a continuación, seleccione la pestaña **Colaboradores** .
3. Seleccione **Agregar colaborador**.
4. En el cuadro de diálogo **Agregar colaborador** , empiece a escribir el nombre del usuario que desea agregar y, a continuación, seleccione el usuario en la lista de usuarios sugeridos. Esta lista se genera a partir de Azure Active Directory de la suscripción de inquilino.
5. Seleccione **Agregar** para agregar el usuario como colaborador o seleccione **Cancelar** cierre el cuadro de diálogo sin agregar el usuario como colaborador.

## <a name="case-actions"></a>Acciones de casos

Los investigadores de riesgo pueden tomar medidas sobre un caso en uno de varios métodos, en función de la gravedad del caso, el historial de riesgo del usuario y las directrices de riesgo de su organización. En algunas situaciones, es posible que tenga que escalar un caso a un usuario o a una investigación de datos para colaborar con otras áreas de su organización y profundizar en las actividades de riesgo. La administración de riesgos internos está estrechamente integrada con otras soluciones de Microsoft Purview para ayudarle con la administración de soluciones de un extremo a otro.

### <a name="send-email-notice"></a>Enviar notificación por correo electrónico

En la mayoría de los casos, las acciones de usuario que crean alertas de riesgo internos son accidentales o accidentales. El envío de un aviso al usuario por correo electrónico es un método eficaz para documentar la revisión y la acción de casos, y es un método para recordar a los usuarios las directivas corporativas o indicarles que actualicen el entrenamiento. Los avisos se generan a partir de [las plantillas de aviso que se crean](insider-risk-management-notices.md) para la infraestructura de administración de riesgos internos.

Es importante recordar que el envío de un aviso de correo electrónico a un usuario ***no** _ resuelve el caso como _Closed*. En algunos casos, es posible que desee dejar un caso abierto después de enviar un aviso a un usuario para buscar actividades de más riesgo sin abrir un nuevo caso. Si quiere resolver un caso después de enviar un aviso, debe seleccionar la opción **Resolver casos** como paso siguiente después de enviar un aviso.

Para enviar un aviso al usuario asignado a un caso:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos** internos y seleccione la pestaña **Casos**.
2. Seleccione un caso y, a continuación, seleccione el botón **Enviar aviso de correo electrónico** en la barra de herramientas de acciones de caso.
3. En el cuadro **de diálogo Enviar aviso de correo electrónico** , seleccione el control desplegable **Elegir una plantilla de aviso** para seleccionar la plantilla de aviso para el aviso. Esta selección rellena previamente los demás campos del aviso.
4. Revise los campos de aviso y actualice según corresponda. Los valores especificados aquí invalidarán los valores de la plantilla.
5. Seleccione **Enviar** para enviar el aviso al usuario o seleccione **Cancelar** cierre el cuadro de diálogo sin enviar el aviso al usuario. Todos los avisos enviados se agregan a la cola de notas de caso en el panel **Notas** del caso.

### <a name="escalate-for-investigation"></a>Escalar para investigación

Escale el caso para la investigación del usuario en situaciones en las que se necesite una revisión legal adicional para la actividad de riesgo del usuario. Esta escalación abre un nuevo caso de Microsoft Purview eDiscovery (Premium) en la organización de Microsoft 365. eDiscovery (Premium) ofrece un flujo de trabajo de un extremo a otro para conservar, recopilar, revisar, analizar y exportar el contenido que responde a las investigaciones legales internas y externas de la organización. También permite que su equipo legal administre todo el flujo de trabajo de notificaciones de retención legal para comunicarse con los administradores implicados en un caso. Escalar a un caso de eDiscovery (Premium) desde un caso de administración de riesgos internos ayuda a su equipo legal a tomar las medidas adecuadas y administrar la conservación del contenido. Para obtener más información sobre los casos de eDiscovery (Premium), consulte [Información general de Microsoft Purview eDiscovery (Premium).](overview-ediscovery-20.md)

Para escalar un caso a una investigación de usuario:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos** internos y seleccione la pestaña **Casos**.
2. Seleccione un caso y, a continuación, seleccione el botón **Escalar para investigación** en la barra de herramientas de acciones de caso.
3. En el cuadro de diálogo **Escalar para investigación** , escriba un nombre para la nueva investigación de usuario. Si es necesario, escriba notas sobre el caso y seleccione **Escalar**.
4. Revise los campos de aviso y actualice según corresponda. Los valores especificados aquí invalidarán los valores de la plantilla.
5. Seleccione **Confirmar** para crear el caso de investigación del usuario o seleccione **Cancelar** para cerrar el cuadro de diálogo sin crear un nuevo caso de investigación de usuario.

Una vez que el caso de administración de riesgos internos se ha escalado a un nuevo caso de investigación de usuarios, puede revisar el nuevo caso en el área **eDiscovery** > **Advanced** del portal de cumplimiento Microsoft Purview.

### <a name="run-automated-tasks-with-power-automate-flows-for-the-case"></a>Ejecución de tareas automatizadas con flujos de Power Automate para el caso

Con los flujos recomendados de Power Automate, los investigadores y analistas de riesgo pueden tomar medidas rápidamente para:

- Solicitar información de RR. HH. o empresa sobre un usuario en un caso de riesgo interno
- Notificar al administrador cuando un usuario tiene una alerta de riesgo interno
- Creación de un registro para un caso de administración de riesgos internos en ServiceNow
- Notificar a los usuarios cuando se agregan a una directiva de riesgo interno

Para ejecutar, administrar o crear flujos de Power Automate para un caso de administración de riesgos internos:

1. Seleccione **Automatizar** en la barra de herramientas de acciones de casos. 
2. Elija el flujo de Power Automate que se va a ejecutar y, a continuación, seleccione **Ejecutar flujo**. 
3. Una vez completado el flujo, seleccione **Listo**.

Para más información sobre los flujos de Power Automate para la administración de riesgos internos, consulte [Introducción a la configuración de administración de riesgos internos](insider-risk-management-settings.md#power-automate-flows-preview).

### <a name="view-or-create-a-microsoft-teams-team-for-the-case"></a>Ver o crear un equipo de Microsoft Teams para el caso

Cuando la integración de Microsoft Teams para la administración de riesgos internos está habilitada en la configuración, se crea automáticamente un equipo de Microsoft Teams cada vez que se confirma una alerta y se crea un caso. Los investigadores y analistas de riesgo pueden abrir Rápidamente Microsoft Teams y navegar directamente al equipo para ver un caso seleccionando **Ver equipo de Microsoft Teams** en la barra de herramientas de acción del caso.

Para los casos abiertos antes de habilitar la integración del equipo de Microsoft, los investigadores y analistas de riesgo pueden crear un nuevo equipo de Microsoft Teams para un caso seleccionando **Crear equipo de Microsoft Teams** en la barra de herramientas de acciones del caso.

Cuando se resuelve un caso, el equipo de Microsoft asociado se archivará automáticamente (oculto y se convertirá en de solo lectura).

Para más información sobre Microsoft Teams para la administración de riesgos internos, consulte [Introducción a la configuración de administración de riesgos](insider-risk-management-settings.md#microsoft-teams-preview) internos.

### <a name="resolve-the-case"></a>Resolver el caso

Una vez que los analistas e investigadores de riesgo han completado su revisión e investigación, se puede resolver un caso para actuar sobre todas las alertas que se incluyen actualmente en el caso. La resolución de un caso agrega una clasificación de resolución, cambia el estado del caso a *Cerrado* y los motivos de la acción de resolución se agregan automáticamente a la cola de notas del caso en el panel **Notas** del caso. Los casos se resuelven ya sea como:

- **Benigno**: la clasificación de los casos en los que las alertas de coincidencia de directivas se evalúan como de bajo riesgo, no grave o falso positivo.
- **Infracción de directiva confirmada**: clasificación de los casos en los que las alertas de coincidencia de directivas se evalúan como de riesgo, grave o resultado de intenciones malintencionadas.

Para resolver un caso:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos** internos y seleccione la pestaña **Casos**.
2. Seleccione un caso y, a continuación, seleccione el botón **Resolver caso** en la barra de herramientas de acciones de caso.
3. En el cuadro de diálogo **Resolver caso** , seleccione el control desplegable **Resolver como** para seleccionar la clasificación de resolución del caso. Las opciones son **Infracciones de directivas benignas** o **confirmadas**.
4. En el cuadro de diálogo **Resolver caso** , escriba los motivos de la clasificación de resolución en el campo **De texto Acción realizada** .
5. Seleccione **Resolver** para cerrar el caso o seleccione **Cancelar** cierre el cuadro de diálogo sin resolverlo.
