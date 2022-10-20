---
title: Administración de pruebas forenses de administración de riesgos internos (versión preliminar)
description: Administrar pruebas forenses de administración de riesgos internos en Microsoft Purview. La evidencia forense es una herramienta de investigación para ver la actividad de usuario relacionada con la seguridad capturada para ayudar a determinar si las acciones del usuario suponen un riesgo y pueden provocar un incidente de seguridad.
keywords: Microsoft 365, Microsoft Purview, riesgo interno, administración de riesgos, cumplimiento
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: a0cbe8409517d5b27e6f7eb1b9dca54cd3b238ae
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68631420"
---
# <a name="manage-insider-risk-management-forensic-evidence-preview"></a>Administración de pruebas forenses de administración de riesgos internos (versión preliminar)

>[!IMPORTANT]
>Administración de riesgos internos de Microsoft Purview correlaciona varias señales para identificar posibles riesgos internos malintencionados o involuntarios, como el robo de IP, la pérdida de datos y las infracciones de seguridad. La administración de riesgos internos permite a los clientes crear directivas para administrar la seguridad y el cumplimiento. Creados con privacidad por diseño, los usuarios se seudonimizan de forma predeterminada y los controles de acceso basados en roles y los registros de auditoría están en su lugar para ayudar a garantizar la privacidad del nivel de usuario.

Una vez completados los pasos de configuración y creado la directiva de pruebas forenses, comenzará a ver alertas de actividades de usuario potencialmente relacionadas con la seguridad que cumplan las condiciones de los indicadores definidos en la directiva.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="dashboard"></a>Panel

El panel de pruebas forenses es la vista de resumen de las áreas clave de la configuración de pruebas forenses en su organización. Para la versión preliminar, el panel solo incluye una sección de **estado del dispositivo de evidencia forense** . Seleccione **Ver informe de estado del dispositivo** para abrir la pestaña **Estado** del dispositivo y el informe. En futuras versiones se incluirán otras secciones.

## <a name="managing-users"></a>Administración de usuarios

Debe solicitar y aprobar usuarios específicos antes de que sean aptos para la captura de pruebas forenses. Simplemente agregar usuarios a una directiva de pruebas forenses no hace que esos usuarios sean aptos para la captura automáticamente. Puede solicitar y aprobar a los usuarios antes o después de crear directivas de pruebas forenses, pero las capturas de clip asociadas a los indicadores de directiva solo se crearán y estarán disponibles para su revisión una vez que se aprueben los usuarios.

Los usuarios asignados a los grupos de roles *Administración de riesgos* internos o *Administración de riesgos* internos pueden enviar solicitudes de aprobación a los usuarios asignados al grupo de roles *Aprobadores de Insider Risk Management* .

### <a name="request-capturing-approvals"></a>Solicitud de captura de aprobaciones

Debe solicitar que la captura de pruebas forenses esté activada para usuarios específicos. Cuando se envía una solicitud, los aprobadores de su organización reciben una notificación por correo electrónico y pueden aprobar o rechazar la solicitud. Si se aprueba, el usuario o aparecerá en la pestaña **Usuarios aprobados** y será apto para la captura. Si no se soluciona, la solicitud expirará 6 meses a partir del día en que se envió.

Para configurar usuarios aprobados para la captura de pruebas forenses, siga estos pasos:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com/), vaya a **Insider Risk Management** > **Forensic evidence (preview)** > **Administración de usuarios**.
2. Seleccione la pestaña **Administrar solicitudes de pruebas forenses** .
3. Seleccione **Crear solicitud**.
4. En la página **Usuarios** , seleccione **Agregar usuarios**.
5. Use **Buscar** para buscar un usuario específico o seleccionar uno o varios usuarios de la lista. Seleccione **Agregar** y, después, seleccione **Siguiente**.
6. En la página **Directiva de evidencia forense** , seleccione una directiva de evidencia forense para los usuarios agregados. La directiva que elija determina el ámbito de la actividad que se va a capturar para los usuarios.
7. Seleccione **Siguiente**.
8. En la página **Justificación** , haga saber al revisor por qué solicita que se habilite la captura para los usuarios que agregó en el cuadro de texto **Justificación para activar la captura de pruebas forenses** . Este campo es obligatorio. Seleccione **Siguiente** cuando esté completo:
9. En la página **Email notificaciones**, puede usar una plantilla de notificación para enviar un correo electrónico a los usuarios que les informen de que la captura de pruebas forenses se activará para su dispositivo de acuerdo con las directivas de su organización. El correo electrónico se enviará a los usuarios solo si se aprueba su solicitud.

    Active la casilla **Enviar una notificación por correo electrónico a los usuarios aprobados** . Elija una plantilla existente o cree una nueva. Para crear una plantilla, seleccione **Crear una plantilla de notificación** y complete los siguientes campos obligatorios en el panel **Nueva plantilla de notificación por correo electrónico** .

10. Seleccione **Siguiente**.
11. En la página **Finalizar** , revise la configuración antes de enviar la solicitud. Seleccione **Editar usuarios** o **Editar justificación** para cambiar cualquiera de los valores de solicitud o seleccione **Enviar** para crear y enviar la solicitud a los revisores.

Para ver las solicitudes de aprobación pendientes, vaya a **Insider Risk Management** > **Prueba forense (versión preliminar)** > **Solicitudes pendientes**. Aquí verá a los usuarios con solicitudes pendientes, su dirección de correo electrónico, la fecha de envío de la solicitud y quién envió la solicitud de aprobación. Si no se muestra ningún usuario, no hay ninguna solicitud de aprobación pendiente para ningún usuario.

Los usuarios asignados al grupo de roles *Aprobadores de Insider Risk Management* pueden seleccionar un usuario en la pestaña **Solicitud de pruebas forenses (versión preliminar)** y revisar la solicitud. Después de revisar la solicitud, estos usuarios pueden aprobar o rechazar la solicitud de captura de pruebas forenses. Al aprobar o rechazar la solicitud de captura, se quita de esta vista la solicitud pendiente para los usuarios.

### <a name="approve-or-reject-capturing-requests"></a>Aprobar o rechazar solicitudes de captura

Una vez completadas las solicitudes, los usuarios asignados al grupo de roles *Aprobadores de Insider Risk Management* recibirán una notificación por correo electrónico para la solicitud de aprobación. Para aprobar o rechazar solicitudes, los revisores deben completar los pasos siguientes:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com/), vaya a **Insider Risk Management** > **Prueba forense (versión preliminar)** > **Solicitudes pendientes**.
2. Seleccione un usuario que desee revisar.
3. En el panel **Revisar solicitud de pruebas forenses (versión preliminar),** revise la justificación enviada por el solicitante. Seleccione **Aprobar** o **Rechazar** según corresponda.
4. En la página **Solicitud aprobada** o **Solicitud rechazada** , seleccione **Cerrar**.

![Aprobación de pruebas forenses de administración de riesgos internos.](../media/insider-risk-forensic-evidence-approval.png)

### <a name="revoke-capturing-approvals"></a>Revocación de aprobaciones de captura

Si es necesario, puede revocar la aprobación de usuarios específicos y excluirlos de la captura de pruebas forenses. Revocar la aprobación no elimina ni quita ninguna captura existente para estos usuarios, solo se deshabilita la captura futura de la actividad para estos usuarios.

Para revocar las aprobaciones de los usuarios, los usuarios asignados al grupo *de roles Aprobadores de Insider Risk Management* deben completar los pasos siguientes:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com/), vaya a **Insider Risk Management** > **Forensic evidence (preview)** > **Administración de usuarios**.
2. Seleccione la pestaña **Usuarios aprobados** .
3. Seleccione un usuario y, a continuación, seleccione **Quitar**.
4. En la página de confirmación de eliminación, seleccione **Quitar** para revocar la aprobación de captura o seleccione **Cancelar** para cerrar la página de confirmación.

## <a name="creating-and-managing-notification-templates"></a>Creación y administración de plantillas de notificación

Puede crear y usar una plantilla de notificación para enviar un correo electrónico a los usuarios para informarles de que la captura de pruebas forenses se activará para su dispositivo de acuerdo con las directivas de su organización. El correo electrónico se envía a los usuarios solo si se aprueba su solicitud.

![Notificación de pruebas forenses de administración de riesgos internos.](../media/insider-risk-forensic-evidence-notification.png)

Para crear una nueva plantilla de notificación, complete los pasos siguientes:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com/), vaya a **Insider Risk Management** > **Forensic evidence (preview)** > **Plantillas de notificación**.
2. Seleccione **Crear plantilla de notificación**.
3. En el panel **Nueva plantilla de notificación por correo electrónico** , complete los siguientes campos obligatorios:
    - Nombre de la plantilla
    - Enviar desde
    - Subject
    - Cuerpo del mensaje
4. Seleccione **Guardar**.

Para eliminar una plantilla de notificación existente, seleccione una plantilla y seleccione **Eliminar**.

## <a name="viewing-capture-clips"></a>Visualización de clips de captura

Si ha seleccionado la opción para capturar solo las actividades definidas por los indicadores seleccionados en las directivas de evidencia forense, los clips de captura están disponibles como parte de la alerta y son accesibles en la pestaña **Pruebas forenses (versión preliminar)** del **panel Alertas**. Si las alertas se escalan posteriormente a casos, se puede acceder a los clips asociados en la pestaña **Pruebas forenses (versión preliminar)** del panel **Casos** .

Si ha seleccionado la opción para capturar cualquier actividad relacionada con la seguridad realizada por los usuarios incluidos en las directivas de pruebas forenses, verá los clips para usuarios individuales en el panel **Informe de actividad de usuario** .

>[!IMPORTANT]
>Los clips de pruebas forenses se eliminan 120 días después de su captura o al final del período de vista previa, lo que sea antes. Puede descargar o transferir clips de evidencia forense antes de que se eliminen.

### <a name="reviewing-capture-clips-included-with-alerts"></a>Revisión de clips de captura incluidos con alertas

En el caso de las alertas generadas por las directivas, las capturas de pruebas forenses para los usuarios están disponibles para su revisión en la pestaña **Pruebas forenses (versión preliminar)** del panel **Alertas** . Si hay una o varias capturas disponibles para la alerta, también verá una notificación **ver evidencia forense** en la sección Actividad que generó este encabezado de alerta. Puede seleccionar el vínculo de notificación o la pestaña **Pruebas forenses (versión preliminar)** para revisar las capturas de actividad.

![Actividad de usuario de pruebas forenses de administración de riesgos internos.](../media/insider-risk-forensic-evidence-user-activity.png)

En general, revisar una alerta para detectar actividades potencialmente de riesgo que pueden contener capturas de evidencia forense es básicamente la misma que revisar una alerta sin capturas de evidencia forense. La diferencia significativa es la inclusión de las capturas aplicables. La pestaña **Pruebas forenses (versión preliminar)** proporciona acceso a todas las capturas disponibles asociadas a la alerta. Cada captura se muestra e incluye la siguiente información:

- **Fecha y hora (UTC):** fecha, hora (UTC) y duración de la captura.
- **Dispositivo**: nombre del dispositivo en Windows 10/11.
- **Tipo de actividad**: tipo de actividad de administración de riesgos internos incluido en la captura. Estas actividades se basan en indicadores globales y de directiva asignados a la directiva asociada.
- **Eventos de captura**: cada captura contiene eventos dentro de la captura para ayudar a centrar la revisión en actividades específicas para la sesión de captura.

Para ver un clip de captura, complete los pasos siguientes:

1. Si es necesario, configure los filtros para las capturas disponibles. Puede filtrar por **fechas (UTC)** o por **actividad**.
2. Seleccione un clip para revisarlo.
3. Seleccione el monitor de dispositivo que se va a revisar. Cada monitor conectado al dispositivo (hasta 4) es apto para la captura de pruebas forenses y aparece como *Pantalla 1*, *Pantalla 2*, etc.
4. Con los controles del reproductor de vídeo, seleccione el *control Reproducir* para revisar todo el clip de principio a fin.
5. Si desea limitar la revisión a un evento específico del clip, seleccione el evento en las listas **Capturar eventos** a la derecha del reproductor de vídeo.

### <a name="reviewing-capture-clips-included-with-cases"></a>Revisión de clips de captura incluidos con casos

Si las alertas se escalan a casos, todas las capturas de evidencia forense asociadas se incluyen como parte del caso. La revisión de las capturas de pruebas forenses para los casos sigue el mismo proceso que cuando se revisan las capturas como parte del examen de alertas.

### <a name="reviewing-capture-clips-without-alerts"></a>Revisión de clips de captura sin alertas

Para ver clips de actividad no asociada a alertas, usará informes de [actividad de usuario](/microsoft-365/compliance/insider-risk-management-activities#user-activity-reports). Los informes de actividad de usuario permiten examinar las actividades de usuarios específicos durante un período de tiempo definido sin tener que asignarlas de forma temporal o explícita a una directiva de administración de riesgos internos. Si estas actividades de usuario incluyen actividades admitidas por la captura de pruebas forenses, los clips se incluyen con la actividad del usuario.

Si ha configurado pruebas forenses para capturar toda la actividad de usuario relacionada con la seguridad, independientemente de si se incluyen en una directiva de pruebas forenses, revisará estas capturas seleccionando **Informes de actividad de usuario** de Administración  >  de **riesgos de Insider** y, a continuación, seleccionando un usuario específico y seleccionando la pestaña **Pruebas forenses (versión preliminar).**

## <a name="device-health-report-preview"></a>Informe de estado del dispositivo (versión preliminar)

Una vez que los dispositivos están configurados para admitir pruebas forenses, puede revisar el estado de mantenimiento del cliente de Microsoft Purview para todos los dispositivos de su organización. Para ello, vaya a **Insider Risk Management** > **Prueba forense (versión preliminar)** > **Estado del dispositivo**.

![Estado del dispositivo de pruebas forenses de administración de riesgos internos.](../media/insider-risk-forensic-evidence-device-health.png)

El informe permite ver el estado y el estado de todos los dispositivos que tienen instalado el agente de evidencia forense. Cada widget de informe del informe muestra información de las últimas 24 horas.

- **Dispositivos en línea**: el número total de dispositivos actualmente en línea.
- **Dispositivos sin conexión**: el número total de dispositivos actualmente sin conexión.
- **Dispositivos con advertencias**: el número total de dispositivos con una advertencia.
- **Dispositivos con errores**: el número total de dispositivos con un error.

En la cola de estado del dispositivo se enumeran todos los dispositivos configurados para la evidencia forense de la organización. Además, el informe muestra el estado de los siguientes atributos de dispositivo:

- **Nombre** del dispositivo: el nombre del dispositivo, definido por el atributo *ComputerName* del dispositivo.
- **Estado del dispositivo**: estado del cliente de Microsoft Purview en el dispositivo. Los valores de estado son los siguientes:
    - ***Correcto***: el cliente del dispositivo funciona correctamente y las características de captura de evidencia forense son totalmente compatibles.
    - ***Advertencia***: El cliente del dispositivo tiene una advertencia y es posible que las características de captura de evidencia forense no sean totalmente compatibles.
    - ***Error***: El cliente del dispositivo tiene un error y las características de captura de evidencia forense están deshabilitadas o no son totalmente compatibles.
- **Detalles del estado**: más información sobre el estado del dispositivo.
- **Última sincronización (UTC):** fecha y hora de la última sincronización de estado del dispositivo.
- **Nombre de usuario**: nombre de usuario del usuario que inició sesión en el dispositivo cuando se realizó la sincronización de estado.
- **Versión de Windows**: la versión de Microsoft Windows instalada en el dispositivo.
- **Versión de cliente**: la versión del cliente de Microsoft Purview instalado en el dispositivo.

El estado de mantenimiento del dispositivo proporciona información sobre posibles problemas con los dispositivos y el cliente de Microsoft Purview. La columna **Estado** del dispositivo de la página **Estado** del dispositivo puede alertarle de problemas de dispositivo que pueden impedir la captura de la actividad del usuario o por qué el volumen de captura de pruebas forenses es inusual. El estado de mantenimiento del dispositivo también puede confirmar que los dispositivos incluidos en la captura de pruebas forenses están en buen estado y no necesitan atención ni cambios de configuración. En la tabla siguiente se enumeran los posibles mensajes de detalles de estado y las acciones recomendadas que puede realizar para abordar advertencias y errores:

|**Detalles del estado**|**Estado**|**Acción sugerida**|
|:----------|:-------|:-------------------|
| Error interno del servidor. Como resultado, es posible que falten datos de captura. | Error | Creación de una incidencia de soporte técnico con Microsoft para una investigación más detallada |
| El ancho de banda de carga ha alcanzado el 90 % del límite configurado en este dispositivo. Las capturas podrían sobrescribirse pronto.  | Advertencia | Aumente el límite de ancho de banda de carga en la página [Configuración de pruebas forenses](/microsoft-365/compliance/insider-risk-management-forensic-evidence-configure) . |
| Se ha alcanzado el límite de ancho de banda de carga configurado en este dispositivo. No se cargarán más capturas durante el día. | Error | Aumente el límite de ancho de banda de carga en la página [Configuración de pruebas forenses](/microsoft-365/compliance/insider-risk-management-forensic-evidence-configure) . |
| El almacenamiento sin conexión ha alcanzado el 90 % del límite configurado en este dispositivo. Las capturas podrían sobrescribirse pronto.  | Advertencia | Aumente el límite de caché de captura sin conexión en la página [Configuración de pruebas forenses](/microsoft-365/compliance/insider-risk-management-forensic-evidence-configure) . |
| Se ha alcanzado el límite de almacenamiento sin conexión configurado en este dispositivo. Como resultado, las capturas sin conexión se sobrescriben. | Error | Aumente el límite de caché de captura sin conexión en la página [Configuración de pruebas forenses](/microsoft-365/compliance/insider-risk-management-forensic-evidence-configure) . |
| El uso de CPU en el dispositivo ha superado el umbral máximo. | Error | El proceso de captura se ha detenido y se reiniciará en unos minutos. |
| El uso de memoria en el dispositivo ha superado el umbral máximo. | Error | El proceso de captura se ha detenido y se reiniciará en unos minutos. |
| El uso de GPU en el dispositivo ha superado el umbral máximo. | Error | El proceso de captura se ha detenido y se reiniciará en unos minutos. |
| El cliente de Microsoft Purview instalado en el dispositivo no puede sincronizarse con la directiva de pruebas forenses. | Advertencia | Conectarse a la red & volver a instalar el cliente |
| El cliente de Microsoft Purview instalado en el dispositivo no se ha sincronizado con la directiva de pruebas forenses en más de 24 horas. | Error | Conectarse a la red & volver a instalar el cliente |
| El cliente de Microsoft Purview no puede capturar la actividad porque no se detecta ninguna tarjeta gráfica en este dispositivo. | Error | Agregar una tarjeta gráfica o reemplazar el dispositivo por uno que tenga una tarjeta gráfica |
| El cliente de Microsoft Purview no puede capturar la actividad porque no se detecta ningún monitor de pantalla en este dispositivo. | Error | Adición de monitores de pantalla para este dispositivo |
| El cliente de Microsoft Purview no puede capturar la actividad porque los monitores de pantalla de este dispositivo se apagaron o desconectaron. | Error | Conexión o activación de monitores de pantalla para el dispositivo |
| El dispositivo no puede acceder al directorio que almacena las capturas de evidencia forense. | Error | Reinstalación del cliente en este dispositivo |
| Error de inicialización del codificador.  | Error | Vuelva a instalar el cliente en este dispositivo. |

Póngase en contacto con el soporte técnico de Microsoft si las acciones recomendadas no resuelven problemas con el cliente.
