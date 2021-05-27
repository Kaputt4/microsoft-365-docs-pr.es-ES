---
title: Investigar y corregir las alertas de cumplimiento de las comunicaciones
description: Investigar y corregir las alertas de cumplimiento de comunicaciones en Microsoft 365.
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
ms.openlocfilehash: 170955ebba633c1749423e11bb34f7bfbdba1f07
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684116"
---
# <a name="investigate-and-remediate-communication-compliance-alerts"></a>Investigar y corregir las alertas de cumplimiento de las comunicaciones

Después de configurar las directivas de cumplimiento de comunicaciones, empezará a recibir alertas en el centro de cumplimiento de Microsoft 365 para los problemas de mensajes que coincidan con las condiciones de la directiva. Siga las instrucciones del flujo de trabajo aquí para investigar y corregir problemas de alerta.

## <a name="investigate-alerts"></a>Investigar alertas

El primer paso para investigar los problemas detectados por las directivas es revisar las alertas de cumplimiento de comunicaciones en el centro de Microsoft 365 cumplimiento. Hay varias áreas en el área de solución de cumplimiento de comunicaciones que le ayudarán a investigar rápidamente las alertas, en función de cómo prefiera ver la agrupación de alertas:

- **Página directiva de cumplimiento de** comunicaciones: cuando inicie sesión en el uso de credenciales para una cuenta de administrador en su organización de Microsoft 365, seleccione Cumplimiento de comunicaciones para mostrar la página Directiva de cumplimiento [https://compliance.microsoft.com](https://compliance.microsoft.com) **de**  comunicaciones. En esta página se muestran las directivas de cumplimiento de comunicaciones configuradas para Microsoft 365 organización y vínculos a plantillas de directiva recomendadas. Cada directiva enumerada incluye el recuento de alertas que necesitan revisión, el número de elementos escalados y resueltos, el estado de la directiva y la fecha y hora del último examen de directiva. Al seleccionar una directiva, se muestran todas las alertas pendientes para las coincidencias con la directiva, se selecciona una alerta específica para iniciar la página de detalles de la directiva e iniciar acciones de corrección.
- **Alertas:** vaya **a Alertas de cumplimiento** de comunicación para mostrar los últimos 30 días de  >   alertas agrupadas por coincidencias de directiva. Esta vista le permite ver rápidamente qué directivas de cumplimiento de comunicaciones generan la mayoría de las alertas ordenadas por gravedad. Para iniciar acciones de corrección, seleccione la directiva asociada a la alerta para iniciar la **página Detalles de la** directiva. Desde la **página** Detalles de la directiva, puede revisar un resumen de las actividades  de la página Información general,  revisar y actuar en los mensajes de alerta de la página Pendiente o revisar el historial de alertas cerradas en la página Resuelto. 
- **Informes:** vaya a Informes **de cumplimiento de**  >  **comunicación** para mostrar widgets de informe de cumplimiento de comunicaciones. Cada widget proporciona una introducción a las actividades y estados de cumplimiento de comunicación, incluido el acceso a información más detallada sobre las coincidencias de directivas y las acciones de corrección.

### <a name="using-filters"></a>Uso de filtros

El siguiente paso es ordenar los mensajes para que le resulte más fácil investigar las alertas. Desde la **página Detalles de** la directiva, el cumplimiento de la comunicación admite el filtrado de varios niveles para varios campos de mensajes que le ayudarán a investigar y revisar rápidamente los mensajes con coincidencias de directiva. El filtrado está disponible para los elementos pendientes y resueltos para cada directiva configurada. Puede configurar las consultas de filtro de una directiva, o configurar y guardar consultas de filtro predeterminado y personalizado para usarlas en cada directiva específica. Después de configurar los campos para un filtro, verá los campos de filtro en la parte superior de la cola de mensajes de alerta que puede configurar para valores de filtro específicos.

Para obtener una lista completa de filtros y detalles de campo, vea [Filters](communication-compliance-feature-reference.md#filters) en el artículo de referencia de características.

#### <a name="to-configure-a-filter"></a>Para configurar un filtro

1. Inicie sesión [https://compliance.microsoft.com](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador en su Microsoft 365 organización.

2. En el centro Microsoft 365 cumplimiento, vaya a **Cumplimiento de comunicaciones.**

3. Seleccione la **pestaña Directivas** y, a continuación, seleccione una directiva para la investigación y haga doble clic para abrir la **página** Directiva.

4. En la **página Directiva,** seleccione la pestaña **Pendiente** o **Resuelto** para mostrar los elementos para filtrar.

5. Seleccione el control **Filters** para abrir la **página De detalles** de filtros.

6. Seleccione una o más casillas para habilitar filtros para estas alertas. Puede elegir entre varios filtros, *incluidos Date*, *Sender*, *Subject/Title*, *Classifiers*, *Language* y mucho más.

7. Si desea guardar el filtro seleccionado como filtro predeterminado, **seleccione Guardar como predeterminado**. Si desea usar este filtro como filtro guardado, seleccione **Listo**.

8. Si desea guardar los filtros seleccionados como una consulta de filtro, seleccione **Guardar** el control de consulta después de configurar al menos un valor de filtro. Escriba un nombre para la consulta de filtro y seleccione **Guardar**. Este filtro solo está disponible para esta directiva y se muestra en la sección Consultas **de filtro guardadas** de la **página Detalles** de filtros.

    ![Controles de detalles del filtro de cumplimiento de comunicaciones](../media/communication-compliance-filter-detail-controls.png)

### <a name="using-near-and-exact-duplicate-analysis"></a>Usar análisis duplicados cercanos y exactos

Las directivas de cumplimiento de comunicaciones analizan y agrupan automáticamente semiduplicados y duplicados exactos de mensaje sin pasos de configuración adicional. Esta vista le permite actuar rápidamente en mensajes similares uno a uno o como grupo, lo que reduce la carga de investigación de mensajes para los revisores. A medida que se detectan los duplicados, los controles de **Semiduplicados** y/o **Duplicados exactos** se muestran en la barra de herramientas de acción de corrección. Esta vista no está disponible si no se encuentran duplicados cercanos o exactos.

#### <a name="to-remediate-duplicates"></a>Para corregir duplicados

1. Inicie sesión [https://compliance.microsoft.com](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador en su Microsoft 365 organización.

2. En el centro Microsoft 365 cumplimiento, vaya a **Cumplimiento de comunicaciones.**

3. Seleccione la **pestaña Directivas** y, a continuación, seleccione una directiva para la investigación y haga doble clic para abrir la **página** Directiva.

4. En la **página Directiva,** seleccione la pestaña **Pendiente** **o** Resuelto para mostrar mensajes duplicados.

5. Seleccione los **controles Duplicados cercanos** **o Duplicados exactos** para abrir la página de detalles de duplicados.

6. Seleccione uno o varios mensajes para corregir los controles de acción de estos mensajes.

7. Seleccione **Resolver**, **Notificar,** **Escalar** o **Descargar** para aplicar la acción a los mensajes duplicados seleccionados como filtro predeterminado.

8. Seleccione **Cerrar** después de completar las acciones de corrección en los mensajes.

    ![Controles duplicados exactos de cumplimiento de comunicación](../media/communication-compliance-duplicates-controls.png)

## <a name="remediate-alerts"></a>Corregir alertas

Independientemente de dónde empiece a revisar las alertas o el filtrado que configure, el siguiente paso es tomar medidas para corregir la alerta. Inicie la corrección de alertas con el siguiente flujo de trabajo en las **páginas Directiva** **o** Alertas.

### <a name="step-1-examine-the-message-basics"></a>Paso 1: Examinar los conceptos básicos del mensaje

 A veces es obvio desde el origen o el asunto que un mensaje se puede corregir inmediatamente. Puede ser que el mensaje es falso o coincide incorrectamente con una directiva y debe resolverse como un falso positivo. Seleccione el control **Falso positivo** para resolver la alerta y quitarla de la cola de alertas pendientes inmediatamente. Desde la información de origen o del remitente, puede que ya sepa cómo se debe enrutar o administrar el mensaje en estas circunstancias. Considere la posibilidad de usar los controles **Etiquetar como** o **Escalar** para asignar una etiqueta a los mensajes aplicables o enviar mensajes a un revisor designado.

![Controles de corrección de cumplimiento de comunicaciones](../media/communication-compliance-remediation-controls.png)

### <a name="step-2-examine-the-message-details"></a>Paso 2: Examinar los detalles del mensaje

Después de revisar los conceptos básicos del mensaje, es el momento de abrir un mensaje para examinar los detalles y determinar acciones de corrección adicionales. Seleccione un mensaje para ver la información completa del encabezado y el cuerpo del mensaje. Hay disponibles varias vistas diferentes para ayudarle a decidir el curso correcto de la acción:

- **Vista de origen**: esta vista es la vista del mensaje estándar que se muestra de manera más común en la mayoría de las plataformas de mensajería basadas en web. La información del encabezado tiene formato en el estilo normal y el cuerpo del mensaje admite archivos gráficos y texto ajustado por palabras. Si el reconocimiento óptico de caracteres [(OCR)](communication-compliance-feature-reference.md#optical-character-recognition-ocr) está habilitado para la directiva, las imágenes que contienen texto impreso o escrito a mano que coinciden con la directiva condicional se ven como un elemento secundario para el mensaje asociado en esta vista.
- **Vista** de texto: la vista Texto muestra una vista de solo texto numerada de línea del mensaje e incluye resaltado de palabras clave en mensajes y datos adjuntos para términos de tipo de información confidencial o palabras clave coincidentes en la directiva de cumplimiento de comunicación asociada. El resaltado de palabras clave puede ayudarle a examinar rápidamente mensajes largos y datos adjuntos para el área de interés. En algunos casos, el texto resaltado puede estar solo en los datos adjuntos de los mensajes que coinciden con las condiciones de la directiva. El resaltado de palabras clave no es compatible con los términos identificados por clasificadores integrados asignados a una directiva. Los archivos incrustados no se muestran y la numeración de línea de esta vista es útil para hacer referencia a detalles pertinentes entre varios revisores.
- **Anotar en la vista**: esta vista permite a los revisores agregar anotaciones directamente en el mensaje que se guarda en la vista del mensaje. Si [OCR está](communication-compliance-feature-reference.md#optical-character-recognition-ocr) habilitado para la directiva, las imágenes que contienen texto impreso o escrito a mano que coinciden con el condicional de la directiva se ven como un elemento secundario para el mensaje asociado en esta vista y pueden anotarse.
- Vista de conversación **(versión preliminar):** disponible para los mensajes de chat de Microsoft Teams, esta vista muestra hasta cinco mensajes antes y después de un mensaje de alerta para ayudar a los revisores a ver la actividad en el contexto de conversación. Este contexto ayuda a los revisores a evaluar rápidamente los mensajes y tomar decisiones de resolución de mensajes más fundamentadas. Se muestran adiciones de mensajes en tiempo real a las conversaciones, incluidas todas las imágenes en línea, emojis y adhesivos disponibles en Teams. No se muestran los datos adjuntos de archivos de imagen o texto de los mensajes. Las notificaciones se muestran automáticamente para los mensajes que se han editado o para los mensajes que se han eliminado de la ventana de conversación. Cuando se resuelve un mensaje, los mensajes de conversación asociados no se conservan con el mensaje resuelto. Los mensajes de conversación están disponibles hasta 60 días después de identificar el mensaje de alerta.
- **Historial de usuario**: la vista Historial de usuario muestra todas las demás alertas generadas por cualquier directiva de cumplimiento de comunicaciones para que el usuario envíe el mensaje.
- **Notificación de patrón detectado:** muchas acciones de acoso y acoso con el tiempo y implican instancias recurrentes del mismo comportamiento por parte de un usuario. La *notificación Patrón detectado* se muestra en los detalles de la alerta y llama la atención a la alerta. La detección de patrones se hace por directiva y evalúa el comportamiento de los últimos 30 días cuando un remitente envía al mismo destinatario al menos dos mensajes. Los investigadores y revisores pueden usar esta notificación para identificar comportamientos repetidos para evaluar la alerta según corresponda.
- **Mostrar vista Traducir:** esta vista convierte automáticamente el texto  del mensaje de alerta al idioma configurado en la configuración idioma mostrado en la suscripción Microsoft 365 para cada revisor. La vista Traducir ayuda a ampliar la compatibilidad de investigación para organizaciones con usuarios multilingües y elimina la necesidad de servicios de traducción adicionales fuera del proceso de revisión de cumplimiento de comunicaciones. Con los servicios de Microsoft Translate, la vista Traducir puede estar activada y desactivada según sea necesario y admite una amplia variedad de idiomas. Para obtener una lista completa de los idiomas admitidos, vea [Microsoft Traductor Languages](https://www.microsoft.com/translator/business/languages/). Los idiomas que aparecen *en Traductor lista de idiomas se* admiten en la vista Traducir.

    ![Controles de vista de mensajes de cumplimiento de comunicación](../media/communication-compliance-message-views.png)

### <a name="step-3-decide-on-a-remediation-action"></a>Paso 3: Decidir sobre una acción de corrección

Ahora que ha revisado los detalles del mensaje para la alerta, puede elegir varias acciones de corrección:

- **Resolver:** al seleccionar el control **Resolver,**  se quita inmediatamente el mensaje de la cola de alertas pendientes y no se puede realizar ninguna acción adicional en el mensaje. Al seleccionar **Resolver,** básicamente ha cerrado la alerta sin clasificación adicional y no se puede volver a abrir para otras acciones. Todos los mensajes resueltos se muestran en la **pestaña Resuelto.**
- **Falso positivo:** siempre puede resolver un mensaje como falso positivo en cualquier momento durante el flujo de trabajo de revisión de mensajes. False positive significa que la alerta no era procesable o que la alerta se generó incorrectamente por el proceso de alerta. El mensaje no se puede volver a abrir y todos los mensajes falsos positivos se muestran en la **pestaña** Resuelto.
- **Power Automate (versión preliminar):** use un flujo de Power Automate para automatizar las tareas de proceso de un mensaje de alerta. De forma predeterminada,  el cumplimiento de la comunicación incluye el Administrador de notificaciones cuando un usuario tiene una plantilla de flujo de alerta de cumplimiento de comunicación que los revisores pueden usar para automatizar el proceso de notificación para los usuarios con alertas de mensajes. Para obtener más información sobre cómo crear y administrar Power Automate flujos de cumplimiento de comunicaciones, vea el artículo de referencia de la característica de cumplimiento [de](communication-compliance-feature-reference.md#power-automate-flows) comunicación.
- **Etiqueta como**: Etiquetar el *mensaje* como *compatible,* no conforme o tan *cuestionable* como se refiere a las directivas y estándares de su organización. Agregar etiquetas y etiquetas de comentarios le ayuda a alertas de directivas de microfiltro para escalaciones o como parte de otros procesos de revisión interna. Una vez completado el etiquetado, también puede decidir resolver el mensaje para sacarlo de la cola de revisión pendiente.
- **Notify**: Puede usar el control **Notify** para asignar una plantilla de aviso personalizada a la alerta y enviar un aviso de advertencia al usuario. Elija la plantilla de aviso adecuada configurada en el área **Configuración** de cumplimiento de comunicaciones y seleccione **Enviar** para enviar un aviso por correo electrónico al usuario que envió el mensaje y para resolver el problema.
- **Escalar:** con el control **Escalate,** puede elegir quién más de su organización debe revisar el mensaje. Elija entre una lista de revisores configurados en la directiva de cumplimiento de comunicaciones para enviar una notificación por correo electrónico que solicite una revisión adicional de la alerta de mensaje. El revisor seleccionado puede usar un vínculo en la notificación por correo electrónico para ir directamente a los elementos que se les han escalado para su revisión.
- **Escala para la investigación:** con el control **Escalate para** la investigación, puede crear un nuevo Advanced eDiscovery [caso](overview-ediscovery-20.md) para mensajes individuales o múltiples. Proporcionará un nombre y notas para el nuevo caso, y el usuario que envió el mensaje que coincide con la directiva se asigna automáticamente como el custodio del caso. No necesita permisos adicionales para administrar el caso. La creación de un caso no resuelve ni crea una nueva etiqueta para el mensaje. Puede seleccionar un total de 100 mensajes al crear un Advanced eDiscovery caso durante el proceso de corrección. Se admiten mensajes en todos los canales de comunicación supervisados por el cumplimiento de la comunicación. Por ejemplo, puede seleccionar 50 chats de Microsoft Teams, 25 mensajes de correo electrónico Exchange Online y 25 mensajes de Yammer al abrir un nuevo caso Advanced eDiscovery para un usuario.
- **Quitar mensaje en Teams:** mediante el control Quitar mensaje de **Teams,** puede bloquear mensajes inapropiados y contenido identificado en alertas de canales de Microsoft Teams y chats de grupo y 1:1. Los mensajes y el contenido eliminados se reemplazan por una sugerencia de directiva que explica que está bloqueado y la directiva que se aplica a su eliminación de la vista. A los destinatarios se les proporciona un vínculo en la sugerencia de directiva para obtener más información sobre la directiva aplicable y el proceso de revisión. El remitente recibe una sugerencia de directiva para el mensaje bloqueado y el contenido, pero puede revisar los detalles del mensaje bloqueado y el contenido para obtener contexto con respecto a la eliminación.

    ![Quitar un mensaje de Microsoft Teams](../media/communication-compliance-remove-teams-message.png)

### <a name="step-4-determine-if-message-details-should-be-archived-outside-of-communication-compliance"></a>Paso 4: Determinar si los detalles del mensaje deben archivarse fuera del cumplimiento de la comunicación

Los detalles del mensaje se pueden exportar o descargar si necesita archivar los mensajes en una solución de almacenamiento independiente. Al seleccionar el control **Descargar** los mensajes seleccionados se agregan automáticamente a un archivo .ZIP que se puede guardar en almacenamiento fuera de Microsoft 365.
