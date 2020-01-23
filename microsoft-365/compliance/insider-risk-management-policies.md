---
title: Directivas de administración de riesgos de Insider (versión preliminar)
description: Obtenga información sobre las directivas de administración de riesgos de Insider en Microsoft 365
keywords: Microsoft 365, administración de riesgos de Insider, administración de riesgos, cumplimiento
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: bf3666d4ad44b4fcf17ec93a1e425ffa0f12f766
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2020
ms.locfileid: "41259808"
---
# <a name="insider-risk-management-policies-preview"></a>Directivas de administración de riesgos de Insider (versión preliminar)

Las directivas de administración de riesgos de Insider determinan qué empleados están en el ámbito y qué tipos de indicadores de riesgo están configurados para las alertas. Puede crear rápidamente una directiva que se aplique a todos los usuarios de la organización, o bien definir grupos o usuarios individuales para la administración en una directiva. Las directivas admiten las prioridades de contenido para centrarse en las condiciones de la Directiva en varios o distintos equipos de Microsoft Teams, sitios de SharePoint, tipos de confidencialidad de datos y etiquetas de datos. Mediante el uso de plantillas, incluyen indicadores de riesgos específicos y la cantidad de peso que tienen asignada dentro de una directiva, que determinan con eficacia el peso de cada desencadenador de alertas de la Directiva. Las ventanas de directivas permiten definir el intervalo de tiempo para aplicar la Directiva a las actividades de alerta y se usan para determinar la duración de la Directiva una vez activada. El límite máximo de directivas es cinco directivas activas al mismo tiempo. Sin embargo, puede configurar directivas adicionales y activar y desactivar directivas según sea necesario.

## <a name="policy-dashboard"></a>Panel de directivas

El **Panel de directivas** permite ver rápidamente las directivas de la organización y el estado actual de las alertas asociadas a cada Directiva.

- **Nombre de directiva**: nombre asignado a la Directiva en el Asistente para directivas.
- **Alertas activas**: el número de alertas activas para cada Directiva.
- **Alertas confirmadas**: número total de alertas que se produjeron en casos de la Directiva en los últimos 365 días.
- **Acciones realizadas en las alertas**: el número total de alertas que se han confirmado o desechado durante los últimos 365 días.
- **Eficacia**de la Directiva: el porcentaje determinado por las alertas confirmadas totales dividido por las acciones totales realizadas en las alertas (que es la suma de las alertas que se confirmaron o despasón durante el año anterior).
- **Active**: el estado del caso, ya sea *sí* o *no*.

![Panel de directivas de administración de riesgos de Insider](media/insider-risk-policy-dashboard.png)

## <a name="policy-templates"></a>Plantillas de directiva

Las plantillas de administración de riesgos de internación son condiciones de directiva predefinidas que definen los tipos de indicadores de riesgo supervisados por una directiva. Cada Directiva debe tener una plantilla asignada en el Asistente para la creación de directivas antes de que se cree la Directiva. Están disponibles las siguientes plantillas:

- **Robo de datos del empleado**de salida: cuando los empleados dejan la organización, hay indicadores de riesgo específicos que normalmente se asocian con el robo de datos al abandonar a los empleados. Esta plantilla de directiva da prioridad a estos indicadores y se centra en la detección y las alertas de este área de riesgos. El robo de datos por parte de los empleados puede incluir la descarga de archivos de SharePoint Online, la copia de archivos en dispositivos portátiles, como unidades USB, la impresión de archivos y la copia de datos a servicios de almacenamiento y mensajería en la nube personal, cerca de la retirada del empleo y fechas de finalización. Esta plantilla prioriza los indicadores de riesgos relacionados con estas actividades y el modo en que se relacionan con el estado de empleo de los empleados.

    >[!IMPORTANT]
    >Cuando use esta plantilla, debe configurar un conector de Microsoft 365 de RRHH para importar periódicamente la información de fecha de retirada y de cancelación para los empleados de su organización. Consulte el tema de [importación de datos con el conector de recursos humanos](import-hr-data.md) para obtener una guía paso a paso sobre la configuración del conector de 365 de RRHH de Microsoft para su organización.

- **Pérdidas de datos**: la protección de datos y la prevención de pérdidas de datos es un reto constante para la mayoría de las organizaciones, especialmente con el rápido crecimiento de los nuevos datos creados por empleados, dispositivos y servicios. Los empleados están capacitados para crear, almacenar y compartir información a través de servicios y dispositivos que hacen que la administración de pérdidas de datos sea cada vez más compleja y difícil. Las pérdidas de datos pueden incluir el reuso compartido accidental de información fuera de la organización o el robo de datos con malas intenciones. Esta plantilla da prioridad a la detección en tiempo real de descargas de datos sospechosas de SharePoint Online, uso compartido de archivos y carpetas, copiando archivos en dispositivos portátiles, como unidades USB, archivos de impresión y copiando datos en servicios de almacenamiento y mensajería en la nube personal.

    >[!IMPORTANT]
    >Al usar esta plantilla, debe configurar al menos una directiva de prevención de pérdida de datos (DLP) para definir la información confidencial de su organización. Consulte el tema [crear, probar y ajustar una directiva DLP](create-test-tune-dlp-policy.md) para obtener una guía paso a paso sobre la configuración de directivas de DLP para la organización.

- **Lenguaje ofensivo en el correo electrónico**: la detección y la realización de acciones para evitar el comportamiento ofensivo y abusivo es un componente crítico para evitar el riesgo. Los clasificadores de idiomas ofensivos integrados en Microsoft 365 pueden analizar los mensajes de correo electrónico enviados desde buzones de Exchange online en su organización para diferentes tipos de problemas de cumplimiento. Estos clasificadores usan una combinación de inteligencia artificial y palabras clave para identificar el idioma en el correo electrónico que probablemente infrinja las directivas de Antiacoso. Use esta plantilla para crear rápidamente una directiva que use estos clasificadores para detectar automáticamente el contenido de los mensajes de correo electrónico que puedan considerarse abusivos u ofensivos. La administración de riesgos de Insiders usa clasificadores que exploran mensajes de correo electrónico enviados según los términos del idioma inglés y que se recomiendan en lenguaje ofensivo.

## <a name="monitoring-windows"></a>Ventanas de supervisión

Las ventanas de supervisión de directivas permiten definir períodos de tiempo que desencadenan la activación de la Directiva en función de eventos y actividades de las plantillas de directiva de administración de riesgos de Insider. Según la plantilla de directiva que elija, estarán disponibles las siguientes ventanas de supervisión:

- **TimeSpan dentro del ámbito**: disponible para todas las plantillas de Directiva, el valor de *TimeSpan dentro del ámbito* es el número de días definido que la ventana activa **después** de un evento desencadenante. La ventana se activa durante 1 a 30 días después de que se produzca un evento desencadenante para cualquier usuario asignado a la Directiva. Por ejemplo, ha configurado una directiva de administración de riesgos de Insider y ha establecido el valor *de TimeSpan del ámbito en* 30 días. Transcurridos varios meses desde la configuración de la Directiva y se produce un evento desencadenante para uno de los usuarios incluidos en la Directiva. El evento desencadenador activa el *TimeSpan del ámbito* y la Directiva está activa para ese usuario durante 30 días después de que se produjera el evento desencadenante.
- **TimeSpan histórica**: disponible para todas las plantillas de Directiva, el valor de *TimeSpan del historial* es el número de días definido durante el cual la ventana se activa **antes** de un evento desencadenante. La ventana se activa de 0 a 180 días antes de que se produzca un evento desencadenante para cualquier usuario asignado a la Directiva. Por ejemplo, ha configurado una directiva de administración de riesgos de Insider y ha establecido el valor de *TimeSpan histórico* en 90 días. Transcurridos varios meses desde la configuración de la Directiva y se produce un evento desencadenante para uno de los usuarios incluidos en la Directiva. El evento desencadenador activa el *TimeSpan histórico* y la Directiva recopila actividades históricas para ese usuario durante 90 días antes del evento desencadenante.
- **Ventana de finalización futura**: verá esta opción en la versión preliminar de la edición, pero no se aplicará a ninguna directiva y se quitará para la versión de producción de esta solución.
- **Ventana de finalización pasada**: verá esta opción en la versión preliminar de la edición, pero no se aplicará a ninguna directiva y se quitará para la versión de producción de esta solución.

## <a name="create-a-new-policy"></a>Crear una nueva Directiva

Para crear una nueva Directiva de administración de riesgos de Insider, use el Asistente para directivas de la solución de **Administración de riesgos de Insider** en el centro de cumplimiento de Microsoft 365.

Complete los siguientes pasos para crear una nueva Directiva:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **directivas** .
2. Seleccione **crear Directiva** para abrir el Asistente para directivas
3. En la página **nueva Directiva de riesgo de Insider** , complete los campos siguientes:
    - **Nombre (obligatorio)**: escriba un nombre descriptivo para la Directiva.
    - **Descripción (opcional)**: escriba una descripción para la Directiva.
    - **Elegir plantilla de directiva (obligatorio)**: Seleccione una de las [plantillas de directiva](insider-risk-management-policies.md#policy-templates) para definir los tipos de indicadores de riesgo que se supervisan mediante la Directiva.

    >[!IMPORTANT]
    >Si selecciona la plantilla de *fugas de datos* , tendrá que configurar al menos una directiva DLP que asignará más adelante en el asistente. Si selecciona la plantilla de *robo de datos de empleado* de la que se descargan, tendrá que configurar el conector de recursos humanos para que use las características de detección de señal completa de la plantilla de directiva.

4. Seleccione **siguiente** para continuar.
5. En la página **usuarios** , seleccione **Agregar usuario o grupo** para definir los usuarios que se incluirán en la Directiva o Active la casilla de verificación **todos los usuarios y grupos con correo habilitado** . Seleccione **siguiente** para continuar.
6. En la página **especificar el contenido que va a priorizar (opcional)** , puede asignar los orígenes para priorizar las actividades de usuario arriesgadas:
    - Sitios de SharePoint: seleccione **Agregar sitio de SharePoint** y seleccione las organizaciones de SharePoint que desea priorizar. Por ejemplo, *"Group1@contoso.sharepoint.com/sites/group1"*.
    - Tipo de información confidencial: seleccione **Agregar información confidencial escriba** y seleccione los tipos de confidencialidad que desea priorizar. Por ejemplo, *"número de cuenta bancaria de Estados Unidos"* y *"número de tarjeta de crédito"*.
    - Etiquetas de confidencialidad: seleccione **Agregar etiqueta de confidencialidad** y seleccione las etiquetas que desea priorizar. Por ejemplo, *"confidencial"* y *"secreto"*.
7. Seleccione **siguiente** para continuar.
8. En la página **elegir indicadores de alerta** , verá los indicadores que se incluyen en la plantilla que ha elegido para esta Directiva. Si seleccionó la plantilla de *fugas de datos* al principio del asistente, debe seleccionar una directiva DLP en la lista desplegable **Directiva de DLP** .
9. En la página **seleccionar ventana de supervisión** , definirá las [condiciones](insider-risk-management-policies.md#monitoring-windows) de la ventana de supervisión para la Directiva. Configure las ventanas de supervisión según corresponda.
10. Seleccione **siguiente** para continuar.
11. En la página **revisión** , revise la configuración que ha elegido para la Directiva. Seleccione **Editar** para cambiar cualquiera de los valores de la Directiva o seleccione **Enviar** para crear y activar la Directiva.

## <a name="update-a-policy"></a>Actualizar una directiva

Para actualizar una directiva de administración de riesgos de Insider existente, use el Asistente para directivas de la solución de **Administración de riesgos de Insider** en el centro de cumplimiento de Microsoft 365.

Complete los siguientes pasos para administrar una directiva existente:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **directivas** .
2. En el panel de directivas, seleccione la Directiva que desea administrar.
3. En la página Detalles de la Directiva, seleccione **Editar Directiva** .
4. En el Asistente para directivas, no puede editar los campos siguientes:
    - **Name**: el nombre descriptivo de la Directiva.
    - **Seleccione Guía**: la plantilla que se usa para definir los tipos de indicadores de riesgo supervisados por la Directiva.
5. Escriba una nueva descripción para la Directiva en el campo **Descripción** . Seleccione **siguiente** para continuar.
6. En la página **usuarios** , seleccione **Agregar usuario o grupo** para definir los usuarios que se incluirán en la Directiva o Active la casilla de verificación **todos los usuarios y grupos con correo habilitado** . Seleccione **siguiente** para continuar.
7. En la página **especificar el contenido que va a priorizar (opcional)** , actualice los orígenes para priorizar las actividades de usuario arriesgadas:
    - Sitios de SharePoint: seleccione **Agregar sitio de SharePoint** y seleccione las organizaciones de SharePoint que desea priorizar. Por ejemplo, *"Group1@contoso.sharepoint.com/sites/group1"*.
    - Tipo de información confidencial: seleccione **Agregar información confidencial escriba** y seleccione los tipos de confidencialidad que desea priorizar. Por ejemplo, *"número de cuenta bancaria de Estados Unidos"* y *"número de tarjeta de crédito"*.
    - Etiquetas de confidencialidad: seleccione **Agregar etiqueta de confidencialidad** y seleccione las etiquetas que desea priorizar. Por ejemplo, *"confidencial"* y *"secreto"*.
8. Seleccione **siguiente** para continuar.
9. En la página **elegir indicadores de alerta** , verá los indicadores que se incluyen en la plantilla que ha elegido para esta Directiva. Si seleccionó la plantilla de *fugas de datos* al principio del asistente, debe seleccionar una directiva DLP en la lista desplegable **Directiva de DLP** .
10. En la página **seleccionar ventana de supervisión** , definirá las [condiciones](insider-risk-management-policies.md#monitoring-windows) de la ventana de supervisión para la Directiva. Configure las ventanas de supervisión según corresponda.
11. En la página **revisión** , revise la configuración que ha elegido para la Directiva. Seleccione **Editar** para cambiar cualquiera de los valores de la Directiva o seleccione **Enviar** para actualizar y activar los cambios en la Directiva.

## <a name="delete-a-policy"></a>Eliminar una directiva

>[!NOTE]
>Al eliminar una directiva no se eliminan las alertas activas o archivadas generadas desde la Directiva.

Para eliminar una directiva de administración de riesgos de Insider existente, siga estos pasos:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **directivas** .
2. En el panel de directivas, seleccione la Directiva que desea administrar.
3. Seleccione **eliminar** en la barra de herramientas del panel.
4. En el cuadro de diálogo **eliminar** , seleccione **sí** para eliminar la Directiva o seleccione **Cancelar** para cerrar el cuadro de diálogo.