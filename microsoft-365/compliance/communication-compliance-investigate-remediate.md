---
title: Investigar y corregir las alertas de cumplimiento de las comunicaciones
description: Investigar y corregir alertas de cumplimiento de comunicaciones en Microsoft 365.
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
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: fc236ea646e9da487c5e2e1178ddf9ca460cb4ae
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63325143"
---
# <a name="investigate-and-remediate-communication-compliance-alerts"></a>Investigar y corregir las alertas de cumplimiento de las comunicaciones

Después de configurar las directivas de cumplimiento de comunicaciones, empezará a recibir alertas en el Centro de cumplimiento de Microsoft 365 para problemas de mensajes que coincidan con las condiciones de la directiva. Siga las instrucciones del flujo de trabajo aquí para investigar y corregir problemas de alerta.

## <a name="investigate-alerts"></a>Investigar alertas

El primer paso para investigar los problemas detectados por las directivas es revisar las alertas de cumplimiento de comunicaciones en el Centro de cumplimiento de Microsoft 365. Hay varias áreas en el área de solución de cumplimiento de comunicaciones que le ayudarán a investigar rápidamente las alertas, en función de cómo prefiera ver la agrupación de alertas:

- **Página directiva de** cumplimiento de comunicaciones: cuando inicie sesión en el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com) con credenciales para una cuenta de administrador de su organización de Microsoft 365, seleccione Cumplimiento  de comunicaciones para mostrar la página Directiva de cumplimiento **de** comunicaciones. En esta página se muestran las directivas de cumplimiento de comunicaciones configuradas Microsoft 365 organización y vínculos a plantillas de directiva recomendadas. Cada directiva enumerada incluye el recuento de alertas que necesitan revisión, el número de elementos escalados y resueltos, el estado de la directiva y la fecha y hora del último examen de directiva. Al seleccionar una directiva, se muestran todas las alertas pendientes para las coincidencias con la directiva, se selecciona una alerta específica para iniciar la página de detalles de la directiva e iniciar acciones de corrección.
- **Alertas**: vaya **a Cumplimiento** >  **de comunicacionesAlerts** para mostrar los últimos 30 días de alertas agrupadas por coincidencias de directiva. Esta vista le permite ver rápidamente qué directivas de cumplimiento de comunicaciones generan la mayoría de las alertas ordenadas por gravedad. Para iniciar acciones de corrección, seleccione la directiva asociada a la alerta para iniciar la **página Detalles de la** directiva. Desde la **página** Detalles de la directiva, puede revisar un resumen de las actividades de la página Información general, revisar y actuar en los mensajes de  alerta de la página Pendiente o revisar el historial de alertas  cerradas en la página Resuelto.
- **Informes**: vaya a **Cumplimiento** >  **de comunicacionesReports** para mostrar widgets de informe de cumplimiento de comunicaciones. Cada widget proporciona una introducción a las actividades y estados de cumplimiento de comunicación, incluido el acceso a información más detallada sobre las coincidencias de directivas y las acciones de corrección.

### <a name="using-filters"></a>Uso de filtros

El siguiente paso es ordenar los mensajes para que le resulte más fácil investigar las alertas. Desde la **página Detalles de** la directiva, el cumplimiento de la comunicación admite el filtrado de varios niveles para varios campos de mensajes que le ayudarán a investigar y revisar rápidamente los mensajes con coincidencias de directiva. El filtrado está disponible para los elementos pendientes y resueltos para cada directiva configurada. Puede configurar las consultas de filtro de una directiva, o configurar y guardar consultas de filtro predeterminado y personalizado para usarlas en cada directiva específica. Después de configurar los campos para un filtro, verá los campos de filtro en la parte superior de la cola de mensajes de alerta que puede configurar para valores de filtro específicos.

Para el filtro de fecha, la fecha y la hora de los eventos se enumeran en La hora universal coordinada (UTC). Al filtrar mensajes para vistas, la fecha y hora local del usuario solicitante determina los resultados en función de la conversión de la fecha y hora local del usuario a UTC. Por ejemplo, si un usuario de la hora de verano del Pacífico (PDT) de Estados Unidos filtra un informe del 30/30/2021 al 8/31/2021 a las 00:00, el informe incluye mensajes del 8/30/2021 07:00 UTC al 8/31/2021 07:00 UTC. Si el mismo usuario estaba en el horario de verano oriental de Estados Unidos (EDT) al filtrar a las 00:00, el informe incluye mensajes del 30/30/2021 de 04:00 UTC al 8/31/2021 04:00 UTC.

#### <a name="filter-details"></a>Detalles del filtro

Los filtros de cumplimiento de comunicaciones permiten filtrar y ordenar mensajes de alerta para acciones de investigación y corrección más rápidas. El filtrado está disponible en **las pestañas Pendiente** y Resuelto para cada directiva. Para guardar un filtro o un conjunto de filtros como una consulta de filtro guardada, uno o varios valores deben configurarse como selecciones de filtro.

En la tabla siguiente se describen los detalles del filtro:

|**Filtro**|**Detalles**|
|:-----|:-----|
| **Date** | La fecha en que un usuario de la organización envió o recibió el mensaje. Para filtrar por un solo día, seleccione un intervalo de fechas que comience con el día para el que desea obtener los resultados y termine con el día siguiente. Por ejemplo, si desea filtrar los resultados del 20/9/2020, elegiría un intervalo de fechas de filtro del 20/09/2020-9/21/2020.|
| **Clase File** | Clase del mensaje según el tipo de mensaje, ya sea *mensaje o* *datos adjuntos*. |
| **Tiene datos adjuntos** | La presencia de datos adjuntos en el mensaje. |
| **Clase Item** | El origen del mensaje según el tipo de mensaje, el correo electrónico, el chat de Microsoft Team, Bloomberg, etc. Para obtener más información sobre tipos de elementos y clases de mensaje comunes, vea [Tipos de elementos y clases de mensaje](/office/vba/outlook/concepts/forms/item-types-and-message-classes). |
| **Dominios de destinatarios** | Dominio al que se envió el mensaje. Normalmente, este dominio es el Microsoft 365 de suscripción de forma predeterminada. |
| **Destinatario** | El usuario al que se envió el mensaje. |
| **Sender** | La persona que envió el mensaje. |
| **Dominio del remitente** | Dominio que envió el mensaje. |
| **Tamaño** | Tamaño del mensaje en KB. |
| **Asunto/Título** | Asunto del mensaje o título del chat. |
| **Tags** | Las etiquetas asignadas a un mensaje, *ya sea Questionable*, *Compliant* o *Non-compliant*. |
| **Language** | El idioma de texto detectado en el mensaje. El mensaje se clasifica según el idioma de la mayoría del texto del mensaje. Por ejemplo, para un mensaje que contiene texto alemán e italiano, pero la mayoría de texto es alemán, el mensaje se clasifica como alemán (DE). Se admiten los siguientes idiomas: chino (simplificado - ZH), inglés (EN), francés (FR), alemán (DE), italiano (IT), japonés (JP), portugués (PT) y español (ES). Por ejemplo, para filtrar mensajes clasificados como alemán e italiano, escriba "DE,IT" (los códigos de idioma de 2 dígitos) en el cuadro de búsqueda Filtro de idioma. Para ver la clasificación de idioma detectado para un mensaje, seleccione un mensaje, seleccione Ver detalles del mensaje y desplácese al campo EmailDetectedLanguage. |
| **Escalado a** | Nombre de usuario de la persona incluida como parte de una acción de escalamiento de mensajes. |
| **Clasificadores** | Nombre de clasificadores integrados y personalizados que se aplican al mensaje. Algunos ejemplos incluyen *Hostigamiento dirigido*, *Profanidad*, *Amenaza* y mucho más.

#### <a name="to-configure-a-filter"></a>Para configurar un filtro

1. Inicie sesión en [el Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador de su Microsoft 365 organización.

2. En el Centro de cumplimiento de Microsoft 365, vaya a **Cumplimiento de comunicaciones**.

3. Seleccione la **pestaña Directivas** y, a continuación, seleccione una directiva para la investigación y haga doble clic para abrir la **página** Directiva.

4. En la **página Directiva** , seleccione la pestaña **Pendiente** **o Resuelto para** mostrar los elementos para filtrar.

5. Seleccione el control **Filters** para abrir la **página De detalles** de filtros.

6. Seleccione una o más casillas para habilitar filtros para estas alertas. Puede elegir entre varios filtros, como *Date*, *Sender*, *Subject/Title*, *Clasificadores*, *Language* y mucho más.

7. Si desea guardar el filtro seleccionado como filtro predeterminado, seleccione **Guardar como predeterminado**. Si desea usar este filtro como filtro guardado, seleccione **Listo**.

8. Si desea guardar los filtros seleccionados como una consulta de filtro, seleccione **Guardar** el control de consulta después de configurar al menos un valor de filtro. Escriba un nombre para la consulta de filtro y seleccione **Guardar**. Este filtro solo está disponible para esta directiva y se muestra en la sección Consultas **de filtro guardadas** de la **página Detalles** de filtros.

    ![Controles de detalles del filtro de cumplimiento de comunicaciones.](../media/communication-compliance-filter-detail-controls.png)

### <a name="using-near-and-exact-duplicate-analysis"></a>Usar análisis duplicados cercanos y exactos

Las directivas de cumplimiento de comunicaciones analizan y agrupan automáticamente semiduplicados y duplicados exactos de mensaje sin pasos de configuración adicional. Esta vista le permite actuar rápidamente en mensajes similares uno a uno o como grupo, lo que reduce la carga de investigación de mensajes para los revisores. A medida que se detectan los duplicados, los controles de **Semiduplicados** y/o **Duplicados exactos** se muestran en la barra de herramientas de acción de corrección. Esta vista no está disponible si no se encuentran duplicados cercanos o exactos.

#### <a name="to-remediate-duplicates"></a>Para corregir duplicados

1. Inicie sesión en [el Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador de su Microsoft 365 organización.

2. En el Centro de cumplimiento de Microsoft 365, vaya a **Cumplimiento de comunicaciones**.

3. Seleccione la **pestaña Directivas** y, a continuación, seleccione una directiva para la investigación y haga doble clic para abrir la **página** Directiva.

4. En la **página Directiva** , seleccione la pestaña **Pendiente** **o Resuelto** para mostrar mensajes duplicados.

5. Seleccione los **controles Duplicados cercanos** **o Duplicados exactos** para abrir la página de detalles de duplicados.

6. Seleccione uno o varios mensajes para corregir los controles de acción de estos mensajes.

7. Seleccione **Resolver**, **Notificar**, **Escalar** o **Descargar** para aplicar la acción a los mensajes duplicados seleccionados como filtro predeterminado.

8. Seleccione **Cerrar** después de completar las acciones de corrección en los mensajes.

    ![Los controles duplicados exactos de cumplimiento de la comunicación.](../media/communication-compliance-duplicates-controls.png)

## <a name="remediate-alerts"></a>Corregir alertas

Independientemente de dónde empiece a revisar las alertas o el filtrado que configure, el siguiente paso es tomar medidas para corregir la alerta. Inicie la corrección de alertas con el siguiente flujo de trabajo en las **páginas Directiva** **o** Alertas.

### <a name="step-1-examine-the-message-basics"></a>Paso 1: Examinar los conceptos básicos del mensaje

 A veces es obvio desde el origen o el asunto que un mensaje se puede corregir inmediatamente. Puede ser que el mensaje es falso o coincide incorrectamente con una directiva y debe resolverse como mal clasificado. Seleccione el **control Informe como** mal clasificado para compartir contenido mal clasificado con Microsoft, resolver inmediatamente la alerta y quitar de la cola de alertas pendientes. Desde la información de origen o del remitente, puede que ya sepa cómo se debe enrutar o administrar el mensaje en estas circunstancias. Considere la posibilidad de usar los controles **Etiquetar como** o **Escalar** para asignar una etiqueta a los mensajes aplicables o enviar mensajes a un revisor designado.

![Controles de corrección de cumplimiento de comunicaciones.](../media/communication-compliance-remediation-controls.png)

### <a name="step-2-examine-the-message-details"></a>Paso 2: Examinar los detalles del mensaje

Después de revisar los conceptos básicos del mensaje, es el momento de abrir un mensaje para examinar los detalles y determinar acciones de corrección adicionales. Seleccione un mensaje para ver la información completa del encabezado y el cuerpo del mensaje. Hay varias opciones y vistas diferentes disponibles para ayudarle a decidir el curso de acción correcto:

- **Datos** adjuntos: esta opción permite examinar los datos adjuntos modernos que coinciden con las condiciones de la directiva. El contenido de datos adjuntos modernos se extrae como texto y se puede ver en el panel de alertas pendientes de una directiva. Para obtener más información, consulte la [referencia de característica de cumplimiento de comunicaciones](/microsoft-365/compliance/communication-compliance-channels).
- **Origen**: esta vista es la vista de mensajes estándar que se ve habitualmente en la mayoría de las plataformas de mensajería basadas en web. La información del encabezado tiene formato en el estilo normal y el cuerpo del mensaje admite archivos gráficos y texto ajustado por palabras. Si el reconocimiento óptico de caracteres [(OCR)](communication-compliance-policies.md#optical-character-recognition-ocr) está habilitado para la directiva, las imágenes que contienen texto impreso o escrito a mano que coinciden con la directiva condicional se ven como un elemento secundario para el mensaje asociado en esta vista.
- **Texto** sin formato: la vista Texto muestra una vista de solo texto numerada de línea del mensaje e incluye resaltado de palabras clave en mensajes y datos adjuntos para términos de tipo de información confidencial o palabras clave coincidentes en la directiva de cumplimiento de comunicación asociada. El resaltado de palabras clave puede ayudarle a examinar rápidamente mensajes largos y datos adjuntos para el área de interés. En algunos casos, el texto resaltado puede estar solo en los datos adjuntos de los mensajes que coinciden con las condiciones de la directiva. El resaltado de palabras clave no es compatible con los términos identificados por clasificadores integrados asignados a una directiva. Los archivos incrustados no se muestran y la numeración de línea de esta vista es útil para hacer referencia a detalles pertinentes entre varios revisores.
- **Conversación (versión preliminar):** disponible para los mensajes de chat Microsoft Teams, esta vista muestra hasta cinco mensajes antes y después de un mensaje de alerta para ayudar a los revisores a ver la actividad en el contexto de conversación. Este contexto ayuda a los revisores a evaluar rápidamente los mensajes y tomar decisiones de resolución de mensajes más fundamentadas. Se muestran adiciones de mensajes en tiempo real a conversaciones, incluidas todas las imágenes en línea, emojis y adhesivos disponibles en Teams. No se muestran los datos adjuntos de archivos de imagen o texto de los mensajes. Las notificaciones se muestran automáticamente para los mensajes que se han editado o para los mensajes que se han eliminado de la ventana de conversación. Cuando se resuelve un mensaje, los mensajes de conversación asociados no se conservan con el mensaje resuelto. Los mensajes de conversación están disponibles hasta 60 días después de identificar el mensaje de alerta.
- **Historial de usuario**: la vista Historial de usuario muestra todas las demás alertas generadas por cualquier directiva de cumplimiento de comunicaciones para que el usuario envíe el mensaje.
- **Notificación de patrón detectado**: muchas acciones de acoso y acoso con el tiempo y implican instancias recurrentes del mismo comportamiento por parte de un usuario. La *notificación Patrón detectado* se muestra en los detalles de la alerta y llama la atención a la alerta. La detección de patrones se hace por directiva y evalúa el comportamiento de los últimos 30 días cuando un remitente envía al mismo destinatario al menos dos mensajes. Los investigadores y revisores pueden usar esta notificación para identificar comportamientos repetidos para evaluar la alerta según corresponda.
- **Traducción**: esta vista convierte automáticamente el texto del mensaje de alerta en el idioma configurado en  la configuración idioma mostrado en la Microsoft 365 suscripción para cada revisor. La *vista Traducción ayuda a* ampliar el soporte de investigación para organizaciones con usuarios multilingües y elimina la necesidad de servicios de traducción adicionales fuera del proceso de revisión de cumplimiento de comunicaciones. Con los servicios de traducción de Microsoft, la *vista* Traducción puede estar activada y desactivada según sea necesario y admite una amplia variedad de idiomas. Para obtener una lista completa de los idiomas admitidos, [vea Traductor de Microsoft Languages](https://www.microsoft.com/translator/business/languages/). Los idiomas incluidos *en Traductor lista de idiomas se* admiten en la *vista* Traducción.

### <a name="step-3-decide-on-a-remediation-action"></a>Paso 3: Decidir sobre una acción de corrección

Ahora que ha revisado los detalles del mensaje para la alerta, puede elegir varias acciones de corrección:

- **Resolver**: al seleccionar el control **Resolver**, se quita inmediatamente el mensaje de  la cola de alertas pendientes y no se puede realizar ninguna acción adicional en el mensaje. Al seleccionar **Resolver**, básicamente ha cerrado la alerta sin clasificación adicional. Todos los mensajes resueltos se muestran en la **pestaña Resuelto** .
- **Report as misclassified (preview):** You can always resolve a message as misclassified at any point during the message review workflow. La clase errónea significa que la alerta no era procesable o que la alerta se generó incorrectamente por el proceso de alerta y los clasificadores que se pueden entrenar. La resolución del elemento como clasificado erróneamente envía contenido del mensaje, datos adjuntos y el asunto del mensaje (incluidos los metadatos) a Microsoft para ayudar a mejorar los clasificadores que se pueden entrenar. Los datos que se envían a Microsoft no contienen información que pueda identificar o usarse para identificar a los usuarios de su organización. No se pueden realizar acciones adicionales en el mensaje y todos los mensajes mal clasificados se muestran en la **pestaña** Resuelto.
- **Power Automate (versión preliminar):** Use un flujo de Power Automate para automatizar las tareas de proceso de un mensaje de alerta. De forma predeterminada, el cumplimiento de  la comunicación incluye el Administrador de notificaciones cuando un usuario tiene una plantilla de flujo de alerta de cumplimiento de comunicación que los revisores pueden usar para automatizar el proceso de notificación para los usuarios con alertas de mensajes. Para obtener más información acerca de cómo crear y administrar Power Automate flujos de comunicación, vea la sección **Paso 5:** Considerar Power Automate flujos en este artículo.
- **Etiqueta como**: Etiquete *el mensaje como* *compatible, no* conforme o tan *cuestionable* como se refiere a las directivas y estándares de su organización. Agregar etiquetas y etiquetas de comentarios le ayuda a alertas de directivas de microfiltro para escalaciones o como parte de otros procesos de revisión interna. Una vez completado el etiquetado, también puede decidir resolver el mensaje para sacarlo de la cola de revisión pendiente.
- **Notify**: Puede usar el control **Notify** para asignar una plantilla de aviso personalizada a la alerta y enviar un aviso de advertencia al usuario. Elija la plantilla de aviso adecuada configurada en el área **Configuración** de cumplimiento de comunicaciones y seleccione **Enviar** para enviar un aviso por correo electrónico al usuario que envió el mensaje y para resolver el problema.
- **Escalar**: con el control **Escalate** , puede elegir quién más de su organización debe revisar el mensaje. Elija entre una lista de revisores configurados en la directiva de cumplimiento de comunicaciones para enviar una notificación por correo electrónico que solicite una revisión adicional de la alerta de mensaje. El revisor seleccionado puede usar un vínculo en la notificación por correo electrónico para ir directamente a los elementos que se les han escalado para su revisión.
- **Escalar para la** investigación: con **el control Escalate para** la investigación, puede crear un nuevo caso Advanced eDiscovery [caso](overview-ediscovery-20.md) para mensajes individuales o múltiples. Proporcionará un nombre y notas para el nuevo caso, y el usuario que envió el mensaje que coincide con la directiva se asigna automáticamente como el custodio del caso. No necesita permisos adicionales para administrar el caso. La creación de un caso no resuelve ni crea una nueva etiqueta para el mensaje. Puede seleccionar un total de 100 mensajes al crear un Advanced eDiscovery caso durante el proceso de corrección. Se admiten mensajes en todos los canales de comunicación supervisados por el cumplimiento de la comunicación. Por ejemplo, puede seleccionar 50 chats de Microsoft Teams, 25 mensajes de correo electrónico Exchange Online y 25 mensajes de Yammer al abrir un nuevo caso Advanced eDiscovery para un usuario.
- **Quitar mensaje en Teams**: con el control Quitar mensaje en **Teams**, puede bloquear mensajes inapropiados y contenido identificado en alertas de canales de Microsoft Teams y chats de grupo y 1:1. Los mensajes y el contenido eliminados se reemplazan por una sugerencia de directiva que explica que está bloqueado y la directiva que se aplica a su eliminación de la vista. A los destinatarios se les proporciona un vínculo en la sugerencia de directiva para obtener más información sobre la directiva aplicable y el proceso de revisión. El remitente recibe una sugerencia de directiva para el mensaje bloqueado y el contenido, pero puede revisar los detalles del mensaje bloqueado y el contenido para obtener contexto con respecto a la eliminación.

    ![Quite un mensaje de Microsoft Teams.](../media/communication-compliance-remove-teams-message.png)

### <a name="step-4-determine-if-message-details-should-be-archived-outside-of-communication-compliance"></a>Paso 4: Determinar si los detalles del mensaje deben archivarse fuera del cumplimiento de la comunicación

Los detalles del mensaje se pueden exportar o descargar si necesita archivar los mensajes en una solución de almacenamiento independiente. Al seleccionar el control **Descargar** los mensajes seleccionados se agregan automáticamente a un archivo .ZIP que se puede guardar en almacenamiento fuera de Microsoft 365.

### <a name="step-5-consider-power-automate-flows"></a>Paso 5: Considerar Power Automate flujos

[Microsoft Power Automate](/power-automate/getting-started) es un servicio de flujo de trabajo que automatiza las acciones entre aplicaciones y servicios. Mediante el uso de flujos de plantillas o creados manualmente, puede automatizar tareas comunes asociadas con estas aplicaciones y servicios. Al habilitar los Power Automate para el cumplimiento de las comunicaciones, puede automatizar tareas importantes para alertas y usuarios. Puede configurar los flujos Power Automate para notificar a los administradores cuando los usuarios tienen alertas de cumplimiento de comunicaciones y otras aplicaciones.

Los clientes con Microsoft 365 que incluyen el cumplimiento de la comunicación no necesitan licencias Power Automate adicionales para usar la plantilla de cumplimiento de comunicaciones Power Automate recomendada. La plantilla predeterminada se puede personalizar para admitir la organización y cubrir los escenarios principales de cumplimiento de comunicaciones. Si elige usar características de Power Automate premium en estas plantillas, cree una plantilla personalizada con el conector de cumplimiento de Microsoft 365 o use plantillas de Power Automate para otras áreas de cumplimiento en Microsoft 365, puede que necesite más Power Automate licencias.

> [!IMPORTANT]
> ¿Recibe avisos para la validación de licencias adicionales al probar Power Automate flujos? Es posible que su organización aún no haya recibido actualizaciones de servicio para esta característica de vista previa. Se están implementando actualizaciones y todas las organizaciones con suscripciones Microsoft 365 que incluyan el cumplimiento de comunicaciones deben tener compatibilidad con licencias para los flujos creados a partir de las plantillas Power Automate recomendadas antes del 30 de octubre de 2020.

![Cumplimiento de Power Automate.](../media/communication-compliance-power-automate.png)

La siguiente Power Automate se proporciona a los clientes para admitir la automatización de procesos para alertas de cumplimiento de comunicaciones:

- **Notificar al administrador cuando un usuario tiene una alerta** de cumplimiento de comunicación: es posible que algunas organizaciones necesiten recibir una notificación de administración inmediata cuando un usuario tiene una alerta de cumplimiento de comunicación. Cuando se configura y selecciona este flujo, se envía un mensaje de correo electrónico al administrador del usuario del caso con la siguiente información sobre todas las alertas:
  - Directiva aplicable para la alerta
  - Fecha y hora de la alerta
  - Nivel de gravedad de la alerta

#### <a name="create-a-power-automate-flow"></a>Crear un flujo Power Automate de datos

Para crear un flujo Power Automate a partir de una plantilla predeterminada recomendada, usará la opción Administrar flujos **de Power Automate** desde el control **Automatizar** al trabajar directamente en una alerta. Para crear un flujo Power Automate con **Administrar Power Automate,** debe ser miembro de al menos un grupo de roles de cumplimiento de comunicaciones.

Siga estos pasos para crear un flujo Power Automate de una plantilla predeterminada:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Cumplimiento** >  de la **comunicaciónPolicies** y seleccione la directiva con la alerta que desea revisar.
2. En la directiva, seleccione la **pestaña** Pendiente y seleccione una alerta pendiente.
3. Seleccione **Power Automate** en el menú de acción de alerta.
4. En la **Power Automate**, seleccione una plantilla predeterminada de la sección Plantillas de cumplimiento de comunicación que le pueden **gustar** en la página.
5. El flujo enumerará las conexiones incrustadas necesarias para el flujo y se mostrará si los estados de conexión están disponibles. Si es necesario, actualice las conexiones que no se muestran como disponibles. Seleccione **Continuar**.
6. De forma predeterminada, los flujos recomendados están preconfigurados con el cumplimiento de comunicaciones recomendado y los campos de datos de servicio Microsoft 365 necesarios para completar la tarea asignada para el flujo. Si es necesario, personalice los componentes de flujo mediante el control **Mostrar** opciones avanzadas y configurando las propiedades disponibles para el componente de flujo.
7. Si es necesario, agregue cualquier paso adicional al flujo seleccionando el **botón Nuevo** paso. En la mayoría de los casos, este cambio no debe ser necesario para las plantillas predeterminadas recomendadas.
8. Seleccione **Guardar borrador** para guardar el flujo para una configuración posterior o **seleccione Guardar** para completar la configuración del flujo.
9. Seleccione **Cerrar** para volver a la página Power Automate flujo. La nueva plantilla aparecerá como un flujo en la pestaña Mis  flujos y estará disponible automáticamente desde el control Power Automate para el usuario que creó el flujo al trabajar con alertas de cumplimiento de comunicaciones.

#### <a name="share-a-power-automate-flow"></a>Compartir un flujo Power Automate de datos

De forma predeterminada, Power Automate flujos creados por un usuario solo están disponibles para ese usuario. Para que otros usuarios de cumplimiento de comunicaciones tengan acceso y usen un flujo, el creador del flujo debe compartir el flujo. Para compartir un flujo, usará el control **Power Automate cuando trabaje** directamente en una alerta.

Para compartir un flujo Power Automate, debe ser miembro de al menos un grupo de roles de cumplimiento de comunicaciones.
Siga estos pasos para compartir un flujo Power Automate datos:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Cumplimiento** >  de la **comunicaciónPolicies** y seleccione la directiva con la alerta que desea revisar.
2. En la directiva, seleccione la **pestaña** Pendiente y seleccione una alerta pendiente.
3. Seleccione **Power Automate** en el menú de acción de alerta.
4. En la **página Power Automate flujos**, seleccione la **pestaña Mis flujos** o **Flujos de** equipo.
5. Seleccione el flujo que desea compartir y, a continuación, **seleccione Compartir** en el menú opciones de flujo.
6. En la página de uso compartido de flujo, escriba el nombre del usuario o grupo que desea agregar como propietario del flujo.
7. En el **cuadro de diálogo Conexión usada** , seleccione **Aceptar** para confirmar que el usuario o grupo agregado tendrá acceso total al flujo.

#### <a name="edit-a-power-automate-flow"></a>Editar un flujo Power Automate datos

Si necesita editar un flujo, usará **el control Power Automate** cuando trabaje directamente en una alerta. Para editar un flujo Power Automate, debe ser miembro de al menos un grupo de roles de cumplimiento de comunicaciones.

Siga estos pasos para editar un flujo Power Automate datos:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Cumplimiento** >  de la **comunicaciónPolicies** y seleccione la directiva con la alerta que desea revisar.
2. En la directiva, seleccione la **pestaña** Pendiente y seleccione una alerta pendiente.
3. Seleccione **Power Automate** en el menú de acción de alerta.
4. En la **página Power Automate flujos**, seleccione flujo para editar. Seleccione **Editar** en el menú control de flujo.
5. Seleccione los **puntos suspensivos** >  **Configuración** para cambiar una configuración de componente de flujo o **puntos** >  suspensivosDelete para eliminar un componente de flujo.
6. Seleccione **Guardar** y, a continuación, **Cerrar** para completar la edición del flujo.

#### <a name="delete-a-power-automate-flow"></a>Eliminar un flujo Power Automate datos

Si necesita eliminar un flujo, usará **el control Power Automate** cuando trabaje directamente en una alerta. Para eliminar un flujo Power Automate, debe ser miembro de al menos un grupo de roles de cumplimiento de comunicaciones.

Siga estos pasos para eliminar un flujo Power Automate datos:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Cumplimiento** >  de la **comunicaciónPolicies** y seleccione la directiva con la alerta que desea revisar.
2. En la directiva, seleccione la **pestaña** Pendiente y seleccione una alerta pendiente.
3. Seleccione **Power Automate** en el menú de acción de alerta.
4. En la **página Power Automate,** seleccione flujo para eliminar. Seleccione **Eliminar** en el menú control de flujo.
5. En el cuadro de diálogo de confirmación de eliminación, seleccione **Eliminar** para quitar el flujo o **seleccione Cancelar** para salir de la acción de eliminación.

### <a name="step-6-consider-creating-notice-templates"></a>Paso 6: Considere la posibilidad de crear plantillas de aviso

Puede crear plantillas de aviso si desea enviar a los usuarios un aviso de aviso por correo electrónico para las coincidencias de directivas como parte del proceso de resolución de problemas. Los avisos solo se pueden enviar a la dirección de correo electrónico del usuario asociada con la coincidencia de directiva que generó la alerta específica para la corrección. Al seleccionar una plantilla de aviso para aplicar a una infracción de directiva como parte del flujo de trabajo de corrección, puede elegir aceptar los valores de campo definidos en la plantilla o sobrescribir los campos según sea necesario.

Las plantillas de avisos son plantillas de correo electrónico personalizadas donde puede definir los siguientes campos de mensaje en el área **Configuración de cumplimiento de** comunicación:

|**Field**|**Required**| **Detalles** |
|:-----|:-----|:-----|
|**Nombre de la plantilla** | Sí | Nombre descriptivo de la plantilla de aviso que seleccionará en el flujo de trabajo de notificación durante la corrección, admite caracteres de texto. |
| **Dirección del remitente** | Sí | La dirección de uno o varios usuarios o grupos que envían el mensaje al usuario con una coincidencia de directiva, seleccionada en Active Directory para la suscripción. |
| **Direcciones CC y CCO** | No | Usuarios o grupos opcionales que se notificarán de la coincidencia de directiva, seleccionados desde Active Directory para su suscripción. |
| **Asunto** | Sí | La información que aparece en la línea de asunto del mensaje admite caracteres de texto. |
| **Cuerpo del mensaje** | Sí | La información que aparece en el cuerpo del mensaje admite valores de texto o HTML. |

### <a name="html-for-notices"></a>HTML para avisos

Si desea crear más que un mensaje de correo electrónico simple basado en texto para notificaciones, puede crear un mensaje más detallado mediante HTML en el campo cuerpo del mensaje de una plantilla de aviso. En el siguiente ejemplo se proporciona el formato del cuerpo del mensaje para una plantilla básica de notificación de correo electrónico basada en HTML:

```HTML
<!DOCTYPE html>
<html>
    <body>
        <h2>Action Required: Contoso Employee Code of Conduct Policy Training</h2>
        <p>A recent message you've sent has generated a policy alert for the Contoso Employee <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
        <p>You are required to attend the Contoso Employee Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
        <p>Thank you,</p>
        <p><em>Human Resources</em></p>
    </body>
</html>
```

> [!NOTE]
> La implementación del atributo href HTML en las plantillas de notificación de cumplimiento de comunicaciones actualmente solo admite comillas simples en lugar de comillas dobles para las referencias url.

## <a name="unresolve-messages-preview"></a>Unresolve messages (preview)

Cuando se resuelven los mensajes, se quitan de la **vista** de pestaña Pendiente y se muestran en la **vista de** pestaña Resuelto. Las acciones de investigación y corrección no están disponibles para los mensajes en la *vista* Resuelto. Sin embargo, puede haber instancias en las que necesite tomar medidas adicionales en un mensaje que se haya resuelto por error o que necesite más investigación después de la resolución inicial. Puede usar la característica de comando deshacer el movimiento de uno o más mensajes de la *vista* Resuelto a la *vista* Pendiente.

Para deshacer la resolve de los mensajes, siga estos pasos:

1. Inicie sesión en [el Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com) con las credenciales de un usuario asignado al analista de  cumplimiento de comunicaciones  o a los grupos de roles de investigador de cumplimiento de comunicaciones de Microsoft 365 organización.
2. En el Centro de cumplimiento de Microsoft 365, vaya a **Cumplimiento de comunicaciones**.
3. Seleccione la **pestaña Directivas** y, a continuación, seleccione una directiva que contenga el mensaje de alerta resuelto, haga doble clic para abrir la **página** Directiva.
4. En la **página Directiva** , seleccione la **pestaña Resuelto** .
5. En la **pestaña Resuelto** , seleccione uno o varios mensajes para volver a *Pendiente*.
6. En la barra de comandos, seleccione **Unresolve**.
7. En el **panel Desasolve** del elemento, agregue los comentarios aplicables a la acción deshacer y seleccione  Guardar para volver a mover el elemento a *Pendiente*.
8. Seleccione la **pestaña** Pendiente para comprobar que se muestran los elementos seleccionados.