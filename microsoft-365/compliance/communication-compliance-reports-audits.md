---
title: Uso de informes y auditorías de cumplimiento de comunicaciones
description: Obtenga más información sobre el uso de informes y auditorías de cumplimiento de comunicaciones.
keywords: Microsoft 365, Microsoft Purview, cumplimiento, cumplimiento de comunicaciones
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
- tier1
- purview-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 05822c0d5c3cf31a87a725d47b707482f2040bd3
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2022
ms.locfileid: "68768176"
---
# <a name="use-communication-compliance-reports-and-audits"></a>Uso de informes y auditorías de cumplimiento de comunicaciones

> [!IMPORTANT]
> Cumplimiento de comunicaciones de Microsoft Purview proporciona las herramientas para ayudar a las organizaciones a detectar infracciones de cumplimiento normativo (por ejemplo, SEC o FINRA), como información confidencial o confidencial, hostigamiento o amenazante del lenguaje y uso compartido de contenido para adultos. Creados con privacidad por diseño, los nombres de usuario se seudonimizan de forma predeterminada, los controles de acceso basados en roles están integrados, los investigadores son admitidos por un administrador y los registros de auditoría están en su lugar para ayudar a garantizar la privacidad del nivel de usuario.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="reports"></a>Informes

El panel **Informes** es la ubicación central para ver todos los informes de cumplimiento de comunicaciones. Para ver y administrar informes, los usuarios deben estar asignados al grupo de roles *Visores de cumplimiento de comunicaciones* .

Los widgets de informe proporcionan una vista rápida de la información más comúnmente necesaria para una evaluación general del estado de las actividades de cumplimiento de comunicaciones. La información contenida en los widgets de informe no se puede exportar. Los informes detallados proporcionan información detallada relacionada con áreas específicas de cumplimiento de comunicaciones y ofrecen la capacidad de filtrar, agrupar, ordenar y exportar información durante la revisión.

Para el filtro de intervalo de fechas, la fecha y hora de los eventos se enumeran en Hora universal coordinada (UTC). Al filtrar mensajes para informes, la fecha y hora local del usuario solicitante determina los resultados en función de la conversión de la fecha y hora local del usuario a UTC. Por ejemplo, si un usuario de la hora de verano del Pacífico (PDT) de Ee. UU. filtra un informe del 8/30/2021 al 8/31/2021 a las 00:00, el informe incluye mensajes de 8/30/2021 07:00 UTC a 8/31/2021 07:00 UTC. Si el mismo usuario estaba en la hora de verano del Este de EE. UU. (EDT) al filtrar a las 00:00, el informe incluye mensajes de 8/30/2021 04:00 UTC a 8/31/2021 04:00 UTC.

![Panel de informes de cumplimiento de comunicaciones](../media/communication-compliance-reports-dashboard.png)

El **panel Informes** contiene los siguientes widgets de informe y vínculos de informes detallados:

### <a name="report-widgets"></a>Widgets de informe

- **Coincidencias de directivas recientes**: muestra el número de coincidencias por directivas activas a lo largo del tiempo.
- **Elementos resueltos por directiva**: muestra el número de alertas de coincidencia de directivas resueltas por directivas a lo largo del tiempo.
- **Usuarios con la mayoría de coincidencias de directiva**: muestra los usuarios (o nombres de usuario anonimizados) y el número de coincidencias de directivas durante un período determinado.
- **Directiva con la mayoría de coincidencias**: muestra las directivas y el número de coincidencias para un período determinado, clasificados de mayor a menor para las coincidencias.
- **Escalaciones por directiva**: muestra el número de escalaciones por directiva durante un tiempo determinado.

### <a name="detailed-reports"></a>Informes detallados

Use la opción *Exportar* para crear un archivo .csv que contenga los detalles del informe para cualquier informe detallado. La opción *Exportar* informe admite descargas de tamaño de archivo de hasta 3 MB.

- **Configuración y estado** de la directiva: proporciona una vista detallada de la configuración y la configuración de la directiva, así como el estado general de cada una de las directivas (coincidencias y acciones) en los mensajes. Incluye información de directiva y cómo se asocian las directivas a usuarios y grupos, ubicaciones, porcentajes de revisión, revisores, estado y cuándo se modificó por última vez la directiva. Use la opción *Exportar* para crear un archivo .csv que contenga los detalles del informe.
- **Elementos y acciones por directiva**: revise y exporte los elementos coincidentes y las acciones de corrección por directiva. Incluye información de directiva y cómo se asocian las directivas a:

  - Elementos coincidentes
  - Elementos escalados
  - Elementos resueltos
  - Etiquetado como compatible
  - Etiquetado como no compatible
  - Etiquetado como cuestionable
  - Elementos pendientes de revisión
  - Notificación del usuario
  - Caso creado

- **Elemento y acciones por ubicación**: revise y exporte los elementos coincidentes y las acciones de corrección por ubicación de Microsoft 365. Incluye información sobre cómo se asocian las plataformas de carga de trabajo a:

  - Elementos coincidentes
  - Elementos escalados
  - Elementos resueltos
  - Etiquetado como compatible
  - Etiquetado como no compatible
  - Etiquetado como cuestionable
  - Elementos pendientes de revisión
  - Notificación del usuario
  - Caso creado

- **Actividad por usuario**: revise y exporte elementos coincidentes y acciones de corrección por usuario. Incluye información sobre cómo se asocian los usuarios a:

  - Elementos coincidentes
  - Elementos escalados
  - Elementos resueltos
  - Etiquetado como compatible
  - Etiquetado como no compatible
  - Etiquetado como cuestionable
  - Elementos pendientes de revisión
  - Notificación del usuario
  - Caso creado

- **Tipo de información confidencial por ubicación** (versión preliminar): revise y exporte información sobre la detección de tipos de información confidencial y los orígenes asociados en las directivas de cumplimiento de comunicaciones. Incluye el total general y el desglose específico de las instancias de tipo de información confidencial en los orígenes configurados en la organización. Los valores de cada origen de terceros se muestran en columnas independientes en el archivo .csv. Los ejemplos son:

  - **Email**: tipos de información confidencial detectados en los mensajes de correo electrónico de Exchange.
  - **Teams**: tipos de información confidencial detectados en los canales y mensajes de chat de Microsoft Teams.
  - **Yammer**: tipos de información confidencial detectados en bandejas de entrada, publicaciones, chats y respuestas de Yammer.
  - **Orígenes de terceros**: se han detectado tipos de información confidencial para las actividades asociadas a conectores de terceros configurados en la organización. Para ver el desglose de orígenes de terceros para un tipo de información confidencial específico en el informe, mantenga el mouse sobre el valor del tipo de información confidencial de la columna Origen de terceros.
  - **Otro**: tipos de información confidencial que se usan para el procesamiento interno del sistema. La selección o anulación de la selección de este origen para el informe no afectará a ningún valor.

### <a name="message-details-report"></a>Informe de detalles del mensaje

Cree informes personalizados y revise los detalles de los mensajes contenidos en directivas específicas en la pestaña **Directivas** . Estos informes se pueden usar para revisiones de todos los mensajes y para crear una instantánea de informe para el estado de los mensajes durante un período de tiempo personalizable. Después de crear un informe, puede ver y descargar el informe de detalles como un archivo .csv en la pestaña **Informes de detalles del mensaje** .

![Informe de detalles del mensaje de cumplimiento de comunicaciones](../media/communication-compliance-message-detail-report.png)

Para crear un nuevo informe de detalles del mensaje, complete los pasos siguientes:

1. Inicie sesión en el portal de cumplimiento Microsoft Purview con una cuenta que sea miembro del grupo de roles *Investigadores de cumplimiento de comunicaciones*.
2. Vaya a la pestaña **Directivas** , seleccione una directiva y, a continuación, seleccione **Crear informe de detalles del mensaje**.
3. En el panel **Crear informe de detalles del mensaje** , escriba un nombre para el informe en el campo **Nombre del** informe.
4. En **Elegir un intervalo de fechas**, seleccione una *fecha de inicio* y *una fecha de finalización* para el informe.
5. Seleccione **Crear**.
6. Se muestra la confirmación de creación del informe.

En función del número de elementos del informe, el informe puede tardar unos minutos o horas en descargarse. Puede comprobar el progreso en la pestaña Informes de detalles del mensaje. El estado del informe es *En curso* o *Listo para descargar*. Puede tener hasta 15 informes independientes procesando simultáneamente. Para descargar un informe, seleccione un informe en el estado *Listo para descargar* y seleccione **Descargar informe**.

> [!NOTE]
> Si el período de tiempo seleccionado no devuelve ningún resultado de mensaje en el informe, no había ningún mensaje para el período de tiempo seleccionado. El informe estará en blanco.

Los informes de detalles del mensaje contienen la siguiente información para cada elemento de mensaje de la directiva:

- **Identificador de coincidencia**: identificador único del mensaje de la directiva.
- **Remitente**: remitente del mensaje.
- **Destinatarios**: destinatarios incluidos para el mensaje.
- **Fecha de envío**: fecha en que se envió el mensaje.
- **Fecha de coincidencia**: fecha en la que el mensaje coincidía con las condiciones de la directiva.
- **Asunto**: Asunto del mensaje.
- **Contiene datos adjuntos**: estado de los datos adjuntos del mensaje. Los valores son *Sí* o *No*.
- **Nombre de la directiva**: nombre de la directiva asociada al mensaje. Este valor será el mismo para todos los mensajes del informe.
- **Estado del elemento**: estado del elemento de mensaje en la directiva. Los valores son *Pending* o *Resolved*.
- **Etiquetas**: etiquetas asignadas al mensaje. Los valores son *Cuestionables, Compatibles* o *No compatibles*.
- **Coincidencias de palabras clave**: coincidencias de palabras clave para el mensaje.
- **Revisores**: revisores asignados al mensaje.
- **Pendiente para (días):** número de días que el mensaje ha estado en estado pendiente. Para los mensajes resueltos, el valor es 0.
- **Comentario para resuelto**: comentarios del mensaje especificado cuando se resuelven.
- **Fecha resuelta**: fecha y hora en que se resolvió el mensaje.
- **Última actualización por**: nombre de usuario del último actualizador.
- **Última actualización:** fecha y hora en que el mensaje se actualizó por última vez.
- **Historial de comentarios**: lista de todos los comentarios de la alerta de mensaje, incluidos el autor de comentarios y la fecha y hora del comentario.

## <a name="audit"></a>Auditoría

En algunos casos, debe proporcionar información a los auditores normativos o de cumplimiento para demostrar la supervisión de las actividades y las comunicaciones del usuario. Esta información puede ser un resumen de todas las actividades asociadas a una directiva de organización definida o en cualquier momento en que cambie una directiva de cumplimiento de comunicaciones. Las directivas de cumplimiento de comunicaciones tienen seguimientos de auditoría integrados para una preparación completa para las auditorías internas o externas. Las directivas de comunicación capturan los historiales de auditoría detallados de cada acción de creación, edición y eliminación para proporcionar una prueba de los procedimientos de supervisión.

> [!IMPORTANT]
> La auditoría debe estar habilitada para su organización antes de que se registren los eventos de cumplimiento de la comunicación. Para habilitar la auditoría, consulte [Habilitación del registro de auditoría](/microsoft-365/compliance/communication-compliance-configure#step-2-required-enable-the-audit-log). Cuando las actividades desencadenan eventos que se capturan en el registro de auditoría de Microsoft 365, estos eventos pueden tardar hasta 48 horas en verse en las directivas de cumplimiento de comunicaciones.

Para ver las actividades de actualización de directivas de cumplimiento de comunicaciones, seleccione el control **Exportar actualizaciones de directivas** en la página principal de cualquier directiva. Debe tener asignados los roles *Administradores globales de Administración* o *cumplimiento de comunicaciones* para exportar las actividades de actualización. Esta acción genera un archivo de auditoría en el formato .csv que contiene la siguiente información:

|Campo|Detalles|
|---|---|
| **CreationDate** | Fecha en que se realizó la actividad de actualización en una directiva. |
| **UserIds** | Usuario que realizó la actividad de actualización en una directiva. |
| **Operations** | Actualizar las operaciones realizadas en la directiva. |
| **AuditData** | Origen de datos principal para todas las actividades de actualización de directivas. Todas las actividades de actualización se registran y separan mediante delimitadores de comas. |

Para ver las actividades de revisión de cumplimiento de comunicaciones de una directiva, seleccione el control **Exportar actividades de revisión** en la página **Información general** de una directiva específica. Debe tener asignados los roles *Administradores globales de Administración* o *de cumplimiento de comunicaciones* para exportar las actividades de revisión. Esta acción genera un archivo de auditoría en el formato .csv que contiene la siguiente información:

|Campo|Detalles|
|---|---|
| **CreationDate** | Fecha en que se realizó la actividad de revisión en una directiva. |
| **UserIds** | Usuario que realizó la actividad de revisión en una directiva. |
| **Operations** | Revise las operaciones realizadas en la directiva. |
| **AuditData** | Origen de datos principal para todas las actividades de revisión de directivas. Todas las actividades de revisión se registran y separan mediante delimitadores de comas. |

También puede ver las actividades de auditoría en el registro de auditoría unificado o con el cmdlet de PowerShell [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) . Para más información sobre las directivas de retención de registros de auditoría, consulte [Administración de directivas de retención de registros de auditoría](/microsoft-365/compliance/audit-log-retention-policies).

Por ejemplo, en el ejemplo siguiente se devuelven las actividades de todas las actividades de revisión de supervisión (directivas y reglas):

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType AeD -Operations SupervisoryReviewTag
```

En este ejemplo se devuelven las actividades de actualización de las directivas de cumplimiento de comunicaciones:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType Discovery -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeleted
```

En este ejemplo se devuelven actividades que coinciden con las directivas de cumplimiento de comunicaciones actuales:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -Operations SupervisionRuleMatch
```

Las coincidencias de directivas de cumplimiento de comunicaciones se almacenan en un buzón de supervisión para cada directiva. En algunos casos, es posible que tenga que comprobar el tamaño del buzón de supervisión de una directiva para asegurarse de que no se aproxima al tamaño de almacenamiento actual de 100 GB o al límite de 1 millón de mensajes. Si se alcanza el límite de buzones de correo, no se capturan las coincidencias de directiva y deberá crear una nueva directiva (con la misma configuración) para seguir capturando coincidencias para las mismas actividades.

Para comprobar el tamaño de un buzón de supervisión de una directiva, siga estos pasos:

1. [Conéctese al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).
2. Ejecute el siguiente comando:

    ```PowerShell
    ForEach ($p in Get-SupervisoryReviewPolicyV2 | Sort-Object Name)
    {
       "<Name of your communication compliance policy>: " + $p.Name
       Get-MailboxStatistics $p.ReviewMailbox | ft ItemCount,TotalItemSize
    }
    ```
