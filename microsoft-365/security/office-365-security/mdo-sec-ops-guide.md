---
title: Guía de operaciones de seguridad para Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Un cuaderno de estrategias prescriptivo para que el personal de SecOps administre Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01c857d96fe461c91c459704f4572191f37ef016
ms.sourcegitcommit: dd5fc139affb4cba4089cbdb2c478968b680699a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2022
ms.locfileid: "64747498"
---
# <a name="microsoft-defender-for-office-365-security-operations-guide"></a>Guía de operaciones de seguridad de Microsoft Defender para Office 365

En este artículo se proporciona información general sobre los requisitos y las tareas para el funcionamiento correcto de Microsoft Defender para Office 365 en su organización. Estas tareas ayudan a garantizar que el centro de operaciones de seguridad (SOC) proporciona un enfoque confiable y de alta calidad para proteger, detectar y responder a amenazas de seguridad relacionadas con el correo electrónico y la colaboración.

En el resto de esta guía se describen las actividades necesarias para el personal de SecOps. Las actividades se agrupan en tareas prescriptivas diarias, semanales, mensuales y ad hoc.

Un artículo complementario de esta guía proporciona información general para [administrar incidentes y alertas de Defender para Office 365 en la página Incidentes del portal de Microsoft 365 Defender](mdo-sec-ops-manage-incidents-and-alerts.md).

La [guía de operaciones de seguridad de Microsoft 365 Defender](/microsoft-365/security/defender/integrate-microsoft-365-defender-secops) contiene información adicional que puede usar para planear y desarrollar.

## <a name="daily-activities"></a>Actividades diarias

### <a name="monitor-the-microsoft-365-defender-incidents-queue"></a>Supervisión de la cola de incidentes de Microsoft 365 Defender

La página **Incidentes** del portal de Microsoft 365 Defender en <https://security.microsoft.com/incidents-queue> (también conocida como _cola de incidentes_) permite administrar y supervisar eventos de los siguientes orígenes en Defender para Office 365:

- [Alertas](../../compliance/alert-policies.md#default-alert-policies).
- [Investigación y respuesta automatizadas (AIR).](automated-investigation-response-office.md)

Para obtener más información sobre la cola incidentes, consulte [Priorización de incidentes en Microsoft 365 Defender](../defender/incident-queue.md).

El plan de evaluación de prioridades para supervisar la cola de incidentes debe usar el siguiente orden de prioridad para los incidentes:

1. **Se detectó un clic de dirección URL potencialmente malintencionado**.
2. **El usuario ha restringido el envío de correo electrónico**.
3. **Se han detectado patrones de envío de correo electrónico sospechosos**.
4. **Correo electrónico notificado por el usuario como malware o phish**, y **varios usuarios informaron de correo electrónico como malware o phish**.
5. **Mensajes de correo electrónico que contienen archivos malintencionados quitados después de la entrega**, **mensajes de correo electrónico que contienen direcciones URL malintencionadas eliminadas después de la entrega** y **mensajes de correo electrónico de una campaña eliminada después de la entrega**.
6. **Phish entregado debido a una invalidación de ETR**, **Phish entregado porque la carpeta correo no deseado de un usuario está deshabilitada** y **Phish se entrega debido a una directiva de ip permitida**
7. **El malware no se zapped porque ZAP está deshabilitado** y **Phish no zapped porque ZAP está deshabilitado**.

La administración de colas de incidentes y los roles responsables se describen en la tabla siguiente:

|Actividad|Cadencia|Descripción|Persona|
|---|---|---|---|
|Valore los incidentes en la cola incidentes en <https://security.microsoft.com/incidents-queue>.|Diario|Compruebe que todos los incidentes de gravedad **media** y **alta** de Defender para Office 365 están evaluados.|Equipo de operaciones de seguridad|
|Investigue y tome medidas de respuesta sobre incidentes.|Diario|Investigue todos los incidentes y realice activamente las acciones de respuesta recomendadas o manuales.|Equipo de operaciones de seguridad|
|Resolución de incidentes.|Diario|Si el incidente se ha corregido, resuelva el incidente. La resolución del incidente resuelve todas las alertas activas vinculadas y relacionadas.|Equipo de operaciones de seguridad|
|Clasificar incidentes.|Diario|Clasifique los incidentes como true o false. Para las alertas verdaderas, especifique el tipo de amenaza. Estas clasificaciones ayudan al equipo de seguridad a ver los patrones de amenazas y a defender su organización de ellos.|Equipo de operaciones de seguridad|

### <a name="manage-false-positive-and-false-negative-detections"></a>Administración de detecciones de falsos positivos y falsos negativos

En Defender para Office 365, se administran falsos positivos (buen correo marcado como incorrecto) y falsos negativos (se permite correo incorrecto) en las siguientes ubicaciones:

- Portal [de envíos (envíos de administradores).](admin-submission.md)
- Lista [de permitidos o bloqueados de inquilinos](tenant-allow-block-list.md)
- [Explorador de amenazas](threat-explorer.md)

Para obtener más información, consulte la sección [Administrar detecciones de falsos positivos y falsos negativos](#manage-false-positive-and-false-negative-detections) más adelante en este artículo.

La administración de falsos positivos y falsos negativos y las personas responsables se describen en la tabla siguiente:

|Actividad|Cadencia|Descripción|Persona|
|---|---|---|---|
|Envíe falsos positivos y falsos negativos a Microsoft en <https://security.microsoft.com/reportsubmission>.|Diario|Proporcione señales a Microsoft mediante la notificación de detecciones incorrectas de correo electrónico, dirección URL y archivos.|Equipo de operaciones de seguridad|
|Analice los detalles del envío del administrador.|Diario|Comprenda los siguientes factores para los envíos que realiza a Microsoft: <ul><li>Lo que causó el falso positivo de falso negativo.</li><li>Estado de la configuración de Defender para Office 365 en el momento del envío.</li><li>Si necesita realizar cambios en la configuración de Defender para Office 365.</li></ul>|Equipo de operaciones de seguridad <br/><br/> Administración de seguridad|
|Agregue entradas de bloque en la lista de permitidos o bloqueados de inquilinos en <https://security.microsoft.com/tenantAllowBlockList>.|Diario|Use la lista de permitidos o bloqueados de inquilinos para agregar entradas de bloque para las detecciones de direcciones URL negativas falsas, archivos o remitentes según sea necesario.|Equipo de operaciones de seguridad|
|Libere los falsos negativos de la cuarentena.|Diario|Después de que el destinatario confirme que el mensaje se puso en cuarentena incorrectamente, puede liberar o aprobar solicitudes de versión para los usuarios. <br/><br/> Para controlar lo que los usuarios pueden hacer con sus propios mensajes en cuarentena (incluida la versión o la solicitud de lanzamiento), consulte [Directivas de cuarentena](quarantine-policies.md).|Equipo de operaciones de seguridad <br/><br/> Equipo de mensajería|

### <a name="review-phishing-and-malware-campaigns-that-resulted-in-delivered-mail"></a>Revisar las campañas de suplantación de identidad (phishing) y malware que dieron lugar a la entrega de correo

|Actividad|Cadencia|Descripción|Persona|
|---|---|---|---|
|Revise las campañas de correo electrónico.|Diario|[Revise las campañas de correo electrónico dirigidas](campaigns.md) a su organización en <https://security.microsoft.com/campaigns>. Céntrese en las campañas que dieron lugar a la entrega de mensajes a los destinatarios. <br/><br/> Quite los mensajes de las campañas que existen en los buzones de usuario. Esta acción solo es necesaria cuando una campaña contiene correo electrónico que aún no se ha corregido mediante acciones de incidentes, [purga automática de cero horas (ZAP)](zero-hour-auto-purge.md) o corrección manual.|Equipo de operaciones de seguridad|

## <a name="weekly-activities"></a>Actividades semanales

### <a name="review-email-detection-trends-in-defender-for-office-365-reports"></a>Revisar las tendencias de detección de correo electrónico en informes de Defender para Office 365

En Defender para Office 365, puede usar los siguientes informes para revisar las tendencias de detección de correo electrónico en su organización:

- Informe [de estado de Flujo de correo](view-mail-flow-reports.md#mailflow-status-report)
- Informe de [estado de Protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)

|Actividad|Cadencia|Descripción|Persona|
|---|---|---|---|
|Revise los informes de detección de correo electrónico en: <ul><li><https://security.microsoft.com/reports/TPSAggregateReportATP></li><li><https://security.microsoft.com/mailflowStatusReport?viewid=type></li></ul>|Semanal|Revise las tendencias de detección de correo electrónico para detectar malware, suplantación de identidad (phishing) y correo no deseado en comparación con un buen correo electrónico. La observación a lo largo del tiempo le permite ver patrones de amenazas y determinar si necesita ajustar las directivas de Defender para Office 365.|Administración de seguridad <br/><br/> Equipo de operaciones de seguridad|

### <a name="track-and-respond-to-emerging-threats-using-threat-analytics"></a>Seguimiento y respuesta a amenazas emergentes mediante análisis de amenazas

Use [Análisis de amenazas](/microsoft-365/security/defender-endpoint/threat-analytics) para revisar las amenazas activas y de tendencia.

|Actividad|Cadencia|Descripción|Persona|
|---|---|---|---|
|Revise las amenazas en Análisis de amenazas en <https://security.microsoft.com/threatanalytics3>.|Semanal|El análisis de amenazas proporciona análisis detallados, incluidos los siguientes elementos: <ul><li>Iocs.</li><li>Consultas de búsqueda sobre los actores de amenazas activos y sus campañas.</li><li>Técnicas de ataque populares y nuevas.</li><li>Vulnerabilidades críticas.</li><li>Superficies de ataque comunes.</li><li>Malware frecuente.</li></ul>|Equipo de operaciones de seguridad <br/><br/> Equipo de búsqueda de amenazas|

### <a name="review-top-targeted-users-for-malware-and-phishing"></a>Revisión de los usuarios principales de destino para el malware y la suplantación de identidad (phishing)

Use la pestaña **[Usuarios de destino superior](threat-explorer.md#top-targeted-users)** del Explorador de amenazas para detectar o confirmar a los usuarios que son los principales destinos de malware y correo electrónico de phishing.

|Actividad|Cadencia|Descripción|Persona|
|---|---|---|---|
|Revise la pestaña **Usuarios principales de destino** en el Explorador de amenazas en <https://security.microsoft.com/threatexplorer>.|Semanal|Use la información para decidir si necesita ajustar directivas o protecciones para estos usuarios. Agregue los usuarios afectados a [las cuentas de prioridad](/microsoft-365/admin/setup/priority-accounts) para obtener las siguientes ventajas: <ul><li>Visibilidad adicional cuando los incidentes les afectan.</li><li>Heurística personalizada para patrones de flujo de correo ejecutivo (protección de cuenta prioritaria).</li><li>[Informe de problemas de correo electrónico para cuentas prioritarias](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</li></ul>|Administración de seguridad <br/><br/> Equipo de operaciones de seguridad|

### <a name="review-top-malware-and-phishing-campaigns-that-target-your-organization"></a>Revise las principales campañas de malware y phishing dirigidas a su organización.

Las vistas de campaña revelan ataques de malware y suplantación de identidad (phishing) contra su organización. Para obtener más información, consulte [Vistas de campaña en Microsoft Defender para Office 365](campaigns.md).

|Actividad|Cadencia|Descripción|Persona|
|---|---|---|---|
|Use **Vistas de campaña** en <https://security.microsoft.com/campaigns> para revisar los ataques de malware y phishing que le afectan.|Semanal|Obtenga información sobre los ataques y las técnicas y qué Defender para Office 365 pudo identificar y bloquear. <br/><br/> Use **Descargar informe de amenazas** en Vistas de campaña para obtener información detallada sobre una campaña.|Equipo de operaciones de seguridad|

## <a name="ad-hoc-activities"></a>Actividades ad hoc

### <a name="manual-investigation-and-removal-of-email"></a>Investigación y eliminación manual del correo electrónico

|Actividad|Cadencia|Descripción|Persona|
|---|---|---|---|
|Investigue y quite el correo electrónico incorrecto en el Explorador de amenazas en <https://security.microsoft.com/threatexplorer> en función de las solicitudes del usuario.|Ad hoc|Use la acción **Desencadenar investigación** en el Explorador de amenazas para iniciar una investigación y un cuaderno de estrategias de respuesta automatizados en cualquier correo electrónico de los últimos 30 días. Desencadenar manualmente una investigación ahorra tiempo y esfuerzo al incluir de forma centralizada: <ul><li>Una investigación raíz.</li><li>Pasos para identificar y correlacionar amenazas.</li><li>Acciones recomendadas para mitigar esas amenazas.</li></ul> <br/> Para obtener más información, vea [Ejemplo: Un mensaje de phish notificado por el usuario inicia un cuaderno de estrategias de investigación](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer). <br/><br/> O bien, puede usar el Explorador de amenazas para [investigar manualmente el correo electrónico](investigate-malicious-email-that-was-delivered.md) con funcionalidades eficaces de búsqueda y filtrado y [realizar acciones de respuesta manual](remediate-malicious-email-delivered-office-365.md) directamente desde el mismo lugar. Acciones manuales disponibles: <ul><li>Mover a la bandeja de entrada</li><li>Mover a correo no deseado</li><li>Mover a elementos eliminados</li><li>Eliminar temporalmente</li><li>Eliminación rígida.</li></ul>|Equipo de operaciones de seguridad|

### <a name="proactively-hunt-for-threats"></a>Búsqueda proactiva de amenazas

|Actividad|Cadencia|Descripción|Persona|
|---|---|---|---|
|Búsqueda periódica y proactiva de amenazas en: <ul><li><https://security.microsoft.com/threatexplorer></li><li><https://security.microsoft.com/v2/advanced-hunting></li></ul>.|Ad hoc|Busque amenazas mediante [el Explorador de amenazas](threat-explorer.md) y la [búsqueda avanzada](../defender-endpoint/advanced-hunting-overview.md).|Equipo de operaciones de seguridad <br/><br/> Equipo de búsqueda de amenazas|
|Compartir consultas de búsqueda.|Ad hoc|Comparta activamente consultas útiles y usadas con frecuencia dentro del equipo de seguridad para una búsqueda y corrección de amenazas manuales más rápidas. <br/><br/> Use [seguimientos de amenazas](threat-trackers.md) y [consultas compartidas en búsqueda avanzada](/microsoft-365/security/defender/advanced-hunting-shared-queries).|Equipo de operaciones de seguridad <br/><br/> Equipo de búsqueda de amenazas|
|Cree reglas de detección personalizadas en <https://security.microsoft.com/custom_detection>.|Ad hoc|[Cree reglas de detección personalizadas](../defender/advanced-hunting-overview.md#get-started-with-advanced-hunting) para supervisar de forma proactiva eventos, patrones y amenazas en función de Defender para Office 365 datos en La búsqueda anticipada. Las reglas de detección contienen consultas de búsqueda avanzadas que generan alertas basadas en los criterios coincidentes.|Equipo de operaciones de seguridad <br/><br/> Equipo de búsqueda de amenazas|

### <a name="review-defender-for-office-365-policy-configurations"></a>Revisión de las configuraciones de directiva de Defender para Office 365

|Actividad|Cadencia|Descripción|Persona|
|---|---|---|---|
|Revise la configuración de las directivas de Defender para Office 365 en <https://security.microsoft.com/configurationAnalyzer>.|Ad hoc <br/><br/> Mensualmente|Use el [Analizador de configuración](configuration-analyzer-for-security-policies.md) para comparar la configuración de directiva existente con los [valores Estándar o Estricto recomendados para Defender para Office 365](recommended-settings-for-eop-and-office365.md). El analizador de configuración identifica cambios accidentales o malintencionados que pueden reducir la posición de seguridad de su organización. <br/><br/> O yu puede usar la [herramienta ORCA](https://aka.ms/getorca) basada en PowerShell.|Administración de seguridad <br/><br/> Equipo de mensajería|
|Revisión de las invalidaciones de detección en Defender para Office 365 en<https://security.microsoft.com/reports/TPSMessageOverrideReportATP>|Ad hoc <br/><br/> Mensualmente|Use la [vista Ver datos por invalidación \> del sistema Desglose del gráfico por motivo](view-email-security-reports.md#view-data-by-system-override-and-chart-breakdown-by-reason) en el **informe de estado de Protección contra amenazas** para revisar el correo electrónico que se detectó como suplantación de identidad (phishing) pero que se entregó debido a la configuración de invalidación de usuario o directiva. <br/><br/> Investigue, quite o ajuste de forma activa las invalidaciones para evitar la entrega de correo electrónico que se determinó que era malintencionado.|Administración de seguridad <br/><br/> Equipo de mensajería|

### <a name="review-spoof-and-impersonation-detections"></a>Revisión de las detecciones de suplantación y suplantación

|Actividad|Cadencia|Descripción|Persona|
|---|---|---|---|
|Revise la **información de inteligencia de suplantación** y la **información de detección de suplantación** en <ul><li><<https://security.microsoft.com/spoofintelligence>></li><li><https://security.microsoft.com/impersonationinsight></li></ul>.|Ad hoc <br/><br/> Mensualmente|Use la [información de inteligencia de](learn-about-spoof-intelligence.md) [suplantación y la información de suplantación](impersonation-insight.md) para ajustar el filtrado para las detecciones de suplantación y suplantación.|Administración de seguridad <br/><br/> Equipo de mensajería|

### <a name="review-priority-account-membership"></a>Revisar la pertenencia a la cuenta de prioridad

|Actividad|Cadencia|Descripción|Persona|
|---|---|---|---|
|Revise quién se define como una cuenta de prioridad en <https://security.microsoft.com/securitysettings/userTags>.|Ad hoc|Mantenga actualizada la pertenencia de [las cuentas de prioridad](/microsoft-365/admin/setup/priority-accounts) con los cambios de la organización para obtener las siguientes ventajas para esos usuarios: <ul><li>Mejor visibilidad en los informes.</li><li>Filtrado en incidentes y alertas.</li><li>Heurística personalizada para patrones de flujo de correo ejecutivo (protección de cuenta prioritaria).</li></ul> <br/> Use [etiquetas de usuario](user-tags.md) personalizadas para que otros usuarios obtengan: <ul><li>Mejor visibilidad en los informes.</li><li>Filtrado en incidentes y alertas.</li></ul>|Equipo de operaciones de seguridad|

## <a name="appendix"></a>Apéndice

### <a name="learn-about-microsoft-defender-for-office-365-tools-and-processes"></a>Más información sobre Microsoft Defender para Office 365 herramientas y procesos

Los miembros del equipo de operaciones de seguridad y respuesta deben integrar Defender para Office 365 herramientas y características en las investigaciones y los procesos de respuesta existentes. Learning sobre las nuevas herramientas y funcionalidades puede tardar tiempo, pero es una parte fundamental del proceso de incorporación. La manera más sencilla de que los miembros del equipo de seguridad de SecOps y correo electrónico obtengan información sobre Defender para Office 365 es usar el contenido de entrenamiento que está disponible como parte del contenido de entrenamiento ninja en <https://aka.ms/mdoninja>.

El contenido está estructurado para diferentes niveles de conocimiento (fundamentales, intermedios y avanzados) con varios módulos por nivel.

Los vídeos breves para tareas específicas también están disponibles en el [canal de YouTube Microsoft Defender para Office 365](https://www.youtube.com/playlist?list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf).

### <a name="permissions-for-defender-for-office-365-activities-and-tasks"></a>Permisos para Defender para Office 365 actividades y tareas

Los permisos para administrar Defender para Office 365 en el portal de Microsoft 365 Defender y PowerShell se basan en el modelo de permisos de control de acceso basado en rol (RBAC). RBAC es el mismo modelo de permisos que usan la mayoría de los servicios de Microsoft 365. Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

> [!NOTE]
> Privileged Identity Management (PIM) en Azure AD también es una manera de asignar los permisos necesarios al personal de SecOps. Para obtener más información, vea [Privileged Identity Management (PIM) y por qué usarlo con Microsoft Defender para Office 365](use-privileged-identity-management-in-defender-for-office-365.md).

Los siguientes permisos (roles y grupos de roles) están disponibles en Defender para Office 365 y se pueden usar para conceder acceso a los miembros del equipo de seguridad:

- **Azure AD roles**: roles centralizados que asignan permisos para _todos los_ servicios de Microsoft 365, incluidos los Defender para Office 365. Puede ver los roles de Azure AD y los usuarios asignados en el portal de Microsoft 365 Defender, pero no puede administrarlos directamente allí. En su lugar, administra Azure AD roles y miembros en <https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/RolesAndAdministrators>. Los roles más frecuentes que usan los equipos de seguridad son:
  - **Administrador de seguridad**
  - **Operador de seguridad**
  - **Lector de seguridad**

- **Roles de colaboración de & por correo electrónico**: roles y grupos de roles que conceden permiso específico para Microsoft Defender para Office 365. El siguiente rol no está disponible en Azure AD, pero puede ser importante para los equipos de seguridad:

  - **Rol de vista previa** : asigne este rol a los miembros del equipo que necesiten obtener una vista previa o descargar mensajes de correo electrónico como parte de las actividades de investigación. Permite a los usuarios [obtener una vista previa y descargar](investigate-malicious-email-that-was-delivered.md#preview-role-permissions) mensajes de correo electrónico en buzones de correo en la nube mediante la [página de entidad de correo electrónico](mdo-email-entity-page.md#email-preview-for-cloud-mailboxes).

    De forma predeterminada, este rol solo se asigna a los siguientes grupos de roles:

    - Investigador de datos
    - Supervisor de eDiscovery

    Para asignar este rol a un grupo de roles nuevo o existente, consulte [Modificar correo electrónico & pertenencia a roles de colaboración en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md#modify-email--collaboration-role-membership-in-the-microsoft-365-defender-portal).

  - **Rol de búsqueda y purga** : apruebe la eliminación de mensajes malintencionados según lo recomendado por AIR o realice acciones manuales en los mensajes en experiencias de búsqueda como el Explorador de amenazas.

    De forma predeterminada, este rol solo se asigna a los siguientes grupos de roles:

    - Investigador de datos
    - Administración de la organización

    Para asignar este rol a un grupo de roles nuevo o existente, consulte [Modificar correo electrónico & pertenencia a roles de colaboración en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md#modify-email--collaboration-role-membership-in-the-microsoft-365-defender-portal).

  - **Administrador allowBlockList de inquilinos**: administre las entradas de permitir y bloquear en la [lista de permitidos o bloqueados de inquilinos](tenant-allow-block-list.md). Bloquear direcciones URL, archivos (mediante hash de archivos) o remitentes es una acción de respuesta útil que se debe realizar al investigar el correo electrónico malintencionado que se ha entregado.

    De forma predeterminada, este rol solo se asigna al grupo de roles **Operador de seguridad** . Sin embargo, los miembros de los grupos de **roles Administradores de seguridad** y **Administración de la organización** también pueden administrar entradas en la lista de permitidos o bloqueados de inquilinos.

### <a name="siemsoar-integration"></a>Integración de SIEM/SOAR

Defender para Office 365 expone la mayoría de sus datos a través de un conjunto de API mediante programación. Estas API le ayudan a automatizar los flujos de trabajo y a hacer un uso completo de las funcionalidades de Defender para Office 365. Los datos están disponibles a través de las [API de Microsoft 365 Defender](/microsoft-365/security/defender/api-overview) y se pueden usar para integrar Defender para Office 365 en soluciones SIEM/SOAR existentes.

- [API de incidentes](/microsoft-365/security/defender/api-incident): las alertas de Defender para Office 365 y las investigaciones automatizadas son partes activas de incidentes en Microsoft 365 Defender. Los equipos de seguridad pueden centrarse en lo que es fundamental mediante la agrupación del ámbito de ataque completo y todos los recursos afectados.

- [API de streaming](/microsoft-365/security/defender/streaming-api) de eventos: permite el envío de eventos y alertas en tiempo real en un único flujo de datos a medida que se producen. Entre los tipos de eventos Defender para Office 365 admitidos se incluyen:
  - [EmailEvents](/microsoft-365/security/defender/advanced-hunting-emailevents-table)
  - [EmailUrlInfo](/microsoft-365/security/defender/advanced-hunting-emailurlinfo-table)
  - [EmailAttachmentInfo](/microsoft-365/security/defender/advanced-hunting-emailattachmentinfo-table)
  - [EmailPostDeliveryEvents](/microsoft-365/security/defender/advanced-hunting-emailpostdeliveryevents-table)

  Los eventos contienen datos del procesamiento de todo el correo electrónico (incluidos los mensajes dentro de la organización) en los últimos 30 días.

- [API de búsqueda avanzada](/microsoft-365/security/defender/api-advanced-hunting): permite la búsqueda de amenazas entre productos.

- [API de evaluación de amenazas](/graph/api/resources/threatassessment-api-overview): se puede usar para informar de correo no deseado, direcciones URL de suplantación de identidad (phishing) o datos adjuntos de malware directamente a Microsoft.

Para conectar Defender para Office 365 incidentes y datos sin procesar con Microsoft Sentinel, puede usar el [conector de Microsoft 365 Defender (M365D)](/azure/sentinel/connect-microsoft-365-defender?tabs=MDO)

Puede usar este sencillo ejemplo de "Hola mundo" para probar el acceso de api a las API de Microsoft Defender: [Hola mundo para Microsoft 365 Defender API REST](/microsoft-365/security/defender/api-hello-world).

Para obtener más información sobre la integración de herramientas SIEM, consulte [Integración de las herramientas SIEM con Microsoft 365 Defender](/microsoft-365/security/defender/configure-siem-defender).

## <a name="address-false-positives-and-false-negatives-in-defender-for-office-365"></a>Abordar falsos positivos y falsos negativos en Defender para Office 365

El envío de usuarios y envíos de administradores de mensajes de correo electrónico son señales de refuerzo positivas críticas para nuestros sistemas de detección de aprendizaje automático. Los envíos nos ayudan a revisar, evaluar, aprender rápidamente y mitigar los ataques. Informar activamente de falsos positivos y falsos negativos es una actividad importante que proporciona comentarios a Defender para Office 365 cuando se cometen errores durante la detección.

Las organizaciones tienen varias opciones para configurar envíos de usuarios. En función de la configuración, los equipos de seguridad pueden tener una participación más activa cuando los usuarios envían falsos positivos o falsos negativos a Microsoft:

- Los envíos de usuarios se envían a Microsoft para su análisis cuando la [configuración de mensajes notificada por el usuario](user-submission.md) se configura con cualquiera de las opciones siguientes:
  - Envíe los mensajes notificados a: Microsoft.
  - Envíe los mensajes notificados a: Microsoft y el buzón de mi organización.

  Los miembros de los equipos de seguridad deben realizar [envíos de administración](admin-submission.md) ad hoc cuando los equipos de operaciones detectaron falsos positivos o falsos negativos que no notificaron los usuarios.

- Cuando los mensajes notificados por el usuario están configurados para enviar mensajes solo al buzón de la organización, los equipos de seguridad deben enviar activamente falsos positivos y falsos negativos notificados por el usuario a Microsoft a través de envíos de administrador.

Cada vez que un usuario notifica un mensaje como phishing, Defender para Office 365 genera una alerta y la alerta desencadenará un cuaderno de estrategias de AIR. La lógica de incidentes correlacionará esta información con otras alertas y eventos siempre que sea posible. Esta consolidación de la información ayuda a los equipos de seguridad a evaluar, investigar y responder al correo electrónico notificado por el usuario.

Los envíos de usuarios y los envíos de administradores se controlan mediante la canalización de envío de Microsoft, que sigue un proceso estrechamente integrado. Este proceso incluye:

- Reducción de ruido.
- Evaluación de prioridades automatizada.
- Clasificación por parte de analistas de seguridad y soluciones basadas en aprendizaje automático asociadas por el usuario.

Para obtener más información, consulte [Generación de informes de un correo electrónico en Defender para Office 365 - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/reporting-an-email-in-microsoft-defender-for-office-365/ba-p/2870231).

Los miembros del equipo de seguridad pueden realizar envíos desde varias ubicaciones en el portal de Microsoft 365 Defender en <https://security.microsoft.com>:

- [Envío de administrador](admin-submission.md): use el portal Envíos para enviar sospechas de correo no deseado, suplantación de identidad (phishing), direcciones URL y archivos a Microsoft.
- Directamente desde el Explorador de amenazas mediante una de las siguientes acciones de mensaje:
  - Informe limpio
  - Informar de suplantación de identidad
  - Informar de malware
  - Notificar correo no deseado

  Puede seleccionar hasta 10 mensajes para realizar un envío masivo. Los envíos de administradores creados de esta manera también se pueden ver en el portal de envío.

Para la mitigación a corto plazo de falsos positivos, los equipos de seguridad pueden administrar directamente [entradas de bloque](manage-tenant-blocks.md) para archivos, direcciones URL y remitentes en la [lista de permitidos o bloqueados de inquilinos](tenant-allow-block-list.md).

Para la mitigación a corto plazo de falsos negativos, los equipos de seguridad no pueden administrar directamente [las entradas permitidas](manage-tenant-allows.md) en la lista de permitidos o bloqueados de inquilinos. En su lugar, deben usar [envíos de administrador](admin-submission.md) y la opción **Permitir mensajes como esta** .

[La cuarentena](manage-quarantined-messages-and-files.md) en Defender para Office 365 contiene mensajes y archivos potencialmente peligrosos o no deseados. Los equipos de seguridad pueden ver, liberar y eliminar todos los tipos de mensajes en cuarentena para todos los usuarios. Esta funcionalidad permite a los equipos de seguridad responder de forma eficaz cuando se pone en cuarentena un mensaje o archivo falso positivo.

## <a name="integrate-third-party-reporting-tools-with-defender-for-office-365-user-submission"></a>Integración de herramientas de informes de terceros con Defender para Office 365 envío de usuario

Si su organización usa una herramienta de informes de terceros que permite a los usuarios informar internamente de correo electrónico sospechoso, puede integrar la herramienta con las funcionalidades de envíos de usuarios de Defender para Office 365. Esta integración proporciona las siguientes ventajas a los equipos de seguridad:

- Integración con las funcionalidades de AIR de Defender para Office 365.
- Evaluación de prioridades simplificada.
- Tiempo reducido de investigación y respuesta.

Designe el buzón personalizado donde se envían los mensajes notificados por el usuario en la página **Envíos** de usuarios del portal de Microsoft 365 Defender en <https://security.microsoft.com/userSubmissionsReportMessage>. Para obtener más información, consulte [Configuración de mensajes notificados por el usuario](user-submission.md).

> [!NOTE]
>
> - El buzón personalizado es un buzón de Exchange Online.
> - La herramienta de informes de terceros debe incluir el mensaje notificado original como un sin comprimir. EML o . Datos adjuntos MSG en el mensaje que se envía al buzón personalizado (no reenvíe el mensaje original al buzón personalizado).
> - El buzón personalizado requiere requisitos previos específicos para permitir la entrega de mensajes potencialmente incorrectos. Para obtener más información, vea [Requisitos previos del buzón personalizado](user-submission.md#custom-mailbox-prerequisites).

Cuando el correo electrónico notificado por el usuario llega al buzón personalizado, Defender para Office 365 genera automáticamente la alerta denominada **Correo electrónico notificada por el usuario como malware o phish**. Esta alerta inicia un [cuaderno de estrategias de AIR](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook). El cuaderno de estrategias realiza una serie de pasos de investigaciones automatizadas:

- Recopile datos sobre el correo electrónico especificado.
- Recopile datos sobre las amenazas y entidades relacionadas con ese correo electrónico. Las entidades pueden incluir archivos, direcciones URL y destinatarios.
- Proporcione las acciones recomendadas para que el equipo de SecOps realice en función de los resultados de la investigación.

**El correo electrónico notificado por el usuario como alertas de malware o phish**, investigaciones automatizadas y sus acciones recomendadas se correlacionan automáticamente con incidentes en Microsoft 365 Defender. Esta correlación simplifica aún más el proceso de evaluación y respuesta para los equipos de seguridad. Si varios usuarios notifican los mismos mensajes o similares, todos los usuarios y mensajes se correlacionan con el mismo incidente.

Los datos de alertas e investigaciones en Defender para Office 365 se comparan automáticamente con las alertas e investigaciones de los demás productos de Microsoft 365 Defender:

- Microsoft Defender para punto de conexión
- Microsoft Defender for Cloud Apps
- Microsoft Defender for Identity

Si se detecta una relación, el sistema crea un incidente que proporciona visibilidad para todo el ataque.
