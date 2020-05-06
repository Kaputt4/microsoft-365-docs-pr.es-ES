---
title: Introducción a la investigación y respuesta automatizada (AIR)
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
ms.custom: air - seo-marvel-mar2020
ms.openlocfilehash: 3f8aa761207be61f78eb5f9b5140439c86455bf3
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035621"
---
# <a name="an-overview-of-automated-investigation-and-response-air-in-microsoft-365"></a>Información general sobre la investigación y la respuesta automatizadas (AIR) en Microsoft 365

A medida que se activen las alertas de seguridad, el equipo de operaciones de seguridad será el encargado de consultar esas alertas y tomar las medidas necesarias para proteger su organización. A veces, los equipos de operaciones de seguridad pueden sentirse abrumados por el volumen de alertas que se desencadenan. Las capacidades de investigación y respuesta automatizadas (AIR) pueden ayudar. AIR permite que el equipo de operaciones de seguridad funcione de forma más eficiente y eficaz. Las capacidades de AIR incluyen procesos de investigación automatizada en respuesta a amenazas bien conocidas que existen en la actualidad. Acciones de corrección adecuadas esperando la aprobación, lo que permite al equipo de operaciones de seguridad responder a amenazas detectadas. 

En este artículo se proporciona información general sobre AIR. Cuando esté listo para empezar a usar AIR, consulte [investigar y responder automáticamente a amenazas](office-365-air.md).

## <a name="at-a-high-level"></a>A un alto nivel

A medida que se activen las alertas, las guías de seguridad entrarán en vigor. En función de la situación, puede comenzar un [proceso de investigación automatizada](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) . Durante y después de una investigación automatizada, se recomiendan [las acciones de corrección](air-remediation-actions.md) . No se realiza automáticamente ninguna acción en la protección contra amenazas avanzada de Office 365. El equipo de operaciones de seguridad revisa y, a continuación, [aprueba o rechaza cada acción de corrección](air-review-approve-pending-completed-actions.md)y, cuando se lleva a cabo, finaliza cada investigación. Todas estas actividades se controlan y se pueden ver en el centro de seguridad & cumplimiento (vea [Ver detalles de una investigación](air-view-investigation-results.md#view-details-of-an-investigation)).

En las secciones siguientes se proporcionan más detalles sobre las alertas, las guías de seguridad y ejemplos de aire en funcionamiento.

## <a name="alerts"></a>Alertas

Las [alertas](../../compliance/alert-policies.md#viewing-alerts) representan desencadenadores de flujos de trabajo del equipo de operaciones de seguridad para respuesta ante incidentes. Establecer prioridades en el conjunto de alertas adecuadas para la investigación, a la vez que asegurarse de que no hay amenazas sin direcciones, supone un reto. Cuando las investigaciones en las alertas se realizan manualmente, los equipos de operaciones de seguridad deben buscar y correlacionar las entidades (como contenido, dispositivos y usuarios) en riesgo de amenazas. Estas tareas y flujos de trabajo pueden ser muy lentos y implican varias herramientas y sistemas. Con AIR, la investigación y la respuesta para eventos de seguridad se automatizan haciendo que las alertas de administración de amenazas y seguridad clave desencadenen las guías de respuesta de seguridad automáticamente. 

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

Si su organización administra sus alertas de seguridad a través de un sistema de administración de alertas, un sistema de administración de servicios o un sistema de administración de eventos e información de seguridad (SIEM), puede enviar alertas a ese sistema mediante una notificación por correo electrónico o a través de la [API de actividad de administración 365 de Office](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). Las notificaciones de alerta de investigación a través de correo electrónico o API incluyen vínculos para acceder a las alertas en el centro de seguridad & cumplimiento, lo que permite que el administrador de seguridad asignado navegue rápidamente a la investigación.

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

Supongamos que un usuario de su organización recibe un correo electrónico que piensa que es un intento de suplantación de identidad. El usuario, entrenado para informar de estos mensajes, usa el [complemento de mensajes de informe](enable-the-report-message-add-in.md) para enviarlo a Microsoft para su análisis. El envío también se envía a su sistema y es visible en el explorador en la vista **envíos** (antes denominada **"vista notificada por el usuario"** ). Además, el mensaje notificado por el usuario ahora desencadena una alerta informativa basada en el sistema, que inicia automáticamente la guía de la investigación.

Durante la fase de investigación raíz, se evalúan varios aspectos del correo electrónico. Entre ellas se incluyen:
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
- Se realiza una comprobación en Exchange Online Protection ([EOP](exchange-online-protection-eop.md)) y Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) para ver si hay otros mensajes similares notificados por los usuarios.
- Se realiza una comprobación para ver si un usuario se ha puesto en peligro. Esta comprobación aprovecha las señales de Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)y [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlacionando las anomalías relacionadas con las actividades de los usuarios. 

Durante la fase de caza, los riesgos y las amenazas se asignan a varios pasos de caza. 

La corrección es la fase final de la guía. Durante esta fase, se realizan pasos de corrección que se basan en las fases de investigación y de caza. 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Ejemplo: un administrador de seguridad desencadena una investigación desde el explorador de amenazas

Además de las investigaciones automáticas desencadenadas por una alerta, el equipo de operaciones de seguridad de la organización puede desencadenar una investigación automática desde una vista del [Explorador de amenazas](threat-explorer.md).

Por ejemplo, supongamos que usa la vista de **malware** en el explorador de amenazas. Mediante las pestañas debajo del gráfico, seleccione la pestaña **correo electrónico** . Si selecciona uno o más elementos de la lista, se activa el botón **+ acciones** . 

:::image type="content" source="../../media/Explorer-Malware-Email-ActionsInvestigate.png" alt-text="Explorador con los mensajes seleccionados":::

Mediante el menú **acciones** , puede seleccionar la **investigación de desencadenadores**.

:::image type="content" source="../../media/explorer-malwareview-selectedemails-actions.jpg" alt-text="Menú acciones para los mensajes seleccionados":::

De forma similar a las guías activadas por una alerta, las investigaciones automáticas que se desencadenan desde una vista del explorador incluyen una investigación raíz, pasos para identificar y correlacionar amenazas y las acciones recomendadas para mitigar esas amenazas.

## <a name="next-steps"></a>Pasos siguientes

- [Empezar a usar AIR](office-365-air.md)

- [Visite el plan de desarrollo de Microsoft 365 para ver lo que estará próximamente y que se implementará](https://www.microsoft.com/microsoft-365/roadmap?filters=)

