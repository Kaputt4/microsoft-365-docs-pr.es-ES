---
title: Alertas de administración de riesgos de Insider
description: Obtenga información sobre las alertas de administración de riesgos de insider en Microsoft 365
keywords: Microsoft 365, riesgo interno, administración de riesgos, cumplimiento
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
ms.openlocfilehash: 9fe1665eda882793a62315299a3cbf6667ec7988
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445658"
---
# <a name="insider-risk-management-alerts"></a>Alertas de administración de riesgos de Insider

Las alertas de administración de riesgos internos se generan automáticamente a través de los indicadores de riesgo definidos en las directivas de administración de riesgos internos. Estas alertas ofrecen a los investigadores y analistas de cumplimiento una vista actualizada del estado de riesgo actual y permiten que su organización valore y tome medidas en función de los riesgos detectados. De forma predeterminada, las directivas generan una cierta cantidad de alertas de gravedad baja, media y alta, pero puede aumentar o disminuir el volumen de alertas según sus necesidades. [](insider-risk-management-settings.md#alert-volume) Además, puede configurar el umbral de alerta para los indicadores de [directiva](insider-risk-management-settings.md#indicator-level-settings-preview) al crear una nueva directiva con el asistente para directivas.

Consulte el [vídeo Insider Risk Management Alerts Triage Experience](https://www.youtube.com/watch?v=KgmpxBLJLPI) para obtener información general sobre cómo las alertas proporcionan detalles, contexto y contenido relacionado para la actividad de riesgo y cómo hacer que el proceso de investigación sea más eficaz.

## <a name="alert-dashboard"></a>Panel de alertas

El panel de alertas de riesgo **interno** le permite ver y actuar en las alertas generadas por las directivas de riesgo de insider. Cada widget de informe muestra información de los últimos 30 días.

- **Total de alertas que necesitan revisión:** se muestra el número total de alertas que necesitan revisión y evaluación, incluido un desglose por gravedad de alerta.
- Alertas abiertas en los últimos **30** días: el número total de alertas creadas por la directiva coincide en los últimos 30 días, ordenadas por niveles de gravedad de alerta altos, medianos y bajos.
- **Tiempo promedio para resolver alertas:** un resumen de estadísticas de alertas útiles:
    - Tiempo medio para resolver alertas de gravedad alta, expresado en horas, días o meses.
    - Tiempo medio para resolver alertas de gravedad media, expresado en horas, días o meses.
    - Tiempo medio para resolver alertas de gravedad baja, expresado en horas, días o meses.

![Panel de alertas de administración de riesgos de Insider](../media/insider-risk-alerts-dashboard.png)

>[!NOTE]
>La administración de riesgos internos usa la limitación de alertas integrada para ayudar a proteger y optimizar su investigación de riesgos y experiencia de revisión. Esta limitación protege contra problemas que pueden causar una sobrecarga de alertas de directiva, como conectores de datos mal configurados o directivas DLP. Como resultado, es posible que haya un retraso al mostrar nuevas alertas para un usuario.

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
- **Hora detectada:** seleccione las fechas de inicio y finalización para cuando se creó la alerta.
- **Directiva:** seleccione una o varias directivas para filtrar las alertas generadas por las directivas seleccionadas.

## <a name="search-alerts-on-the-alert-dashboard"></a>Alertas de búsqueda en el panel de alertas

Para buscar una palabra específica en el nombre de la alerta, seleccione el control **Búsqueda** y escriba la palabra que desea buscar. Los resultados de búsqueda muestran cualquier alerta de directiva que contenga la palabra definida en la búsqueda.

## <a name="triage-alerts"></a>Alertas de triaje

Para realizar una evaluación de una alerta de riesgo insider, siga estos pasos:

1. En el [centro Microsoft 365 cumplimiento,](https://compliance.microsoft.com)vaya a Administración de riesgos **de Insider** y seleccione **la** pestaña Alertas.
2. En el **panel De alertas,** seleccione la alerta que desea triage.
3. En el **panel de detalles Alertas,** puede revisar las siguientes pestañas y realizar una evaluación de la alerta:
    - **Resumen:** esta pestaña contiene información general sobre la alerta y le permite confirmar la alerta y crear un nuevo caso o le permite descartar la alerta. Incluye el estado actual de la alerta y el nivel de gravedad del riesgo de alerta, enumerados como *High*, *Medium* o *Low*. El nivel de gravedad puede aumentar o disminuir con el tiempo si la alerta no está triaged.
        - **Qué sucedió (versión preliminar):** muestra las tres actividades de riesgo y las coincidencias de directiva principales durante el período de evaluación de actividad, incluido el tipo de infracción asociada a la actividad y el número de repeticiones.
        - **Detalles del usuario:** muestra información general sobre el usuario asignado a la alerta. Si la anonimización está habilitada, los campos nombre de usuario, dirección de correo electrónico, alias y organización se anonimizan.
        - **Detalles de** la alerta: incluye el período de tiempo desde que se generó la alerta, se enumeran las directivas que generaron la alerta y se muestra el caso generado a partir de la alerta. Para las alertas nuevas, el **campo Caso** muestra Ninguno.
        - **Contenido detectado (versión preliminar):** incluye contenido asociado a las actividades de riesgo de la alerta y resume los eventos de actividad por áreas clave. Al seleccionar un vínculo de actividad, se abre el explorador de actividades y se muestran detalles adicionales sobre la actividad.
    - **Actividad de usuario:** esta pestaña muestra el historial de actividades del usuario asociado a la alerta. Este historial incluye otras alertas y actividades relacionadas con los indicadores de riesgo definidos en la plantilla asignada a la directiva para esta alerta. Este historial permite a los analistas de riesgos e investigadores tener en cuenta cualquier comportamiento de riesgo pasado para el empleado como parte del proceso de evaluación.
    - **Acciones:** las siguientes acciones están disponibles para cada alerta:
        - **Vista expandida abierta:** abre el panel **del explorador de** actividades.
        - **Confirmar y crear caso:** use esta acción para confirmar y crear un nuevo caso para todas las alertas asociadas con un usuario. Esta acción cambia automáticamente el estado de alerta a *Confirmado*.
        - **Descartar alerta:** use esta acción para descartar la alerta. Esta acción cambia el estado de alerta a *Resuelto*.

## <a name="activity-explorer-preview"></a>Explorador de actividades (versión preliminar)

>[!NOTE]
>El explorador de actividades está disponible en el área de administración de alertas para usuarios con eventos desencadenados después de que esta característica esté disponible en la organización.

El explorador de actividades proporciona a los investigadores y analistas de riesgos una herramienta de análisis completa que proporciona información detallada sobre las alertas. Con el explorador de actividades, los revisores pueden revisar rápidamente una escala de tiempo de actividad de riesgo detectada e identificar y filtrar todas las actividades de riesgo asociadas con alertas. Para filtrar alertas en el Explorador de actividades, seleccione el control Filtro. Puede filtrar las alertas por uno o varios atributos enumerados en el panel de detalles de la alerta. El explorador de actividades también admite columnas personalizables para ayudar a los investigadores y analistas a centrar el panel en la información más importante para ellos.

![Introducción al explorador de actividades de administración de riesgos de Insider](../media/insider-risk-activity-explorer.png)

Para usar el **explorador de actividades,** siga estos pasos:

1. En el centro Microsoft 365 cumplimiento, vaya a Administración de riesgos **de Insider** y seleccione la **pestaña** Alertas.
2. En el **panel De alertas,** seleccione la alerta que desea triage.
3. En el **panel de detalles Alertas,** **seleccione Abrir vista expandida**.
4. En la página de la alerta seleccionada, seleccione la **pestaña Explorador de** actividades.

Al revisar las actividades en el explorador de actividades, los investigadores y analistas pueden seleccionar una actividad específica y abrir el panel de detalles de la actividad. El panel muestra información detallada sobre la actividad que los investigadores y analistas pueden usar durante el proceso de evaluación de alertas. La información detallada puede proporcionar contexto para la alerta y ayudar a identificar el ámbito completo de la actividad de riesgo que desencadenó la alerta.

![Detalles del explorador de actividades de administración de riesgos de Insider](../media/insider-risk-activity-explorer-details.png)

## <a name="create-a-case-for-an-alert"></a>Crear un caso para una alerta

A medida que se revisa y se revisa la alerta, puede crear un nuevo caso para investigar aún más la actividad de riesgo. Para crear un caso para una alerta, siga estos pasos:

1. En el [centro Microsoft 365 cumplimiento,](https://compliance.microsoft.com)vaya a Administración de riesgos **de Insider** y seleccione **la** pestaña Alertas.
2. En el **panel De alertas,** seleccione la alerta para la que desea confirmar y crear un nuevo caso.
3. En el **panel Detalles de alertas,** seleccione **Acciones**  >  **Confirmar alertas & crear caso**.
4. En el **cuadro de diálogo** Confirmar alerta y crear caso de riesgo interno, escriba un nombre para el caso, seleccione usuarios para agregar como colaboradores y agregue comentarios según corresponda. Los comentarios se agregan automáticamente al caso como nota de caso.
5. Seleccione **Crear caso** para crear un nuevo caso o **cancelar** para cerrar el cuadro de diálogo sin crear un caso.

Una vez creado el caso, los investigadores y analistas pueden administrar y actuar en el caso. Vea el [artículo sobre el caso de administración de riesgos de Insider](insider-risk-management-cases.md) para obtener más información.
