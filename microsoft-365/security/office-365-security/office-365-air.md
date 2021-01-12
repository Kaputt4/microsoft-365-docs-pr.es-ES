---
title: Investigación y respuesta automatizadas en Microsoft Defender para Office 365
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzada, amenaza, protección
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
- m365initiative-defender-office365
description: Introducción al uso de capacidades automatizadas de investigación y respuesta en Microsoft Defender para Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 6ccefb5c435f08fcef4dcc872af676fba70668ee
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794549"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Investigación y respuesta automatizada (AIR) en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft Defender para Office 365](office-365-atp.md) incluye potentes capacidades de investigación y respuesta automatizadas (AIR) que pueden ahorrar tiempo y esfuerzo al equipo de operaciones de seguridad. A medida que se desencadenan las alertas, el equipo de operaciones de seguridad debe revisar, priorizar y responder a dichas alertas. Mantenerse al día con el volumen de alertas entrantes puede ser abrumador. Automatizar algunas de estas tareas puede ser de ayuda.

AIR permite que el equipo de operaciones de seguridad funcione de forma más eficaz y eficaz. Las capacidades de AIR incluyen procesos de investigación automatizados en respuesta a amenazas conocidas que existen actualmente. Las acciones de corrección apropiadas esperan la aprobación, lo que permite al equipo de operaciones de seguridad responder eficazmente a las amenazas detectadas. Con AIR, el equipo de operaciones de seguridad puede centrarse en tareas de mayor prioridad sin perder de vista las alertas importantes que se desencadenan.

Este artículo describe:

- El [flujo general de AIR;](#the-overall-flow-of-air)
- [Cómo obtener AIR;](#how-to-get-air) y
- Los [permisos necesarios para](#required-permissions-to-use-air-capabilities) configurar o usar las funcionalidades de AIR.

En este artículo también [se incluyen los siguientes pasos](#next-steps)y recursos para obtener más información.

## <a name="the-overall-flow-of-air"></a>Flujo general de AIR

Se desencadena una alerta y un libro de estrategias de seguridad inicia una investigación automatizada, lo que da como resultado resultados y acciones recomendadas. Este es el flujo general de AIR, paso a paso:

1. Una investigación automatizada se inicia de una de las siguientes maneras:

   - Una [alerta se desencadena por](#which-alert-policies-trigger-automated-investigations) un mensaje sospechoso en el correo electrónico (como un mensaje, datos adjuntos, dirección URL o una cuenta de usuario comprometida). Se crea un incidente y comienza una investigación automatizada.

     --- o ---

   - Un analista de [seguridad inicia una investigación automatizada](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) mientras usa el Explorador de [amenazas.](threat-explorer.md)

2. Mientras se ejecuta una investigación automatizada, recopila datos adicionales sobre el correo electrónico en cuestión y las entidades relacionadas con ese correo electrónico. Estas entidades pueden incluir archivos, direcciones URL y destinatarios.  El ámbito de la investigación puede aumentar a medida que se desencadenan alertas nuevas y relacionadas.

3. Durante y después de una investigación automatizada, [los detalles y los resultados](air-view-investigation-results.md) están disponibles para verlos. Los [resultados incluyen acciones recomendadas](air-remediation-actions.md) que se pueden realizar para responder y corregir las amenazas encontradas. Además, hay disponible un [registro de playbook](air-view-investigation-results.md#playbook-log) que realiza un seguimiento de toda la actividad de investigación.

4. El equipo de operaciones de seguridad revisa los [resultados de la](air-view-investigation-results.md)investigación y las recomendaciones, y [aprueba o rechaza las acciones de corrección.](air-review-approve-pending-completed-actions.md)

5. A medida que se aprueban (o rechazan) las acciones correctivas pendientes, se completa la investigación automatizada.

> [!IMPORTANT]
> En Microsoft Defender para Office 365, no se realiza ninguna acción de corrección automáticamente. Solo se realizan acciones de corrección tras obtener la aprobación del equipo de seguridad de su organización.
>
> Las capacidades de AIR ahorran tiempo al equipo de operaciones de seguridad al identificar acciones correctivas y proporcionar los detalles necesarios para tomar una decisión fundamentada.

Durante y después de cada investigación automatizada, el equipo de operaciones de seguridad puede:

- [Ver detalles sobre una alerta relacionada con una investigación](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [Ver los detalles de los resultados de una investigación](air-view-investigation-results.md#view-details-of-an-investigation)

- [Revisar y aprobar acciones como resultado de una investigación](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Para obtener información general más detallada, consulte [Cómo funciona AIR.](automated-investigation-response-office.md)

## <a name="how-to-get-air"></a>Cómo obtener AIR

Las funcionalidades de AIR se incluyen [en Microsoft Defender para Office 365,](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)siempre que se configuren las directivas y las alertas. Si desea obtener ayuda con esto, [](protect-against-threats.md) siga las instrucciones de Protección contra amenazas para configurar o configurar las siguientes opciones de protección:

1. [Registro de auditoría](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (debe estar activado)

2. [Directivas antimalware](protect-against-threats.md#part-1---anti-malware-protection)

3. [Protección antiphishing](protect-against-threats.md#part-2---anti-phishing-protection)

4. [Protección contra correo no deseado.](protect-against-threats.md#part-3---anti-spam-protection)

5. [Vínculos seguros y datos adjuntos seguros.](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)

6. [Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams.](protect-against-threats.md#part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)

7. [Purga automática de cero horas para el correo electrónico.](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop)

Además, asegúrese de revisar [las](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)directivas de alerta de su organización, especialmente las directivas predeterminadas en la categoría de administración [de amenazas.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies)

## <a name="which-alert-policies-trigger-automated-investigations"></a>¿Qué directivas de alerta desencadenan investigaciones automatizadas?

Microsoft 365 proporciona muchas directivas de alerta integradas que ayudan a identificar el abuso de permisos de administrador de Exchange, la actividad de malware, las posibles amenazas internas y externas, y los riesgos de gobierno de la información. Varias de las [directivas de alerta predeterminadas](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) pueden desencadenar investigaciones automatizadas. En la siguiente tabla se describen las alertas que desencadenan investigaciones automatizadas, su gravedad en el Centro de seguridad de Microsoft 365 y cómo se generan:

|Alerta|Severity|Cómo se genera la alerta|
|---|---|---|
|Se detectó un clic de dirección URL potencialmente malintencionado|**Alto**|Esta alerta se genera cuando se produce cualquiera de las siguientes situaciones: <ul><li>Un usuario protegido por [vínculos seguros](atp-safe-links.md) de su organización hace clic en un vínculo malintencionado</li><li>Microsoft Defender identifica los cambios de veredicto de las direcciones URL para Office 365</li><li>Los usuarios invalidan las páginas de advertencia de Vínculos seguros (en función de la directiva de [vínculos seguros de su organización).](set-up-atp-safe-links-policies.md)</li></ul> <p> Para obtener más información sobre los eventos que desencadenan esta alerta, vea [Configurar directivas de vínculos seguros.](set-up-atp-safe-links-policies.md)|
|Un usuario notifica un mensaje de correo electrónico como malware o phishing|**Informativo**|Esta alerta se genera cuando los usuarios de su organización informan de mensajes como correo electrónico de suplantación de identidad mediante el [complemento Mensaje de informe.](enable-the-report-message-add-in.md)|
|Los mensajes de correo electrónico que contienen malware se eliminan después de la entrega|**Informativo**|Esta alerta se genera cuando los mensajes de correo electrónico que contienen malware se entregan a los buzones de la organización. Si se produce este evento, Microsoft quita los mensajes infectados de los buzones de Exchange Online mediante purga automática [de cero horas.](zero-hour-auto-purge.md)|
|Los mensajes de correo electrónico que contienen direcciones URL de suplantación de identidad se quitan después de la entrega|**Informativo**|Esta alerta se genera cuando los mensajes que contienen suplantación de identidad se entregan a los buzones de la organización. Si se produce este evento, Microsoft quita los mensajes infectados de los buzones de Exchange Online mediante la purga automática [de hora cero.](zero-hour-auto-purge.md)|
|Se detectan patrones sospechosos de envío de correo electrónico|**Medio**|Esta alerta se genera cuando alguien de su organización ha enviado correo electrónico sospechoso y corre el riesgo de que se le restringa el envío de correo electrónico. Se trata de una advertencia anticipada para el comportamiento que podría indicar que la cuenta está en peligro, pero no lo suficientemente grave como para restringir al usuario. <p> Aunque es raro, una alerta generada por esta directiva puede ser una anomalía. Sin embargo, es una buena idea comprobar [si la cuenta de usuario está en peligro.](responding-to-a-compromised-email-account.md)|
|Un usuario tiene restricciones para enviar correo electrónico|**Alto**|Esta alerta se genera cuando alguien de su organización tiene restricciones para enviar correo saliente. Esto suele ocurrir cuando una [cuenta de correo electrónico está en peligro.](responding-to-a-compromised-email-account.md) <p> Para obtener más información acerca de los usuarios restringidos, vea Quitar usuarios bloqueados del portal de usuarios restringidos [en Microsoft 365.](removing-user-from-restricted-users-portal-after-spam.md)|
|

> [!TIP]
> Para obtener más información sobre las directivas de alerta o editar la configuración predeterminada, consulte Directivas de alerta en el Centro de cumplimiento de [Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)

## <a name="required-permissions-to-use-air-capabilities"></a>Permisos necesarios para usar las funcionalidades de AIR

Los permisos se conceden a través de determinados roles, como los que se describen en la tabla siguiente:

|Tarea|Roles requeridos|
|---|---|
|Configurar las características de AIR|Uno de los siguientes roles: <ul><li>Administrador global</li><li>Administrador de seguridad</li></ul> <p> Estos roles se pueden asignar en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o en el Centro de & [cumplimiento.](permissions-in-the-security-and-compliance-center.md)|
|Iniciar una investigación automatizada <p> --- o --- <p> Aprobar o rechazar las acciones recomendadas|Uno de los siguientes roles, asignados en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o en el Centro de & [cumplimiento:](permissions-in-the-security-and-compliance-center.md) <ul><li>Administrador global</li><li>Administrador de seguridad</li><li>Lector de seguridad <br> --- y --- </li><li>Búsqueda y depuración (este rol solo se asigna en el Centro de & [cumplimiento.](permissions-in-the-security-and-compliance-center.md) Es posible que tenga que crear un nuevo grupo de roles allí y agregar el rol Buscar y purgar a ese nuevo grupo de roles.</li></ul>|
|

## <a name="required-licenses"></a>Licencias necesarias

[Las licencias de Microsoft Defender para Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) deben asignarse a:

- Administradores de seguridad (incluidos los administradores globales)
- El equipo de operaciones de seguridad de la organización (incluidos los lectores de seguridad y los que tienen el rol **Desa** cabo de búsqueda y depuración)
- Usuarios finales

## <a name="next-steps"></a>Pasos siguientes

- [Ver detalles y resultados de una investigación automatizada](air-view-investigation-results.md#view-details-of-an-investigation)

- [Revisar y aprobar acciones pendientes](air-remediation-actions.md)

## <a name="see-also"></a>Vea también

- [Investigación y corrección automatizadas en Microsoft Defender para endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Investigación y respuesta automatizadas en Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
