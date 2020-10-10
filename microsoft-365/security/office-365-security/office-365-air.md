---
title: 'Investigación y respuesta automatizadas (AIR): introducción'
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 09/29/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
description: Empiece a usar las capacidades de investigación y respuesta automatizadas en Microsoft defender para Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: c2ce99a2a7033c7cdcf435e237b46438259f37e4
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412963"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-office-365"></a>Introducción al uso de investigación y respuesta automatizadas (AIR) en Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft defender para Office 365](office-365-atp.md) incluye capacidades de investigación y respuesta automáticas (Air) eficaces que pueden ahorrar tiempo y esfuerzo en el equipo de operaciones de seguridad. A medida que se activen las alertas, el equipo de operaciones de seguridad debe revisar, priorizar y responder a esas alertas. Mantener el volumen de las alertas entrantes puede ser abrumador. Automatizar parte de esto puede resultar útil. Con AIR, el equipo de operaciones de seguridad puede centrarse en las tareas de mayor prioridad sin perder la vista de las alertas que se activan.

En este artículo se incluyen los siguientes casos:
- El [flujo general](#the-overall-flow-of-air) de aire;
- [Cómo obtener aire](#how-to-get-air); y 
- Los [permisos necesarios](#required-permissions-to-use-air-capabilities) para configurar o usar las funcionalidades de Air. 

## <a name="the-overall-flow-of-air"></a>Flujo general de aire

En un nivel alto, se desencadena una alerta y una guía de seguridad inicia una investigación automatizada, lo que da como resultado conclusiones y recomendaciones. Este es el flujo de aire general, paso a paso:

1. Una investigación automatizada se inicia de una de las siguientes maneras:

   - Un evento de Office desencadena una [alerta](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) , que crea un incidente. Según el tipo de incidente, una guía de [seguridad](automated-investigation-response-office.md#security-playbooks) inicia una investigación automatizada. 

     --- o ---
   
   - Un analista de seguridad [inicia una investigación automatizada](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) mientras utiliza el [Explorador de amenazas](threat-explorer.md).

2. Mientras se ejecuta una investigación automatizada, recopila datos adicionales sobre el correo electrónico en cuestión y las entidades relacionadas con ese correo electrónico. Estas entidades pueden incluir archivos, direcciones URL y destinatarios.  El ámbito de la investigación puede aumentar a medida que se desencadenen alertas nuevas y relacionadas.

3. Durante y después de una investigación automatizada, [los detalles y los resultados](air-view-investigation-results.md) están disponibles para su visualización. Los resultados incluyen [acciones recomendadas](air-remediation-actions.md) que se pueden llevar a cabo para responder y corregir cualquier amenaza que se detectó. Además, hay disponible un registro de la [Guía](air-view-investigation-results.md#playbook-log) que realiza un seguimiento de la actividad de la investigación.

    Si su organización usa una solución de informes personalizada o una solución de terceros, puede [usar la API de actividad de administración de Office 365](air-custom-reporting.md) para ver información sobre las amenazas y las investigaciones automatizadas.

4. El equipo de operaciones de seguridad revisa los resultados de la [investigación y las recomendaciones](air-view-investigation-results.md)y [aprueba o rechaza acciones de corrección](air-review-approve-pending-completed-actions.md). 

    Como las acciones de corrección pendientes son aprobadas (o rechazadas), se completa la investigación automatizada.

> [!NOTE]
> En Office 365 ATP, no se realizan automáticamente acciones de corrección. Solo se realizan acciones de corrección tras obtener la aprobación del equipo de seguridad de su organización. 

Durante y después de un proceso de investigación automatizado, su equipo de seguridad puede hacer lo siguiente:

- [Ver los detalles de una alerta relacionada con una investigación](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [Ver los detalles de los resultados de una investigación](air-view-investigation-results.md#view-details-of-an-investigation)

- [Revisión y aprobación de acciones como resultado de una investigación](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Para obtener más información, consulte [how Air Works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="how-to-get-air"></a>Cómo obtener aire

Las funcionalidades de AIR se incluyen en [Microsoft defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2). Sin embargo, las [directivas deben estar configuradas](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) para que Air funcione como se esperaba. Además, asegúrese de revisar y configurar potencialmente [las directivas de alertas](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)de su organización. 

Microsoft 365 proporciona muchas directivas de alertas integradas que ayudan a identificar los permisos de administrador de Exchange, la actividad de malware, las amenazas potenciales externas y externas y los riesgos de control de la información. Varias de las [directivas de alerta predeterminadas](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) pueden desencadenar investigaciones automatizadas. Entre ellas se incluyen las siguientes:

- Se ha detectado un clic en una dirección URL potencialmente malintencionada

- Un usuario ha notificado un mensaje de correo electrónico como phish

- Los mensajes de correo electrónico que contienen malware se eliminan después de la entrega

- Los mensajes de correo electrónico que contienen direcciones URL de phish se eliminan después de la entrega

- Se detectan patrones de envío de correo sospechoso

- Se ha restringido el envío de correo electrónico a un usuario

[Obtenga más información sobre las alertas y el aire](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="required-permissions-to-use-air-capabilities"></a>Permisos necesarios para usar capacidades de AIR

Los permisos se conceden a través de determinadas funciones, como las que se describen en la tabla siguiente: 

|Task |Roles necesarios |
|--|--|
|Para configurar las características de AIR |Una de las siguientes funciones: <br/>-Administrador global<br/>-Administrador de seguridad <br/>Estos roles se pueden asignar en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o en el [centro de seguridad & cumplimiento](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|Para aprobar o rechazar las acciones recomendadas|Una de las siguientes funciones, asignada en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o en el [centro de seguridad & cumplimiento](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):<br/>-Administrador global <br/>-Administrador de seguridad<br/>-Lector de seguridad <br/>--- y ---<br/>-Búsqueda y depuración (este rol solo se asigna en el [centro de seguridad & cumplimiento](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Es posible que tenga que crear un nuevo grupo de funciones y agregar el rol de búsqueda y depuración al nuevo grupo de roles.

Las licencias [de Microsoft defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) deben asignarse a:
- Administradores de seguridad (incluidos los administradores globales)
- El equipo de operaciones de seguridad de la organización (incluidos los lectores de seguridad y los que tienen el rol de búsqueda y depuración)
- Usuarios finales

Además, [las directivas de Microsoft defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) deben definirse y aplicarse para que la protección esté en su ubicación.

## <a name="next-steps"></a>Pasos siguientes

- [Ver los detalles y los resultados de una investigación automatizada](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [Revisar y aprobar acciones pendientes](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a>Artículos relacionados

- [Investigación y corrección automáticas en Microsoft defender para el punto de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Investigación y respuesta automatizadas en Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
