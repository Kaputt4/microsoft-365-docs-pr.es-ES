---
title: Casos de administración de riesgos de Insider
description: Obtenga información sobre los casos de administración de riesgos de Insider en Microsoft 365
keywords: Microsoft 365, administración de riesgos de Insider, administración de riesgos, cumplimiento
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
ms.openlocfilehash: 8667c625de4c83c98efd8f1cf20f3db57ed0d4c5
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416564"
---
# <a name="insider-risk-management-cases"></a>Casos de administración de riesgos de Insider

Los casos son el corazón de la administración de riesgos de Insiders y le permiten investigar y actuar con profundidad en los problemas generados por los indicadores de riesgo definidos en las directivas. Los casos se crean manualmente a partir de alertas en situaciones en las que es necesario realizar acciones adicionales para resolver un problema relacionado con el cumplimiento de un usuario. Cada caso está en el ámbito de un único usuario y se pueden agregar varias alertas para el usuario a un caso existente o a un nuevo caso. 

Una vez que haya investigado los detalles de un caso, puede emprender las acciones siguientes:

- Enviar un aviso al usuario
- resolver el caso como benigno
- uso compartido del caso con su instancia de ServiceNow o con un destinatario de correo electrónico
- remitir el caso para una investigación avanzada de eDiscovery

## <a name="cases-dashboard"></a>Panel de casos

El **Panel de casos** de administración de riesgos de Insider le permite ver y actuar en casos. Cada widget de informe del panel muestra información de los últimos 30 días.

- **Casos activos**: el número total de casos activos en investigación.
- **Casos durante los últimos 30 días**: el número total de casos creados, ordenados por estado *activo* y *cerrado* .
- **Estadísticas**: tiempo promedio de los casos activos, enumerados en horas, días o meses.

La cola de casos enumera todos los casos activos y cerrados para la organización, además del estado actual de los siguientes atributos de caso:

- **Nombre de caso**: nombre del caso, definido cuando se confirma una alerta y se crea el caso.  
- **Status**: el estado del caso, ya sea *activo* o *cerrado*.
- **User**: el usuario para el caso. Si anonymization para usernames está habilitada, se muestra la información de anonimizan.
- **Caso de tiempo de apertura**: tiempo que ha pasado desde que se abrió el caso.
- **Total de alertas de directiva**: el número de coincidencias de directivas incluidas en el caso. Este número puede aumentar si se agregan nuevas alertas al caso.
- **Última actualización**: el tiempo que ha pasado desde que se ha agregado una nota de caso o un cambio en el estado de caso.
- **Última actualización**: el nombre del analista o investigador de administración de riesgos de Insider que ha actualizado el caso por última vez.

![Panel de casos de administración de riesgos de Insider](../media/insider-risk-cases-dashboard.png)

Use el control de **búsqueda** para buscar nombres de casos específicos de texto y usar el filtro de casos para ordenar los casos por los siguientes atributos:

- Estado
- Tiempo de uso abierto, fecha de inicio y fecha de finalización
- Última actualización, fecha de inicio y fecha de finalización

## <a name="filter-cases"></a>Filtrar casos

Según el número y el tipo de directivas activas de administración de riesgos de Insider en la organización, la revisión de una gran cola de casos puede resultar complicada. El uso de filtros Case puede ayudar a los analistas e investigadores a clasificar los casos por varios atributos. Para filtrar alertas en el **Panel casos**, seleccione el control **filtro** . Puede filtrar los casos por uno o más atributos:

- **Estado**: Seleccione uno o más valores de estado para filtrar la lista de casos. Las opciones son *activo* y *cerrado*.
- **Caso abierto**: seleccione las fechas de inicio y finalización para cuando se abrió el caso.
- **Última actualización**: seleccione las fechas de inicio y finalización para cuando se actualizó el caso.

## <a name="investigate-a-case"></a>Investigar un caso

Es fundamental realizar una investigación más profunda de las alertas de administración de riesgos de Insider para llevar a cabo las acciones correctivas adecuadas. Los casos de administración de riesgos de Insider son la herramienta de administración central para profundizar en el historial de actividad de los riesgos de usuario y en los detalles de las alertas, y explorar el contenido y los mensajes expuestos a los riesgos. Los analistas de riesgos y investigadores también usan casos para centralizar comentarios y notas de revisión y para procesar la resolución de casos.

Al seleccionar un caso, se abren las herramientas de administración de casos y se permite a los analistas e investigadores profundizar en los detalles de los casos.

### <a name="case-overview"></a>Introducción al caso

La ficha **información general del caso** resume la actividad de alerta y el historial de nivel de riesgo en el caso. 

- El widget **alertas** muestra la coincidencia de la Directiva con el caso, incluido el estado de la alerta, la gravedad del riesgo de la alerta y el momento en que se detectó la alerta. 
- El gráfico **historial de nivel de riesgo** muestra el nivel de riesgo de usuario en los últimos 30 días. El gráfico de líneas permite a los analistas y investigadores ver rápidamente la tendencia del riesgo global del usuario a lo largo del tiempo. 
- El widget de **contenido de actividad de riesgos** resume los tipos de datos y el contenido que se incluyen en las alertas que se agregan al caso. Este widget proporciona una vista completa de todo el conjunto de datos y contenido en riesgo en el caso.

El panel de **detalles de caso** está disponible en todas las pestañas de administración de casos y resume los detalles de casos para investigadores y analistas de riesgos. Incluye las siguientes áreas:

- **Nombre de caso**: nombre del caso, prefijo de un número de secuencia de caso generado automáticamente y el nombre del riesgo asociado con la plantilla de directiva que coincide con la primera alerta confirmada. 
- **Estado del caso**: estado actual del caso, ya sea *activo* o *cerrado*.
- **Puntuación de riesgo del usuario**: el nivel de riesgo calculado actual del usuario para el caso. Esta puntuación se calcula cada 24 horas y usa los resultados de riesgo de alertas de todas las alertas activas asociadas al usuario.
- **Alertas confirmadas**: lista de alertas del usuario confirmada para el caso.
- **Contenido relacionado**: lista de contenido, ordenada por tipos y orígenes de contenido. Por ejemplo, por caso de contenido de alertas en SharePoint Online, es posible que aparezcan nombres de archivo o carpeta asociados a la actividad de riesgo para las alertas en el caso.

![Detalles de casos de administración de riesgos de Insider](../media/insider-risk-case-details.png)

### <a name="alerts"></a>Alertas

La ficha **alertas** resume las alertas actuales incluidas en el caso. Se pueden agregar nuevas alertas a un caso existente y se agregarán a la cola de **alertas** a medida que se asignen. Los siguientes atributos de alerta aparecen en la cola:

- Estado
- Severity
- Tiempo detectado

Seleccione una alerta de la cola para mostrar la página de detalles de la **alerta** .

Use el control de búsqueda para buscar nombres de alertas de texto específico y use el filtro de alerta para ordenar los casos por los siguientes atributos:

- Estado
- Severity
- Tiempo detectado, fecha de inicio y fecha de finalización

Use el control Filter para filtrar alertas con varios atributos, como:

- **Estado**: Seleccione uno o más valores de estado para filtrar la lista de alertas. Las opciones se *confirman*, *desechan*, *necesitan revisión*y se *resuelven*.
- **Gravedad**: Seleccione uno o más niveles de gravedad de riesgo de alerta para filtrar la lista de alertas. Las opciones son *alta*, *media*y *baja*.
- **Tiempo detectado**: seleccione las fechas de inicio y finalización para cuando se creó la alerta.
- **Directiva**: Seleccione una o más directivas para filtrar las alertas generadas por las directivas seleccionadas.

### <a name="user-activity"></a>Actividad de usuario

La ficha de **actividad de usuario** es una de las herramientas más eficaces para el análisis y la investigación de riesgos internos para los casos de la solución de administración de riesgos de Insider. Esta ficha está estructurada para habilitar la revisión rápida de un caso, incluida una escala de tiempo histórica de todas las alertas, todos los detalles de las alertas, la puntuación de riesgo actual para el usuario en el caso y los controles para emprender acciones efectivas que contengan los riesgos en el caso.

![Actividad de usuario de administración de riesgos de Insider](../media/insider-risk-user-activities.png)

1. **Filtros de tiempo de fecha y de ventana**: de forma predeterminada, los últimos seis meses de alertas confirmadas en el caso se muestran en el gráfico de actividad del usuario. Puede filtrar fácilmente la vista de gráfico con los controles deslizantes situados en ambos extremos de la ventana gráfico o definiendo fechas de inicio y finalización específicas en el control de filtro de gráfico.
2. **Actividad de alertas de riesgos y detalles**: las actividades de riesgo se muestran visualmente como burbujas de color en el gráfico de actividad del usuario. Las burbujas se crean para diferentes categorías de riesgo y el tamaño de la burbuja es proporcional al número de actividades de riesgo para la categoría. Seleccione una burbuja para mostrar los detalles de cada actividad de riesgo. Entre los detalles se incluyen:
    - **Fecha** de la actividad de riesgo.
    - Categoría de la **actividad de riesgo**. Por ejemplo, *correo electrónico con datos adjuntos enviados fuera de la organización* o *archivos descargados desde SharePoint Online*.
    - **Puntuación de riesgo** para la alerta. Esta puntuación es la puntuación numérica para el nivel de gravedad de riesgo de alertas.
    - Número de eventos asociados a la alerta. También se encuentran disponibles vínculos a cada archivo o correo electrónico asociado con la actividad de riesgo.
3. **Leyenda de actividad de riesgo**: en la parte inferior del gráfico de actividad de usuario, una leyenda con código de color ayuda a determinar rápidamente la categoría de riesgo para cada alerta.
4. **Actividad de riesgo cronología**: se enumera toda la cronología de todas las alertas de riesgo asociadas con el caso, incluidos todos los detalles disponibles en la burbuja de alerta correspondiente.
5. **Acciones de casos**: las opciones para resolver el caso se muestran en la barra de herramientas acción de escenario. Puede resolver un caso, enviar un aviso por correo electrónico al usuario o remitir el caso a un usuario o a una investigación del usuario.

### <a name="content-explorer"></a>Explorador de contenido

La ficha **Explorador de contenido** permite a los analistas de riesgos y a los investigadores revisar las copias de todos los archivos individuales y los mensajes de correo electrónico asociados a las alertas de riesgos. Por ejemplo, si se crea una alerta cuando un usuario descarga cientos de archivos de SharePoint Online y la actividad desencadena una alerta de Directiva, todos los archivos descargados para la alerta se capturan y se copian en el caso de administración de riesgos de Insider desde orígenes de almacenamiento originales.

El explorador de contenido es una herramienta eficaz con características básicas y avanzadas de búsqueda y filtrado. Para obtener más información sobre el uso del explorador de contenido, vea el [Explorador de contenido de administración de riesgos de Insider](insider-risk-management-content-explorer.md).

![Explorador de contenido de caso de administración de riesgos de Insider](../media/insider-risk-content-explorer.png)

### <a name="case-notes"></a>Notas del caso

La ficha **notas del caso** es donde los analistas de riesgos y los investigadores comparten comentarios, comentarios e información sobre su trabajo en el caso. Las notas son adiciones permanentes a un caso y no se pueden editar ni eliminar después de guardar la nota. Cuando se crea un caso desde una alerta, los comentarios introducidos en el cuadro de diálogo **confirmar ADVERTENCIA y crear caso de riesgo de Insider** se agregan automáticamente como una nota de caso.

El panel de notas de caso muestra las notas del usuario que creó la nota y el tiempo que ha transcurrido desde que se guardó la nota. Para buscar en el campo de texto Nota de caso una palabra clave específica, use el botón **Buscar** del panel caso y escriba una palabra clave específica.

Para agregar una nota a un caso:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **casos** .
2. Seleccione un caso y, a continuación, seleccione la pestaña **notas de caso** .
3. Seleccione **Agregar nota de caso**.
4. En el cuadro de diálogo **Agregar nota de caso** , escriba la nota para el caso. Seleccione **Guardar** para agregar la nota al caso o seleccione **Cancelar** cierre sin guardar la nota en el caso.

### <a name="contributors"></a>Colaboradores

La ficha **colaboradores** , en caso de que los analistas de riesgos y los investigadores puedan agregar otros revisores al caso. De forma predeterminada, todos los usuarios asignados a los roles de **analistas de administración de riesgos** de Insider y **investigadores de administración de riesgos de Insider** se enumeran como colaboradores para cada caso activo y cerrado.

Todos los casos de administración de riesgos de Insider deben administrarse con los controles de acceso adecuados en su ubicación para mantener la confidencialidad y la integridad de la investigación. Para ayudar a mantener el control de acceso de los casos, a los usuarios se les asignan dos tipos de acceso a los casos:

- **Acceso permanente**: el acceso permanente se concede automáticamente a los usuarios con los roles de **analistas de administración de riesgos** de Insider y **investigadores de administración de riesgos de Insider** cuando se crea el caso desde una alerta. El acceso permanente concede un control total sobre el caso durante la vigencia del caso y concede la capacidad de agregar otros colaboradores de caso.
- **Acceso temporal**: los colaboradores solo conceden acceso temporal a los usuarios que tienen acceso permanente en el caso. Normalmente, este nivel de acceso se concede al usuario que necesita agregar notas a un caso. Los colaboradores con acceso temporal tienen todos el control de la administración de casos excepto:
    - Permiso para confirmar o descartar alertas
    - Permiso para editar los colaboradores en los casos
    - Permiso para ver archivos y mensajes en el explorador de contenido

Para agregar un colaborador a un caso:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **casos** .
2. Seleccione un caso y, a continuación, seleccione la pestaña **colaboradores** .
3. Seleccione **Agregar colaborador**.
4. En el cuadro de diálogo **Agregar colaborador** , empiece a escribir el nombre del usuario que desea agregar y, a continuación, seleccione el usuario de la lista de usuarios sugeridos. Esta lista se genera a partir de Azure Active Directory de su suscripción de inquilino.
5. En el cuadro de diálogo **Agregar colaborador** , seleccione el nivel de acceso para el colaborador. Puede seleccionar **permanente** o **temporal**.
6. Seleccione **Agregar** para agregar al usuario como colaborador o **Cancelar** cierre el cuadro de diálogo sin agregar el usuario como colaborador.

## <a name="case-actions"></a>Acciones de caso

Los analistas de riesgos y los investigadores pueden tomar medidas en un caso en uno de varios métodos, en función de la gravedad del caso, el historial del riesgo del usuario y las directrices de riesgo de la organización. En algunas situaciones, es posible que deba remitir un caso a un usuario o a una investigación de datos para colaborar con otras áreas de la organización y profundizar en las actividades de riesgo. La administración de riesgos de Insider se integra estrechamente con otras soluciones de cumplimiento de Microsoft 365 para ayudarle con la administración de la resolución de un extremo a otro.

### <a name="send-email-notice"></a>Notificación de envío de correo electrónico

En la mayoría de los casos, las acciones del usuario que crean alertas de riesgo de Insider son involuntarias o accidentales. El envío de un aviso de aviso al usuario por correo electrónico es un método eficaz para documentar la revisión y la acción de los casos, así como un método para recordar a los usuarios las directivas corporativas o dirigirlos a un entrenamiento de actualización. Los avisos se generan a partir de [plantillas de aviso](insider-risk-management-notices.md) creadas para la infraestructura de administración de riesgos de Insider.

Es importante recordar que, al enviar un aviso de correo electrónico a un usuario, ***no*** se resuelve el caso como *cerrado*. En algunos casos, es posible que desee dejar un caso abierto después de enviar un aviso a un usuario para que busque otras actividades de riesgo sin abrir un nuevo caso. Si desea resolver un caso después de enviar un aviso, debe seleccionar el paso **resolver caso** como un paso posterior tras enviar un aviso.

Para enviar un aviso al usuario asignado a un caso:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **casos** .
2. Seleccione un caso y, a continuación, seleccione el botón **Enviar aviso de correo electrónico** en la barra de herramientas acción de escenario.
3. En el cuadro de diálogo **notificación de correo electrónico de envío** , seleccione el control desplegable **Seleccionar plantilla de notificación** para seleccionar la plantilla de aviso del aviso. Esta selección rellenará previamente el resto de los campos de la notificación.
4. Revise los campos de aviso y actualice según corresponda. Los valores especificados aquí reemplazarán los valores de la plantilla.
5. Seleccione **Enviar** para enviar el aviso al usuario o seleccione **Cancelar** para cerrar el cuadro de diálogo sin enviar el aviso al usuario. Se agregan todos los avisos enviados a la cola de notas de casos en el panel de **notas de caso** .

### <a name="escalate-for-investigation"></a>Escalar para investigación

Remitir el caso de la investigación del usuario en situaciones en las que se necesita una revisión legal adicional para la actividad de riesgo del usuario. Esta escalado abre un nuevo caso de exhibición avanzada de documentos electrónicos en su organización de Microsoft 365. EDiscovery avanzado proporciona un flujo de trabajo de un extremo a otro para preservar, recopilar, revisar, analizar y exportar contenido que responde a las investigaciones legales internas y externas de la organización. También permite que su equipo legal administre todo el flujo de trabajo de notificación de retención legal para comunicarse con los custodios que participan en un caso. La asignación de un revisor como custodio en un caso de eDiscovery avanzado creado a partir de un caso de administración de riesgos de Insider ayuda al equipo legal a tomar las medidas adecuadas y administrar la preservación del contenido. Para obtener más información sobre los casos avanzados de eDiscovery, vea [información general sobre EDiscovery avanzado en Microsoft 365](overview-ediscovery-20.md).

Para remitir un caso a una investigación de usuario:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **casos** .
2. Seleccione un caso y, a continuación, seleccione el botón **remitir a investigación** en la barra de herramientas acción de escenario.
3. En el cuadro de diálogo **escalar para investigación** , escriba un nombre para la nueva investigación de usuario. Si es necesario, escriba notas sobre el caso y seleccione **escalar**.
5. Seleccione **confirmar** para crear el caso de investigación del usuario o seleccione **Cancelar** para cerrar el cuadro de diálogo sin crear un nuevo caso de investigación del usuario.

Una vez que el caso de administración de riesgos de Insider se ha remitido a un nuevo caso de investigación de **eDiscovery**usuario, puede revisar el nuevo caso en el  >  área**Advanced** eDiscovery del centro de cumplimiento de Microsoft 365.

### <a name="share-a-case"></a>Compartir un caso

Compartir un caso de administración de riesgos de Insider permite que los investigadores y las revisiones colaboren fácilmente con otras partes interesadas del cumplimiento de su organización. Puede compartir rápidamente un vínculo a un caso de administración de riesgos de Insider con partes interesadas externas del área de administración de casos. Para acceder al caso de la administración de riesgos de Insider desde el vínculo, las partes interesadas deben incluirse en cualquiera de los grupos de roles de administración de riesgos de Insider.

Están disponibles las siguientes opciones de uso compartido: 

- **ServiceNow**: Tras configurar el conector de servicenow de 365 de Microsoft para su organización de Microsoft 365, puede compartir fácilmente un vínculo al caso, abrir un incidente o solicitar un cambio con su organización de ServiceNow. Para compartir el caso con ServiceNow, seleccione **compartir**  >  **ServiceNow** en la acción del caso. La integración de ServiceNow con la administración de riesgos de Insider admite incluye la siguiente información de casos y acciones:
    - **Nombre de tarea**: el nombre de la nueva tarea de ServiceNow.
    - **Descripción**de la tarea: Descripción de la nueva tarea de ServiceNow. Este campo de Descripción editable incluye automáticamente un vínculo al caso de administración de riesgos de Insider.
    - **Tipo de tarea**: el tipo de tarea para la nueva tarea de ServiceNow, ya sea *incidente* o *cambio de solicitud*.
    - **Priority**: prioridad para la nueva tarea de ServiceNow, ya sea *planificación*, *baja*, *moderada*, *alta*o *crítica*.
    - **Fecha de vencimiento**: fecha solicitada para completar la tarea de ServiceNow.

![Uso compartido de administración de riesgos de Insider con ServiceNow](../media/insider-risk-share-servicenow.png)

- **Email**: comparte un vínculo al caso de administración de riesgos de Insider en un correo electrónico. Puede elegir cualquier cliente de correo electrónico configurado localmente con esta opción de uso compartido. Para compartir el vínculo de caso con correo electrónico, seleccione **compartir**  >  **correo electrónico** en la barra de herramientas de acciones de escenario.
- **Copiar vínculo**: copia un vínculo al caso de administración de riesgos de Insider en el portapapeles. Para copiar el vínculo de caso al portapapeles, seleccione **compartir**  >  **Copiar vínculo** en la barra de herramientas de acciones de escenario.

### <a name="resolve-the-case"></a>Resolver el caso

Una vez que los analistas de riesgos y los investigadores han completado su revisión e investigación, se puede resolver un caso para que actúe en todas las alertas incluidas actualmente en el caso. La resolución de un caso agrega una clasificación de resolución, cambia el estado de caso a *cerrado*y los motivos de acción de resolución se agregan automáticamente a la cola de notas de casos en el panel de **notas de caso** . Los casos se resuelven como:

- **Benigno**: clasificación para los casos en los que las alertas de coincidencia de Directiva se evalúan como de bajo riesgo, no grave o falso positivo.
- **Infracción de directiva confirmada**: clasificación de casos en los que las alertas de coincidencia de la Directiva se evalúan como peligroso, serio o como resultado de un intento malintencionado.

Para resolver un caso:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **casos** .
2. Seleccione un caso y, a continuación, seleccione el botón **resolver caso** en la barra de herramientas de acciones de escenario.
3. En el cuadro de diálogo **resolver caso** , seleccione el control desplegable **resolver como** para seleccionar la clasificación de resolución para el caso. Las opciones son infracción de directiva **benigna** o **confirmada**.
4. En el cuadro de diálogo **resolver caso** , especifique los motivos de la clasificación de resolución en el campo de texto **acción tomada** .
5. Seleccione **resolver** para cerrar el caso o seleccione **Cancelar** cierre el cuadro de diálogo sin resolver el caso.
