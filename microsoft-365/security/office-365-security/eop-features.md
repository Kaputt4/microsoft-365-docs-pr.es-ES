---
title: Características de EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: La tabla siguiente proporciona una lista de las características que están disponibles en el servicio de filtrado de correo hospedado Exchange Online Protection.
ms.openlocfilehash: dcbb7d2e31e230633d0401eee0ef0874eb6af615
ms.sourcegitcommit: 9546708a5506fdbadbfe2500cbf1bd1aeaec6fcb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49021042"
---
# <a name="eop-features"></a>Características de EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


La tabla siguiente proporciona una lista de las características que están disponibles en el servicio de filtrado de correo hospedado Exchange Online Protection.

> [!TIP]
> El [plan de desarrollo de Microsoft 365 para empresas](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) es un buen recurso para buscar información sobre las nuevas características nuevas. Para obtener una visión más amplia acerca de las características que están disponibles con los distintos planes de suscripción a EOP, vea [Descripción del servicio Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

****

|Característica|Descripción|
|---|---|
|**Protección contra correo no deseado**||
|Detección de correo no deseado de entrada|Para obtener más información, vea [protección contra correo no deseado en Microsoft 365](anti-spam-protection.md). <p> En entornos de EOP independientes en los que EOP protege los buzones de Exchange locales, tiene que configurar las reglas de flujo de correo (también conocidas como reglas de transporte) en Exchange local para traducir el veredicto de filtro de correo no deseado de EOP para que la regla de correo no deseado pueda mover el mensaje a la carpeta de correo electrónico no deseado. Para obtener más información, consulte [configurar un EOP independiente para entregar el correo no deseado a la carpeta de correo no deseado en entornos híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) .|
|Detección de correo no deseado de salida|La protección contra correo no deseado saliente siempre está habilitada si usa el servicio para enviar correo saliente. Para obtener más información, consulte [protección contra correo no deseado de salida](outbound-spam-controls.md).|
|Protección de indispersión|Para obtener más información, consulte [retrodispersión y EOP](backscatter-messages-and-eop.md).|
|Filtrado de correo masivo|EOP usa el umbral de reclamo en masa (BCL) para marcar los mensajes de correo electrónico masivos como correo no deseado. Para obtener más información, vea los siguientes temas: <p> [¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md) <p> [Nivel de queja masiva (BCL) en EOP](bulk-complaint-level-values.md) <p> [Configurar directivas contra correo electrónico no deseado](configure-your-spam-filter-policies.md)|
|Listas de bloque de direcciones URL malintencionadas|EOP usa varias listas de bloqueo de URL que ayudan a detectar vínculos malintencionados conocidos dentro de los mensajes.|
|Protección contra suplantación de identidad|EOP incluye 750.000 dominios de remitentes de correo no deseado conocidos.|
|Protección contra la suplantación de identidad|Para obtener más información, consulte [protección contra la suplantación de identidad](anti-spoofing-protection.md).|
|**Administración del correo no deseado**||
|Configurar remitentes seguros y remitentes bloqueados|Para obtener más información, vea [crear listas de remitentes seguros](create-safe-sender-lists-in-office-365.md) y [crear listas de remitentes bloqueados](create-block-sender-lists-in-office-365.md).|
|Crear directivas contra correo no deseado personalizadas|Para una mayor granularidad, puede crear directivas de correo no deseado personalizadas y aplicarlas a usuarios, grupos o dominios específicos de la organización. Las directivas personalizadas siempre tienen prioridad con respecto a la directiva predeterminada, pero puede cambiar la prioridad (es decir, el orden de ejecución) de las directivas personalizadas. Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado](configure-your-spam-filter-policies.md).|
|Configurar las acciones en los mensajes filtrados contra correo electrónico no deseado|Por ejemplo, puede eliminar los mensajes filtrados por contenido o enviarlos a la carpeta Correo electrónico no deseado o a cuarentena. Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado](configure-your-spam-filter-policies.md).|
|Filtrado de correo no deseado internacional|Puede configurar el filtrado contra correo no deseado para filtrar los mensajes escritos en idiomas específicos o enviados desde países o regiones específicos. Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado](configure-your-spam-filter-policies.md).|
|Administración de correo no deseado a través de Outlook o Outlook en la web (anteriormente conocido como Outlook Web App)|Los administradores y usuarios finales pueden crear listas de remitentes seguros y listas de remitentes bloqueados. Para obtener más información, consulte Acerca de la [configuración del correo no deseado en Outlook](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook). <p> Si está usando EOP para proteger los buzones locales, asegúrese de usar la sincronización de directorios para ayudar a garantizar que esta configuración se sincronice con el servicio. Para más información sobre cómo configurar la sincronización de directorios, vea "Usar la sincronización de directorios para administrar usuarios de correo" en [Administrar usuarios de correo en EOP](manage-mail-users-in-eop.md).|
|Informar de falsos positivos y falsos negativos a Microsoft.|Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).|
|Notificaciones de cuarentena de correo no deseado de usuario final|Para obtener más información, vea [notificaciones de correo no deseado para el usuario final](use-spam-notifications-to-release-and-report-quarantined-messages.md) y [configurar notificaciones de correo no deseado para el usuario final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications).|
|Permite ver, buscar y administrar mensajes en el portal de cuarentena.|Para obtener más información, vea [Manage Quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md) o [Find and Release Quarantined messages as a User](find-and-release-quarantined-messages-as-a-user.md).|
|Ver encabezados de mensajes en cuarentena de correo no deseado|Después de ver el encabezado de mensaje en cuarentena, también puede copiar y pegar el texto del encabezado en el [analizador de encabezados de mensaje](https://mha.azurewebsites.net/) para averiguar qué ha sucedido con el mensaje.|
|**Protección antimalware**||
|Varios motores para la protección antimalware|Varios motores antimalware ayudan a proteger automáticamente a nuestros clientes en todo momento.|
|La posibilidad de deshabilitar el filtrado de malware|No se puede deshabilitar el filtrado de malware. Creemos que ofrecer un nivel constante y riguroso de protección para todos nuestros productos es una parte fundamental de la estrategia de defensa necesaria para ayuda a proteger su entorno de mensajería de correo electrónico. Como resultado, el filtrado de malware está habilitado automáticamente para todos los clientes.|
|Inspección de malware en el cuerpo del mensaje y los datos adjuntos|El servicio inspecciona la carga activa en el cuerpo del mensaje y en todos los archivos adjuntos a mensajes en busca de malware.|
|Notificaciones de alerta de malware predeterminadas o personalizadas|Puede enviar un mensaje de notificación a los remitentes o administradores. Para obtener más información, vea [Configure anti-malware Policies](configure-anti-malware-policies.md).|
|Notificaciones de destinatarios|Poner en cuarentena el mensaje en modo silencioso o poner en cuarentena el mensaje, y también entregarlo con todos los datos adjuntos reemplazados por un solo archivo de texto que contenga texto personalizado o estándar. Para obtener más información, vea [Configure anti-malware Policies](configure-anti-malware-policies.md).|
|Filtrado de datos adjuntos comunes|Puede habilitar y personalizar una lista de tipos de archivo que siempre se considera malware. Para obtener más información, vea [protección contra malware en EOP](anti-malware-protection.md).|
|Protección contra spyware|La protección antimalware incluye protección antivirus y antispyware.|
|Crear directivas de filtro de malware personalizadas|Para una mayor precisión, puede crear directivas de filtrado de malware personalizadas y aplicarlas a usuarios, grupos o dominios específicos en la organización. Las directivas personalizadas siempre tienen prioridad con respecto a la directiva predeterminada, pero puede cambiar la prioridad (es decir, el orden de ejecución) de las directivas personalizadas. Para obtener más información, vea [Configure anti-malware Policies](configure-anti-malware-policies.md).|
|**Enrutamiento y conectores de correo**||
|Enrutamiento de correo condicional|Para obtener más información, consulte [Escenario: Enrutamiento de correo condicional en Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).|
|TLS oportunista o forzada|La TLS oportunista o forzada está disponible con conectores. La TLS oportunista intenta una conexión TLS, pero usa una conexión SMTP si la conexión TLS no se realiza correctamente. Forzar TLS exige conexiones TLS, lo que significa que el mensaje se rechaza si la conexión TLS no se realiza correctamente. Para obtener más información sobre la seguridad TLS, consulte [Set up connectors for secure mail flow with a partner organization](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner).|
|Enrutamiento regional (restricción de flujo de correo a una región específica)|Para obtener más información, vea la sección de "Centros de datos de EOP" en [Información general de Exchange Online Protection](exchange-online-protection-overview.md).|
|Herramienta Comprobador de conectividad SMTP|Para obtener más información acerca del uso de esta herramienta para probar el flujo de correo, vea [Test mail Flow Validating Your Microsoft 365 Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).|
|Subdominios coincidentes|Para obtener más información sobre cómo habilitar el flujo de correo hacia y desde los subdominios de los dominios aceptados, vea [mail Flow in EOP](mail-flow-in-eop.md).|
|**Reglas de flujo de correo**||
|Filtrado y acciones basados en directivas|Las directivas personalizadas se basan en reglas de flujo de correo de Exchange (también conocidas como reglas de transporte). Puede filtrar por dominio, palabra clave, nombre de archivo, tipo de archivo, línea de asunto, cuerpo del mensaje, remitente, destinatario, encabezado y dirección IP. Para obtener más información, vea [reglas de flujo de correo (reglas de transporte) en Exchange Online Protection](mail-flow-rules-transport-rules-0.md).|
|Filtrar por patrones de texto|Las reglas de flujo de correo pueden usar una matriz o expresiones regulares para hacer coincidir el texto. También puede usar una cadena o una matriz de cadenas para buscar por varias propiedades de mensaje, como dirección, asunto, cuerpo o nombres de datos adjuntos. Para obtener más información, vea [reglas de flujo de correo (reglas de transporte) en Exchange Online Protection](mail-flow-rules-transport-rules-0.md) .|
|Diccionarios personalizados|Las reglas de flujo de correo pueden incluir largas listas de texto y palabras clave, lo que proporciona la misma funcionalidad que un diccionario personalizado.|
|Reglas de directiva por dominio|Se puede personalizar el ámbito de una regla de flujo de correo para que se ajuste a los nombres de dominio de remitente o destinatario, intervalos de direcciones IP, palabras clave de dirección o patrones, pertenencias a grupos y otras condiciones.|
|Examen de archivos adjuntos|Se pueden crear reglas para examinar el nombre de archivo, la extensión y el contenido de los datos adjuntos.|
|Enviar notificaciones sobre las reglas de directiva al remitente|Puede rechazar mensajes y enviar un informe de no entrega (también conocido como un mensaje NDR o de devolución) al remitente a través de la acción **rechazar el mensaje con la explicación** o **rechazar el mensaje con el código de estado mejorado** . Para obtener más información, vea [acciones de las reglas de flujo de correo en Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).|
|Redirigir o copiar mensajes|Las reglas de flujo de correo pueden redirigir, agregar destinatarios por CC o CCO, simplemente agregar destinatarios y otras opciones. Para obtener más información, vea [acciones de las reglas de flujo de correo en Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).|
|Ajustar la prioridad de la regla en varias reglas|Use el Centro de administración de Exchange para cambiar el orden en que se procesan las reglas.|
|Filtrar mensajes y, a continuación, cambiar la distribución o los atributos de un mensaje|Puede filtrar los mensajes según una amplia variedad de condiciones y, después, aplicar una serie de acciones a cada mensaje. Para obtener más información, vea [reglas de flujo de correo (reglas de transporte) en Exchange Online Protection](mail-flow-rules-transport-rules-0.md).|
|Cambiar el nivel de confianza contra correo no deseado (SCL) de un mensaje por regla.|Puede inspeccionar un mensaje en tránsito y asignarle un nivel de confianza de correo no deseado basándose en los criterios que elija. Para obtener más información, vea [usar reglas de flujo de correo para establecer el nivel de confianza contra correo no deseado (SCL) en los mensajes](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).|
|Inspeccionar archivos adjuntos a mensajes|Puede examinar el contenido o las características de un archivo adjunto y definir la acción que se realizará según lo que se encuentre. Para obtener más información, vea [usar reglas de flujo de correo para inspeccionar datos adjuntos de mensajes en Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments).|
|**Administración**||
|Administración basada en web|Los administradores pueden administrar el servicio en el centro de administración de Exchange (EAC), que se admite en los idiomas de 60. Para obtener más información, vea [centro de administración de Exchange en EOP independiente](exchange-admin-center-in-exchange-online-protection-eop.md).|
|Sincronización de directorios|La sincronización de directorios se puede realizar con la Herramienta de sincronización de Microsoft Azure Active Directory. Para obtener más información, vea la sección "Usar la sincronización de directorios para administrar usuarios de correo" en [Administrar usuarios de correo en EOP](manage-mail-users-in-eop.md).  |
|Bloqueo perimetral basado en directorios (DBEB)|La característica DBEB permite rechazar mensajes para destinatarios no válidos en el perímetro de la red de servicio. DBEB permite a los administradores agregar destinatarios habilitados para correo a Microsoft 365 y bloquear todos los mensajes enviados a direcciones de correo electrónico que no están presentes en Microsoft 365. Para obtener más información acerca de la configuración de DBEB, vea [use Directory based Edge blocking to Reject messages sent to invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).|
|PowerShell|La funcionalidad completa de EOP está disponible en PowerShell de EOP independiente. Para obtener más información, vea [PowerShell de Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell).|
|**Informes y registro**||
|Seguimiento de mensajes|Los administradores pueden seguir los mensajes de correo electrónico a medida que pasan por el servicio. Puede determinar si el servicio ha recibido, rechazado, aplazado o entregado un mensaje de correo electrónico dirigido. Le permite, de forma eficaz, responder las preguntas de los usuarios, resolver problemas con el flujo de correo y validar los cambios de directiva, y elimina la necesidad de solicitar asistencia al soporte técnico. Para obtener más información, consulte [seguimiento de mensajes en el centro de cumplimiento y de seguridad](message-trace-scc.md).|
|Informes basados en web|Los informes de protección de correo en el centro de seguridad & cumplimiento proporcionan datos de mensajería. Por ejemplo, puede supervisar la cantidad de correo no deseado y malware que se detecta, o la frecuencia con la que las reglas de flujo de correo coinciden. Con estos informes interactivos, puede obtener rápidamente un informe visual de los datos resumidos y obtener más detalles acerca de los mensajes individuales, hasta un máximo de 90 días. Para obtener más información, vea [usar informes de protección de correo para ver datos sobre malware, correo no deseado y detecciones de reglas](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports).|
|Registro de auditoría|El informe del grupo de roles de administrador y el registro de auditoría de administrador están disponibles para los administradores de EOP. Para obtener más información, vea [Informes de auditoría en EOP](auditing-reports-in-eop.md).  |
|**Acuerdos de nivel de servicio (SLA) y soporte técnico**||
|SLA de efectividad en cuanto a correo no deseado|\> 99%|
|SLA sobre proporción de falsos positivos|\< 1:250000|
|SLA sobre detección y bloqueo de virus|100% de virus conocidos|
|SLA sobre el tiempo de actividad mensual|99,999%|
|Soporte técnico por web y teléfono 24 horas al día, siete días a la semana|Para obtener más información acerca de las opciones de soporte técnico y ayuda de EOP, vea [Ayuda y soporte técnico para EOP](help-and-support-for-eop.md).|
|**Otras características**||
|Una red mundial georredundante de servidores|EOP se ejecuta en una red mundial de centros de datos que están diseñados para ayudar a proporcionar la mejor disponibilidad. Para obtener más información, vea la sección "Centros de datos de EOP" en [Información general de Exchange Online Protection](exchange-online-protection-overview.md).  |
|Puesta en cola de los mensajes cuando el servidor local no puede aceptar correo|Los mensajes en aplazamientos permanecen en nuestras colas durante un día. Los reintentos de envío de mensajes se basan en el error que se obtiene del sistema de correo del destinatario. Los mensajes se reintentan cada 5 minutos, como valor promedio. Para obtener más información, vea [Preguntas más frecuentes sobre mensajes devueltos, aplazados y en cola de EOP](eop-queued-deferred-and-bounced-messages-faq.md).|
|Cifrado de mensajes de Office 365 disponible como servicio complementario|Para obtener más información, vea [Cifrado en Office 365](../../compliance/encryption.md).|
|
