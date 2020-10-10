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
ms.collection:
- M365-security-compliance
- m365-initiative-defender-office365
keywords: respuesta de incidente automatizada, investigación, corrección, protección contra amenazas
ms.date: 09/29/2020
description: Obtenga información general sobre las capacidades de investigación y respuesta automatizadas en Microsoft defender para Office 365
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 850291966c2f2da51782d8e70de23ff4f06d6136
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413967"
---
# <a name="an-overview-of-automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Información general sobre investigación y respuesta automatizada (AIR) en Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


A medida que se activen las alertas de seguridad, el equipo de operaciones de seguridad será el encargado de consultar esas alertas y tomar las medidas necesarias para proteger su organización. A veces, los equipos de operaciones de seguridad pueden sentirse abrumados por el volumen de alertas que se desencadenan. La funcionalidad de investigación y respuesta automatizada (AIR) de Microsoft defender para Office 365 puede ayudarle. 

AIR permite que el equipo de operaciones de seguridad funcione de forma más eficiente y eficaz. Las capacidades de AIR incluyen procesos de investigación automatizada en respuesta a amenazas bien conocidas que existen en la actualidad. Acciones de corrección adecuadas esperando la aprobación, lo que permite al equipo de operaciones de seguridad responder a amenazas detectadas. 

En este artículo se proporciona información general sobre AIR. Cuando esté listo para empezar a usar AIR, consulte [investigar y responder automáticamente a amenazas](office-365-air.md).

## <a name="at-a-high-level"></a>A un alto nivel

A medida que se activen las alertas, las guías de seguridad entrarán en vigor. En función de la situación, puede comenzar un [proceso de investigación automatizada](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) . Durante y después de una investigación automatizada, se recomiendan [las acciones de corrección](air-remediation-actions.md) . No se realizan acciones automáticamente en Microsoft defender para Office 365. El equipo de operaciones de seguridad revisa y, a continuación, [aprueba o rechaza cada acción de corrección](air-review-approve-pending-completed-actions.md). Cuando se aprueban o rechazan todas las acciones que siguen a la investigación, se completa la investigación. Se realiza el seguimiento y la visualización de todas estas actividades en el centro de seguridad 365 de Microsoft ( [https://security.microsoft.com](https://security.microsoft.com) ). (Para obtener más información, consulte [Ver detalles de una investigación](air-view-investigation-results.md#view-details-of-an-investigation)).

En las secciones siguientes se proporcionan más detalles sobre las alertas, las guías de seguridad y ejemplos de aire en funcionamiento.

## <a name="alerts"></a>Alertas

Las [alertas](../../compliance/alert-policies.md#viewing-alerts) representan desencadenadores de flujos de trabajo del equipo de operaciones de seguridad para respuesta ante incidentes. Establecer prioridades en el conjunto de alertas adecuadas para la investigación, a la vez que asegurarse de que no hay amenazas sin direcciones, supone un reto. Cuando las investigaciones en las alertas se realizan manualmente, los equipos de operaciones de seguridad deben buscar y correlacionar las entidades (como contenido, dispositivos y usuarios) en riesgo de amenazas. Estas tareas y flujos de trabajo pueden ser muy lentos y implican varias herramientas y sistemas. Con AIR, la investigación y la respuesta para eventos de seguridad se automatizan haciendo que las alertas de administración de amenazas y seguridad clave desencadenen las guías de respuesta de seguridad automáticamente. 

Actualmente, las alertas generadas a partir de los siguientes tipos de directivas de alerta se investigan automáticamente:  

- Se ha detectado un clic en una dirección URL potencialmente malintencionada
- Correo electrónico notificado por el usuario como phish`*`
- Mensajes de correo electrónico que contienen malware quitados después de la entrega`*`
- Mensajes de correo electrónico que contienen direcciones URL de phish quitadas después de la entrega`*`
- Patrones de envío de correo electrónico sospechosos detectados
- El usuario restringió el envío de correo electrónico
- El administrador ha activado la investigación manual del correo electrónico`*`

> [!NOTE]
> A las alertas marcadas con un asterisco ( `*` ) se les asigna una gravedad *informativa* en las respectivas directivas de alerta en el centro de seguridad de Microsoft 365, con notificaciones de correo electrónico desactivadas. Las notificaciones por correo electrónico se pueden activar a través de la configuración de la [Directiva de alerta](../../compliance/alert-policies.md#alert-policy-settings). 

Para ver las alertas, en el centro de seguridad & cumplimiento, elija **alertas**  >  **Ver alertas**. Seleccione una alerta para ver sus detalles y, desde allí, use el vínculo **Ver investigación** para ir a la [investigación](air-view-investigation-results.md#investigation-graph)correspondiente.  

> [!NOTE]
> Las alertas informativas están ocultas de forma predeterminada en la vista de alertas. Para verlos, cambie el filtrado de alertas para incluir alertas informativas.

Si su organización administra sus alertas de seguridad a través de un sistema de administración de alertas, un sistema de administración de servicios o un sistema de administración de eventos e información de seguridad (SIEM), puede enviar alertas a ese sistema mediante una notificación por correo electrónico o a través de la [API de actividad de administración 365 de Office](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). Las notificaciones de alerta de investigación a través del correo electrónico o la API incluyen vínculos para acceder a las alertas en el centro de seguridad de Microsoft 365, lo que permite que el administrador de seguridad asignado navegue rápidamente a la investigación.

![Alertas que vinculan a investigaciones](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>Guías de seguridad

Las guías de seguridad son directivas de back-end que están en el corazón de la automatización de Microsoft defender para Office 365 y protección contra amenazas de Microsoft. Las guías de seguridad que se proporcionan en AIR se basan en escenarios comunes de seguridad de todo el mundo y se desarrollan en función de los comentarios de los equipos de operaciones de seguridad. Una guía de seguridad se inicia automáticamente cuando se desencadenan alertas específicas dentro de la organización. Una vez que se activa la alerta, el sistema de investigación y respuesta automatizada ejecuta la guía asociada. La investigación avanza paso a paso por el análisis de la alerta basándose en la guía de la alerta en particular, examinando todos los metadatos asociados (incluidos los mensajes de correo electrónico, usuarios, asuntos, remitentes, etc.). Basándose en los resultados de la guía de investigación, AIR recomienda un conjunto de acciones que el equipo de seguridad de la organización puede llevar a cabo para controlar y mitigar la amenaza. 

Las guías de seguridad que recibirá con AIR están diseñadas para enfrentarse a las amenazas más frecuentes que las organizaciones detectan actualmente con el correo electrónico. Se basan en la información de las operaciones de seguridad y los equipos de respuesta ante incidentes, incluidas las personas que ayudan a defender a Microsoft y a los activos de nuestros clientes.

- Mensaje de phish notificado por el usuario
- URL-hacer clic en el cambio de veredicto
- Malware detectado después de la entrega (ZAP de malware)
- Phish detectado tras entrega tras entrega (ZAP de Phish)
- Usuario notificado como comprometido 
- Investigación manual de correo electrónico (desencadenado por el administrador desde malware, phish o todas las vistas de correo electrónico)

Se publicarán más guías y actualizaciones de la guía a medida que se completen. Visite el [mapa de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para ver lo que más está previsto y próximamente.

### <a name="playbooks-include-investigation-and-recommendations"></a>Las guías incluyen investigación y recomendaciones

En AIR, cada guía de seguridad incluye: 

- una investigación raíz de las entidades de un correo electrónico (como archivos, direcciones URL, destinatarios, direcciones IP, etc.)
- mayor búsqueda de mensajes de correo electrónico similares recibidos por la organización 
- pasos que hay que seguir para identificar y correlacionar otras posibles amenazas y 
- acciones recomendadas de corrección de amenazas.

Cada paso de alto nivel incluye una serie de subpasos que se ejecutan para proporcionar una respuesta profunda, detallada y exhaustiva a las amenazas.

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Ejemplo: un mensaje de phish notificado por el usuario inicia una guía de investigación

Supongamos que un usuario de su organización recibe un correo electrónico que piensa que es un intento de suplantación de identidad. El usuario, entrenado para informar de estos mensajes, usa el [complemento de mensajes de informe](enable-the-report-message-add-in.md) para enviarlo a Microsoft para su análisis. El envío también se envía a su sistema y es visible en el explorador en la vista **envíos** (antes denominada **"vista notificada por el usuario"** ). Además, el mensaje notificado por el usuario ahora desencadena una alerta informativa basada en el sistema, que inicia automáticamente la guía de la investigación.

Durante la fase de investigación raíz, se evalúan varios aspectos del correo electrónico. Estos aspectos incluyen:

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
- La señal se comparte con otras plataformas, como [Microsoft defender para el punto de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).
- Se determina si algún usuario ha hecho clic en cualquier vínculo malintencionado en mensajes de correo electrónico sospechosos.
- Se realiza una comprobación en Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) y Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) para ver si hay otros mensajes similares notificados por los usuarios.
- Se realiza una comprobación para ver si un usuario se ha puesto en peligro. Esta comprobación aprovecha las señales de Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)y [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlacionando las anomalías relacionadas con las actividades de los usuarios.

Durante la fase de caza, los riesgos y las amenazas se asignan a varios pasos de caza. 

La corrección es la fase final de la guía. Durante esta fase, se realizan pasos de corrección que se basan en las fases de investigación y de caza. 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Ejemplo: un administrador de seguridad desencadena una investigación desde el explorador de amenazas

Además de las investigaciones automatizadas que se desencadenan por una alerta, el equipo de operaciones de seguridad de la organización puede desencadenar una investigación automatizada desde una vista en el [Explorador de amenazas](threat-explorer.md).  Esta investigación también crea una alerta, de modo que los incidentes de Microsoft defender y las herramientas de SIEM externa puedan ver que se ha desencadenado esta investigación. 

Por ejemplo, supongamos que usa la vista de **malware** en el explorador. Mediante las pestañas debajo del gráfico, seleccione la pestaña **correo electrónico** . Si selecciona uno o más elementos de la lista, se activa el botón **+ acciones** . 

![Explorador con los mensajes seleccionados](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

Mediante el menú **acciones** , puede seleccionar la **investigación de desencadenadores**.

![Menú acciones para los mensajes seleccionados](../../media/explorer-malwareview-selectedemails-actions.jpg)

De forma similar a las guías activadas por una alerta, las investigaciones automáticas que se desencadenan desde una vista del explorador incluyen una investigación raíz, pasos para identificar y correlacionar amenazas y las acciones recomendadas para mitigar esas amenazas.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>Ejemplo: un equipo de operaciones de seguridad integra AIR con su SIEM mediante la API de actividad de administración 365 de Office

Las funcionalidades de AIR de Microsoft defender para Office 365 incluyen [informes & detalles](air-view-investigation-results.md) que los equipos de operaciones de seguridad pueden usar para supervisar y solucionar amenazas. Pero también puede integrar las capacidades de AIR con otras soluciones. Algunos ejemplos son un sistema de administración de eventos e información de seguridad (SIEM), un sistema de administración de casos o una solución de informes personalizada. Estos tipos de integraciones se pueden realizar mediante el uso de la [API de actividad de administración 365 de Office](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

Por ejemplo, recientemente, una organización estableció una forma de que su equipo de operaciones de seguridad vea las alertas de phish notificadas por el usuario que ya se procesaron por vía aérea. Su solución integra alertas relevantes con el servidor SIEM de la organización y su sistema de administración de casos. La solución reduce en gran medida el número de falsos positivos para que su equipo de operaciones de seguridad pueda centrar su tiempo y esfuerzo en amenazas reales. Para obtener más información sobre esta solución personalizada, vea [blog de la comunidad tecnológica: mejorar la efectividad de su SOC con Office 365 ATP y la API de administración de O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

## <a name="next-steps"></a>Pasos siguientes

- [Empezar a usar AIR](office-365-air.md)

- [Visite el plan de desarrollo de Microsoft 365 para ver lo que se ha planeado y lanzado pronto](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [Obtenga más información sobre las capacidades de investigación y respuesta automatizadas adicionales en Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide&preserve-view=true)
