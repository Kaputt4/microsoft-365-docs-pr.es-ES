---
title: Guía de operaciones de seguridad para Microsoft 365 Empresa Premium
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-security
ms.subservice: other
ms.date: 09/15/2022
ms.localizationpriority: high
ms.collection:
- m365solution-smb
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
description: 'Un conjunto de sugerencias sobre en qué centrar sus esfuerzos en el portal de Defender cuando se trata de operaciones diarias, semanales o mensuales. '
ms.openlocfilehash: 95a05dfee0cea3cc8da7832964ca7465c1d5e7d6
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67743292"
---
# <a name="microsoft-365-business-premium-security-operations-guide"></a>Guía de operaciones de seguridad de Microsoft 365 Empresa Premium

Si no está familiarizado con Microsoft 365 Empresa Premium, o si aún no tiene una guía de operaciones de seguridad, este artículo puede servir como punto de partida. Si ya tiene una guía de operaciones de seguridad, revísela con las recomendaciones de este artículo.

Puede usar esta guía para tomar decisiones sobre las prioridades de incidentes de seguridad y las tareas que realizará su equipo de seguridad en el portal de Microsoft Defender ([https://security.microsoft.com](https://security.microsoft.com)).

| Frecuencia sugerida | Tareas  |
|---------|---------|
| Diario  | [Comprobar la vulnerabilidad de amenazas](#check-your-threat-vulnerability).<br/>[Revisar las acciones pendientes en el centro de actividades](#review-pending-actions-in-the-action-center).<br/>[Revisar los dispositivos con detecciones de amenazas](#review-devices-with-threat-detections).<br/>[Obtener información sobre nuevos incidentes o alertas](#learn-about-new-incidents-or-alerts). |
| Semanal | [Supervisar y mejorar su puntuación de seguridad de Microsoft](#monitor-and-improve-your-microsoft-secure-score).<br/>[Revisar la puntuación de seguridad de los dispositivos](#review-the-secure-score-for-devices).<br/>[Mejorar la puntuación de seguridad de los dispositivos](#improve-your-secure-score-for-devices). |
| Mensualmente | [Ejecutar informes](#run-reports).<br/>[Ejecutar un tutorial de simulación](#run-a-simulation-tutorial).<br/>[Explorar el Centro de aprendizaje](#explore-the-learning-hub). |
| (Según sea necesario) | [Usar el panel de análisis de amenazas](#use-the-threat-analytics-dashboard).<br/>[Ejecutar un examen o una investigación automatizada](#run-a-scan-or-automated-investigation).<br/>[Corregir un elemento](#remediate-an-item). | 

En las secciones siguientes se proporcionan más detalles sobre cada tarea.
  
## <a name="suggested-daily-tasks"></a>Tareas diarias sugeridas

Estas son algunas sugerencias para las tareas de seguridad que se llevan a cabo a diario.

- [Comprobar la vulnerabilidad de amenazas](#check-your-threat-vulnerability).
- [Revisar las acciones pendientes en el centro de actividades](#review-pending-actions-in-the-action-center).
- [Revisar los dispositivos con detecciones de amenazas](#review-devices-with-threat-detections).
- [Obtener información sobre nuevos incidentes o alertas](#learn-about-new-incidents-or-alerts).

### <a name="check-your-threat-vulnerability"></a>Comprobar la vulnerabilidad de amenazas.

En resumen, puede obtener una instantánea de una vulnerabilidad de amenazas consultando el panel de administración de vulnerabilidades. Refleja lo vulnerable que es su organización a las amenazas de ciberseguridad. Una puntuación de exposición alta significa que los dispositivos son más vulnerables a la explotación.

1. En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en el panel de navegación, seleccione **Administración de vulnerabilidades > Panel**.

2. Eche un vistazo a la puntuación de exposición de la organización. Si está en el nivel aceptable o > Alto> rango, puede continuar. Si no es así, seleccione **Mejorar puntuación** para ver detalles adicionales y recomendaciones de seguridad para mejorar esta puntuación.

Tener en cuenta la puntuación de exposición le ayuda a:

- Comprender e identificar rápidamente conclusiones generales sobre el estado de la seguridad en su organización
- Detectar y responder a áreas que requieren investigación o acción para mejorar el estado actual
- Comunicarse con compañeros y administración sobre el impacto de los esfuerzos de seguridad

### <a name="review-pending-actions-in-the-action-center"></a>Revisar las acciones pendientes en el centro de actividades

A medida que se detectan amenazas, entran en juego las acciones de corrección. En función de la amenaza concreta y de cómo se configuren las opciones de seguridad, las acciones de corrección pueden realizarse automáticamente o solo tras su aprobación, motivo por el que se deben supervisar periódicamente. Entre los ejemplos de acciones de corrección se incluyen el envío de un archivo en cuarentena, la detención de la ejecución de un proceso o la eliminación de una tarea programada. Se realiza un seguimiento de todas las acciones de corrección en el centro de actividades.

1. En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en el panel de navegación, elija **Centro de actividades**.

2. Seleccione la pestaña **Pendiente** para ver y aprobar (o rechazar) las acciones pendientes. Estas acciones pueden surgir de la protección antivirus/antimalware, las investigaciones automatizadas, las actividades de respuesta manual o las sesiones de respuesta inmediata.

3. Seleccione la pestaña **Historial** para ver una lista de las acciones completadas.

### <a name="review-devices-with-threat-detections"></a>Revisar los dispositivos con detecciones de amenazas

Para averiguar si tiene algún dispositivo que haya tenido amenazas, haga lo siguiente.

1. En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en el panel de navegación, elija **Informes > General > Informe de seguridad**.

2. Desplácese hacia abajo hasta la fila Dispositivos vulnerables. Si se detectaron amenazas en los dispositivos, verá esa información en esta fila.

### <a name="learn-about-new-incidents-or-alerts"></a>Obtener información sobre nuevos incidentes o alertas

1. En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en el menú de navegación, seleccione **Incidentes**. Los incidentes se muestran en la página con alertas asociadas.

2. Seleccione una alerta para abrir su panel flotante, donde puede obtener más información sobre la alerta.

3. En el control flotante, puede ver el título de la alerta, ver una lista de los recursos (como puntos de conexión o cuentas de usuario) que se vieron afectados, realizar acciones disponibles y usar vínculos para ver más información e incluso abrir la página de detalles de la alerta seleccionada.

### <a name="run-a-scan-or-automated-investigation"></a>Ejecutar un examen o una investigación automatizada

1. En el portal de Microsoft 365 Defender (https://security.microsoft.com), en el panel de navegación, elija Inventario de dispositivos.

2. Seleccione un dispositivo para abrir su panel flotante y revise la información que se muestra.

3. Seleccione los puntos suspensivos (...) para abrir el menú acciones.

4. Seleccione una acción, como **Ejecutar escaneo antivirus** o **Iniciar Investigación automatizada**.

## <a name="suggested-weekly-tasks"></a>Tareas semanales sugeridas

Estas son algunas sugerencias de tareas de seguridad importantes que se deben realizar al menos cada semana.

- [Supervisar y mejorar su puntuación de seguridad de Microsoft](#monitor-and-improve-your-microsoft-secure-score).
- [Revisar la puntuación de seguridad de los dispositivos](#review-the-secure-score-for-devices).
- [Mejorar la puntuación de seguridad de los dispositivos](#improve-your-secure-score-for-devices).

### <a name="monitor-and-improve-your-microsoft-secure-score"></a>Supervisar y mejorar la puntuación de seguridad de Microsoft

La Puntuación de seguridad de Microsoft es una medida de la actitud de seguridad de una organización, donde un número más alto indica que se necesitan menos acciones de mejora.

La puntuación de seguridad ayuda a las organizaciones a:

- Informar sobre el estado actual de la situación en materia de seguridad de la organización.
- Mejorar la situación de seguridad proporcionando capacidad de descubrimiento, visibilidad, orientación y control.
- Comparar con puntos de referencia y establecer indicadores clave de rendimiento (KPI).

1. Para comprobar la puntuación de seguridad, en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en el panel de navegación, elija **Puntuación de seguridad**. 

2. Revise y tome decisiones sobre las correcciones y acciones con el fin de mejorar la puntuación de seguridad general de Microsoft.

### <a name="review-the-secure-score-for-devices"></a>Revisión de la puntuación de seguridad de los dispositivos

También se encuentra en el panel administración de vulnerabilidades la puntuación de seguridad de Microsoft para la tarjeta de dispositivos. Esta tarjeta muestra la puntuación actual y una puntuación más alta indica que los puntos de conexión son más resistentes a los ciberataques. Refleja el estado de seguridad de todos los dispositivos, colectivamente.

Los datos de esta tarjeta son el producto de un proceso de detección de vulnerabilidades constante y constante. Se agrega con evaluaciones de detección de configuración que continuamente:

- Comparar las configuraciones recopiladas con las pruebas comparativas recopiladas para detectar recursos mal configurados
- Asignar configuraciones a vulnerabilidades que se pueden corregir o corregir parcialmente (reducción de riesgos)
- Recopilar y mantener pruebas comparativas de configuración de procedimientos recomendados (proveedores, fuentes de seguridad, equipos de investigación internos)
- Recopilar y supervisar los cambios del estado de configuración del control de seguridad de todos los recursos

### <a name="improve-your-secure-score-for-devices"></a>Mejorar la puntuación de seguridad de los dispositivos

Mejore la configuración de seguridad mediante la corrección de problemas mediante la lista de recomendaciones de seguridad. A medida que lo hace, la Puntuación de seguridad de Microsoft para dispositivos mejora y su organización se vuelve más resistente frente a las amenazas y vulnerabilidades de ciberseguridad en el futuro. Siempre merece la pena el tiempo que se tarda en revisar y mejorar la puntuación.

1. Para comprobar la puntuación de seguridad, en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en el panel de navegación, seleccione **Puntuación de seguridad**.

2. En la tarjeta **Puntuación de seguridad de Microsoft** para dispositivos del panel Administración de vulnerabilidades de Defender, seleccione una de las categorías. Se muestra una lista de recomendaciones relacionadas con esa categoría, junto con las recomendaciones.

3. Seleccione un elemento de la lista para mostrar los detalles relacionados con la recomendación.

4. Seleccione **Opciones de corrección**.

5. Lea la descripción para comprender el contexto del problema y qué hacer a continuación. Elija una fecha de vencimiento, agregue notas y seleccione Exportar todos los datos de actividad de corrección a CSV para que pueda adjuntarlos a un correo electrónico para su seguimiento. Se ha creado un mensaje de confirmación que indica que se ha creado la tarea de corrección.

6. Envíe un correo electrónico de seguimiento al administrador de TI y espere el tiempo que ha asignado para que la corrección se propague en el sistema.

7. Vuelva a la tarjeta Puntuación de seguridad de Microsoft para dispositivos en el panel. El número de recomendaciones de controles de seguridad ha disminuido como resultado de las acciones.

8. Seleccione **Controles de seguridad** para volver a la página Recomendaciones de seguridad. El elemento que ha abordado ya no aparece en la lista, lo que mejora la puntuación de seguridad de Microsoft.

## <a name="suggested-monthly-tasks"></a>Tareas mensuales sugeridas

Estas tareas deben realizarse al menos mensualmente, si no con más frecuencia. 

- [Ejecutar informes](#run-reports).
- [Ejecutar un tutorial de simulación](#run-a-simulation-tutorial).
- [Explorar el Centro de aprendizaje](#explore-the-learning-hub).

### <a name="run-reports"></a>Ejecutar informes

Los informes de protección están disponibles en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)).

1. En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en el panel de navegación, seleccione **Informes**.

2. Elija un informe para revisar. Cada informe muestra muchas categorías pertinentes para ese informe.

3. Seleccione **Ver detalles** para ver información más detallada de cada categoría.

4. Seleccione el título de una amenaza determinada para ver detalles específicos de ella.

### <a name="run-a-simulation-tutorial"></a>Ejecución de un tutorial de simulación

Siempre es una buena idea aumentar la preparación de seguridad para usted y su equipo a través del entrenamiento. Puede acceder a los tutoriales de simulación en el portal de Microsoft 365 Defender. En los tutoriales se tratan varios tipos de amenazas cibernéticas. 

Para empezar:

1. En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en el panel de navegación, elija **Tutoriales**.

2. Lea el tutorial de un tutorial que le interese ejecutar y, a continuación, descargue el archivo o copie el script necesario para ejecutar la simulación según las instrucciones.

### <a name="explore-the-learning-hub"></a>Exploración del Centro de aprendizaje

Hay muchas áreas en el Centro de aprendizaje a través de las cuales puede aumentar su conocimiento de muchas de las amenazas que existen y cómo abordarlas. Se recomienda que usted y sus equipos dediquen algún tiempo a explorar los recursos que se ofrecen, especialmente en las secciones Microsoft 365 Defender y Puntos de conexión.

1. En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en el panel de navegación, elija **Centro de aprendizaje**.

2. Seleccione un área, como **Microsoft 365 Defender** o **Puntos de conexión**.

3. Seleccione un elemento para obtener más información sobre cada concepto. 

> [!NOTE]
> Algunos recursos del Centro de aprendizaje pueden cubrir funciones que no se incluyen realmente en Microsoft 365 Empresa Premium. Por ejemplo, las funcionalidades de búsqueda avanzada se incluyen en las suscripciones empresariales, como Defender para punto de conexión Plan 2 o Microsoft 365 Defender, pero no en Microsoft 365 Empresa Premium. [Comparar las características de seguridad de los planes de Microsoft 365 para pequeñas y medianas empresas](../security/defender-business/compare-mdb-m365-plans.md).

## <a name="as-needed"></a>(Según sea necesario)

Realice estas tareas según sea necesario o según corresponda:

- [Usar el panel de análisis de amenazas](#use-the-threat-analytics-dashboard).
- [Ejecutar un examen o una investigación automatizada](#run-a-scan-or-automated-investigation).
- [Corregir un elemento](#remediate-an-item).

### <a name="use-the-threat-analytics-dashboard"></a>Uso del panel de análisis de amenazas

Use el panel de análisis de amenazas para obtener información general sobre el panorama de amenazas actual resaltando los informes más relevantes para su organización. 

1. En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en el panel de navegación, seleccione **Análisis de amenazas** para mostrar el panel de análisis de amenazas. 

   El panel resume las amenazas en las secciones siguientes:

   - Amenazas más recientes> enumera los informes de amenazas publicados o actualizados más recientemente, junto con el número de alertas activas y resueltas.
   - Amenazas de alto impacto> enumera las amenazas que tienen el mayor impacto en su organización. En esta sección se enumeran primero las amenazas con el mayor número de alertas activas y resueltas.
   - Mayor exposición>enumera primero las amenazas con los niveles de exposición más altos. El nivel de exposición de una amenaza se calcula con dos fragmentos de información: la gravedad de las vulnerabilidades asociadas a la amenaza y el número de dispositivos de su organización que podrían aprovecharse de esas vulnerabilidades.

2. Seleccione el título que quiere investigar y lea el informe asociado. 

3. También puede revisar el informe de analista completo para obtener más detalles o seleccionar otros encabezados para ver los incidentes relacionados, los recursos afectados y la exposición y mitigaciones.

### <a name="remediate-an-item"></a>Corregir un elemento

Microsoft 365 Empresa Premium incluye varias acciones de corrección. Estas acciones incluyen acciones de contestación manual, acciones después de la investigación automatizada y acciones de respuesta inmediata.

1. En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en el panel de navegación, vaya a **Dispositivos activos** > .

   :::image type="content" source="./../media/defender-business/mdb-deviceinventory.png" alt-text="Pantalla del inventario de dispositivos":::

2. Seleccione un dispositivo, como uno con un nivel de riesgo o nivel de exposición alto. Se abre un panel flotante y muestra más información sobre las alertas e incidentes generados para ese elemento, como se muestra en la siguiente imagen:  

   :::image type="content" source="./../media/defender-business/mdb-deviceinventory-selecteddeviceflyout.png" alt-text="Pantalla del panel flotante de un dispositivo seleccionado":::

3. En el control flotante, vea la información que se muestra. Seleccione los puntos suspensivos (...) para abrir un menú que muestra las acciones disponibles, como se muestra en la siguiente imagen: 

   :::image type="content" source="./../media/defender-business/mdb-deviceinventory-selecteddeviceflyout-menu.png" alt-text="Pantalla de acciones disponibles para un dispositivo seleccionado":::

4. Seleccione una acción disponible. Por ejemplo, puede elegir **Ejecutar examen antivirus**, lo que hará que Antivirus de Microsoft Defender inicie un examen rápido en el dispositivo. O bien, puede seleccionar **Iniciar investigación automatizada** para desencadenar una investigación automatizada en el dispositivo.

#### <a name="remediation-actions-in-microsoft-365-business-premium"></a>Acciones de corrección en Microsoft 365 Empresa Premium

En la tabla siguiente se resumen las acciones de corrección que están disponibles en Microsoft 365 Empresa Premium:

| Origen  | Acciones  |
|---------|---------|
| Investigaciones automatizadas      | - Poner en cuarentena un archivo <br/>- Quitar una clave del registro <br/>- Eliminación de un proceso <br/>- Detener un servicio <br/>- Deshabilitar un controlador <br/>- Quitar una tarea programada        |
| Acciones de contestación manual   | - Ejecutar examen de antivirus <br/>- Aislar el dispositivo <br/>- Detener y poner en cuarentena <br/>- Agregar un indicador para bloquear o permitir un archivo       |
| Respuesta inmediata  | - Recopilación de datos forenses <br/>- Análisis de un archivo <br/>- Ejecutar un script <br/>- Envío de una entidad sospechosa a Microsoft para su análisis <br/>- Corrección de un archivo <br/>- Buscar amenazas de forma proactiva  |




## <a name="see-also"></a>Vea también

[Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)