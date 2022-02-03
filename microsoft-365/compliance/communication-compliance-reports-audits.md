---
title: Usar informes y auditorías de cumplimiento de comunicaciones
description: Obtenga más información sobre el uso de informes y auditorías de cumplimiento de comunicaciones.
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
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: a65a72538afa3684cf4ad9351d30313e0dc43b8d
ms.sourcegitcommit: 726a72f135358603c2fde3f4067d834536e6deb2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2022
ms.locfileid: "62327440"
---
# <a name="use-communication-compliance-reports-and-audits"></a>Usar informes y auditorías de cumplimiento de comunicaciones

## <a name="reports"></a>Informes

El nuevo **panel de** informes es la ubicación central para ver todos los informes de cumplimiento de comunicaciones. Los widgets de informe proporcionan una vista rápida de los conocimientos más necesarios para una evaluación general del estado de las actividades de cumplimiento de comunicaciones. La información contenida en los widgets del informe no es exportable. Los informes detallados proporcionan información detallada relacionada con áreas específicas de cumplimiento de comunicaciones y ofrecen la capacidad de filtrar, agrupar, ordenar y exportar información durante la revisión. 

Para el filtro de intervalo de fechas, la fecha y la hora de los eventos se enumeran en Hora universal coordinada (UTC). Al filtrar mensajes para informes, la fecha y hora local del usuario solicitante determina los resultados en función de la conversión de la fecha y hora local del usuario a UTC. Por ejemplo, si un usuario de la hora de verano del Pacífico (PDT) de Estados Unidos filtra un informe del 30/30/2021 al 8/31/2021 a las 00:00, el informe incluye mensajes del 8/30/2021 07:00 UTC al 8/31/2021 07:00 UTC. Si el mismo usuario estaba en el horario de verano oriental de Estados Unidos (EDT) al filtrar a las 00:00, el informe incluye mensajes del 30/30/2021 de 04:00 UTC al 8/31/2021 04:00 UTC.

![Panel de informes de cumplimiento de comunicaciones.](../media/communication-compliance-reports-dashboard.png)

El **panel informes contiene** los siguientes widgets de informe y vínculos de informes detallados:

### <a name="report-widgets"></a>Widgets de informe

- **Coincidencias de directiva recientes**: muestra el número de coincidencias por directiva activa con el tiempo.
- **Elementos resueltos por directiva**: muestra el número de alertas de coincidencia de directivas resueltas por directiva con el tiempo.
- **Usuarios con la mayoría de las coincidencias de** directiva: muestra los usuarios (o nombres de usuario anonimizados) y el número de coincidencias de directiva durante un período determinado.
- **Directiva con la mayoría de coincidencias**: muestra las directivas y el número de coincidencias de un período determinado, clasificados de mayor a menor para las coincidencias.
- **Escalaciones por directiva**: muestra el número de escalaciones por directiva durante un tiempo determinado.

### <a name="detailed-reports"></a>Informes detallados

Use la *opción* Exportar para crear un archivo .csv que contenga los detalles del informe para cualquier informe detallado.

- **Configuración y** estado de la directiva: proporciona una vista detallada de la configuración y la configuración de la directiva, así como el estado general de cada una de las directivas (coincidencias y acciones) de los mensajes. Incluye información de directiva y cómo se asocian las directivas con usuarios y grupos, ubicaciones, porcentajes de revisión, revisores, estado y cuándo se modificó por última vez la directiva. Use la *opción* Exportar para crear un archivo .csv que contenga los detalles del informe.
- **Elementos y acciones por directiva**: revisar y exportar elementos y acciones de corrección correspondientes por directiva. Incluye información de directivas y cómo se asocian las directivas con:

    - Elementos coincidentes
    - Elementos escalados
    - Elementos resueltos
    - Etiquetado como compatible
    - Etiquetado como no compatible
    - Etiquetado como cuestionable
    - Revisión pendiente de elementos
    - Notificación de usuario
    - Case created

- **Elemento y acciones por ubicación**: revisar y exportar elementos y acciones de corrección correspondientes por Microsoft 365 ubicación. Incluye información sobre cómo están asociadas las plataformas de carga de trabajo:

    - Elementos coincidentes
    - Elementos escalados
    - Elementos resueltos
    - Etiquetado como compatible
    - Etiquetado como no compatible
    - Etiquetado como cuestionable
    - Revisión pendiente de elementos
    - Notificación de usuario
    - Case created

- **Actividad por usuario**: revise y exporte elementos y acciones de corrección correspondientes por usuario. Incluye información sobre cómo se asocian los usuarios a:

    - Elementos coincidentes
    - Elementos escalados
    - Elementos resueltos
    - Etiquetado como compatible
    - Etiquetado como no compatible
    - Etiquetado como cuestionable
    - Revisión pendiente de elementos
    - Notificación de usuario
    - Case created

- **Tipo de información confidencial por ubicación** (versión preliminar): revise y exporte información sobre la detección de tipos de información confidencial y los orígenes asociados en las directivas de cumplimiento de comunicaciones. Incluye el total general y el desglose específico de las instancias de tipo de información confidencial en los orígenes configurados en la organización. Los valores de cada origen de terceros se muestran en columnas independientes en el .csv archivo. Algunos ejemplos son:

    - **Correo** electrónico: tipos de información confidencial detectados en Exchange de correo electrónico.
    - **Teams**: tipos de información confidencial detectados en Microsoft Teams canales y mensajes de chat.
    - **Skype Empresarial**: tipos de información confidencial detectados en Skype para comunicaciones empresariales.
    - **Yammer**: tipos de información confidencial detectados en Yammer bandejas de entrada, publicaciones, chats y respuestas.
    - **Orígenes de terceros**: tipos de información confidencial detectados para actividades asociadas con conectores de terceros configurados en la organización. Para ver el desglose de orígenes de terceros para un tipo de información confidencial específico en el informe, mantenga el mouse sobre el valor del tipo de información confidencial en la columna Origen de terceros.
    - **Otros**: Tipos de información confidencial usados para el procesamiento interno del sistema. Seleccionar o anular la selección de este origen para el informe no afectará a ningún valor.

### <a name="message-details-report-preview"></a>Informe de detalles del mensaje (versión preliminar)

Cree informes personalizados y revise los detalles de los mensajes contenidos en directivas específicas en la **pestaña** Directivas. Estos informes se pueden usar para revisiones de todos los mensajes y para crear una instantánea de informe para el estado de los mensajes durante un período de tiempo personalizable. Después de crear un informe, puede ver y descargar el informe de detalles como un archivo .csv en la pestaña **Informes de detalles del** mensaje.

![Informe de detalles del mensaje de cumplimiento de la comunicación.](../media/communication-compliance-message-detail-report.png)

Para crear un nuevo informe de detalles del mensaje, siga estos pasos:

1. Inicie sesión en el Centro de cumplimiento de Microsoft 365 con una cuenta que sea miembro del grupo de roles *Investigadores de cumplimiento de* comunicación.
2. Vaya a la **pestaña Directivas** , seleccione una directiva y, a continuación, **seleccione Crear informe de detalles del mensaje**.
3. En el **panel Crear informe de detalles de** mensaje, escriba un nombre para el informe en el **campo Nombre del** informe.
4. En **Elegir un intervalo de fechas**, seleccione una *fecha de inicio y* *una fecha de finalización* para el informe.
5. Seleccione **Crear**.
6. Se muestra la confirmación de creación de informes.

Según el número de elementos del informe, puede tardar unos minutos en horas antes de que el informe esté listo para descargarse. Puede comprobar el progreso en la pestaña Informes de detalles del mensaje. El estado del informe *es En curso* o *Listo para descargar*. Puede tener hasta 15 informes independientes procesando simultáneamente. Para descargar un informe, seleccione un informe en el estado *Listo para descargar* y seleccione **Descargar informe**.

> [!NOTE]
> Si el período de tiempo seleccionado no devuelve ningún resultado de mensaje en el informe, no hubo ningún mensaje para el período de tiempo seleccionado. El informe estará en blanco.

Los informes de detalles del mensaje contienen la siguiente información para cada elemento de mensaje de la directiva:

- **Identificador de** coincidencia: identificador único para el mensaje de la directiva.
- **Remitente**: el remitente del mensaje.
- **Destinatarios**: los destinatarios incluidos para el mensaje.
- **Fecha de envío**: la fecha en que se envió el mensaje.
- **Fecha de coincidencia**: la fecha en que el mensaje coincide con las condiciones de la directiva.
- **Asunto**: el asunto del mensaje.
- **Contiene datos** adjuntos: el estado de los datos adjuntos del mensaje. Los valores son Sí o No.
- **Nombre de la** directiva: el nombre de la directiva asociada al mensaje. Este valor será el mismo para todos los mensajes del informe.
- **Estado del elemento**: el estado del elemento de mensaje en la directiva. Los valores son Pendiente o Resuelto.
- **Etiquetas**: las etiquetas asignadas al mensaje. Los valores son cuestionables, compatibles o no compatibles.
- **Coincidencias de** palabras clave: coincidencias de palabras clave para el mensaje.
- **Revisores**: revisores asignados al mensaje.
- **Pendiente para (días):** el número de días que el mensaje ha estado en un estado pendiente. Para los mensajes resueltos, el valor es 0.
- **Comentario para resuelto**: los comentarios del mensaje escritos cuando se resuelven.
- **Fecha resuelta**: la fecha y hora en que se resolvió el mensaje.
- **Last Updated By**: el nombre de usuario del último actualizador.
- **Last Updated On**: la fecha y hora en que se actualizó por última vez el mensaje.
- **Historial de comentarios**: lista de todos los comentarios de la alerta del mensaje, incluido el autor del comentario y la fecha y hora del comentario.

## <a name="audit"></a>Auditoría

En algunos casos, debe proporcionar información a auditores normativos o de cumplimiento para demostrar la supervisión de las actividades y comunicaciones de los usuarios. Esta información puede ser un resumen de todas las actividades asociadas con una directiva organizativa definida o en cualquier momento en que cambie una directiva de cumplimiento de comunicación. Las directivas de cumplimiento de comunicaciones tienen seguimientos de auditoría integrados para una preparación completa para auditorías internas o externas. Las directivas de comunicación capturan historiales de auditoría detallados de cada acción de creación, edición y eliminación para proporcionar una prueba de los procedimientos de supervisión.

> [!IMPORTANT]
> La auditoría debe estar habilitada para su organización antes de que se grabe el cumplimiento de la comunicación. Para habilitar la auditoría, vea [Habilitar el registro de auditoría](communication-compliance-configure.md#step-2-required-enable-the-audit-log). Cuando las actividades desencadenan eventos que se capturan en el registro de auditoría de Microsoft 365, pueden tardar hasta 48 horas antes de que estos eventos se puedan ver en las directivas de cumplimiento de comunicación.

Para ver las actividades de actualización de directivas de cumplimiento de comunicaciones, seleccione el control **Exportar actualizaciones de directivas** en la página principal de cualquier directiva. Debe tener asignados los roles *Administrador global* o Administrador de cumplimiento *de* comunicaciones para exportar actividades de actualización. Esta acción genera un archivo de auditoría en el .csv que contiene la siguiente información:

|**Field**|**Detalles**|
|:-----|:-----|
| **CreationDate** | La fecha en que se realizó la actividad de actualización en una directiva. |
| **UserIds** | El usuario que realizó la actividad de actualización en una directiva. |
| **Operaciones** | Las operaciones de actualización realizadas en la directiva. |
| **AuditData** | Este campo es el origen de datos principal de todas las actividades de actualización de directivas. Todas las actividades de actualización se registran y se separan por delimitadores por comas. |

Para ver las actividades de revisión de cumplimiento de comunicación de una directiva, seleccione el control **Exportar** actividades de revisión **en la página** Información general de una directiva específica. Debe tener asignados los roles Administrador *global* o Administrador de cumplimiento *de* comunicaciones para exportar actividades de revisión. Esta acción genera un archivo de auditoría en el .csv que contiene la siguiente información:

|**Field**|**Detalles**|
|:-----|:-----|
| **CreationDate** | La fecha en que se realizó la actividad de revisión en una directiva. |
| **UserIds** | El usuario que realizó la actividad de revisión en una directiva. |
| **Operaciones** | Las operaciones de revisión realizadas en la directiva. |
| **AuditData** | Este campo es el origen de datos principal de todas las actividades de revisión de directivas. Todas las actividades de revisión se registran y se separan por delimitadores por comas. |

También puede ver las actividades de auditoría en el registro de auditoría unificado o con el cmdlet [de PowerShell Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) . Para obtener más información sobre las directivas de retención de registros de auditoría, vea [Administrar directivas de retención de registros de auditoría](audit-log-retention-policies.md).

Por ejemplo, el siguiente ejemplo devuelve las actividades de todas las actividades de revisión de supervisión (directivas y reglas):

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType AeD -Operations SupervisoryReviewTag
```

En este ejemplo se devuelven las actividades de actualización de las directivas de cumplimiento de comunicación:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType Discovery -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeleted
```

En este ejemplo se devuelven actividades que coinciden con las directivas de cumplimiento de comunicaciones actuales:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -Operations SupervisionRuleMatch
```

Las coincidencias de directivas de cumplimiento de comunicaciones se almacenan en un buzón de supervisión para cada directiva. En algunos casos, es posible que deba comprobar el tamaño del buzón de supervisión de una directiva para asegurarse de que no se acerca al tamaño de almacenamiento de 100 GB actual o al límite de 1 millón de mensajes. Si se alcanza el límite de buzones de correo, las coincidencias de directiva no se capturan y tendrás que crear una nueva directiva (con la misma configuración) para seguir capturando coincidencias para las mismas actividades.

Para comprobar el tamaño de un buzón de supervisión para una directiva, siga estos pasos:

1. Use el cmdlet [Conectar-ExchangeOnline](/powershell/module/exchange/connect-exchangeonline) en el módulo Exchange Online PowerShell V2 para conectarse a Exchange Online PowerShell mediante la autenticación moderna.
2. Ejecute el siguiente comando en PowerShell:

    ```PowerShell
    ForEach ($p in Get-SupervisoryReviewPolicyV2 | Sort-Object Name)
    {
       "<Name of your communication compliance policy>: " + $p.Name
       Get-MailboxStatistics $p.ReviewMailbox | ft ItemCount,TotalItemSize
    }
    ```
