---
title: Investigar y corregir las alertas de cumplimiento de las comunicaciones
description: Investigue y corrija las alertas de cumplimiento de comunicaciones en Microsoft 365.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 566ee3645fbb5b753269f82f5a43b07e06c4878d
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597485"
---
# <a name="investigate-and-remediate-communication-compliance-alerts"></a>Investigar y corregir las alertas de cumplimiento de las comunicaciones

Una vez que haya configurado las directivas de cumplimiento de comunicaciones, empezará a recibir alertas en el centro de cumplimiento de Microsoft 365 para los problemas de mensajes que coinciden con las condiciones de la Directiva. Siga las instrucciones de flujo de trabajo aquí para investigar y corregir los problemas de alertas.

## <a name="investigate-alerts"></a>Investigar alertas

El primer paso para investigar los problemas detectados por las directivas es revisar las alertas de cumplimiento de comunicaciones en el centro de cumplimiento de Microsoft 365. Hay varias áreas en el área de solución de cumplimiento de comunicaciones para ayudarle a investigar rápidamente las alertas, en función de cómo prefiera ver la agrupación de alertas:

- **Página de directiva de cumplimiento de comunicaciones**: cuando inicie sesión en [https://compliance.microsoft.com](https://compliance.microsoft.com) uso de credenciales para una cuenta de administrador en la organización de Microsoft 365, seleccione **cumplimiento de comunicaciones** para mostrar la página **Directiva** de cumplimiento de comunicaciones. Esta página muestra las directivas de cumplimiento de comunicaciones configuradas para la organización de Microsoft 365 y vínculos a las plantillas de directiva recomendadas. Cada directiva enumerada incluye el número de alertas que necesitan revisión, el número de elementos escalados y resueltos y el estado actual de la Directiva. Al seleccionar una directiva, se muestran todas las alertas pendientes de las coincidencias con la Directiva, se selecciona una alerta específica para iniciar la página de detalles de la Directiva y se inician las acciones de corrección.
- **Alertas**: Navegue a alertas de **cumplimiento de comunicaciones**  >  **Alerts** para mostrar los últimos 30 días de las alertas agrupadas por coincidencias de directivas. Esta vista permite ver rápidamente qué directivas de cumplimiento de comunicación están generando la mayoría de las alertas ordenadas por gravedad. Para iniciar acciones de corrección, seleccione la directiva asociada a la alerta para iniciar la página de detalles de la **Directiva** . En la página de detalles de la **Directiva** , puede revisar un resumen de las actividades en la página **información general** , revisar los mensajes de alerta de la página **pendiente** y actuar sobre ellos, o revisar el historial de las alertas cerradas en la página **resuelta** .
- **Informes**: Navegue a **Communication compliance**  >  **informes** de cumplimiento de comunicaciones para mostrar widgets de informe de cumplimiento de comunicaciones. Cada widget proporciona información general sobre los Estados y las actividades de cumplimiento de la comunicación, incluido el acceso a información detallada sobre las coincidencias de directivas y las acciones de corrección.

### <a name="using-filters"></a>Uso de filtros

El siguiente paso es ordenar los mensajes para que sea más fácil investigar las alertas. En la página de detalles de la **Directiva** , el cumplimiento de la comunicación admite el filtrado de varios niveles para varios campos de mensaje para ayudarle a investigar y revisar rápidamente los mensajes con coincidencias de directivas. El filtrado está disponible para los elementos pendientes y resueltos para cada directiva configurada. Puede configurar consultas de filtro para una directiva o configurar y guardar consultas de filtro personalizadas y predeterminadas para usarlas en cada Directiva específica. Después de configurar los campos de un filtro, verá los campos de filtro que se muestran en la parte superior de la cola de mensajes de alerta que puede configurar para valores de filtro específicos.

Para obtener una lista completa de los filtros y los detalles de los campos, consulte [Filters](communication-compliance-feature-reference.md#filters) en el artículo de referencia de características.

#### <a name="to-configure-a-filter"></a>Para configurar un filtro

1. Inicie sesión [https://compliance.microsoft.com](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador en la organización de Microsoft 365.

2. En el centro de cumplimiento de Microsoft 365, vaya a **cumplimiento de comunicaciones**.

3. Seleccione la pestaña **directivas** y, a continuación, seleccione una directiva de investigación, haga doble clic para abrir la página **Directiva** .

4. En la página **Directiva** , seleccione la pestaña **pendiente** o **resuelto** para mostrar los elementos que se van a filtrar.

5. Seleccione el control **filtros** para abrir la página de detalles de **filtros** .

6. Active una o más casillas para habilitar los filtros para estas alertas. Puede elegir entre varios filtros, incluidos *fecha*, *remitente*, *asunto/título*, *clasificadores*, etc.

7. Si desea guardar el filtro seleccionado como filtro predeterminado, seleccione **Guardar como predeterminado**. Si desea usar este filtro como filtro guardado, seleccione **listo**.

8. Si desea guardar los filtros seleccionados como una consulta de filtro, seleccione **guardar el control de consulta** después de haber configurado al menos un valor de filtro. Escriba un nombre para la consulta de filtro y seleccione **Guardar**. Este filtro está disponible para usarse solo para esta directiva y aparece en la sección **consultas de filtro guardadas** de la página de detalles de **filtros** .

    ![Controles de detalle del filtro de cumplimiento de comunicaciones](../media/communication-compliance-filter-detail-controls.png)

### <a name="using-near-and-exact-duplicate-analysis"></a>Uso del análisis de duplicados Near y Exact

Las directivas de cumplimiento de comunicaciones analizan y agrupan automáticamente los duplicados de mensajes cercanos y exactos sin ningún paso de configuración adicional. Esta vista le permite actuar rápidamente en mensajes similares uno a uno o como un grupo, lo que reduce la carga de la investigación de mensajes para revisores. A medida que se detectan duplicados, los controles de duplicados **cercanos** o los controles de **duplicados exactos** se muestran en la barra de herramientas acción de corrección. Esta vista no está disponible si no se encuentran duplicados cercanos o exactos.

#### <a name="to-remediate-duplicates"></a>Para corregir duplicados

1. Inicie sesión [https://compliance.microsoft.com](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador en la organización de Microsoft 365.

2. En el centro de cumplimiento de Microsoft 365, vaya a **cumplimiento de comunicaciones**.

3. Seleccione la pestaña **directivas** y, a continuación, seleccione una directiva de investigación, haga doble clic para abrir la página **Directiva** .

4. En la página **Directiva** , seleccione la pestaña **pendiente** o **resuelto** para mostrar los mensajes duplicados.

5. Seleccione los controles **Near Duplicates** o **exactamente duplicados** para abrir la página de detalles de duplicados.

6. Seleccione uno o más mensajes para corregir los controles de acción de estos mensajes.

7. Seleccione **resolver**, **notificar**, **remitir a escalar**o **Descargar** para aplicar la acción a los mensajes duplicados seleccionados como filtro predeterminado.

8. Seleccione **cerrar** después de completar las acciones de corrección en los mensajes.

    ![Controles de duplicados exactos de cumplimiento de comunicaciones](../media/communication-compliance-duplicates-controls.png)

## <a name="remediate-alerts"></a>Corregir alertas

Independientemente de dónde empiece a revisar las alertas o el filtrado que configure, el siguiente paso consiste en tomar medidas para corregir la alerta. Inicie la corrección de alertas mediante el siguiente flujo de trabajo en las páginas **Directiva** o **alertas** :

1. **Examine los conceptos básicos de los mensajes**: a veces es obvio que el origen o el asunto es un mensaje que se puede corregir inmediatamente. Puede que el mensaje sea falso o incorrectamente coincidente con una directiva y debe resolverse como falso positivo. Seleccione el control de **falso positivo** para resolver inmediatamente la alerta y quitarla de la cola de alertas pendientes. En la información de origen o de remitente, es posible que ya sepa cómo se debe enrutar o administrar el mensaje en estas circunstancias. Considere la posibilidad de usar los controles **etiquetar como** o **escalar** para asignar una etiqueta a los mensajes correspondientes o para enviar mensajes a un revisor designado.

    ![Controles de corrección de cumplimiento de comunicaciones](../media/communication-compliance-remediation-controls.png)

2. **Examine los detalles del mensaje**: después de revisar los conceptos básicos del mensaje, es el momento de abrir un mensaje para examinar los detalles y para determinar las acciones de corrección adicionales. Seleccione un mensaje para ver la información del cuerpo y el encabezado del mensaje completo. Hay disponibles varias vistas diferentes para ayudarle a decidir el curso adecuado de acción:

    - **Vista de código fuente**: esta vista es la vista de mensajes estándar que normalmente se ve en la mayoría de las plataformas de mensajería basadas en Web. La información de encabezado tiene el formato normal y el cuerpo del mensaje admite archivos gráficos incrustados y texto con ajuste de texto.
    - **Vista**de texto: la vista de texto muestra una vista de texto con numeración de líneas del mensaje e incluye un resaltado de palabras clave para los términos que coinciden en la Directiva de cumplimiento de comunicación asociada. El resaltado de palabras clave puede ayudarle a examinar rápidamente los mensajes largos del área de interés. Los archivos incrustados no se muestran y la numeración de las líneas esta vista resulta útil para hacer referencia a detalles relevantes entre varios revisores.
    - **Vista de anotar**: esta vista permite a los revisores agregar anotaciones directamente en el mensaje que se guardan en la vista del mensaje.
    - **Historial del usuario**: la vista historial del usuario muestra todas las demás alertas generadas por cualquier directiva de cumplimiento de la comunicación para el usuario que envía el mensaje.
    - **Vista de detalles del mensaje**: vista avanzada de metadatos de mensajes e información de configuración.
    - **Notificación de patrón detectado (versión preliminar)**: muchas acciones de acoso y acosos con el tiempo e implican repeticiones del mismo comportamiento por parte de un usuario. La notificación de *patrón detectado* se muestra en los detalles de la alerta y reproduce la atención de la alerta. La detección de patrones se realiza en función de cada directiva y evalúa el comportamiento en los últimos 30 días cuando al menos dos mensajes se envían al mismo destinatario por un remitente. Los investigadores y revisores pueden usar esta notificación para identificar el comportamiento repetido para evaluar la alerta según corresponda.

    ![Controles de vista de mensajes de cumplimiento de comunicaciones](../media/communication-compliance-message-views.png)

3. **Decidir una acción de corrección**: ahora que ha revisado los detalles del mensaje para la alerta, puede elegir varias acciones de corrección:

    - **Resolve**: al seleccionar el control **resolver** , el mensaje se quita inmediatamente de la cola de **alertas pendientes** y no se pueden realizar más acciones en el mensaje. Al seleccionar **resolver**, básicamente ha cerrado la alerta sin más clasificación y no se puede volver a abrir para acciones adicionales. Todos los mensajes resueltos se muestran en la pestaña **resueltos** .
    - **Falso positivo**: siempre puede resolver un mensaje como falso positivo en cualquier momento durante el flujo de trabajo de revisión de mensajes. Falso positivo significa que la alerta no es accionable o que el proceso de alerta ha generado la alerta incorrectamente. No se puede volver a abrir el mensaje y se muestran todos los mensajes falsos positivos en la ficha **resueltos** .
    - **Etiqueta como**: etiquete el mensaje como *compatible*, *no compatible*o tan *dudoso* como relacionado con las directivas y los estándares de su organización. Agregar etiquetas y comentarios de etiquetado ayuda a microfiltrar las alertas de las directivas para las escalaciones o como parte de otros procesos internos de revisión. Una vez finalizado el etiquetado, también puede optar por resolver el mensaje para moverlo de la cola de revisión pendiente.
    - **Notify**: puede usar el control **Notify** para asignar una plantilla de notificación personalizada a la alerta y para enviar un aviso de advertencia al usuario. Elija la plantilla de aviso adecuada configurada en el área **configuración de cumplimiento de comunicaciones** y seleccione **Enviar** a correo electrónico un aviso al usuario que envió el mensaje y para resolver el problema.
    - **Escalar**: con el control **remitir** a, puede elegir quién más de la organización debe revisar el mensaje. Elija de una lista de revisores configurados en la Directiva de cumplimiento de comunicaciones para enviar una notificación de correo electrónico para solicitar una revisión adicional de la alerta de mensaje. El revisor seleccionado puede usar un vínculo en la notificación de correo electrónico para ir directamente a los elementos que se han remitido a ellos para que los revisen.
    - **Escalar para investigación**: con el control **escalar para investigación** , puede crear un nuevo [caso de eDiscovery avanzado](overview-ediscovery-20.md) para uno o varios mensajes. Proporcionará un nombre y notas para el nuevo caso, y el usuario que envió el mensaje que coincida con la Directiva se asigna automáticamente como custodio de caso. No es necesario ningún permiso adicional para administrar el caso. La creación de un caso no resuelve ni crea una nueva etiqueta para el mensaje. Puede seleccionar un total de 100 mensajes al crear un caso de exhibición avanzada de documentos electrónicos durante el proceso de corrección. Se admiten los mensajes de todos los canales de comunicación supervisados por el cumplimiento de la comunicación. Por ejemplo, puede seleccionar 50 chats de Microsoft Teams, 25 mensajes de correo electrónico de Exchange Online y 25 mensajes de Yammer al abrir un nuevo caso de exhibición avanzada de documentos electrónicos para un usuario.
    - **Quitar mensaje de Teams (versión preliminar)**: Si usa el control **quitar mensaje en Microsoft Teams** , puede bloquear los mensajes y el contenido inapropiados que se identifican en las alertas de los canales de Microsoft Teams y 1:1 y chats de grupo. Los mensajes y el contenido quitados se reemplazan por una sugerencia de directiva que explica que está bloqueado y la Directiva que se aplica a su eliminación de la vista. A los destinatarios se les proporciona un vínculo en la sugerencia de directiva para obtener más información sobre la Directiva aplicable y el proceso de revisión. El remitente recibe una sugerencia de directiva para el mensaje y el contenido bloqueados, pero puede revisar los detalles del mensaje bloqueado y el contenido para el contexto relacionado con la eliminación.

    ![Quitar un mensaje de Microsoft Teams](../media/communication-compliance-remove-teams-message.png)

4. **Determine si los detalles del mensaje deben archivarse fuera del cumplimiento de la comunicación**: los detalles del mensaje se pueden exportar o descargar si necesita archivar los mensajes en una solución de almacenamiento independiente. Al seleccionar el control de **descarga** , se agregan automáticamente los mensajes seleccionados a un. Archivo ZIP que puede guardarse en el almacenamiento fuera de Microsoft 365.
