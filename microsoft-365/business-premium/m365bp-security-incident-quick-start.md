---
title: Guía de operaciones de incidentes de seguridad
f1.keywords:
- NOCSH
ms.author: v-kcirillo
author: cirilk
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 80bdae57-f8bc-4e40-a58c-956007117ecb
description: 'Un conjunto de sugerencias sobre en qué centrar sus esfuerzos en el portal de Defender cuando se trata de operaciones diarias, semanales o mensuales. '
ms.openlocfilehash: 5ab0d8ec21ffeac7f8b68a5169641bb9191d3438
ms.sourcegitcommit: 85799f0efc06037c1ff309fe8e609bbd491f9b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2022
ms.locfileid: "66574377"
---
# <a name="microsoft-365-business-premium-security-operations-guide"></a>Guía de operaciones de seguridad de Microsoft 365 Empresa Premium

La siguiente guía proporciona un punto de partida para ayudarle a tomar decisiones sobre las prioridades de los incidentes de seguridad en el portal de Microsoft Defender.
  
## <a name="suggested-daily-tasks"></a>Tareas diarias sugeridas

Estas son algunas sugerencias para las tareas de seguridad que se llevan a cabo a diario.

### <a name="review-for-devices-with-threat-detections"></a>Revisión de dispositivos con detecciones de amenazas

Para averiguar si tiene algún dispositivo que haya tenido amenazas, haga lo siguiente.

1. Vaya al portal de Microsoft 365 Defender (https://security.microsoft.com) e inicie sesión.

1. En el panel de navegación, elija **Informes > General > Informe de seguridad**.

1. Desplácese hacia abajo hasta la fila Dispositivos vulnerables. Si se detectaron amenazas en los dispositivos, verá esa información en esta fila.

### <a name="new-incidents-or-alerts"></a>Nuevos incidentes o alertas

1. Vaya al portal de Microsoft 365 Defender (https://security.microsoft.com) e inicie sesión.

1. En el menú navegación, seleccione **Incidentes**. Los incidentes se muestran en la página con alertas asociadas.

1. Seleccione una alerta para abrir su panel flotante, donde puede obtener más información sobre la alerta.

1. En el control flotante, puede ver el título de la alerta, ver una lista de los recursos (como puntos de conexión o cuentas de usuario) que se vieron afectados, realizar acciones disponibles y usar vínculos para ver más información e incluso abrir la página de detalles de la alerta seleccionada.

### <a name="run-a-scan-or-investigation"></a>Ejecutar un examen o una investigación

1. En el portal de Microsoft 365 Defender (https://security.microsoft.com), en el panel de navegación, elija Inventario de dispositivos.

1. Seleccione un dispositivo para abrir su panel flotante y revise la información que se muestra.

1. Seleccione los puntos suspensivos (...) para abrir el menú acciones.

1. Seleccione una acción, como **Ejecutar escaneo antivirus** o **Iniciar Investigación automatizada**.

## <a name="suggested-weekly-tasks"></a>Tareas semanales sugeridas

Estas son algunas sugerencias de tareas de seguridad importantes que se deben realizar al menos cada semana.

### <a name="monitor-and-respond-to-your-microsoft-secure-score"></a>Supervisar y responder a su Puntuación de Seguridad de Microsoft

La Puntuación de seguridad de Microsoft es una medida de la actitud de seguridad de una organización, donde un número más alto indica que se necesitan menos acciones de mejora.

La puntuación de seguridad ayuda a las organizaciones a:

- Informar sobre el estado actual de la situación en materia de seguridad de la organización.
- Mejorar la situación de seguridad proporcionando capacidad de descubrimiento, visibilidad, orientación y control.
- Comparar con puntos de referencia y establecer indicadores clave de rendimiento (KPI).

Para comprobar la puntuación de seguridad, en el panel de navegación, elija **Puntuación de seguridad**. Revise y tome decisiones sobre las correcciones y acciones con el fin de mejorar la puntuación de seguridad general de Microsoft.

### <a name="look-at-threat-vulnerability"></a>Examen de la vulnerabilidad de amenazas

En resumen, puede obtener una instantánea de una vulnerabilidad de amenazas consultando el panel de administración de vulnerabilidades. Refleja lo vulnerable que es su organización a las amenazas de ciberseguridad. Una puntuación de exposición alta significa que los dispositivos son más vulnerables a la explotación.

1. En el panel de navegación, seleccione **Administración de vulnerabilidades > Panel**.

1. Eche un vistazo a la puntuación de exposición de la organización. Si está en el nivel aceptable o > Alto> rango, puede continuar. Si no es así, haga clic en **Mejorar puntuación** para ver detalles adicionales y recomendaciones de seguridad para mejorar esta puntuación.

Tener en cuenta la puntuación de exposición le ayuda a:

- Comprender e identificar rápidamente conclusiones generales sobre el estado de la seguridad en su organización
- Detectar y responder a áreas que requieren investigación o acción para mejorar el estado actual
- Comunicarse con compañeros y administración sobre el impacto de los esfuerzos de seguridad

### <a name="review-the-secure-score-for-devices"></a>Revisión de la puntuación de seguridad de los dispositivos

También se encuentra en el panel administración de vulnerabilidades la puntuación de seguridad de Microsoft para la tarjeta de dispositivos. Esta tarjeta muestra la puntuación actual y una puntuación más alta indica que los puntos de conexión son más resistentes a los ciberataques. Refleja el estado de seguridad de todos los dispositivos, colectivamente.

Los datos de esta tarjeta son el producto de un proceso de detección de vulnerabilidades constante y constante. Se agrega con evaluaciones de detección de configuración que continuamente:

- Comparar las configuraciones recopiladas con las pruebas comparativas recopiladas para detectar recursos mal configurados
- Asignar configuraciones a vulnerabilidades que se pueden corregir o corregir parcialmente (reducción de riesgos)
- Recopilar y mantener pruebas comparativas de configuración de procedimientos recomendados (proveedores, fuentes de seguridad, equipos de investigación internos)
- Recopilar y supervisar los cambios del estado de configuración del control de seguridad de todos los recursos

### <a name="improve-your-secure-score-for-devices"></a>Mejorar la puntuación de seguridad de los dispositivos

Mejore la configuración de seguridad mediante la corrección de problemas mediante la lista de recomendaciones de seguridad. A medida que lo hace, la Puntuación de seguridad de Microsoft para dispositivos mejora y su organización se vuelve más resistente frente a las amenazas y vulnerabilidades de ciberseguridad en el futuro. Siempre merece la pena el tiempo que se tarda en revisar y mejorar la puntuación.

1. Para comprobar la puntuación de seguridad, en el panel de navegación, seleccione **Puntuación de seguridad**.

1. En la tarjeta Puntuación de seguridad de Microsoft para dispositivos del panel Administración de vulnerabilidades de Defender, seleccione una de las categorías. Se muestra una lista de recomendaciones relacionadas con esa categoría, junto con las recomendaciones.

1. Seleccione un elemento de la lista para mostrar los detalles relacionados con la recomendación.

1. Seleccione **Opciones de corrección**.

1. Lea la descripción para comprender el contexto del problema y qué hacer a continuación. Elija una fecha de vencimiento, agregue notas y seleccione Exportar todos los datos de actividad de corrección a CSV para que pueda adjuntarlos a un correo electrónico para su seguimiento. Se ha creado un mensaje de confirmación que indica que se ha creado la tarea de corrección.

1. Envíe un correo electrónico de seguimiento al administrador de TI y espere el tiempo que ha asignado para que la corrección se propague en el sistema.

1. Vuelva a la tarjeta Puntuación de seguridad de Microsoft para dispositivos en el panel. El número de recomendaciones de controles de seguridad ha disminuido como resultado de las acciones.

1. Seleccione **Controles de seguridad** para volver a la página Recomendaciones de seguridad. El elemento que ha abordado ya no aparece en la lista, lo que mejora la puntuación de seguridad de Microsoft.

## <a name="suggested-monthly-tasks"></a>Tareas mensuales sugeridas

Se trata de tareas que debe realizar mensualmente, si no con más frecuencia. 

### <a name="use-the-threat-analytics-dashboard"></a>Uso del panel de análisis de amenazas

Use el panel de análisis de amenazas para obtener información general sobre el panorama de amenazas actual resaltando los informes más relevantes para su organización. 

Seleccione **Análisis de amenazas** en el panel de navegación para mostrar el panel de análisis de amenazas. El panel resume las amenazas en las secciones siguientes:

- Amenazas más recientes> enumera los informes de amenazas publicados o actualizados más recientemente, junto con el número de alertas activas y resueltas.
- Amenazas de alto impacto> enumera las amenazas que tienen el mayor impacto en su organización. En esta sección se enumeran primero las amenazas con el mayor número de alertas activas y resueltas.
- Mayor exposición>enumera primero las amenazas con los niveles de exposición más altos. El nivel de exposición de una amenaza se calcula con dos fragmentos de información: la gravedad de las vulnerabilidades asociadas a la amenaza y el número de dispositivos de su organización que podrían aprovecharse de esas vulnerabilidades.

Haga clic en el título del que desea investigar y lea el informe asociado. También puede revisar el informe de analista completo para obtener detalles adicionales o seleccionar otros encabezados para ver los incidentes relacionados, los recursos afectados y la exposición y mitigaciones.

### <a name="review-pending-items-in-action-center"></a>Revisar elementos pendientes en el centro de actividades

A medida que se detectan amenazas, entran en juego las acciones de corrección. En función de la amenaza concreta y de cómo se configuren las opciones de seguridad, las acciones de corrección pueden realizarse automáticamente o solo tras su aprobación, motivo por el que se deben supervisar periódicamente. Entre los ejemplos de acciones de corrección se incluyen el envío de un archivo en cuarentena, la detención de la ejecución de un proceso o la eliminación de una tarea programada. Se realiza un seguimiento de todas las acciones de corrección en el centro de actividades.

1. En el panel de navegación, elija **Centro de actividades**.

2. Seleccione la pestaña **Pendiente** para ver y aprobar (o rechazar) las acciones pendientes. Estas acciones pueden surgir de la protección antivirus/antimalware, las investigaciones automatizadas, las actividades de respuesta manual o las sesiones de respuesta inmediata.

3. Seleccione la pestaña **Historial** para ver una lista de las acciones completadas.

### <a name="remediate-an-item"></a>Corregir un elemento

Microsoft Defender para Empresas incluye varias acciones de corrección. Estas acciones incluyen acciones de contestación manual, acciones después de la investigación automatizada y acciones de respuesta inmediata.

### <a name="run-reports"></a>Ejecutar informes

Los informes de protección están disponibles en el portal de Microsoft 365 Defender.

1. Seleccione **Reports** en el panel de navegación.

2. Elija un informe para revisar. Cada informe muestra una serie de categorías pertinentes para ese informe.

3. Haga clic en **Ver detalles** para ver información más detallada de cada categoría.

4. Seleccione el título de una amenaza determinada para ver detalles específicos de ella.

### <a name="run-a-simulation-tutorial"></a>Ejecución de un tutorial de simulación

Siempre es una buena idea aumentar la preparación de seguridad para usted y su equipo a través del entrenamiento. En el menú de navegación de Defender, hay tutoriales que abarcan varios tipos de amenazas cibernéticas. 

Para empezar:

1. Elija **Tutoriales** en el panel de navegación.

2. Lea el tutorial de un tutorial que le interese ejecutar y, a continuación, descargue el archivo o copie el script necesario para ejecutar la simulación según las instrucciones.

### <a name="explore-the-learning-hub"></a>Exploración del Centro de aprendizaje

Hay una serie de áreas en el Centro de aprendizaje a través de las cuales puede aumentar su conocimiento de muchas de las amenazas que existen y cómo abordarlas. Le recomendamos que usted y sus equipos dediquen mucho tiempo a explorar los temas que se ofrecen, especialmente en las secciones Microsoft 365 Defender y Puntos de conexión.

## <a name="see-also"></a>Vea también

[Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)