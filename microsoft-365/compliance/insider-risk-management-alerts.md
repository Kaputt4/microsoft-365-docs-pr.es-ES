---
title: Alertas de administración de riesgos de Insider
description: Obtenga información sobre las alertas de administración de riesgos de Insider en Microsoft 365
keywords: Microsoft 365, riesgo para Insiders, administración de riesgos, cumplimiento
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

Los indicadores de riesgo definidos en las directivas de administración de riesgos de Insider generan automáticamente alertas de administración de riesgos de Insider. Estas alertas dan a los analistas y investigadores de cumplimiento una visión general del estado de riesgo actual y permiten que su organización clasifique y realice acciones para los riesgos detectados. De forma predeterminada, las directivas generan una determinada cantidad de alertas de gravedad baja, media y alta, pero puede [aumentar o disminuir el volumen de alertas](insider-risk-management-settings.md#alert-volume) según sus necesidades. Además, puede configurar el [umbral de alerta para los indicadores de directiva](insider-risk-management-settings.md#indicator-level-settings-preview) al crear una nueva directiva con el Asistente para directivas.

## <a name="alert-dashboard"></a>Panel de alertas

El panel de **alertas** de riesgo de Insider le permite ver y actuar en alertas generadas por las directivas de riesgos de Insider. Cada widget de informe muestra información de los últimos 30 días.

- **Alertas para revisión**: se enumera el número total de alertas que se deben revisar y clasificar, incluido un desglose por gravedad de alerta.
- **Alertas abiertas durante los últimos 30 días**: el número total de alertas creadas por las coincidencias de directivas en los últimos 30 días, ordenadas por niveles de gravedad de alertas alta, media y baja.
- **Tiempo promedio para resolver alertas**: un resumen de las estadísticas de alertas útiles:
    - Tiempo medio para resolver alertas de gravedad alta, enumeradas en horas, días o meses.
    - Tiempo medio para resolver alertas de gravedad media, enumeradas en horas, días o meses.
    - Tiempo medio para resolver alertas de gravedad baja, enumeradas en horas, días o meses.

![Panel de alertas de administración de riesgos de Insider](../media/insider-risk-alerts-dashboard.png)

>[!NOTE]
>La administración de riesgos de Insiders usa la limitación de alertas integradas para ayudar a proteger y optimizar la experiencia de revisión y de investigación de riesgos. Esta limitación evita los problemas que podrían dar como resultado una sobrecarga de alertas de Directiva, como los conectores de datos configurados incorrectamente o las directivas de DLP. Como resultado, es posible que se produzca un retraso en la visualización de alertas nuevas para un usuario.

## <a name="alert-status-and-severity"></a>Estado y gravedad de la alerta

Puede clasificar las alertas en uno de los Estados siguientes:

- **Confirmado**: una alerta confirmada y asignada a un caso nuevo o existente.
- **Desechado**: una alerta que se descarta como benigna en el proceso de clasificación.
- **Revisión de necesidades**: una nueva alerta en la que todavía no se han llevado A cabo las acciones de evaluación.
- **Resuelto**: una alerta que forma parte de un caso cerrado y resuelto.

Los resultados de riesgo de alertas se calculan automáticamente a partir de varios indicadores de actividad de riesgos. Estos indicadores incluyen el tipo de actividad de riesgo, el número y la frecuencia de la ocurrencia de la actividad, el historial de la actividad de riesgos de usuario y la adición de riesgos de actividad que puedan aumentar la gravedad de la actividad. La puntuación de riesgo de alertas controla la asignación mediante programación de un nivel de gravedad de riesgo para cada alerta y no se puede personalizar. Si las alertas siguen siendo no clasificadas y las actividades de riesgo continúan acumuladas en la alerta, el nivel de gravedad del riesgo puede aumentar. Los analistas de riesgos y investigadores pueden usar la gravedad de riesgo de alertas para ayudar a evaluar las alertas de acuerdo con las directivas y estándares de riesgo de su organización.

Los niveles de gravedad de riesgo de alertas son:

- **Gravedad alta**: las actividades y los indicadores de la alerta presentan un riesgo significativo. Las actividades de riesgo asociadas son serias, repetitivas y corelacionadas de manera segura con otros factores de riesgo significativos.
- **Gravedad media**: las actividades y los indicadores de la alerta representan un riesgo moderado. Las actividades de riesgo asociadas son moderadas, frecuentes y tienen cierta correlación con otros factores de riesgo.
- **Gravedad baja**: las actividades y los indicadores de la alerta suponen un riesgo menor. Las actividades de riesgo asociadas son secundarias, más poco frecuentes y no corelacionadas con otros factores de riesgo significativos.

## <a name="filter-alerts-on-the-alert-dashboard"></a>Filtrar alertas en el panel de alertas

Según el número y el tipo de directivas activas de administración de riesgos de Insider en la organización, la revisión de una cola de alertas de gran tamaño puede resultar complicada. El uso de filtros de alerta puede ayudar a los analistas y investigadores a ordenar las alertas por varios atributos. Para filtrar las alertas del **Panel alertas**, seleccione el control **filtro** . Puede filtrar las alertas por uno o más atributos:

- **Estado**: Seleccione uno o más valores de estado para filtrar la lista de alertas. Las opciones se *confirman*, *desechan*, *necesitan revisión*y se *resuelven*.
- **Gravedad**: Seleccione uno o más niveles de gravedad de riesgo de alerta para filtrar la lista de alertas. Las opciones son *alta*, *media*y *baja*.
- **Tiempo detectado**: seleccione las fechas de inicio y finalización para cuando se creó la alerta.
- **Directiva**: Seleccione una o más directivas para filtrar las alertas generadas por las directivas seleccionadas.

## <a name="search-alerts-on-the-alert-dashboard"></a>Alertas de búsqueda en el panel de alertas

Para buscar en el nombre de la alerta una palabra específica, seleccione el control de **búsqueda** y escriba la palabra que desea buscar. Los resultados de la búsqueda muestran cualquier alerta de directiva que contenga la palabra definida en la búsqueda.

## <a name="triage-alerts"></a>Alertas de clasificación

Para clasificar una alerta de riesgo de Insider, siga los pasos que se indican a continuación:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **alertas** .
2. En el **Panel alertas**, seleccione la alerta que desea clasificar.
3. En el **Panel de detalles de alertas**, puede revisar las siguientes pestañas y clasificar la alerta:
    - **Resumen**: esta ficha contiene información general sobre la alerta y le permite confirmar la alerta y crear un nuevo caso o permite descartar la alerta. Incluye el estado actual de la alerta y el nivel de gravedad de riesgo de la alerta, enumerados como *alto*, *medio*o *bajo*. El nivel de gravedad puede aumentar o disminuir con el tiempo si la alerta no se clasifica.
        - **Lo que sucedió**: muestra las tres principales actividades de riesgo y coincidencias de directivas durante el período de evaluación de la actividad, incluido el tipo de infracción asociada con la actividad.
        - **Detalles del usuario**: muestra información general acerca del usuario asignado a la alerta. Si anonymization está habilitado, los campos nombre de usuario, dirección de correo electrónico, alias y organización son anonimizan.
        - **Detalles**de la alerta: incluye el período de tiempo desde que se generó la alerta, las directivas que generaron la alerta aparecen en la lista y se muestra el caso generado a partir de la alerta. Para las nuevas alertas, el campo **caso** muestra ninguno.
        - **Contenido detectado**: incluye contenido asociado a las actividades de riesgo para la alerta y resume los eventos de actividad por áreas clave. Al seleccionar un vínculo de actividad se abre el explorador de actividades y se muestran detalles adicionales sobre la actividad.
    - **Actividad de usuario**: esta pestaña muestra el historial de actividades del usuario asociado a la alerta. Este historial incluye otras alertas y actividades relacionadas con los indicadores de riesgo definidos en la plantilla asignada a la Directiva para esta alerta. Este historial permite a los analistas de riesgos y a los investigadores factorizar cualquier comportamiento de riesgo pasado para el empleado como parte del proceso de evaluación de prioridades.
    - **Acciones**: están disponibles las siguientes acciones para cada alerta:
        - **Abrir vista expandida**: abre el panel del **Explorador de actividades** .
        - **Confirmar y crear caso**: Use esta acción para confirmar y crear un nuevo caso para todas las alertas asociadas a un usuario. Esta acción cambia automáticamente el estado de la alerta a *confirmado*.
        - **Descartar alerta**: Use esta acción para descartar la alerta. Esta acción cambia el estado de la alerta a *resuelto*.

## <a name="activity-explorer-preview"></a>Explorador de actividades (versión preliminar)

>[!NOTE]
>El explorador de actividades está disponible en el área de administración de alertas para los usuarios con eventos desencadenantes después de que esta característica esté disponible en la organización.

El explorador de actividades proporciona a los investigadores y analistas de riesgos una herramienta analítica completa que proporciona información detallada sobre las alertas. Con el explorador de actividades, los revisores pueden revisar rápidamente una escala de tiempo de actividad de riesgo detectada e identificar y filtrar todas las actividades de riesgo asociadas con las alertas. Para filtrar alertas en el explorador de actividades, seleccione el control de filtro. Puede filtrar las alertas por uno o más atributos que aparecen en el panel de detalles de la alerta. Activity Explorer también admite columnas personalizables para ayudar a los investigadores y analistas a centrar el panel sobre la información más importante para ellos.

![Introducción al explorador de actividad de administración de riesgos de Insider](../media/insider-risk-management-activity-explorer.png)

Para usar el **Explorador de actividades**, siga estos pasos:

1. En el centro de cumplimiento de Microsoft 365, vaya a **Administración de riesgos de Insider** y seleccione la pestaña **alertas** .
2. En el **Panel alertas**, seleccione la alerta que desea clasificar.
3. En el **Panel de detalles de alertas**, seleccione **abrir vista expandida**.
4. En la página de la alerta seleccionada, seleccione la pestaña **Explorador de actividades** .

Al revisar actividades en el explorador de actividades, los investigadores y analistas pueden seleccionar una actividad específica y abrir el panel de detalles de la actividad. El panel muestra información detallada sobre la actividad que pueden usar los investigadores y analistas durante el proceso de clasificación de alertas. La información detallada puede proporcionar contexto para la alerta y ayudar a identificar el ámbito completo de la actividad de riesgo que activó la alerta.

![Detalles del explorador de actividad de administración de riesgos de Insider](../media/insider-risk-management-activity-explorer-details.png)

## <a name="create-a-case-for-an-alert"></a>Crear un caso para una alerta

Como la alerta se ha revisado y se ha clasificado, puede crear un nuevo caso para seguir investigando la actividad de riesgo. Para crear un caso para una alerta, siga estos pasos:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **alertas** .
2. En el **Panel alertas**, seleccione la alerta que desea confirmar y cree un nuevo caso para.
3. En el **Panel de detalles de alertas**, seleccione **acciones**  >  **confirmar alertas & crear caso**.
4. En el cuadro de diálogo **confirmar la alerta y crear un caso de riesgo de Insider** , escriba un nombre para el caso, seleccione usuarios para agregarlos como colaboradores y agregue comentarios según corresponda. Los comentarios se agregan automáticamente al caso como una nota de caso.
5. Seleccione **crear caso** para crear un caso nuevo o seleccione **Cancelar** para cerrar el cuadro de diálogo sin crear un caso.

Una vez creado el caso, los investigadores y analistas pueden administrar y actuar en el caso. Consulte el artículo sobre el [caso de administración de riesgos de Insider](insider-risk-management-cases.md) para obtener más información.
