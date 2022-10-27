---
title: Investigación de actividades de administración de riesgos internos
description: Más información sobre la investigación de actividades de administración de riesgos internos en Microsoft Purview
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
ms.openlocfilehash: e35809f3cf95bd9995c21b638e5a4c1fef8027df
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68734921"
---
# <a name="investigate-insider-risk-management-activities"></a>Investigación de actividades de administración de riesgos internos

>[!IMPORTANT]
>Administración de riesgos internos de Microsoft Purview correlaciona varias señales para identificar posibles riesgos internos malintencionados o involuntarios, como el robo de IP, la pérdida de datos y las infracciones de seguridad. La administración de riesgos internos permite a los clientes crear directivas para administrar la seguridad y el cumplimiento. Creados con privacidad por diseño, los usuarios se seudonimizan de forma predeterminada y los controles de acceso basados en roles y los registros de auditoría están en su lugar para ayudar a garantizar la privacidad del nivel de usuario.

La investigación de actividades de usuario potencialmente arriesgadas es un primer paso importante para minimizar los riesgos internos para su organización. Estos riesgos pueden ser actividades que generan alertas a partir de directivas de administración de riesgos internos. También pueden ser riesgos de actividades relacionadas con el cumplimiento que detectan las directivas, pero no crean inmediatamente alertas de administración de riesgos internos para los usuarios. Puede investigar estos tipos de actividades mediante los informes de **actividad de usuario (versión preliminar)** o con el **panel Alerta**.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="user-activity-reports"></a>Informes de actividad de usuario

Los informes de actividad de usuario permiten examinar actividades potencialmente de riesgo (para usuarios específicos y durante un período de tiempo definido) sin tener que asignar estas actividades, de forma temporal o explícita, a una directiva de administración de riesgos internos. En la mayoría de los escenarios de administración de riesgos internos, los usuarios se definen explícitamente en las directivas y pueden tener alertas de directiva (en función de los eventos desencadenantes) y puntuaciones de riesgo asociadas a las actividades. Pero en algunos escenarios, es posible que desee examinar las actividades de los usuarios que no están definidas explícitamente en una directiva. Estas actividades pueden ser para los usuarios a los que ha recibido una sugerencia sobre el usuario y las actividades potencialmente de riesgo, o para los usuarios que normalmente no necesitan asignarse a una directiva de administración de riesgos internos.

Después de configurar los indicadores en la página **Configuración** de administración de riesgos internos, se detecta la actividad del usuario para la actividad potencialmente de riesgo asociada a los indicadores seleccionados. Esta configuración significa que toda la actividad detectada para los usuarios está disponible para su revisión, independientemente de si tiene un evento desencadenante o si crea una alerta. Los informes se crean por usuario y pueden incluir todas las actividades durante un período personalizado de 90 días. No se admiten varios informes para el mismo usuario.

Después de examinar actividades potencialmente peligrosas, los investigadores pueden descartar las actividades de un usuario individual como benignas. También pueden compartir o enviar por correo electrónico un vínculo al informe con otros investigadores, o bien optar por asignar usuarios (de forma temporal o explícita) a una directiva de administración de riesgos internos. Los usuarios deben estar asignados al grupo de roles *Investigadores de Administración de riesgos* internos para ver la página **Informes de actividad de usuario** .  

![Información general sobre la actividad del usuario de administración de riesgos internos.](../media/insider-risk-user-activity-report-overview.png)

Para empezar, seleccione **Administrar informes** en la sección **Investigar actividad de usuario** de la página **Información general sobre** la administración de riesgos internos. 

Para ver las actividades de un usuario, seleccione primero **Crear informe de actividad de usuario** y complete los campos siguientes en el panel **Nuevo informe de actividad de usuario** :

- **Usuario**: busque un usuario por nombre o dirección de correo electrónico.
- **Fecha de inicio**: use el control de calendario para seleccionar la fecha de inicio de las actividades del usuario.
- **Fecha de finalización**: use el control de calendario para seleccionar la fecha de finalización de las actividades del usuario. La fecha de finalización seleccionada debe ser mayor que dos días después de la fecha de inicio seleccionada y no superior a 90 días a partir de la fecha de inicio seleccionada.
 
Los informes nuevos suelen tardar hasta 10 horas en estar listos para su revisión. Cuando el informe esté listo, verá *Informe listo* en la columna **Estado** de la página Informe de actividad de usuario. Seleccione el usuario para ver el informe detallado:

![Informe de actividad de usuario de administración de riesgos internos](../media/insider-risk-user-activity-report.png)

El **informe de actividad de usuario** del usuario seleccionado contiene las pestañas **Actividad de usuario**, **Explorador de actividad** y **Pruebas forenses (versión preliminar** ):

- **Actividad del usuario**: use esta vista de gráfico para investigar actividades potencialmente de riesgo y ver las actividades potencialmente relacionadas que se producen en secuencias. Esta pestaña está estructurada para permitir la revisión rápida de un caso, incluida una escala de tiempo histórica de todas las actividades, los detalles de la actividad, la puntuación de riesgo actual del usuario en el caso, la secuencia de eventos de riesgo y los controles de filtrado para ayudar con los esfuerzos de investigación.
- **Explorador de actividades**: esta pestaña proporciona a los investigadores de riesgos una herramienta de análisis completa que proporciona información detallada sobre las actividades. Con el Explorador de actividades, los revisores pueden revisar rápidamente una escala de tiempo de la actividad de riesgo detectada e identificar y filtrar todas las actividades potencialmente de riesgo asociadas a alertas. Para más información sobre el uso del Explorador de actividad, consulte la sección *Explorador de actividad* más adelante en este artículo.

## <a name="alert-dashboard"></a>Panel de alertas

Las alertas de administración de riesgos internos se generan automáticamente mediante indicadores de riesgo definidos en las directivas de administración de riesgos internos. Estas alertas proporcionan a los analistas e investigadores de cumplimiento una visión general del estado actual del riesgo y permiten a su organización evaluar y tomar medidas para detectar posibles riesgos. De forma predeterminada, las directivas generan una cierta cantidad de alertas de gravedad baja, media y alta, pero puede [aumentar o reducir el volumen de alertas](insider-risk-management-settings.md#alert-volume) para satisfacer sus necesidades. Además, puede configurar el umbral de [alerta para los indicadores de directiva al](insider-risk-management-settings.md#indicator-level-settings-preview) crear una nueva directiva con la herramienta de creación de directivas.

Consulte el vídeo Experiencia de evaluación de prioridades de [Insider Risk Management](https://www.youtube.com/watch?v=KgmpxBLJLPI) para obtener información general sobre cómo las alertas proporcionan detalles, contexto y contenido relacionado para la actividad de riesgo y cómo hacer que el proceso de investigación sea más eficaz.

El **panel de alertas** de riesgo interno permite ver y actuar sobre las alertas generadas por las directivas de riesgo internos. Cada widget de informe muestra información de los últimos 30 días.

- **Total de alertas que necesitan revisión**: se muestra el número total de alertas que necesitan revisión y evaluación de prioridades, incluido un desglose por gravedad de alerta.
- **Alertas abiertas en los últimos 30 días**: el número total de alertas creadas por la directiva coincide en los últimos 30 días, ordenado por niveles de gravedad de alertas altos, medios y bajos.
- **Tiempo medio para resolver alertas**: un resumen de las estadísticas de alertas útiles:
  - Tiempo medio para resolver alertas de gravedad alta, expresado en horas, días o meses.
  - Tiempo medio para resolver alertas de gravedad media, expresado en horas, días o meses.
  - Tiempo medio para resolver alertas de gravedad baja, expresado en horas, días o meses.

![Panel de alertas de administración de riesgos internos](../media/insider-risk-alerts-dashboard.png)

> [!NOTE]
> La administración de riesgos internos usa la limitación de alertas integrada para ayudar a proteger y optimizar su investigación de riesgos y experiencia de revisión. Esta limitación protege frente a problemas que pueden dar lugar a una sobrecarga de alertas de directiva, como conectores de datos mal configurados o directivas de prevención de pérdida de datos. Como resultado, es posible que haya un retraso al mostrar nuevas alertas para un usuario.

## <a name="alert-status-and-severity"></a>Estado de alerta y gravedad

Puede clasificar las alertas en uno de los siguientes estados:

- **Confirmado**: una alerta confirmada y asignada a un caso nuevo o existente.
- **Descartado**: una alerta descartada como benigna en el proceso de triaje. Puede proporcionar un motivo para el despido de la alerta e incluir notas que están disponibles en el historial de alertas del usuario para proporcionar contexto adicional para futuras referencias o para otros revisores. Los motivos pueden ir desde las actividades esperadas, los eventos no afectados, simplemente la reducción del número de actividades de alerta para el usuario o un motivo relacionado con las notas de alerta. Las opciones de clasificación de motivos incluyen *actividad que se espera para este usuario*, *la actividad es lo suficientemente impactante como para que yo investigue más* y *las alertas para este usuario contienen demasiada actividad*.
- **Revisión de necesidades**: una nueva alerta en la que aún no se han realizado acciones de evaluación de prioridades.
- **Resuelto**: alerta que forma parte de un caso cerrado y resuelto.

Las puntuaciones de riesgo de alerta se calculan automáticamente a partir de varios indicadores de actividad de riesgo. Estos indicadores incluyen el tipo de actividad de riesgo, el número y la frecuencia de la aparición de la actividad, el historial de la actividad de riesgo de los usuarios y la adición de riesgos de actividad que pueden aumentar la gravedad de la actividad potencialmente riesgosa. La puntuación de riesgo de alerta controla la asignación mediante programación de un nivel de gravedad de riesgo para cada alerta y no se puede personalizar. Si las alertas siguen sin administrarse y las actividades de riesgo continúan acumulando en la alerta, el nivel de gravedad del riesgo puede aumentar. Los analistas e investigadores de riesgos pueden usar la gravedad del riesgo de alertas para ayudar a evaluar las alertas de acuerdo con las directivas y estándares de riesgo de su organización.

Los niveles de gravedad del riesgo de alerta son:

- **Gravedad alta**: las actividades y los indicadores potencialmente peligrosos de la alerta suponen un riesgo significativo. Las actividades de riesgo asociadas son graves, repetitivas y se relacionan fuertemente con otros factores de riesgo significativos.
- **Gravedad media**: las actividades y los indicadores potencialmente peligrosos de la alerta suponen un riesgo moderado. Las actividades de riesgo asociadas son moderados, frecuentes y tienen cierta correlación con otros factores de riesgo.
- **Gravedad baja**: las actividades y los indicadores potencialmente peligrosos de la alerta suponen un riesgo menor. Las actividades de riesgo asociadas son menores, más poco frecuentes y no se relacionan con otros factores de riesgo significativos.

## <a name="filter-alerts-on-the-alert-dashboard"></a>Filtrar alertas en el panel de alertas

Según el número y el tipo de directivas activas de administración de riesgos internos de su organización, revisar una larga cola de alertas puede ser todo un reto. El uso de filtros de alertas puede ayudar a los analistas e investigadores a ordenar las alertas por varios atributos. 

Para filtrar alertas en el **panel Alertas**, seleccione el control **Filtro** . Puede filtrar las alertas por uno o varios atributos:

- **Estado**: seleccione uno o varios valores de estado para filtrar la lista de alertas. Las opciones son *Confirmada*, *Descartada*, *Falta por revisar*, y *Resuelta*.
- **Gravedad**: seleccione uno o varios niveles de gravedad de riesgo de alerta para filtrar la lista de alertas Las opciones son *Alta*, *Media* y *Baja*.
- **Hora detectada**: seleccione las fechas de inicio y finalización para cuando se creó la alerta. Este filtro busca alertas entre UTC 00:00 en la fecha de inicio y UTC 00:00 en la fecha de finalización. Para filtrar las alertas de un día específico, escriba la fecha del día en el campo **Fecha de inicio** y la fecha del día siguiente en el campo **Fecha de finalización** .
- **Directiva**: seleccione una o varias directivas para filtrar las alertas generadas por las directivas seleccionadas.
- **Factores de riesgo**: seleccione uno de los factores de riesgo más para filtrar la lista de alertas. Las opciones son *Actividades de filtración acumulativas*, *Las actividades incluyen el contenido prioritario*, *las actividades de secuencia* y *las actividades incluyen dominios no permitidos*.

## <a name="search-alerts-on-the-alert-dashboard"></a>Búsqueda de alertas en el panel de alertas

Para buscar una palabra específica en el nombre de la alerta, seleccione el control **Búsqueda** y escriba la palabra que desea buscar. Los resultados de búsqueda muestran cualquier alerta de directiva que contenga la palabra definida en la búsqueda.

## <a name="dismiss-multiple-alerts-preview"></a>Descartar varias alertas (versión preliminar)

Puede ayudar a ahorrar tiempo de evaluación para que los analistas e investigadores descarten inmediatamente varias alertas a la vez. La opción **Descartar alertas** de la barra de comandos le permite seleccionar una o varias alertas con un estado *De necesidad de revisión* en el panel y descartar rápidamente estas alertas como benignas según corresponda en el proceso de evaluación de prioridades. Puede seleccionar hasta 400 alertas para descartarlas a la vez.

Para descartar una alerta de riesgo interno, siga estos pasos:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos** internos y seleccione la pestaña **Alertas**.
2. En el **panel Alertas**, seleccione la alerta (o alertas) con el estado *Necesita revisión* que desea descartar.
3. En la barra de comandos Alertas, seleccione **Descartar alertas**.
4. En el panel **Descartar detalles de alertas** , puede revisar los detalles de usuario y directiva asociados a las alertas seleccionadas.
5. Seleccione **Descartar alertas** para resolver las alertas como benignas o seleccione **Cancelar** para cerrar el panel de detalles sin descartar las alertas.

## <a name="triage-alerts"></a>Evaluación de las alertas

Para evaluar una alerta de riesgo interno, complete los pasos siguientes:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos** internos y seleccione la pestaña **Alertas**.
2. En el **panel Alertas**, seleccione la alerta que desea evaluar.
3. En la página **Detalles de la alerta** , puede revisar la información sobre la alerta. Puede confirmar la alerta y crear un caso nuevo, confirmar la alerta y agregarla a un caso existente, o descartar la alerta. Esta página también incluye el estado actual de la alerta y el nivel de gravedad del riesgo de alerta, que se muestran como Alto, Medio o Bajo. El nivel de gravedad puede aumentar o disminuir con el tiempo si no se evalúa la alerta.

Use las secciones y pestañas siguientes en la página Detalles de la alerta para obtener más información sobre la alerta:

### <a name="headersummary-section"></a>Sección encabezado/resumen

Esta sección contiene información general sobre el usuario y la alerta. Esta información está disponible para contexto al revisar información detallada sobre la actividad de administración de riesgos detectada incluida en la alerta para el usuario:

- **Actividad que generó esta alerta**: muestra la principal actividad potencialmente de riesgo y la coincidencia de directivas durante el período de evaluación de la actividad que condujo a la generación de la alerta.
- **Evento desencadenante**: muestra el evento desencadenante más reciente que solicitó a la directiva que empezara a asignar puntuaciones de riesgo a la actividad del usuario. Si ha configurado la [integración con el cumplimiento de comunicaciones](/microsoft-365/compliance/communication-compliance-policies#integration-with-insider-risk-management-preview) para *las fugas de datos por parte de usuarios descontentos* o *infracciones de directivas de seguridad por directivas de usuarios descontentos* , el evento desencadenante de estas alertas se limitará a la actividad de cumplimiento de comunicaciones.
- **Perfil de usuario**: muestra información general sobre el usuario asignado a la alerta. Si la anonimización está habilitada, los campos nombre de usuario, dirección de correo electrónico, alias y organización se anonimizan.
- **Historial de alertas** de usuario: muestra una lista de alertas para el usuario durante los últimos 30 días. Incluye un vínculo para ver el historial de alertas completo del usuario.

Las alertas generadas a partir de directivas destinadas solo a actividades que incluyen [contenido prioritario](/microsoft-365/compliance/insider-risk-management-policies#prioritize-content-in-policies) incluyen la *única actividad con contenido de prioridad puntuada para esta* notificación de alerta en esta sección.

### <a name="all-risk-factors"></a>Todos los factores de riesgo

Esta pestaña abre el resumen de los factores de riesgo de la actividad de alerta del usuario. Los factores de riesgo pueden ayudarle a determinar el riesgo que supone la actividad de administración de riesgos de este usuario durante la revisión. Los factores de riesgo incluyen resúmenes de:

- **Principales actividades de filtración**: muestra las actividades de filtración con el número o eventos más altos de la alerta.
- **Actividades de filtración acumulativas**: muestra eventos asociados a actividades de filtración acumulativas.
- **Secuencias de actividades**: muestra las actividades potencialmente de riesgo detectadas asociadas a secuencias de riesgo.
- **Actividad inusual para este usuario**: muestra actividades específicas para el usuario que se consideran potencialmente de riesgo, ya que son inusuales y se apartan de sus actividades típicas.
- **Contenido de prioridad**: muestra actividades potencialmente de riesgo asociadas con el contenido prioritario.
- **Dominios no permitidos**: muestra actividades potencialmente de riesgo para eventos asociados a dominios no permitidos.
- **Acceso a registros de estado**: muestra actividades potencialmente de riesgo para los eventos asociados con el acceso a los registros de estado.
- **Uso de exploradores de riesgo**: muestra actividades potencialmente arriesgadas para eventos asociados con la navegación a sitios web potencialmente inadecuados.

Con estos filtros, solo verá alertas con los factores de riesgo anteriores, pero es posible que la actividad que generó una alerta no se incluya en ninguna de estas categorías. Por ejemplo, es posible que se haya generado una alerta que contiene actividades de secuencia simplemente porque el usuario copió un archivo en un dispositivo USB.

### <a name="content-detected"></a>Contenido detectado

La sección de la pestaña **Todos los factores de riesgo** incluye contenido asociado a las actividades de riesgo de la alerta y resume los eventos de actividad por áreas clave. Al seleccionar un vínculo de actividad, se abre el Explorador de actividades y se muestran más detalles sobre la actividad.

### <a name="activity-explorer"></a>Explorador de actividad

Esta pestaña abre el Explorador de actividad. Para obtener más información, consulte la sección Explorador de actividad de este artículo.

### <a name="user-activity"></a>Actividad de usuario

El gráfico **de actividad De usuario** es una de las herramientas más eficaces para el análisis de riesgos internos y la investigación de alertas y casos en la solución de administración de riesgos internos. Esta pestaña está estructurada para permitir la revisión rápida de todas las actividades de un usuario, incluida una escala de tiempo histórica de todas las alertas, detalles de alerta, la puntuación de riesgo actual del usuario y la secuencia de eventos de riesgo.

![Actividad de usuario de administración de riesgos internos](../media/insider-risk-user-activities.png)

1. **Filtros de tiempo**: de forma predeterminada, los últimos tres meses de actividades potencialmente arriesgadas se muestran en el gráfico Actividad del usuario. Puede filtrar fácilmente la vista de gráfico seleccionando las pestañas *6 Meses*, *3 Meses* o *1 Mes* en el gráfico de burbujas.
2. **Actividad y detalles de alertas de riesgo**: las actividades potencialmente de riesgo se muestran visualmente como burbujas de color en el gráfico Actividad del usuario. Las burbujas se crean para diferentes categorías de riesgo y. Seleccione una burbuja para mostrar los detalles de cada actividad potencialmente de riesgo. Los detalles incluyen:
    - **Fecha** de la actividad de riesgo.
    - Categoría de **actividad de riesgo**. Por ejemplo, *Email con datos adjuntos enviados fuera de la organización* o *archivos descargados de SharePoint Online*.
    - **Nivel de riesgo** de la alerta. Esta puntuación es la puntuación numérica para el nivel de gravedad del riesgo de alerta.
    - Número de eventos asociada a la alerta. También están disponibles vínculos a cada archivo o correo electrónico asociado a la actividad de riesgo.
3. **Filtros y ordenación (versión preliminar):**
    - **Categoría de riesgo**: Filtre las actividades por las siguientes categorías de riesgo: *actividades con puntuaciones de riesgo > 15 (a menos que en una secuencia)* y *actividades de secuencia*.
    - **Tipo de actividad**: Filtre las actividades por los siguientes tipos: *Access*, *Deletion*, *Collection*, *Exfiltration*, *Infiltration*, *Ofusscation* y *Security*.
    - **Ordenar por**: enumere la escala de tiempo de las actividades potencialmente de riesgo por *Fecha ocurrida* o *Puntuación de riesgo*.
4. **Secuencia de riesgo**: el orden cronológico de las actividades potencialmente arriesgadas es un aspecto importante de la investigación de riesgos y la identificación de estas actividades relacionadas es una parte importante de la evaluación del riesgo general para su organización. Las actividades de alerta relacionadas se muestran con líneas de conexión para resaltar que estas actividades están asociadas a un área de riesgo mayor. Las secuencias también se identifican en esta vista mediante un icono situado encima de las actividades de secuencia en relación con la puntuación de riesgo de la secuencia. Mantenga el puntero sobre el icono para ver la fecha y hora de la actividad de riesgo asociada a esta secuencia. Esta visión de las actividades puede ayudar a los investigadores literalmente a "conectar los puntos" para las actividades de riesgo que podrían haberse visto como eventos aislados o puntuales. Seleccione el icono o cualquier burbuja de la secuencia para mostrar los detalles de todas las actividades de riesgo asociadas. Los detalles incluyen:

    - **Nombre** de la secuencia.
    - **Intervalo de fechas** o **fechas** de la secuencia.
    - **Puntuación de riesgo** para la secuencia. Esta puntuación es la puntuación numérica de la secuencia de los niveles de gravedad de riesgo de alerta combinados para cada actividad relacionada de la secuencia.
    - **Número de eventos asociados a cada alerta de la secuencia**. También están disponibles vínculos a cada archivo o correo electrónico asociado a cada actividad potencialmente arriesgada.
    - **Mostrar actividades en secuencia**. Muestra la secuencia como una línea de resaltado en el gráfico de burbujas y expande los detalles de la alerta para mostrar todas las alertas relacionadas en la secuencia.

5. **Leyenda de actividad de riesgo**: en la parte inferior del gráfico de actividad del usuario, una leyenda codificada por colores le ayuda a determinar rápidamente la categoría de riesgo para cada alerta.
6. **Cronología de la actividad de riesgo**: se muestra la cronología completa de todas las alertas de riesgo asociadas al caso, incluidos todos los detalles disponibles en la burbuja de alerta correspondiente.
7. **Acciones de caso**: las opciones para resolver el caso se encuentran en la barra de herramientas de acciones de casos. Al ver un caso, puede resolver un caso, enviar un aviso de correo electrónico al usuario o escalar el caso para una investigación de datos o usuario.

## <a name="activity-explorer"></a>Explorador de actividad

> [!NOTE]
> El Explorador de actividades está disponible en el área de administración de alertas para los usuarios con eventos desencadenantes después de que esta característica esté disponible en su organización.

El Explorador de actividades proporciona a los investigadores y analistas de riesgos una herramienta de análisis completa que proporciona información detallada sobre las alertas. Con el Explorador de actividades, los revisores pueden revisar rápidamente una escala de tiempo de actividad potencialmente riesgosa detectada e identificar y filtrar todas las actividades de riesgo asociadas a alertas. 

Para filtrar alertas en el Explorador de actividad para obtener información de columna, seleccione el control Filtro. Puede filtrar las alertas por uno o varios atributos enumerados en el panel de detalles de la alerta. El explorador de actividades también admite columnas personalizables para ayudar a los investigadores y analistas a centrar el panel en la información más importante para ellos.

Use los filtros *Ámbito de actividad* y *Información de riesgo* para mostrar y ordenar las actividades y la información de las áreas siguientes.

- **Filtros de ámbito de actividad**: filtra todas las actividades puntuadas para el usuario.
  - Toda la actividad puntuada para este usuario
  - Solo actividad puntuada en esta alerta

- **Filtros de factor de** riesgo: filtros para la actividad del factor de riesgo aplicable a todas las directivas que asignan puntuaciones de riesgo Esto incluye toda la actividad de todas las directivas para los usuarios dentro del ámbito.
  - Actividad inusual
  - Incluye eventos con contenido prioritario
  - Incluye eventos con dominio no permitido
  - Actividades de secuencia
  - Actividades de filtración acumulativas
  - Actividades de acceso a registros de estado
  - Uso de explorador de riesgo

![Información general sobre el explorador de actividades de administración de riesgos internos](../media/insider-risk-activity-explorer.png)

Para usar el **Explorador de actividad**, complete los pasos siguientes:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos** internos y seleccione la pestaña **Alertas**.
2. En el **panel Alertas**, seleccione la alerta que desea evaluar.
3. En el **panel Detalles de alertas**, seleccione **Abrir vista expandida**.
4. En la página de la alerta seleccionada, seleccione la pestaña **Explorador de actividad** .

Al revisar las actividades en el Explorador de actividades, los investigadores y analistas pueden seleccionar una actividad específica y abrir el panel de detalles de la actividad. En el panel se muestra información detallada sobre la actividad que los investigadores y analistas pueden usar durante el proceso de evaluación de prioridades de alertas. La información detallada puede proporcionar contexto para la alerta y ayudar a identificar el ámbito completo de la actividad de riesgo que desencadenó la alerta.

Al seleccionar los eventos de una actividad de la escala de tiempo de actividad, es posible que el número de actividades que se muestran en el explorador no coincida con el número de eventos de actividad enumerados en la escala de tiempo. Ejemplos de por qué puede producirse esta diferencia:

- **Detección de filtración acumulativa**: la detección acumulativa de filtración analiza los registros de eventos, pero aplica un modelo que incluye la desduplicación de actividades similares para calcular el riesgo de filtración acumulativa. Además, también puede haber una diferencia en el número de actividades potencialmente arriesgadas que se muestran en el Explorador de actividades si ha realizado cambios en la directiva o configuración existentes. Por ejemplo, si modifica dominios permitidos o no permitidos o agrega nuevas exclusiones de tipos de archivo una vez creada una directiva y se han producido coincidencias de actividad potencialmente riesgosas, las actividades de detección de filtración acumulativa diferirán de los resultados antes de que cambie la directiva o la configuración. Los totales de actividad de detección de filtración acumulativa se basan en la configuración de directiva y configuración en el momento del cálculo y no incluyen actividades antes de los cambios de directiva y configuración.
- **Correos electrónicos a destinatarios externos**: a la actividad potencialmente arriesgada de los correos electrónicos enviados a destinatarios externos se le asigna una puntuación de riesgo en función del número de correos electrónicos enviados, que pueden no coincidir con los registros de eventos de actividad.

![Detalles del explorador de actividades de administración de riesgos internos.](../media/insider-risk-activity-explorer-details.png)

## <a name="create-a-case-for-an-alert"></a>Creación de un caso para una alerta

A medida que se revisa y se evalúa la alerta, puede crear un nuevo caso para investigar aún más la actividad potencialmente de riesgo. Para crear un caso para una alerta, siga estos pasos:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos** internos y seleccione la pestaña **Alertas**.
2. En el **panel Alertas**, seleccione la alerta para la que desea confirmar y cree un nuevo caso.
3. En el **panel Detalles de alertas**, seleccione **Acciones** > **Confirmar alertas & crear caso**.
4. En el cuadro de diálogo **Confirmar alerta y crear caso de riesgo interno** , escriba un nombre para el caso, seleccione los usuarios que desea agregar como colaboradores y agregue comentarios según corresponda. Los comentarios se agregan automáticamente al caso como nota de caso.
5. Seleccione **Crear caso** para crear un nuevo caso o seleccione **Cancelar** para cerrar el cuadro de diálogo sin crear un caso.

Una vez creado el caso, los investigadores y analistas pueden administrar y actuar sobre el caso. Para obtener más información, consulte el artículo sobre el [caso de administración de riesgos de Insider](insider-risk-management-cases.md) .

## <a name="retention-and-item-limits"></a>Límites de retención y elementos

A medida que la administración de riesgos internos alerta de la antigüedad, su valor para minimizar la actividad potencialmente riesgosa disminuye para la mayoría de las organizaciones. Por el contrario, los casos activos y los artefactos asociados (alertas, información, actividades) siempre son útiles para las organizaciones y no deben tener una fecha de expiración automática. Esto incluye todas las alertas y artefactos futuros en un estado activo para cualquier usuario asociado a un caso activo.

Para ayudar a minimizar el número de elementos anteriores que proporcionan un valor actual limitado, se aplican los siguientes límites y retención para alertas, casos e informes de usuario de administración de riesgos internos:

|**Elemento**|**Retención/límite**|
|:-------|:------------------|
|Alertas con estado de revisión de necesidades|120 días desde la creación de alertas y, a continuación, se elimina automáticamente|
|Casos activos (y artefactos asociados)|Retención indefinida, nunca expirar|
|Casos resueltos (y artefactos asociados)|120 días a partir de la resolución de casos y, a continuación, se elimina automáticamente|
|Número máximo de casos activos|100|
|Informes de actividades de usuario|120 días desde la detección de actividad y, a continuación, se elimina automáticamente|

## <a name="get-help-managing-your-insider-risk-alert-queue"></a>Obtener ayuda para administrar la cola de alertas de riesgo internos

Revisar, investigar y actuar sobre alertas internas potencialmente arriesgadas son partes importantes de la minimización de los riesgos internos en su organización. Tomar medidas rápidamente para minimizar el impacto de estos riesgos puede ahorrar tiempo, dinero y ramificaciones normativas o legales para su organización. En este proceso de corrección, el primer paso para revisar las alertas puede parecer la tarea más difícil para muchos analistas e investigadores. Dependiendo de sus circunstancias, es posible que se enfrente a algunos obstáculos menores al actuar sobre alertas internas potencialmente arriesgadas. Revise las siguientes recomendaciones y aprenda a optimizar el proceso de revisión de alertas.

### <a name="too-many-alerts-to-review"></a>Demasiadas alertas para revisar

Sentirse abrumado por el número de alertas generadas por las directivas de administración de riesgos internos podría resultar frustrante. El número de alertas se puede abordar rápidamente con pasos sencillos, en función de los tipos de volumen de alertas que reciba. Es posible que reciba demasiadas alertas válidas o que tenga demasiadas alertas obsoletas de bajo riesgo. Considere la posibilidad de realizar las siguientes acciones:

- **Ajustar las directivas de riesgo internos**: seleccionar y configurar la directiva de riesgo interno correcta es el método más básico para abordar el tipo y el volumen de alertas. A partir de la [plantilla de directiva](insider-risk-management-policies.md#policy-templates) adecuada, se centran los tipos de actividades de riesgo y las alertas que verá. Otros factores que pueden afectar al volumen de alertas son el tamaño del usuario y los grupos dentro del ámbito y el contenido y [los canales que se priorizan](insider-risk-management-policies.md#prioritize-content-in-policies). Considere la posibilidad de ajustar las directivas para ajustar estas áreas a lo que es más importante para su organización.
- **Modificar la configuración de riesgo interno**: la configuración de riesgo de Insider incluye una amplia variedad de opciones de configuración que pueden afectar al volumen y los tipos de alertas que recibirá. Estos incluyen [configuraciones para indicadores de directiva,](insider-risk-management-settings.md#indicators) [umbrales de indicadores](insider-risk-management-settings.md#indicator-level-settings-preview) y [períodos de tiempo de la directiva](insider-risk-management-settings.md#policy-timeframes). Considere la posibilidad de configurar opciones [de detecciones inteligentes](insider-risk-management-settings.md#intelligent-detections) para excluir tipos de archivo específicos y tipos de información confidencial, definir umbrales mínimos antes de que las directivas notifiquen las alertas de actividad y cambiar la configuración del volumen de alertas a una configuración inferior.
- **Habilitar la personalización de alertas insertadas (versión preliminar):** la [habilitación de la personalización de alertas insertadas](/microsoft-365/compliance/insider-risk-management-settings#inline-alert-customization-preview) permite a analistas e investigadores editar directivas rápidamente al revisar alertas. Pueden actualizar umbrales para la detección de actividad con recomendaciones de Microsoft, configurar umbrales personalizados o omitir el tipo de actividad que creó la alerta. Si esto no está habilitado, solo los usuarios asignados al grupo de roles *Insider Risk Management* pueden usar la personalización de alertas en línea.
- **Eliminación masiva de alertas cuando corresponda**: puede ayudar a ahorrar tiempo de evaluación de la evaluación para que los analistas e investigadores [descarten inmediatamente varias alertas](insider-risk-management-activities.md#dismiss-multiple-alerts-preview) a la vez. Puede seleccionar hasta 400 alertas para descartarlas a la vez.

### <a name="not-familiar-with-the-alert-triage-process"></a>No está familiarizado con el proceso de evaluación de prioridades de alertas

Investigar y actuar sobre alertas en la administración de riesgos internos es sencillo:

1. **Revise el [panel Alertas](insider-risk-management-activities.md#alert-dashboard) para ver las alertas con el estado Necesita revisar**. [Filtre](insider-risk-management-activities.md#filter-alerts-on-the-alert-dashboard) por *estado de* alerta si es necesario para ayudar a localizar estos tipos de alertas.
2. **Comience con las alertas con la gravedad más alta**. [Filtre](insider-risk-management-activities.md#filter-alerts-on-the-alert-dashboard) por *gravedad de* alerta si es necesario para ayudar a localizar estos tipos de alertas.
3. **Seleccione una alerta para detectar más información y revisar los detalles de la alerta**. Si es necesario, use el [Explorador de actividad](insider-risk-management-activities.md#activity-explorer) para revisar una escala de tiempo del comportamiento potencialmente peligroso asociado e identificar todas las actividades de riesgo de la alerta.
4. **Actuar sobre la alerta**. Puede confirmar y [crear un caso](insider-risk-management-activities.md#create-a-case-for-an-alert) para la alerta o descartar y resolver la alerta.

### <a name="resource-constraints-in-my-organization"></a>Restricciones de recursos en mi organización

Los usuarios modernos del área de trabajo suelen tener una amplia variedad de responsabilidades y demandas en su tiempo. Hay varias acciones que puede realizar para ayudar a abordar las restricciones de recursos:

- **Céntrese primero en los esfuerzos de analistas e investigadores en las alertas de mayor riesgo**. En función de las directivas, es posible que esté capturando actividades del usuario y generando alertas con distintos grados de impacto potencial en los esfuerzos de mitigación de riesgos. [Filtre las alertas](insider-risk-management-activities.md#filter-alerts-on-the-alert-dashboard) por gravedad y dé prioridad a las *alertas de gravedad alta* .
- **Asigne usuarios como analistas e investigadores**. Tener al usuario adecuado asignado a los roles adecuados es una parte importante del proceso de revisión de alertas de riesgo internos. Asegúrese de que ha asignado los usuarios adecuados a los grupos de roles *Insider Risk Management Analysts* y *Insider Risk Management Investigators* .  
- **Use características de riesgo internos automatizadas para ayudar a descubrir las actividades de mayor riesgo**. La [detección de secuencias de](insider-risk-management-policies.md#sequence-detection-preview) administración de riesgos internos y las características [de detección de filtración acumulativa](insider-risk-management-policies.md#cumulative-exfiltration-detection-preview) pueden ayudarle a detectar rápidamente riesgos más difíciles de encontrar en su organización. Considere la posibilidad de ajustar los [refuerzos de la puntuación de riesgo, la](insider-risk-management-settings.md#indicators) [detección de actividad de archivos](insider-risk-management-settings.md#file-activity-detection), [los dominios](insider-risk-management-settings.md#domains) y la [configuración mínima del umbral de indicador](insider-risk-management-settings.md#indicator-level-settings-preview) para las directivas.
