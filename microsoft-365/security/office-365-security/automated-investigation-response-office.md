---
title: Investigación y respuesta automatizadas (AIR) en Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Obtenga información general sobre las capacidades de investigación y respuesta automatizadas en Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 8f781687047f39d4d038e293e50c9caad83d051a
ms.sourcegitcommit: 87cc278ea2ddcd536ecfaa3dfae9a5ddaa502cf9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179251"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a>Investigación y respuesta automatizadas (AIR) en Office 365

A medida que se activen las alertas de seguridad, el equipo de operaciones de seguridad será el encargado de consultar esas alertas y tomar las medidas necesarias para proteger su organización. A veces, los equipos de operaciones de seguridad pueden sentirse abrumados por el volumen de alertas que se desencadenan. La funcionalidad de investigación y respuesta automatizada (AIR) de Office 365 puede ser de ayuda. AIR permite que el equipo de operaciones de seguridad funcione de forma más eficiente y eficaz. Las capacidades de AIR incluyen procesos de investigación automatizada en respuesta a amenazas bien conocidas que existen en la actualidad. Acciones de corrección adecuadas esperando la aprobación, lo que permite al equipo de operaciones de seguridad responder a amenazas detectadas. 

En este artículo se proporciona información general sobre AIR y sus componentes. Cuando esté listo para empezar a usar AIR, vea [investigar y responder automáticamente a amenazas en Office 365](office-365-air.md).

> [!TIP]
> ¿Tiene Microsoft 365 E5 o Microsoft 365 E3 junto con la protección de la identidad y contra amenazas? Considere probar la [Protección contra amenazas de Microsoft](../mtp/microsoft-threat-protection.md).

## <a name="at-a-high-level"></a>A un alto nivel

A medida que se activen las alertas, las guías de seguridad entrarán en vigor. En función de la situación, puede comenzar un [proceso de investigación automatizada](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) . Durante y después de una investigación automatizada, se recomiendan [las acciones de corrección](air-remediation-actions.md) . No se realiza automáticamente ninguna acción en la protección contra amenazas avanzada de Office 365. El equipo de operaciones de seguridad revisa y, a continuación, [aprueba o rechaza cada acción de corrección](air-remediation-actions.md#approve-or-reject-pending-actions)y, cuando se lleva a cabo, finaliza cada investigación. Se realiza el seguimiento y la visualización de todas estas actividades en el centro de seguridad & cumplimiento de Office 365 (vea [Ver detalles de una investigación](air-view-investigation-results.md#view-details-of-an-investigation)).

En las secciones siguientes se proporcionan más detalles sobre las alertas, las guías de seguridad y ejemplos de aire en funcionamiento.

## <a name="alerts"></a>Alertas

Las [alertas](../../compliance/alert-policies.md#viewing-alerts) representan desencadenadores de flujos de trabajo del equipo de operaciones de seguridad para respuesta ante incidentes. Establecer prioridades en el conjunto de alertas adecuadas para la investigación, a la vez que asegurarse de que no hay amenazas sin direcciones, supone un reto. Cuando las investigaciones en las alertas se realizan manualmente, los equipos de operaciones de seguridad deben buscar y correlacionar las entidades (como contenido, dispositivos y usuarios) en riesgo de amenazas. Estas tareas y flujos de trabajo pueden ser muy lentos y implican varias herramientas y sistemas. Con AIR, la investigación y la respuesta para Office 365 los eventos de seguridad se automatizan haciendo que las alertas de administración de amenazas y seguridad clave desencadenen las guías de respuesta de seguridad automáticamente. 

Actualmente, las alertas generadas a partir de los siguientes tipos de directivas de alerta se investigan automáticamente:  

- Se ha detectado un clic en una dirección URL potencialmente malintencionada
- Correo electrónico notificado por el usuario como phish *
- Mensajes de correo electrónico que contienen malware quitados después de la entrega *
- Mensajes de correo electrónico que contienen direcciones URL de phish quitadas después de la entrega *
- Patrones de envío de correo electrónico sospechosos detectados #
- El usuario restringió el envío de correo electrónico #

> [!NOTE]
> A las alertas marcadas con un asterisco (*) se les asigna una gravedad *informativa* en las respectivas directivas de alerta en el centro de seguridad & cumplimiento, con las notificaciones de correo electrónico desactivadas. Las notificaciones por correo electrónico se pueden activar a través de la configuración de la [Directiva de alerta](../../compliance/alert-policies.md#alert-policy-settings). Las alertas marcadas con un hash (#) están normalmente disponibles como alertas asociadas con las guías de vista previa pública.

Para ver las alertas, en el centro de seguridad & cumplimiento, elija **alertas** > **Ver alertas**. Seleccione una alerta para ver sus detalles y, desde allí, use el vínculo **Ver investigación** para ir a la [investigación](air-view-investigation-results.md#investigation-graph)correspondiente.  

> [!NOTE]
> Las alertas informativas están ocultas de forma predeterminada en la vista de alertas. Para verlos, cambie el filtrado de alertas para incluir alertas informativas.

Si su organización administra sus alertas de seguridad a través de un sistema de administración de alertas, un sistema de administración de servicios o un sistema de administración de eventos e información de seguridad (SIEM), puede enviar alertas de Office 365 a ese sistema mediante una notificación por correo electrónico o a través de la [API de actividad de administración de office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). Las notificaciones de alerta de investigación a través de correo electrónico o API incluyen vínculos para acceder a las alertas en el centro de seguridad & cumplimiento, lo que permite que el administrador de seguridad asignado navegue rápidamente a la investigación.

![Alertas que vinculan a investigaciones](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>Guías de seguridad

Las guías de seguridad son directivas de back-end que se encuentran en el corazón de la automatización de la protección contra amenazas avanzada de Office y en la protección contra amenazas de Microsoft. Las guías de seguridad que se proporcionan en AIR se basan en escenarios comunes de seguridad de todo el mundo y se desarrollan en función de los comentarios de los equipos de operaciones de seguridad. Una guía de seguridad se inicia automáticamente cuando se desencadenan alertas específicas dentro de la organización. Una vez que se activa la alerta, el sistema de investigación y respuesta automatizada (AIR) ejecuta la guía asociada. La investigación avanza paso a paso por el análisis de la alerta basándose en la guía de la alerta en particular, examinando todos los metadatos asociados (incluidos los mensajes de correo electrónico, usuarios, asuntos, remitentes, etc.). Basándose en los resultados de la guía de investigación, AIR recomienda un conjunto de acciones que el equipo de seguridad de la organización puede llevar a cabo para controlar y mitigar la amenaza. 

Las guías de seguridad que recibirá con AIR están diseñadas para enfrentarse a las amenazas más frecuentes que las organizaciones detectan actualmente con el correo electrónico. Se basan en la información de las operaciones de seguridad y los equipos de respuesta ante incidentes, incluidos los que ayudan a defender a Microsoft y a los activos de nuestros clientes.

### <a name="security-playbooks-are-rolling-out-in-phases"></a>Las guías de seguridad se implementan en fases

Como parte de AIR, las guías de seguridad se implementan en fases. La fase 1 suele estar disponible e incluye varias guías que proporcionan recomendaciones para las acciones que los administradores de seguridad pueden revisar y aprobar:
- Mensaje de phish notificado por el usuario
- Dirección URL haga clic en cambiar veredicto
- Malware detectado después de la entrega (ZAP de malware)
- Phish detectado tras entrega tras entrega (ZAP de Phish)

La fase 1 también incluye compatibilidad para las investigaciones de correo electrónico desencadenadas por el administrador (mediante el [Explorador de amenazas](threat-explorer.md)).

La fase 2 está ahora en progreso con las siguientes guías en la **versión preliminar pública**y se proporcionan recomendaciones para acciones y para ayudar a los administradores de seguridad en la investigación de problemas:
- Usuario notificado como comprometida (vista previa pública)

Las guías adicionales se publicarán cuando se completen. Visite el [mapa de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para ver lo que más está previsto y próximamente.

### <a name="playbooks-include-investigation-and-recommendations"></a>Las guías incluyen investigación y recomendaciones

En AIR, cada guía de seguridad incluye: 
- una investigación raíz de las entidades de un correo electrónico (archivos, direcciones URL, destinatarios, direcciones IP, etc.)
- mayor búsqueda de mensajes de correo electrónico similares recibidos por la organización 
- pasos que hay que seguir para identificar y correlacionar otras posibles amenazas y 
- acciones recomendadas de corrección de amenazas.

Cada paso de alto nivel incluye una serie de subpasos que se ejecutan para proporcionar una respuesta profunda, detallada y exhaustiva a las amenazas.

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Ejemplo: un mensaje de phish notificado por el usuario inicia una guía de investigación

Cuando un usuario de la organización envía un mensaje de correo electrónico y lo notifica a Microsoft mediante el [complemento de mensajes de informe para Outlook o Outlook Web App](enable-the-report-message-add-in.md), el informe también se envía al sistema y es visible en el explorador en la vista notificada por el usuario. Este mensaje de usuario ha informado ahora de una alerta informativa basada en el sistema, que inicia automáticamente la guía de la investigación.

Durante la fase de investigación raíz, se evalúan varios aspectos del correo electrónico. Entre ellos se incluyen:
- Una determinación del tipo de amenaza que podría ser;
- Quién lo envió;
- Dónde se envió el correo electrónico desde (infraestructura de envío);
- Si se han entregado o bloqueado otras instancias del correo electrónico;
- Una evaluación de nuestros analistas;
- Si el correo electrónico está asociado con alguna de las campañas conocidas;
- etc.

Una vez completada la investigación raíz, la guía proporciona una lista de las acciones recomendadas que se deben realizar en el correo electrónico original y las entidades asociadas con ella.
  
A continuación, se ejecutan varios pasos de investigación y de búsqueda de amenazas:

- Los mensajes de correo electrónico similares se identifican mediante búsquedas de clúster de correo electrónico.
- La señal se comparte con otras plataformas, como [ATP de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).
- Se determina si algún usuario ha hecho clic en cualquier vínculo malintencionado en mensajes de correo electrónico sospechosos.
- Una comprobación se realiza a través de Office 365 Exchange Online Protection ([EOP](exchange-online-protection-eop.md)) y de la protección contra amenazas avanzada ([ATP](office-365-atp.md)) de Office 365 para ver si hay otros mensajes similares detectados por los usuarios.
- Se realiza una comprobación para ver si un usuario se ha puesto en peligro. Esta comprobación aprovecha las señales de Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)y [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlacionando las anomalías relacionadas con las actividades de los usuarios. 

Durante la fase de caza, los riesgos y las amenazas se asignan a varios pasos de caza. 

La corrección es la fase final de la guía. Durante esta fase, se realizan pasos de corrección que se basan en las fases de investigación y de caza. 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Ejemplo: un administrador de seguridad desencadena una investigación desde el explorador de amenazas

Además de las investigaciones automáticas desencadenadas por una alerta, el equipo de operaciones de seguridad de la organización puede desencadenar una investigación automática desde una vista del [Explorador de amenazas](threat-explorer.md).

Por ejemplo, supongamos que está viendo datos en el explorador acerca de los mensajes detectados por el usuario. Puede seleccionar un elemento de la lista de resultados y, a continuación, hacer clic en **investigar** en el menú Acción (siempre que tenga permisos de corrección apropiados).

![Mensajes detectados por el usuario en el explorador con el botón investigar](../../media/Explorer-UserReported-Investigate.png)

Como otro ejemplo, supongamos que está viendo datos sobre los mensajes de correo electrónico que se detectan como que contienen malware y que se detectan varios mensajes de correo electrónico que contienen malware. Puede seleccionar la pestaña **correo electrónico** , seleccionar uno o más mensajes de correo electrónico y, a continuación, en el menú **acciones** , seleccione **investigar**. 

![Iniciar una investigación de malware en el explorador](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

De forma similar a las guías activadas por una alerta, las investigaciones automáticas que se desencadenan desde una vista del explorador incluyen una investigación raíz, pasos para identificar y correlacionar amenazas y las acciones recomendadas para mitigar esas amenazas.

## <a name="how-to-get-air"></a>Cómo obtener aire

Office 365 AIR está incluido en las siguientes suscripciones:

- Microsoft 365 E5
- Office 365 E5
- Protección contra amenazas de Microsoft
- Protección contra amenazas avanzada de Office 365 (plan 2)

Si no tiene ninguna de estas suscripciones, [inicie una prueba gratuita](https://go.microsoft.com/fwlink/p/?LinkID=698279&culture=en-US&country=US).

Para obtener más información acerca de la disponibilidad de características, visite la [característica disponibilidad en los planes de protección contra amenazas avanzada (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

## <a name="required-permissions-to-use-air-capabilities"></a>Permisos necesarios para usar capacidades de AIR

Los permisos se conceden a través de determinadas funciones, como las que se describen en la tabla siguiente: 

|Tarea |Roles necesarios |
|--|--|
|Para configurar las características de AIR |Una de las siguientes funciones: <br/>- **Administrador global**<br/>- **Administrador de seguridad** <br/>Estos roles se pueden asignar en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o en el [centro de seguridad & cumplimiento de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|Para aprobar o rechazar las acciones recomendadas|Una de las siguientes funciones, asignada en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o en el [centro de seguridad & cumplimiento de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):<br/>- **Administrador global** <br/>- **Administrador de seguridad**<br/>- **Lector de seguridad** <br/>--- y ---<br/>- **Búsqueda y depuración** (este rol solo se asigna en el [centro de cumplimiento de & de seguridad de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Es posible que tenga que crear un nuevo grupo de funciones y agregar el rol de búsqueda y depuración al nuevo grupo de roles.

## <a name="next-steps"></a>Pasos siguientes

- [Introducción al uso de AIR en Office 365](office-365-air.md)

- [Visite el plan de desarrollo de Microsoft 365 para ver lo que estará próximamente y que se implementará](https://www.microsoft.com/microsoft-365/roadmap?filters=)

