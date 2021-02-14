---
title: Alertas de administración de riesgos de Insider
description: Más información sobre las alertas de administración de riesgos interno en Microsoft 365
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
ms.openlocfilehash: 602571e5cbd3132209382ca2e2a3d8941ea8ab2e
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208842"
---
# <a name="insider-risk-management-alerts"></a>Alertas de administración de riesgos de Insider

Las alertas de administración de riesgos de Insider se generan automáticamente mediante indicadores de riesgo definidos en las directivas de administración de riesgos internas. Estas alertas dan a los analistas e investigadores de cumplimiento una vista general del estado de riesgo actual y permiten a su organización realizar una evaluación y tomar medidas para los riesgos detectados. De forma predeterminada, las directivas generan una cierta cantidad de alertas de gravedad baja, media y alta, pero puedes aumentar o disminuir el volumen de alertas para adaptarlo a tus necesidades. [](insider-risk-management-settings.md#alert-volume) Además, puedes configurar el umbral de alerta para los indicadores de [directiva](insider-risk-management-settings.md#indicator-level-settings-preview) al crear una nueva directiva con el asistente para directivas.

## <a name="alert-dashboard"></a>Panel de alertas

El panel de **alertas de** riesgo interno te permite ver y actuar sobre las alertas generadas por las directivas de riesgo de Insider. Cada widget de informe muestra información de los últimos 30 días.

- **Alertas para revisar:** se muestra el número total de alertas que necesitan revisión y evaluación, incluido un desglose por gravedad de alerta.
- **Open alerts over past 30 days:** The total number of alerts created by policy matches over the last 30 days, sorted by high, medium, and low alert severity levels.
- **Tiempo promedio para resolver alertas:** un resumen de estadísticas de alertas útiles:
    - Tiempo promedio para resolver alertas de gravedad alta, enumeradas en horas, días o meses.
    - Tiempo medio para resolver alertas de gravedad media, enumeradas en horas, días o meses.
    - Tiempo promedio para resolver alertas de gravedad baja, enumeradas en horas, días o meses.

![Panel de alertas de administración de riesgos de Insider](../media/insider-risk-alerts-dashboard.png)

>[!NOTE]
>La administración de riesgos de Insider usa la limitación de alertas integrada para ayudar a proteger y optimizar la experiencia de investigación y revisión de riesgos. Esta limitación protege contra problemas que pueden provocar una sobrecarga de alertas de directiva, como conectores de datos mal configurados o directivas DLP. Como resultado, puede haber un retraso en la visualización de nuevas alertas para un usuario.

## <a name="alert-status-and-severity"></a>Estado y gravedad de la alerta

Puedes realizar una triage de las alertas en uno de los siguientes estados:

- **Confirmado:** alerta confirmada y asignada a un caso nuevo o existente.
- **Descartado:** una alerta descartada como benigna en el proceso de evaluación.
- **Necesita revisión:** una nueva alerta en la que aún no se han realizado acciones de evaluación.
- **Resuelto:** alerta que forma parte de un caso cerrado y resuelto.

Las puntuaciones de riesgo de alerta se calculan automáticamente a partir de varios indicadores de actividad de riesgo. Estos indicadores incluyen el tipo de actividad de riesgo, el número y la frecuencia de la repetición de la actividad, el historial de actividad de riesgo de usuario y la adición de riesgos de actividad que pueden aumentar la gravedad de la actividad. La puntuación de riesgo de alerta dirige la asignación mediante programación de un nivel de gravedad de riesgo para cada alerta y no se puede personalizar. Si las alertas siguen sin evaluarse y las actividades de riesgo siguen acumulándose a la alerta, el nivel de gravedad del riesgo puede aumentar. Los analistas e investigadores de riesgos pueden usar la gravedad de riesgo de alerta para ayudar a evaluar las alertas de acuerdo con las directivas y estándares de riesgo de su organización.

Los niveles de gravedad de riesgo de alerta son:

- **Gravedad alta: las** actividades y los indicadores de la alerta representan un riesgo significativo. Las actividades de riesgo asociadas son graves, repetitivas y se relacionan con otros factores de riesgo importantes.
- **Gravedad media:** las actividades y los indicadores de la alerta representan un riesgo moderado. Las actividades de riesgo asociadas son moderadas, frecuentes y tienen cierta correlación con otros factores de riesgo.
- **Gravedad baja:** las actividades y los indicadores de la alerta representan un riesgo menor. Las actividades de riesgo asociadas son menores, más poco frecuentes y no se reducen a otros factores de riesgo significativos.

## <a name="filter-alerts-on-the-alert-dashboard"></a>Filtrar alertas en el panel de alertas

Según el número y el tipo de directivas de administración de riesgos internas activas de la organización, revisar una cola grande de alertas puede ser difícil. El uso de filtros de alerta puede ayudar a los analistas e investigadores a ordenar las alertas por varios atributos. Para filtrar alertas en el panel **alertas,** seleccione el control **de** filtro. Puedes filtrar las alertas por uno o varios atributos:

- **Estado:** seleccione uno o más valores de estado para filtrar la lista de alertas. Las opciones son *Confirmado,* *Descartado*, *Necesita revisión* y *Resuelto.*
- **Gravedad:** seleccione uno o más niveles de gravedad de riesgo de alerta para filtrar la lista de alertas. Las opciones son *Alta,* *Media* y *Baja.*
- **Hora detectada:** seleccione las fechas de inicio y finalización para cuando se creó la alerta.
- **Directiva:** seleccione una o más directivas para filtrar las alertas generadas por las directivas seleccionadas.

## <a name="search-alerts-on-the-alert-dashboard"></a>Buscar alertas en el panel de alertas

Para buscar una palabra específica en el nombre de la alerta, seleccione el control **de** búsqueda y escriba la palabra en la que buscar. Los resultados de la búsqueda muestran cualquier alerta de directiva que contenga la palabra definida en la búsqueda.

## <a name="triage-alerts"></a>Alertas de triage

Para realizar una evaluación de una alerta de riesgo interno, siga estos pasos:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione la **pestaña Alertas.**
2. En el **panel Alertas,** selecciona la alerta que quieras triage.
3. En el **panel de detalles alertas,** puede revisar las siguientes pestañas y realizar una evaluación de la alerta:
    - **Resumen:** esta pestaña contiene información general sobre la alerta y le permite confirmar la alerta y crear un nuevo caso o le permite descartar la alerta. Incluye el estado actual de la alerta y el nivel de gravedad de riesgo de alerta, enumerado como *Alto,* *Medio* o *Bajo.* El nivel de gravedad puede aumentar o disminuir con el tiempo si la alerta no se ha recortado.
        - **Qué ha ocurrido:** muestra las tres actividades de riesgo principales y coincidencias de directivas durante el período de evaluación de la actividad, incluido el tipo de infracción asociada a la actividad.
        - **Detalles del usuario:** muestra información general sobre el usuario asignado a la alerta. Si la anonimización está habilitada, el nombre de usuario, la dirección de correo electrónico, el alias y los campos de la organización se anonimizan.
        - **Detalles de** la alerta: incluye el período de tiempo desde que se generó la alerta, se enumeran las directivas que generaron la alerta y se muestra el caso generado a partir de la alerta. Para las nuevas alertas, el **campo Caso** muestra Ninguno.
        - **Contenido detectado:** incluye contenido asociado a las actividades de riesgo de la alerta y resume los eventos de actividad por áreas clave. Al seleccionar un vínculo de actividad, se abre el Explorador de actividades y se muestran detalles adicionales sobre la actividad.
    - **Actividad de usuario:** esta pestaña muestra el historial de actividades del usuario asociado a la alerta. Este historial incluye otras alertas y actividades relacionadas con los indicadores de riesgo definidos en la plantilla asignada a la directiva para esta alerta. Este historial permite a los analistas de riesgos e investigadores tener en cuenta cualquier comportamiento de riesgo pasado para el empleado como parte del proceso de evaluación.
    - **Acciones:** las siguientes acciones están disponibles para cada alerta:
        - **Vista expandida abierta:** abre el panel **del Explorador de** actividades.
        - **Confirmar y crear caso:** use esta acción para confirmar y crear un nuevo caso para todas las alertas asociadas con un usuario. Esta acción cambia automáticamente el estado de alerta a *Confirmado*.
        - **Descartar alerta:** use esta acción para descartar la alerta. Esta acción cambia el estado de alerta a *Resuelto.*

## <a name="activity-explorer-preview"></a>Explorador de actividades (versión preliminar)

>[!NOTE]
>El explorador de actividades está disponible en el área de administración de alertas para los usuarios con eventos desencadenados después de que esta característica esté disponible en la organización.

El explorador de actividades proporciona a los analistas y investigadores de riesgos una herramienta analítica completa que proporciona información detallada sobre las alertas. Con el explorador de actividades, los revisores pueden revisar rápidamente una escala de tiempo de actividad de riesgo detectada e identificar y filtrar todas las actividades de riesgo asociadas con las alertas. Para filtrar alertas en el Explorador de actividades, seleccione el control Filtro. Puedes filtrar las alertas por uno o más atributos enumerados en el panel de detalles de la alerta. El explorador de actividades también admite columnas personalizables para ayudar a los investigadores y analistas a centrar el panel en la información más importante para ellos.

![Introducción al explorador de actividad de administración de riesgos de Insider](../media/insider-risk-management-activity-explorer.png)

Para usar el **Explorador de actividades,** siga estos pasos:

1. En el Centro de cumplimiento de Microsoft 365, vaya a Administración de riesgos de **Insider** y seleccione la **pestaña Alertas.**
2. En el **panel Alertas,** selecciona la alerta que quieras triage.
3. En el panel **de detalles Alertas,** seleccione **Abrir vista expandida.**
4. En la página de la alerta seleccionada, seleccione la **pestaña Explorador de** actividades.

Al revisar las actividades en el explorador de actividades, los investigadores y analistas pueden seleccionar una actividad específica y abrir el panel de detalles de la actividad. El panel muestra información detallada sobre la actividad que los investigadores y analistas pueden usar durante el proceso de evaluación de alertas. La información detallada puede proporcionar contexto para la alerta y ayudar a identificar el ámbito completo de la actividad de riesgo que desencadenó la alerta.

![Detalles del explorador de actividad de administración de riesgos de Insider](../media/insider-risk-management-activity-explorer-details.png)

## <a name="create-a-case-for-an-alert"></a>Crear un caso para una alerta

A medida que la alerta se revisa y se revisa, puede crear un nuevo caso para investigar aún más la actividad de riesgo. Para crear un caso para una alerta, siga estos pasos:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione la **pestaña Alertas.**
2. En el **panel alertas,** seleccione la alerta para la que desea confirmar y crear un nuevo caso.
3. En el panel **de detalles de alertas,** seleccione **Acciones**  >  **Confirmar alertas & crear caso.**
4. En el **cuadro de diálogo** Confirmar alerta y crear casos de riesgo interno, escriba un nombre para el caso, seleccione los usuarios que desea agregar como colaboradores y agregue comentarios según corresponda. Los comentarios se agregan automáticamente al caso como nota de caso.
5. Seleccione **Crear caso** para crear un nuevo caso o Cancelar para cerrar el cuadro de diálogo sin crear un caso. 

Una vez creado el caso, los investigadores y analistas pueden administrar y actuar en el caso. Consulta el artículo [sobre casos de administración de riesgos de Insider](insider-risk-management-cases.md) para obtener más información.
