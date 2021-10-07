---
title: Investigar actividades de administración de riesgos de insider
description: Obtenga información sobre cómo investigar las actividades de administración de riesgos de insider en Microsoft 365
keywords: Microsoft 365, riesgo interno, administración de riesgos, cumplimiento
ms.localizationpriority: medium
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: d97ddce798a043f2f73bf3f6bf62fdb890fdfee1
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190814"
---
# <a name="investigate-insider-risk-management-activities"></a>Investigar actividades de administración de riesgos de insider

Investigar actividades de usuario arriesgadas es un primer paso importante para minimizar los riesgos de información interna para su organización. Estos riesgos pueden ser actividades que generan alertas de directivas de administración de riesgos internas o riesgos de actividades detectadas por las directivas, pero que no crean inmediatamente una alerta de administración de riesgos internas para los usuarios. Puede investigar estos tipos de actividades mediante los informes de actividad de usuario **(versión preliminar)** o con el panel **de alertas**.

## <a name="user-activity-reports-preview"></a>Informes de actividad de usuario (versión preliminar)

Los informes de actividad de usuario permiten examinar las actividades de usuarios específicos durante un período de tiempo definido sin tener que asignarlas de forma temporal o explícita a una directiva de administración de riesgos de insider. En la mayoría de los escenarios de administración de riesgos internas, los usuarios se definen explícitamente en las directivas y pueden tener alertas de directiva (según los eventos desencadenantes) y puntuaciones de riesgo asociadas con las actividades. Pero en algunos escenarios, es posible que desee examinar las actividades de los usuarios que no están definidas explícitamente en una directiva. Estas actividades pueden ser para usuarios que han recibido una sugerencia sobre el usuario y actividades potencialmente arriesgadas, o usuarios que normalmente no necesitan asignarse a una directiva de administración de riesgos de información interna.

Después de configurar los indicadores en  la página de administración de riesgos Configuración información interna, se detecta actividad de usuario para la actividad de riesgo asociada con los indicadores seleccionados. No es necesario configurar una directiva para que los informes de actividad de los usuarios detecten e informen actividades de riesgo por parte de los usuarios de la organización. Las actividades incluidas en los informes de actividad de usuario no requieren la activación de eventos para que se muestren las actividades. Esta configuración significa que toda la actividad detectada para el usuario está disponible para su revisión, independientemente de si tiene un evento desencadenante o si crea una alerta. Los informes se crean por usuario y pueden incluir todas las actividades durante un período personalizado de 90 días. No se admiten varios informes para el mismo usuario.

Después de examinar las actividades de un usuario, los investigadores pueden descartar actividades individuales como benignas, compartir o enviar por correo electrónico un vínculo al informe con otros investigadores, o elegir asignar al usuario de forma temporal o explícita a una directiva de administración de riesgos de insider. Los usuarios deben estar asignados al grupo de *roles Investigadores* de administración de riesgos de Insider para ver la **página Informes de actividad de** usuario.  

![Información general sobre el informe de actividad del usuario de administración de riesgos de Insider.](../media/insider-risk-user-activity-report-overview.png)

Para empezar, seleccione Administrar **informes**  en la sección Investigar actividad del usuario en la página Información general sobre la administración de riesgos **de** insider. Para ver las actividades de un usuario, seleccione primero **Crear informe** de actividad de usuario y complete los siguientes campos en el panel Nuevo informe de **actividad de** usuario:

- **Usuario:** buscar un usuario por nombre o dirección de correo electrónico
- **Fecha de inicio:** use el control de calendario para seleccionar la fecha de inicio de las actividades del usuario.
- **Fecha de finalización:** use el control de calendario para seleccionar la fecha de finalización de las actividades del usuario. La fecha de finalización seleccionada debe ser mayor que dos días después de la fecha de inicio seleccionada y no más de 90 días a partir de la fecha de inicio seleccionada.
Los nuevos informes suelen tardar hasta 10 horas antes de que estén listos para su revisión. Cuando el informe esté listo, verá Informe  *listo* en la columna Estado de la página Informe de actividad de usuario. Seleccione el usuario para ver el informe detallado:

![Informe de actividad de usuario de administración de riesgos de Insider.](../media/insider-risk-user-activity-report.png)

El **informe de actividad de usuario** del usuario seleccionado contiene las pestañas Actividad **de** usuario y Explorador **de** actividades:

- **Actividad de usuario:** use esta vista de gráfico para investigar actividades y ver las actividades potenciales que se producen en secuencias. Esta pestaña está estructurada para permitir la revisión rápida de un caso, incluida una escala de tiempo histórica de todas las actividades, detalles de actividad, la puntuación de riesgo actual para el usuario en el caso, la secuencia de eventos de riesgo y controles de filtrado para ayudar con los esfuerzos de investigación.
- **Explorador de** actividades: la **pestaña Explorador de** actividades proporciona a los investigadores de riesgos una herramienta de análisis completa que proporciona información detallada sobre las actividades. Con el explorador de actividades, los revisores pueden revisar rápidamente una escala de tiempo de actividad de riesgo detectada e identificar y filtrar todas las actividades de riesgo asociadas con alertas. Para obtener más información sobre cómo usar el explorador de actividades, vea la sección Explorador *de* actividades más adelante en este artículo.

## <a name="alert-dashboard"></a>Panel de alertas

Las alertas de administración de riesgos internos se generan automáticamente a través de los indicadores de riesgo definidos en las directivas de administración de riesgos internos. Estas alertas ofrecen a los investigadores y analistas de cumplimiento una vista actualizada del estado de riesgo actual y permiten que su organización valore y tome medidas en función de los riesgos detectados. De forma predeterminada, las directivas generan una cierta cantidad de alertas de gravedad baja, media y alta, pero puede aumentar o disminuir el volumen de alertas según sus necesidades. [](insider-risk-management-settings.md#alert-volume) Además, puede configurar el umbral de alerta para los indicadores de [directiva](insider-risk-management-settings.md#indicator-level-settings-preview) al crear una nueva directiva con la herramienta de creación de directivas.

Consulte el [vídeo Insider Risk Management Alerts Triage Experience](https://www.youtube.com/watch?v=KgmpxBLJLPI) para obtener información general sobre cómo las alertas proporcionan detalles, contexto y contenido relacionado para la actividad de riesgo y cómo hacer que el proceso de investigación sea más eficaz.

El panel de alertas de riesgo **interno** le permite ver y actuar en las alertas generadas por las directivas de riesgo de insider. Cada widget de informe muestra información de los últimos 30 días.

- **Total de alertas que necesitan revisión:** se muestra el número total de alertas que necesitan revisión y evaluación, incluido un desglose por gravedad de alerta.
- Alertas abiertas en los últimos **30** días: el número total de alertas creadas por la directiva coincide en los últimos 30 días, ordenadas por niveles de gravedad de alerta altos, medianos y bajos.
- **Tiempo promedio para resolver alertas:** un resumen de estadísticas de alertas útiles:
  - Tiempo medio para resolver alertas de gravedad alta, expresado en horas, días o meses.
  - Tiempo medio para resolver alertas de gravedad media, expresado en horas, días o meses.
  - Tiempo medio para resolver alertas de gravedad baja, expresado en horas, días o meses.

![Panel de alertas de administración de riesgos insider.](../media/insider-risk-alerts-dashboard.png)

> [!NOTE]
> La administración de riesgos internos usa la limitación de alertas integrada para ayudar a proteger y optimizar su investigación de riesgos y experiencia de revisión. Esta limitación protege contra problemas que pueden causar una sobrecarga de alertas de directiva, como conectores de datos mal configurados o directivas DLP. Como resultado, es posible que haya un retraso al mostrar nuevas alertas para un usuario.

## <a name="alert-status-and-severity"></a>Estado de alerta y gravedad

Puede realizar una triage de alertas en uno de los siguientes estados:

- **Confirmado:** una alerta confirmada y asignada a un caso nuevo o existente.
- **Descartado:** una alerta descartada como benigna en el proceso de evaluación.
- **Revisión de** necesidades: una nueva alerta en la que aún no se han realizado acciones de evaluación.
- **Resuelto:** una alerta que forma parte de un caso cerrado y resuelto.

Las puntuaciones de riesgo de alerta se calculan automáticamente a partir de varios indicadores de actividad de riesgo. Estos indicadores incluyen el tipo de actividad de riesgo, el número y la frecuencia de la aparición de la actividad, el historial de actividad de riesgo del usuario y la adición de riesgos de actividad que pueden aumentar la gravedad de la actividad. La puntuación de riesgo de la alerta impulsa la asignación mediante la programación de un nivel de gravedad de riesgo para cada alerta y no se puede personalizar. Si las alertas siguen sin evaluarse y las actividades de riesgo siguen acumulándose en la alerta, el nivel de gravedad del riesgo puede aumentar. Los analistas e investigadores de riesgos pueden usar la gravedad del riesgo de alerta para ayudar a evaluar las alertas de acuerdo con las directivas y estándares de riesgo de su organización.

Los niveles de gravedad del riesgo de alerta son:

- **Gravedad alta:** las actividades e indicadores de la alerta representan un riesgo significativo. Las actividades de riesgo asociadas son graves, repetitivas y se acentúan con fuerza a otros factores de riesgo significativos.
- **Gravedad media:** las actividades e indicadores de la alerta representan un riesgo moderado. Las actividades de riesgo asociadas son moderados, frecuentes y tienen cierta correlación con otros factores de riesgo.
- **Gravedad baja:** las actividades e indicadores de la alerta representan un riesgo menor. Las actividades de riesgo asociadas son menores, más poco frecuentes y no se pueden realizar en otros factores de riesgo significativos.

## <a name="filter-alerts-on-the-alert-dashboard"></a>Filtrar alertas en el panel de alertas

Según el número y el tipo de directivas activas de administración de riesgos internos de su organización, revisar una larga cola de alertas puede ser todo un reto. El uso de filtros de alerta puede ayudar a los analistas e investigadores a ordenar las alertas por varios atributos. Para filtrar alertas en el **panel de alertas,** seleccione el control **Filtro.** Puede filtrar alertas por uno o varios atributos:

- **Estado:** seleccione uno o más valores de estado para filtrar la lista de alertas. Las opciones son *Confirmada*, *Descartada*, *Falta por revisar*, y *Resuelta*.
- **Gravedad:** seleccione uno o más niveles de gravedad de riesgo de alerta para filtrar la lista de alertas. Las opciones son *Alta*, *Media*, y *Baja*.
- **Hora detectada:** seleccione las fechas de inicio y finalización para cuando se creó la alerta. Este filtro busca alertas entre las 00:00 UTC de la fecha de inicio y las 00:00 UTC de la fecha de finalización. Para filtrar alertas para un día específico, escriba la fecha del día en el campo **Fecha** de inicio y la fecha del día siguiente en el **campo Fecha de** finalización.
- **Directiva:** seleccione una o varias directivas para filtrar las alertas generadas por las directivas seleccionadas.

## <a name="search-alerts-on-the-alert-dashboard"></a>Alertas de búsqueda en el panel de alertas

Para buscar una palabra específica en el nombre de la alerta, seleccione el control **Búsqueda** y escriba la palabra que desea buscar. Los resultados de búsqueda muestran cualquier alerta de directiva que contenga la palabra definida en la búsqueda.

## <a name="dismiss-multiple-alerts-preview"></a>Descartar varias alertas (versión preliminar)

Puede ayudar a ahorrar tiempo de triaje para que los analistas e investigadores descarten inmediatamente varias alertas a la vez. La **opción de** la barra de comandos Descartar  alertas le permite seleccionar una o varias alertas con el estado Necesita revisión en el panel y descartar rápidamente estas alertas como benignas según corresponda en el proceso de evaluación. Puede seleccionar hasta 400 alertas para descartar a la vez.

Para descartar una alerta de riesgo de insider, siga estos pasos:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a Administración de riesgos de **Insider** y seleccione la **pestaña** Alertas.
2. En el **panel De alertas,** seleccione la alerta (o alertas) con el estado Necesita *revisión* que desea descartar.
3. En la barra de comandos Alertas, seleccione **Descartar alertas**.
4. En el **panel de detalles** Descartar alertas, puede revisar los detalles de usuario y directiva asociados con las alertas seleccionadas.
5. Seleccione **Descartar alertas** para resolver las alertas como benignas o **seleccione Cancelar** para cerrar el panel de detalles sin descartar las alertas.

## <a name="triage-alerts"></a>Alertas de triaje

Para realizar una evaluación de una alerta de riesgo insider, siga estos pasos:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a Administración de riesgos de **Insider** y seleccione la **pestaña** Alertas.
2. En el **panel De alertas,** seleccione la alerta que desea triage.
3. En la página Detalles **de** alerta, puede revisar la información sobre la alerta y puede confirmar la alerta y crear un nuevo caso, confirmar la alerta y agregarla a un caso existente, o descartar la alerta. Esta página también incluye el estado actual de la alerta y el nivel de gravedad del riesgo de alerta, enumerado como Alto, Medio o Bajo. El nivel de gravedad puede aumentar o disminuir con el tiempo si la alerta no está triaged.

    Las pestañas de la **página Detalles de** alerta proporcionan más información para la alerta:
    - **Resumen:** esta pestaña contiene información general sobre la alerta.
        - **¿Cuál fue el evento desencadenante?**: Muestra el evento de activación más reciente que instó a la directiva a empezar a asignar puntuaciones de riesgo a la actividad del usuario.
        - **Actividad que generó esta alerta:** muestra la actividad de mayor riesgo y la coincidencia de directiva durante el período de evaluación de actividad que llevó a la alerta que se generó.
        - **Perspectivas de riesgos para la actividad de esta alerta:** muestra el número de información de riesgos para la alerta. Algunos ejemplos son si la alerta contiene actividades de secuencia, riesgo acumulado de actividad de exfiltración, actividad que incluye eventos con dominios no permitidos, actividad que incluye eventos con contenido prioritario o actividades que son inusuales para el usuario.
        - **Detalles del usuario:** muestra información general sobre el usuario asignado a la alerta. Si la anonimización está habilitada, los campos nombre de usuario, dirección de correo electrónico, alias y organización se anonimizan.
        - **Detalles de** la alerta: incluye el período de tiempo desde que se generó la alerta, se enumeran las directivas que generaron la alerta y se muestra el caso generado a partir de la alerta. Para las alertas nuevas, el **campo Caso** muestra Ninguno.
        - **Contenido detectado:** incluye contenido asociado a las actividades de riesgo de la alerta y resume los eventos de actividad por áreas clave. Al seleccionar un vínculo de actividad, se abre el explorador de actividades y se muestran más detalles sobre la actividad.
    - **Explorador de actividades:** esta pestaña abre el **explorador de actividades**. Para obtener más información, consulte la siguiente sección de este artículo.

## <a name="activity-explorer"></a>Explorador de actividad

> [!NOTE]
> El explorador de actividades está disponible en el área de administración de alertas para usuarios con eventos desencadenados después de que esta característica esté disponible en la organización.

El explorador de actividades proporciona a los investigadores y analistas de riesgos una herramienta de análisis completa que proporciona información detallada sobre las alertas. Con el explorador de actividades, los revisores pueden revisar rápidamente una escala de tiempo de actividad de riesgo detectada e identificar y filtrar todas las actividades de riesgo asociadas con alertas. 

Para filtrar alertas en el Explorador de actividades para obtener información de columna, seleccione el control Filtro. Puede filtrar las alertas por uno o varios atributos enumerados en el panel de detalles de la alerta. El explorador de actividades también admite columnas personalizables para ayudar a los investigadores y analistas a centrar el panel en la información más importante para ellos.

Use los filtros Ámbito de actividad y Perspectiva de riesgos para mostrar y ordenar actividades e información para las siguientes áreas.

- **Filtros de ámbito de** actividad: filtra todas las actividades puntuadas para el usuario.
    - Toda la actividad puntuada para este usuario
    - Solo actividad puntuada en esta alerta

- **Filtros de información de riesgos:** filtra la actividad aplicable a todas las directivas que asignan puntuaciones de riesgo.
    - Actividades de exfiltración acumulativas
    - Incluye evento con contenido de prioridad
    - Incluye evento con dominio no permitido
    - Actividades de secuencia
    - Actividad inusual

![Introducción al explorador de actividades de administración de riesgos de Insider.](../media/insider-risk-activity-explorer.png)

Para usar el **explorador de actividades,** siga estos pasos:

1. En el Centro de cumplimiento de Microsoft 365, vaya a Administración de riesgos **de Insider** y seleccione la **pestaña** Alertas.
2. En el **panel De alertas,** seleccione la alerta que desea triage.
3. En el **panel de detalles Alertas,** **seleccione Abrir vista expandida**.
4. En la página de la alerta seleccionada, seleccione la **pestaña Explorador de** actividades.

Al revisar las actividades en el explorador de actividades, los investigadores y analistas pueden seleccionar una actividad específica y abrir el panel de detalles de la actividad. El panel muestra información detallada sobre la actividad que los investigadores y analistas pueden usar durante el proceso de evaluación de alertas. La información detallada puede proporcionar contexto para la alerta y ayudar a identificar el ámbito completo de la actividad de riesgo que desencadenó la alerta.

Al seleccionar los eventos de una actividad de la escala de tiempo de actividad, es posible que el número de actividades que se muestran en el explorador no coincida con el número de eventos de actividad enumerados en la escala de tiempo. Ejemplos de por qué puede producirse esta diferencia:

- **Detección acumulativa** de exfiltración: la detección acumulativa de exfiltración analiza los registros de eventos, pero aplica un modelo que incluye la desduplicación de actividades similares para calcular el riesgo de exfiltración acumulado. Además, también puede haber una diferencia en el número de actividades que se muestran en el explorador de actividades si ha realizado cambios en la directiva o configuración existentes. Por ejemplo, si modifica dominios permitidos o no permitidos o agrega nuevas exclusiones de tipos de archivo después de crear una directiva y de que se hayan producido coincidencias de actividad, las actividades acumulativas de detección de exfiltración diferirán de los resultados antes de que cambie la directiva o la configuración. Los totales acumulados de actividad de detección de exfiltración se basan en la configuración de directiva y configuración en el momento del cálculo y no incluyen actividades antes de los cambios de directiva y configuración
- **Correos electrónicos a destinatarios externos:** la actividad de los correos electrónicos enviados a destinatarios externos tiene asignada una puntuación de riesgo en función del número de correos electrónicos enviados, que puede no coincidir con los registros de eventos de actividad.

![Detalles del explorador de actividades de administración de riesgos de Insider.](../media/insider-risk-activity-explorer-details.png)

## <a name="create-a-case-for-an-alert"></a>Crear un caso para una alerta

A medida que se revisa y se revisa la alerta, puede crear un nuevo caso para investigar aún más la actividad de riesgo. Para crear un caso para una alerta, siga estos pasos:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a Administración de riesgos de **Insider** y seleccione la **pestaña** Alertas.
2. En el **panel De alertas,** seleccione la alerta para la que desea confirmar y crear un nuevo caso.
3. En el **panel Detalles de alertas,** seleccione **Acciones**  >  **Confirmar alertas & crear caso**.
4. En el **cuadro de diálogo** Confirmar alerta y crear caso de riesgo interno, escriba un nombre para el caso, seleccione usuarios para agregar como colaboradores y agregue comentarios según corresponda. Los comentarios se agregan automáticamente al caso como nota de caso.
5. Seleccione **Crear caso** para crear un nuevo caso o **cancelar** para cerrar el cuadro de diálogo sin crear un caso.

Una vez creado el caso, los investigadores y analistas pueden administrar y actuar en el caso. Para obtener más información, consulte el artículo sobre casos de administración [de riesgos de Insider.](insider-risk-management-cases.md)

## <a name="get-help-managing-your-insider-risk-alert-queue"></a>Obtener ayuda para administrar la cola de alertas de riesgo de insider

Revisar, investigar y actuar en alertas de riesgo de información interna son partes importantes para minimizar los riesgos de insider en la organización. Tomar medidas rápidamente para minimizar el impacto de estos riesgos puede ahorrar tiempo, dinero y ramificaciones legales o reglamentarias para su organización. En este proceso de corrección, el primer paso de revisar las alertas puede parecer la tarea más difícil para muchos analistas e investigadores. Según sus circunstancias, es posible que se esté enfrentando a algunos obstáculos menores al actuar en alertas de riesgo de información interna. Revise las siguientes recomendaciones y obtenga información sobre cómo optimizar el proceso de revisión de alertas.

### <a name="too-many-alerts-to-review"></a>Demasiadas alertas para revisar

Sentirse abrumado por el número de alertas generadas por las directivas de administración de riesgos de insider podría resultar frustrante. El número de alertas se puede abordar rápidamente con pasos sencillos, en función de los tipos de volumen de alerta que reciba. Es posible que reciba demasiadas alertas válidas o que tenga demasiadas alertas de bajo riesgo obsoletas. Considere la posibilidad de realizar las siguientes acciones:

- Ajustar las directivas de riesgo de **insider:** seleccionar y configurar la directiva de riesgo insider correcta es el método más básico para abordar el tipo y el volumen de alertas. A partir de la plantilla [de directiva adecuada,](insider-risk-management-policies.md#policy-templates) ayuda a centrar los tipos de actividades de riesgo y alertas que verá. Otros factores que pueden afectar al volumen de alertas son el tamaño del usuario y los grupos del ámbito y el contenido y los canales que [se priorizan.](insider-risk-management-policies.md#prioritize-content-in-policies) Considere la posibilidad de ajustar las directivas para refinar estas áreas a lo que es más importante para su organización.
- Modificar la configuración de riesgos de **insider:** las opciones de riesgo de Insider incluyen una amplia variedad de opciones de configuración que pueden afectar al volumen y a los tipos de alertas que recibirás. Estos incluyen la configuración de [indicadores de directiva,](insider-risk-management-settings.md#indicators) [umbrales de indicadores](insider-risk-management-settings.md#indicator-level-settings-preview)y [períodos de tiempo de directiva.](insider-risk-management-settings.md#policy-timeframes) Considere la posibilidad de configurar opciones de detecciones [inteligentes](insider-risk-management-settings.md#intelligent-detections) para excluir tipos de archivo específicos, definir umbrales mínimos antes de que las directivas notifican alertas de actividad y cambiar la configuración del volumen de alertas a una configuración inferior.
- **Eliminación masiva de alertas** cuando corresponda: puede ayudar a ahorrar tiempo de triaje para que los analistas e investigadores descarten inmediatamente [varias alertas](insider-risk-management-activities.md#dismiss-multiple-alerts-preview) a la vez. Puede seleccionar hasta 400 alertas para descartar a la vez.

### <a name="not-familiar-with-the-alert-triage-process"></a>No está familiarizado con el proceso de evaluación de alertas

Investigar y actuar en alertas en la administración de riesgos de insider es sencillo:

1. **Revise el [panel de alertas](insider-risk-management-activities.md#alert-dashboard) para alertas con el estado Necesita revisión**. [Filtrar](insider-risk-management-activities.md#filter-alerts-on-the-alert-dashboard) por estado *de alerta* si es necesario para ayudar a localizar estos tipos de alertas.
2. **Comience con las alertas con la gravedad más alta.** [Filtrar](insider-risk-management-activities.md#filter-alerts-on-the-alert-dashboard) por gravedad *de alerta si* es necesario para ayudar a localizar estos tipos de alertas.
3. **Seleccione una alerta para descubrir más información y revisar los detalles de la alerta**. Si es necesario, use el [Explorador de actividades](insider-risk-management-activities.md#activity-explorer) para revisar una escala de tiempo del comportamiento de riesgo asociado e identificar todas las actividades de riesgo de la alerta.
4. **Actuar en la alerta**. Puede confirmar y crear [un caso para](insider-risk-management-activities.md#create-a-case-for-an-alert) la alerta o descartar y resolver la alerta.

### <a name="resource-constraints-in-my-organization"></a>Restricciones de recursos en mi organización

Los usuarios modernos del lugar de trabajo suelen tener una amplia variedad de responsabilidades y demandas en su tiempo. Hay varias acciones que puede realizar para ayudar a solucionar las restricciones de recursos:

- En primer lugar, centra los esfuerzos de analistas e **investigadores en las alertas de mayor riesgo.** Dependiendo de las directivas, es posible que esté capturando actividades y generando alertas con distintos grados de impacto potencial en sus esfuerzos de mitigación de riesgos. [Filtra las alertas](insider-risk-management-activities.md#filter-alerts-on-the-alert-dashboard) por gravedad y prioriza *las alertas de gravedad* alta.
- **Asignar usuarios como analistas e investigadores**. Tener asignado el usuario adecuado a los roles adecuados es una parte importante del proceso de revisión de alertas de riesgo de insider. Asegúrese de que ha asignado los usuarios adecuados a los grupos de roles Analistas de administración de riesgos de *Insider* e Investigadores de administración de riesgos de *Insider.*  
- **Use características de riesgo insider automatizadas para ayudar a descubrir las actividades de mayor riesgo.** La detección [](insider-risk-management-policies.md#sequence-detection-preview) de secuencias de administración de riesgos insider y las características acumulativas de detección de [exfiltración](insider-risk-management-policies.md#cumulative-exfiltration-detection-preview) pueden ayudarle a descubrir rápidamente los riesgos más difíciles de encontrar en su organización. Considera la posibilidad de ajustar los [refuerzos de la puntuación](insider-risk-management-settings.md#indicators)de riesgo, [las exclusiones](insider-risk-management-settings.md#file-type-exclusions)de tipos de [archivo,](insider-risk-management-settings.md#domains-preview)los dominios y la configuración mínima del umbral del indicador [para](insider-risk-management-settings.md#indicator-level-settings-preview) tus directivas.
