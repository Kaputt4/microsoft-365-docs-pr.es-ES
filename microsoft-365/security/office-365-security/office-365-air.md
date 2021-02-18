---
title: Investigación y respuesta automatizadas en Microsoft Defender para Office 365
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 01/29/2021
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
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b2e359f193f3c8b0502a1995b8e9d515eb03a983
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287694"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Investigación y respuesta automatizada (AIR) en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[Microsoft Defender para Office 365](office-365-atp.md) incluye potentes capacidades de investigación y respuesta automatizadas (AIR) que pueden ahorrar tiempo y esfuerzo al equipo de operaciones de seguridad. A medida que se desencadenan las alertas, el equipo de operaciones de seguridad debe revisar, priorizar y responder a dichas alertas. Mantenerse al día con el volumen de alertas entrantes puede ser abrumador. Automatizar algunas de estas tareas puede ser de ayuda.

AIR permite que el equipo de operaciones de seguridad funcione de forma más eficaz y eficaz. Las capacidades de AIR incluyen procesos de investigación automatizados en respuesta a amenazas conocidas que existen actualmente. Las acciones de corrección apropiadas esperan la aprobación, lo que permite al equipo de operaciones de seguridad responder eficazmente a las amenazas detectadas. Con AIR, el equipo de operaciones de seguridad puede centrarse en tareas de mayor prioridad sin perder de vista las alertas importantes que se desencadenan.

Este artículo describe:

- El [flujo general de AIR;](#the-overall-flow-of-air)
- [Cómo obtener AIR;](#how-to-get-air) y
- Los [permisos necesarios para](#required-permissions-to-use-air-capabilities) configurar o usar las funcionalidades de AIR.
- Cambios que estarán disponibles próximamente en el centro de seguridad

En este artículo también [se incluyen los siguientes pasos](#next-steps)y recursos para obtener más información.

## <a name="the-overall-flow-of-air"></a>Flujo general de AIR

Se desencadena una alerta y un libro de estrategias de seguridad inicia una investigación automatizada, lo que da como resultado resultados y acciones recomendadas. Este es el flujo general de AIR, paso a paso:

1. Una investigación automatizada se inicia de una de las siguientes maneras:
   - Una [alerta se desencadena por](#which-alert-policies-trigger-automated-investigations) un mensaje sospechoso en el correo electrónico (como un mensaje, datos adjuntos, dirección URL o una cuenta de usuario comprometida). Se crea un incidente y comienza una investigación automatizada; o
   - Un analista de [seguridad inicia una investigación automatizada](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) mientras usa el Explorador de [amenazas.](threat-explorer.md)
2. Mientras se ejecuta una investigación automatizada, recopila datos sobre el correo electrónico en cuestión y las entidades relacionadas con ese correo electrónico. Estas entidades pueden incluir archivos, direcciones URL y destinatarios. El ámbito de la investigación puede aumentar a medida que se desencadenan alertas nuevas y relacionadas.
3. Durante y después de una investigación automatizada, [los detalles y los resultados](air-view-investigation-results.md) están disponibles para ver. Los [resultados incluyen acciones recomendadas](air-remediation-actions.md) que se pueden realizar para responder y corregir las amenazas encontradas.
4. El equipo de operaciones de seguridad revisa los [resultados de la](air-view-investigation-results.md)investigación y las recomendaciones, y [aprueba o rechaza las acciones de corrección.](air-review-approve-pending-completed-actions.md)
5. A medida que se aprueban (o rechazan) las acciones correctivas pendientes, se completa la investigación automatizada.

En Microsoft Defender para Office 365, no se realiza ninguna acción de corrección automáticamente. Solo se realizan acciones de corrección tras obtener la aprobación del equipo de seguridad de su organización. Las capacidades de AIR ahorran tiempo al equipo de operaciones de seguridad al identificar acciones correctivas y proporcionar los detalles necesarios para tomar una decisión fundamentada.

Durante y después de cada investigación automatizada, el equipo de operaciones de seguridad puede:

- [Ver detalles sobre una alerta relacionada con una investigación](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [Ver los detalles de los resultados de una investigación](air-view-investigation-results.md#view-details-of-an-investigation)
- [Revisar y aprobar acciones como resultado de una investigación](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Para obtener información general más detallada, consulte [Cómo funciona AIR.](automated-investigation-response-office.md)

## <a name="how-to-get-air"></a>Cómo obtener AIR

Las funcionalidades de AIR se incluyen [en Microsoft Defender para Office 365,](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)siempre que se configuren las directivas y las alertas. ¿Necesita ayuda? Siga las instrucciones de [Protección contra amenazas](protect-against-threats.md) para configurar o configurar las siguientes opciones de protección:

- [Registro de auditoría](../../compliance/turn-audit-log-search-on-or-off.md) (debe estar activado)
- [Directivas antimalware](protect-against-threats.md#part-1---anti-malware-protection)
- [Protección antiphishing](protect-against-threats.md#part-2---anti-phishing-protection)
- [Protección contra correo no deseado](protect-against-threats.md#part-3---anti-spam-protection)
- [Vínculos seguros y datos adjuntos seguros](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)
- [Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](protect-against-threats.md#part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)
- [Purga automática de cero horas para el correo electrónico.](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop)

Además, asegúrese de revisar [las](../../compliance/alert-policies.md)directivas de alerta de su organización, especialmente las directivas predeterminadas en la categoría de administración [de amenazas.](../../compliance/alert-policies.md#default-alert-policies)

## <a name="which-alert-policies-trigger-automated-investigations"></a>¿Qué directivas de alerta desencadenan investigaciones automatizadas?

Microsoft 365 proporciona muchas directivas de alerta integradas que ayudan a identificar el abuso de permisos de administrador de Exchange, la actividad de malware, las posibles amenazas internas y externas, y los riesgos de gobierno de la información. Varias de las [directivas de alerta predeterminadas](../../compliance/alert-policies.md#default-alert-policies) pueden desencadenar investigaciones automatizadas. En la siguiente tabla se describen las alertas que desencadenan investigaciones automatizadas, su gravedad en el Centro de seguridad de Microsoft 365 y cómo se generan:

|Alerta|Severity|Cómo se genera la alerta|
|:---|:---|:---|
|Se detectó un clic de dirección URL potencialmente malintencionado|**Alto**|Esta alerta se genera cuando se produce cualquiera de las siguientes situaciones: <ul><li>Un usuario protegido por [vínculos seguros](atp-safe-links.md) de su organización hace clic en un vínculo malintencionado</li><li>Microsoft Defender identifica los cambios de veredicto de las direcciones URL para Office 365</li><li>Los usuarios invalidan las páginas de advertencia de Vínculos seguros (según la directiva de [vínculos seguros](set-up-atp-safe-links-policies.md)de su organización).</li></ul> <p> Para obtener más información sobre los eventos que desencadenan esta alerta, vea [Configurar directivas de vínculos seguros.](set-up-atp-safe-links-policies.md)|
|Un usuario notifica un mensaje de correo electrónico como malware o phishing|**Informativo**|Esta alerta se genera cuando los usuarios de su [](enable-the-report-message-add-in.md) organización informan de mensajes como correo electrónico de suplantación de identidad mediante el complemento Informar de mensaje o el complemento Informar [de suplantación de identidad](enable-the-report-phish-add-in.md).|
|Los mensajes de correo electrónico que contienen malware se eliminan después de la entrega|**Informativo**|Esta alerta se genera cuando los mensajes de correo electrónico que contienen malware se entregan a los buzones de la organización. Si se produce este evento, Microsoft quita los mensajes infectados de los buzones de Exchange Online mediante purga automática [de cero horas.](zero-hour-auto-purge.md)|
|Los mensajes de correo electrónico que contienen direcciones URL de suplantación de identidad se quitan después de la entrega|**Informativo**|Esta alerta se genera cuando los mensajes que contienen suplantación de identidad se entregan a los buzones de la organización. Si se produce este evento, Microsoft quita los mensajes infectados de los buzones de Exchange Online mediante la purga automática [de hora cero.](zero-hour-auto-purge.md)|
|Se detectan patrones sospechosos de envío de correo electrónico|**Medio**|Esta alerta se genera cuando alguien de su organización ha enviado correos electrónicos sospechosos y corre el riesgo de que se le restringa el envío de correo electrónico. La alerta es una advertencia anticipada para el comportamiento que podría indicar que la cuenta está en peligro, pero no lo suficientemente grave como para restringir al usuario. <p> Aunque es raro, una alerta generada por esta directiva puede ser una anomalía. Sin embargo, es una buena idea comprobar [si la cuenta de usuario está en peligro.](responding-to-a-compromised-email-account.md)|
|Se restringe el envío de correo electrónico a un usuario|**Alto**|Esta alerta se genera cuando alguien de su organización tiene restricciones para enviar correo saliente. Esta alerta normalmente se produce cuando una [cuenta de correo electrónico está en peligro.](responding-to-a-compromised-email-account.md) <p> Para obtener más información acerca de los usuarios restringidos, vea Quitar usuarios bloqueados del portal de usuarios restringidos [en Microsoft 365.](removing-user-from-restricted-users-portal-after-spam.md)|
|

> [!TIP]
> Para obtener más información sobre las directivas de alerta o editar la configuración predeterminada, consulte Directivas de alerta en el Centro de cumplimiento de [Microsoft 365.](../../compliance/alert-policies.md)

## <a name="required-permissions-to-use-air-capabilities"></a>Permisos necesarios para usar las funcionalidades de AIR

Los permisos se conceden a través de determinados roles, como los que se describen en la tabla siguiente:

|Task|Roles requeridos|
|---|---|
|Configurar las características de AIR|Uno de los siguientes roles: <ul><li>Administrador global</li><li>Administrador de seguridad</li></ul> <p> Estos roles se pueden asignar en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o en el Centro de & [cumplimiento.](permissions-in-the-security-and-compliance-center.md)|
|Iniciar una investigación automatizada <p> --- o --- <p> Aprobar o rechazar las acciones recomendadas|Uno de los siguientes roles, asignados en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o en el Centro de & [cumplimiento:](permissions-in-the-security-and-compliance-center.md) <ul><li>Administrador global</li><li>Administrador de seguridad</li><li>Operador de seguridad</li><li>Lector de seguridad <br> --- y --- </li><li>Búsqueda y depuración (este rol solo se asigna en el Centro de & [cumplimiento.](permissions-in-the-security-and-compliance-center.md) Es posible que tenga que crear un nuevo grupo de roles allí y agregar el rol Buscar y purgar a ese nuevo grupo de roles.</li></ul>|

## <a name="required-licenses"></a>Licencias necesarias

[Las licencias de Microsoft Defender para Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) deben asignarse a:

- Administradores de seguridad (incluidos los administradores globales)
- El equipo de operaciones de seguridad de su organización (incluidos los lectores de seguridad y los que tienen el rol **Buscar y** purgar)
- Usuarios finales


## <a name="changes-are-coming-soon-in-your-security-center"></a>Los cambios estarán disponibles próximamente en el centro de seguridad

Si ya usa las funcionalidades de AIR en Microsoft Defender para Office 365, está a punto de ver algunos cambios en el Centro de seguridad de [Microsoft 365 mejorado.](../mtp/overview-security-center.md)

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Centro de acciones unificado":::

El nuevo y mejorado centro de seguridad reúne las capacidades de AIR en Microsoft Defender para [Office 365](office-365-atp.md) y en [Microsoft Defender para Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) Con estas actualizaciones y mejoras, el equipo de operaciones de seguridad podrá ver detalles sobre las investigaciones automatizadas y las acciones de corrección en el correo electrónico, el contenido de colaboración, las cuentas de usuario y los dispositivos, todo en un solo lugar.

> [!TIP]
> El nuevo Centro de seguridad de Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ) reemplaza los siguientes centros:
>
> - Centro de seguridad y & cumplimiento de Office 365 ( [https://protection.office.com](https://protection.office.com) )
> - Centro de seguridad de Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )
>
> Además de cambiar la dirección URL, hay una nueva apariencia, diseñada para ofrecer a su equipo de seguridad una experiencia más optimizada, con visibilidad de más detecciones de amenazas en un solo lugar.

### <a name="what-to-expect"></a>Qué esperar

En la tabla siguiente se enumeran los cambios y mejoras que se incluyen en AIR en Microsoft Defender para Office 365.

|Elemento|¿Qué está cambiando?|
|---|---|
|**Página Investigaciones**|La página **Investigaciones actualizada es** más coherente con lo que ve en [Microsoft Defender para Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) Verá algunos cambios generales de formato y estilo que se alinean con la nueva vista **Investigaciones unificadas.** Por ejemplo, el gráfico de investigación tiene un formato más unificado.|
|**Pestaña Usuarios**|La **pestaña** Usuarios ahora es la **pestaña Buzones.** Los detalles sobre los usuarios aparecen en la **pestaña Buzón de** correo.|
|**Pestaña Correo** electrónico|Se **ha quitado** la pestaña Correo electrónico; visite la **pestaña Entidades para** ver una lista de elementos de clúster de correo electrónico y correo electrónico.|
|**Pestaña Entidades**|La **pestaña Entidades** tiene un estilo de pestaña en pestaña que incluye una vista de resumen y la capacidad de filtrar por tipo de entidad. La **pestaña Entidades** ahora incluye una opción Ir a **la** búsqueda además de la opción Abrir **en el** Explorador. Ahora puede usar el Explorador [de amenazas](threat-explorer.md) o la búsqueda [avanzada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) para buscar entidades y amenazas, y filtrar los resultados.|
|**Pestaña Acciones**|La pestaña **Acciones** actualizada ahora incluye una **pestaña Acciones pendientes** y una **pestaña Historial de** acciones. Las acciones se pueden aprobar (o rechazar) en un panel lateral que se abre al seleccionar una acción pendiente.|
|**Pestaña Evidencias**|Una nueva **pestaña Evidencia** muestra los resultados clave de la entidad relacionados con las acciones. Las acciones relacionadas con cada evidencia se pueden aprobar (o rechazar) en un panel lateral que se abre al seleccionar una acción pendiente.|
|**Centro de acciones**|El Centro **de actividades** actualizado ( ) reúne las acciones pendientes y completadas en el <https://security.microsoft.com/action-center> correo electrónico, los dispositivos y las identidades. Para obtener más información, consulta el Centro de acciones. (Para obtener más información, consulta [El Centro de acciones).](../mtp/mtp-action-center.md)|
|**Página Incidentes**|Ahora, **la página** Incidentes correlaciona varias investigaciones para proporcionar una mejor vista consolidada de las investigaciones. ([Obtenga más información sobre incidentes).](../mtp/incidents-overview.md)|
|

## <a name="next-steps"></a>Pasos siguientes

- [Ver detalles y resultados de una investigación automatizada](air-view-investigation-results.md#view-details-of-an-investigation)
- [Revisar y aprobar acciones pendientes](air-remediation-actions.md)
