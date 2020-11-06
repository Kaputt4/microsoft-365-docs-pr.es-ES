---
title: Introducción a la investigación y la respuesta automatizadas en Microsoft defender para Office 365
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/05/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Empiece a usar las capacidades de investigación y respuesta automatizadas en Microsoft defender para Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 5796cdf21f9dd12c35a2f84422f03503433755b0
ms.sourcegitcommit: 24826e1b61e7aace12fc9e8ae84ae3e760658b50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2020
ms.locfileid: "48931941"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Introducción al uso de investigación y respuesta automatizadas (AIR) en Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft defender para Office 365](office-365-atp.md) incluye capacidades de investigación y respuesta automáticas (Air) eficaces que pueden ahorrar tiempo y esfuerzo en el equipo de operaciones de seguridad. A medida que se activen las alertas, el equipo de operaciones de seguridad debe revisar, priorizar y responder a esas alertas. Mantener el volumen de las alertas entrantes puede ser abrumador. Automatizar algunas de estas tareas puede resultar útil. 

AIR permite que el equipo de operaciones de seguridad funcione de forma más eficiente y eficaz. Las capacidades de AIR incluyen procesos de investigación automatizada en respuesta a amenazas bien conocidas que existen en la actualidad. Acciones de corrección adecuadas esperando la aprobación, lo que permite que el equipo de operaciones de seguridad responda con eficacia a las amenazas detectadas. Con AIR, el equipo de operaciones de seguridad puede centrarse en las tareas de mayor prioridad sin perder la vista de las alertas importantes que se desencadenan.

Este artículo describe:
- El [flujo general de aire](#the-overall-flow-of-air);
- [Cómo obtener aire](#how-to-get-air); y 
- Los [permisos necesarios](#required-permissions-to-use-air-capabilities) para configurar o usar las funcionalidades de Air. 

En este artículo también se incluyen [los pasos siguientes](#next-steps)y recursos para obtener más información.

## <a name="the-overall-flow-of-air"></a>Flujo general de aire

Se desencadena una alerta y una guía de seguridad inicia una investigación automatizada, lo que da como resultado conclusiones y acciones recomendadas. Este es el flujo de aire general, paso a paso:

1. Una investigación automatizada se inicia de una de las siguientes maneras:

   - Una [alerta se activa](#which-alert-policies-trigger-automated-investigations) por algo sospechoso en el correo electrónico (como un mensaje, datos adjuntos, una dirección URL o una cuenta de usuario en peligro). Se crea un incidente y se inicia una investigación automatizada. 

     --- o ---
   
   - Un analista de seguridad [inicia una investigación automatizada](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) mientras utiliza el [Explorador de amenazas](threat-explorer.md).

2. Mientras se ejecuta una investigación automatizada, recopila datos adicionales sobre el correo electrónico en cuestión y las entidades relacionadas con ese correo electrónico. Estas entidades pueden incluir archivos, direcciones URL y destinatarios.  El ámbito de la investigación puede aumentar a medida que se desencadenen alertas nuevas y relacionadas.

3. Durante y después de una investigación automatizada, [los detalles y los resultados](air-view-investigation-results.md) están disponibles para su visualización. Los resultados incluyen [acciones recomendadas](air-remediation-actions.md) que se pueden realizar para responder a cualquier amenaza que se detectó y solucionarlo. Además, hay disponible un registro de la [Guía](air-view-investigation-results.md#playbook-log) que realiza un seguimiento de la actividad de la investigación.


4. El equipo de operaciones de seguridad revisa los resultados de la [investigación y las recomendaciones](air-view-investigation-results.md)y [aprueba o rechaza acciones de corrección](air-review-approve-pending-completed-actions.md). 

5. Como las acciones de corrección pendientes son aprobadas (o rechazadas), se completa la investigación automatizada.

> [!IMPORTANT]
> En Microsoft defender para Office 365, no se realiza ninguna acción de corrección automáticamente. Solo se realizan acciones de corrección tras obtener la aprobación del equipo de seguridad de su organización. 
>
> Las funcionalidades de AIR guardan el tiempo del equipo de operaciones de seguridad mediante la identificación de acciones de corrección y la entrega de los detalles necesarios para tomar una decisión informada.

Durante y después de cada investigación automatizada, el equipo de operaciones de seguridad puede:

- [Ver los detalles de una alerta relacionada con una investigación](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [Ver los detalles de los resultados de una investigación](air-view-investigation-results.md#view-details-of-an-investigation)

- [Revisión y aprobación de acciones como resultado de una investigación](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Para obtener información más detallada, consulte [how Air Operations](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)(en inglés).

## <a name="how-to-get-air"></a>Cómo obtener aire

Las funcionalidades de AIR se incluyen en [Microsoft defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2), siempre que se configuran las directivas y las alertas. Si desea obtener ayuda, siga las instrucciones de protección [contra amenazas](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) para configurar o configurar las siguientes opciones de protección: 

1. [Registro de auditoría](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (debe estar activado)

2. [Directivas antimalware](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-1---anti-malware-protection)

3. [Protección contra la suplantación de identidad](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-2---anti-phishing-protection)
   
4. [Protección contra correo electrónico no deseado](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-3---anti-spam-protection).
   
5. [Vínculos seguros y datos adjuntos seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365).
   
6. [Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on).
   
7. [Purga automática de cero horas para el correo electrónico](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?zero-hour-auto-purge-for-email-in-eop).

Además, asegúrese de revisar las [directivas de alertas de la organización](https://docs.microsoft.com/microsoft-365/compliance/alert-policies), especialmente las [directivas predeterminadas de la categoría administración de amenazas](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies). 

## <a name="which-alert-policies-trigger-automated-investigations"></a>¿Qué directivas de alerta desencadenan investigaciones automatizadas?

Microsoft 365 proporciona muchas directivas de alertas integradas que ayudan a identificar los permisos de administrador de Exchange, la actividad de malware, las amenazas potenciales externas y externas y los riesgos de control de la información. Varias de las [directivas de alerta predeterminadas](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) pueden desencadenar investigaciones automatizadas. En la tabla siguiente se describen las alertas que desencadenan investigaciones automatizadas, su gravedad en el centro de seguridad 365 de Microsoft y cómo se generan:


|Alerta  |Severity |Cómo se genera la alerta  |
|---------|---------|--------|
|Se ha detectado un clic en una dirección URL potencialmente malintencionada     |**Alto** |Esta alerta se genera cuando se produce alguna de las siguientes situaciones:<br/> -Un usuario protegido por [vínculos seguros](atp-safe-links.md) en su organización hace clic en un vínculo malintencionado <br/>-Los cambios de veredicto para direcciones URL se identifican por Microsoft defender para Office 365 <br/>-Los usuarios reemplazan las páginas de advertencia de vínculos seguros (según la [Directiva de vínculos seguros](set-up-atp-safe-links-policies.md)de la organización).<br/><br/> Para obtener más información acerca de los eventos que desencadenan esta alerta, consulte [configurar directivas de vínculos seguros](set-up-atp-safe-links-policies.md).         |
|Un usuario ha notificado un mensaje de correo electrónico como malware o phish |**Informativo**    |Esta alerta se genera cuando los usuarios de la organización notifican mensajes como correo electrónico de suplantación de identidad mediante el [complemento de mensajes de informe](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in). |
|Los mensajes de correo electrónico que contienen malware se eliminan después de la entrega |**Informativo**     |Esta alerta se genera cuando los mensajes de correo electrónico que contienen malware se entregan a los buzones de la organización. Si se produce este evento, Microsoft quita los mensajes infectados de los buzones de correo de Exchange online mediante la [purga automática de cero horas](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge).   |
|Los mensajes de correo electrónico que contienen direcciones URL de phish se eliminan después de la entrega     |**Informativo**        |Esta alerta se genera cuando se entregan mensajes que contienen phish a los buzones de la organización. Si se produce este evento, Microsoft quita los mensajes infectados de los buzones de correo de Exchange online mediante la [purga automática de cero horas](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge).  |
|Se detectan patrones de envío de correo sospechoso     |**Medio**         |Esta alerta se genera cuando alguien de su organización ha enviado correo electrónico sospechoso y está en riesgo de que no pueda enviar correo electrónico. Se trata de una advertencia temprana para el comportamiento que podría indicar que la cuenta está en peligro, pero que no es lo suficientemente grave como para restringir al usuario.<br/><br/> Aunque es raro, una alerta generada por esta Directiva puede ser una anomalía. Sin embargo, es una buena idea [comprobar si la cuenta de usuario está comprometida](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).  |
|Se ha restringido el envío de correo electrónico a un usuario    |**Alto** |Esta alerta se genera cuando una persona de su organización tiene restringido el envío de correo saliente. Normalmente, esto se produce cuando una [cuenta de correo electrónico se ve comprometida](responding-to-a-compromised-email-account.md).<br/><br/>Para obtener más información acerca de los usuarios restringidos, consulte [quitar usuarios bloqueados del portal de usuarios restringidos en Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam).    |

> [!TIP]
> Para obtener más información acerca de las directivas de alerta o editar la configuración predeterminada, consulte [Alert policies en el centro de cumplimiento de Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).

## <a name="required-permissions-to-use-air-capabilities"></a>Permisos necesarios para usar capacidades de AIR

Los permisos se conceden a través de determinadas funciones, como las que se describen en la tabla siguiente: 

|Task |Roles necesarios |
|:--|:--|
|Configurar características de AIR |Una de las siguientes funciones: <br/>-Administrador global<br/>-Administrador de seguridad <br/>Estos roles se pueden asignar en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o en el [centro de seguridad & cumplimiento](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|Iniciar una investigación automatizada <br/><br/>--- o ---<br/><br/>Aprobar o rechazar acciones recomendadas|Una de las siguientes funciones, asignada en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o en el [centro de seguridad & cumplimiento](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):<br/>-Administrador global <br/>-Administrador de seguridad<br/>-Lector de seguridad <br/>--- y ---<br/>-Búsqueda y depuración (este rol solo se asigna en el [centro de seguridad & cumplimiento](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Es posible que tenga que crear un nuevo grupo de funciones y agregar el rol de búsqueda y depuración al nuevo grupo de roles. |

## <a name="required-licenses"></a>Licencias necesarias

Las licencias [de Microsoft defender para Office 365 plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#microsoft-defender-for-office-365-plan-1-and-plan-2) se deben asignar a:
- Administradores de seguridad (incluidos los administradores globales)
- El equipo de operaciones de seguridad de la organización (incluidos los lectores de seguridad y los que tienen el rol de **búsqueda y depuración** )
- Usuarios finales


## <a name="next-steps"></a>Pasos siguientes

- [Ver los detalles y los resultados de una investigación automatizada](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [Revisar y aprobar acciones pendientes](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="see-also"></a>Vea también

- [Investigación y corrección automáticas en Microsoft defender para el punto de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Investigación y respuesta automatizadas en Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
