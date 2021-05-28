---
title: Investigación y respuesta automatizadas en Microsoft Defender para Office 365
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automated, investigation, response, remediation, threats, advanced, threat, protection
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
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
ms.openlocfilehash: 7632efb2014af9f55e9cad700bceeeabe555fb8b
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2021
ms.locfileid: "52696579"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Investigación y respuesta automatizadas (AIR) en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender para Office 365](defender-for-office-365.md) incluye potentes capacidades de investigación y respuesta automatizadas (AIR) que pueden ahorrar tiempo y esfuerzo al equipo de operaciones de seguridad. A medida que se desencadenan las alertas, el equipo de operaciones de seguridad debe revisar, priorizar y responder a dichas alertas. Mantenerse al día con el volumen de alertas entrantes puede ser abrumador. Automatizar algunas de estas tareas puede ser de ayuda.

AIR permite que el equipo de operaciones de seguridad funcione de forma más eficaz y eficaz. Las capacidades de AIR incluyen procesos de investigación automatizados en respuesta a amenazas conocidas que existen actualmente. Las acciones de corrección apropiadas esperan su aprobación, lo que permite al equipo de operaciones de seguridad responder eficazmente a las amenazas detectadas. Con AIR, el equipo de operaciones de seguridad puede centrarse en tareas de mayor prioridad sin perder de vista las alertas importantes que se desencadenan.

Este artículo describe:

- El [flujo general de AIR](#the-overall-flow-of-air);
- [Cómo obtener AIR](#how-to-get-air); y
- Los [permisos necesarios para](#required-permissions-to-use-air-capabilities) configurar o usar las funcionalidades de AIR.
- Cambios que se van a realizar próximamente en el centro de seguridad

En este artículo también se [incluyen los pasos siguientes](#next-steps)y los recursos para obtener más información.

## <a name="the-overall-flow-of-air"></a>El flujo general de AIR

Se desencadena una alerta y un libro de juegos de seguridad inicia una investigación automatizada, lo que da como resultado resultados y acciones recomendadas. Este es el flujo general de AIR, paso a paso:

1. Una investigación automatizada se inicia de una de las siguientes maneras:
   - Una [alerta se desencadena por](#which-alert-policies-trigger-automated-investigations) algo sospechoso en el correo electrónico (como un mensaje, datos adjuntos, dirección URL o una cuenta de usuario comprometida). Se crea un incidente y comienza una investigación automatizada; o
   - Un analista de [seguridad inicia una investigación automatizada](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) mientras usa el Explorador de [amenazas.](threat-explorer.md)
2. Mientras se ejecuta una investigación automatizada, recopila datos sobre el correo electrónico en cuestión y las entidades relacionadas con ese correo electrónico. Estas entidades pueden incluir archivos, direcciones URL y destinatarios. El ámbito de la investigación puede aumentar a medida que se desencadenan alertas nuevas y relacionadas.
3. Durante y después de una investigación automatizada, [los detalles y los resultados](air-view-investigation-results.md) están disponibles para ver. Los [resultados incluyen acciones recomendadas](air-remediation-actions.md) que se pueden realizar para responder y corregir las amenazas encontradas.
4. El equipo de operaciones de seguridad revisa los [resultados y recomendaciones de](air-view-investigation-results.md)la investigación y [aprueba o rechaza las acciones de corrección](air-review-approve-pending-completed-actions.md).
5. A medida que se aprueban (o rechazan) las acciones de corrección pendientes, se completa la investigación automatizada.

En Microsoft Defender para Office 365, no se realiza ninguna acción de corrección automáticamente. Solo se realizan acciones de corrección tras obtener la aprobación del equipo de seguridad de su organización. Las capacidades de AIR ahorran tiempo al equipo de operaciones de seguridad identificando acciones de corrección y proporcionando los detalles necesarios para tomar una decisión fundamentada.

Durante y después de cada investigación automatizada, el equipo de operaciones de seguridad puede:

- [Ver detalles sobre una alerta relacionada con una investigación](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [Ver los detalles de resultados de una investigación](air-view-investigation-results.md#view-details-of-an-investigation)
- [Revisar y aprobar acciones como resultado de una investigación](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Para obtener una introducción más detallada, vea [How AIR works](automated-investigation-response-office.md).

## <a name="how-to-get-air"></a>Cómo obtener AIR

Las funcionalidades de AIR se incluyen en [Microsoft Defender para Office 365](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2), siempre que se configuren las directivas y las alertas. ¿Necesita ayuda? Siga las instrucciones de [Protección contra amenazas](protect-against-threats.md) para configurar o configurar las siguientes opciones de protección:

- [Registro de auditoría](../../compliance/turn-audit-log-search-on-or-off.md) (debe estar activado)
- [Directivas antimalware](protect-against-threats.md#part-1---anti-malware-protection-in-eop)
- [Protección contra phishing](protect-against-threats.md#part-2---anti-phishing-protection)
- [Protección contra correo no deseado](protect-against-threats.md#part-3---anti-spam-protection-in-eop)
- [Caja fuerte Vínculos y Caja fuerte datos adjuntos](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)
- [Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](protect-against-threats.md#part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)
- [Purga automática de hora cero para correo electrónico](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop)

Además, asegúrese de revisar [las](../../compliance/alert-policies.md)directivas de alerta de su organización, especialmente las directivas predeterminadas en la categoría Administración [de amenazas.](../../compliance/alert-policies.md#default-alert-policies)

## <a name="which-alert-policies-trigger-automated-investigations"></a>¿Qué directivas de alerta desencadenan investigaciones automatizadas?

Microsoft 365 proporciona muchas directivas de alerta integradas que ayudan Exchange identificar el uso indebido de permisos de administrador, la actividad de malware, las posibles amenazas externas e internas y los riesgos de gobierno de la información. Varias de las [directivas de alerta predeterminadas](../../compliance/alert-policies.md#default-alert-policies) pueden desencadenar investigaciones automatizadas. En la tabla siguiente se describen las alertas que desencadenan investigaciones automatizadas, su gravedad en el centro de seguridad de Microsoft 365 y cómo se generan:

|Alerta|Gravedad|Cómo se genera la alerta|
|---|---|---|
|Se detectó un clic de dirección URL potencialmente malintencionado|**Alto**|Esta alerta se genera cuando se produce cualquiera de las siguientes situaciones: <ul><li>Un usuario protegido por [Caja fuerte vínculos de](safe-links.md) la organización hace clic en un vínculo malintencionado</li><li>Microsoft Defender identifica los cambios de veredicto para las direcciones URL Office 365</li><li>Los usuarios invalidan Caja fuerte de advertencia vínculos (según la directiva de vínculos de Caja fuerte [de la organización).](set-up-safe-links-policies.md)</li></ul> <p> Para obtener más información sobre los eventos que desencadenan esta alerta, vea [Configurar Caja fuerte de vínculos](set-up-safe-links-policies.md).|
|Un usuario notifica un mensaje de correo electrónico como malware o phish|**Informativo**|Esta alerta se genera cuando los usuarios de la organización informan de mensajes como correo electrónico de suplantación de identidad mediante el complemento Report [Message](enable-the-report-message-add-in.md) o el complemento [Report Phishing](enable-the-report-phish-add-in.md).|
|Los mensajes de correo electrónico que contienen malware se quitan después de la entrega|**Informativo**|Esta alerta se genera cuando los mensajes de correo electrónico que contienen malware se entregan a los buzones de la organización. Si se produce este evento, Microsoft quita los mensajes infectados de los buzones de correo Exchange Online mediante la purga automática de hora [cero](zero-hour-auto-purge.md).|
|Los mensajes de correo electrónico que contienen direcciones URL de suplantación de identidad se quitan después de la entrega|**Informativo**|Esta alerta se genera cuando los mensajes que contienen phish se entregan a los buzones de la organización. Si se produce este evento, Microsoft quita los mensajes infectados de los buzones de correo Exchange Online mediante la purga automática de hora [cero](zero-hour-auto-purge.md).|
|Se detectan patrones de envío de correo electrónico sospechosos|**Medio**|Esta alerta se genera cuando alguien de la organización ha enviado correo electrónico sospechoso y corre el riesgo de que se le restringa el envío de correo electrónico. La alerta es una advertencia anticipada para el comportamiento que puede indicar que la cuenta está en peligro, pero no lo suficientemente grave como para restringir al usuario. <p> Aunque es poco común, una alerta generada por esta directiva puede ser una anomalía. Sin embargo, es una buena idea comprobar si la cuenta de usuario [está en peligro.](responding-to-a-compromised-email-account.md)|
|A un usuario se le restringe el envío de correo electrónico|**Alto**|Esta alerta se genera cuando alguien de la organización tiene restringido el envío de correo saliente. Normalmente, esta alerta se produce cuando una cuenta [de correo electrónico está en peligro.](responding-to-a-compromised-email-account.md) <p> Para obtener más información acerca de los usuarios restringidos, vea [Remove blocked users from the Restricted Users portal in Microsoft 365](removing-user-from-restricted-users-portal-after-spam.md).|
|

> [!TIP]
> Para obtener más información acerca de las directivas de alerta o editar la configuración predeterminada, vea Directivas de [alerta en el centro de Microsoft 365 cumplimiento.](../../compliance/alert-policies.md)

## <a name="required-permissions-to-use-air-capabilities"></a>Permisos necesarios para usar funcionalidades de AIR

Los permisos se conceden a través de determinados roles, como los que se describen en la tabla siguiente:

|Tarea|Rol(s) obligatorio(s)|
|---|---|
|Configurar características de AIR|Uno de los siguientes roles: <ul><li>Administrador global</li><li>Administrador de seguridad</li></ul> <p> Estos roles se pueden asignar en [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o en el [Centro de seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md).|
|Iniciar una investigación automatizada <p> --- o --- <p> Aprobar o rechazar acciones recomendadas|Uno de los siguientes roles, asignados en [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o en el Centro de [seguridad & cumplimiento:](permissions-in-the-security-and-compliance-center.md) <ul><li>Administrador global</li><li>Administrador de seguridad</li><li>Operador de seguridad</li><li>Lector de seguridad <br> --- y --- </li><li>Buscar y purgar (este rol solo se asigna en el Centro de [seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md). Es posible que tenga que crear un nuevo grupo de roles allí y agregar el rol Buscar y purgar a ese nuevo grupo de roles.</li></ul>|

## <a name="required-licenses"></a>Licencias necesarias

[Las licencias Office 365 plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) de Microsoft Defender deben asignarse a:

- Administradores de seguridad (incluidos los administradores globales)
- El equipo de operaciones de seguridad de la organización (incluidos los lectores de seguridad y los que tienen el rol **Buscar y** purgar)
- Usuarios finales

## <a name="changes-are-coming-soon-in-your-security-center"></a>Los cambios se realizarán próximamente en el centro de seguridad

Si ya estás usando funcionalidades de AIR en Microsoft Defender para Office 365, estás a punto de ver algunos cambios en el centro de seguridad Microsoft 365 [de seguridad.](../defender/overview-security-center.md)

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Centro de acciones unificadas":::

El nuevo y mejorado centro de seguridad reúne las capacidades de AIR en [Microsoft Defender](defender-for-office-365.md) para Office 365 y en Microsoft Defender [para endpoint](../defender-endpoint/automated-investigations.md). Con estas actualizaciones y mejoras, su equipo de operaciones de seguridad podrá ver detalles sobre investigaciones automatizadas y acciones de corrección en todos sus correos electrónicos, contenido de colaboración, cuentas de usuario y dispositivos, todo en un mismo sitio.

> [!TIP]
> El nuevo Microsoft 365 de seguridad ( <https://security.microsoft.com> ) reemplaza a los siguientes centros:
>
> - Office 365 Centro & cumplimiento normativo ( <https://protection.office.com> )
> - Centro de seguridad de Microsoft Defender ( <https://securitycenter.windows.com> )
>
> Además de cambiar la dirección URL, hay un nuevo aspecto, diseñado para ofrecer a su equipo de seguridad una experiencia más optimizada, con visibilidad de más detecciones de amenazas en un solo lugar.

### <a name="what-to-expect"></a>Qué esperar

En la tabla siguiente se enumeran los cambios y mejoras que se han realizado en AIR en Microsoft Defender para Office 365.

|Elemento|¿Qué está cambiando?|
|---|---|
|**Página Investigaciones**|La página **Investigaciones actualizada es** más coherente con lo que se ve en [Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations). Verá algunos cambios generales de formato y estilo que se alinean con la nueva vista **Investigaciones unificada.** Por ejemplo, el gráfico de investigación tiene un formato más unificado.|
|**Pestaña Usuarios**|La **pestaña Usuarios** ahora es la pestaña **Buzones.** Los detalles sobre los usuarios se enumeran en la **pestaña Buzón** de correo.|
|**Pestaña Correo** electrónico|Se **ha quitado** la pestaña Correo electrónico; visite la **pestaña Entidades** para ver una lista de elementos del clúster de correo electrónico y correo electrónico.|
|**Pestaña Entidades**|La **pestaña Entidades** tiene un estilo de pestaña en pestaña que incluye una vista de resumen total y la capacidad de filtrar por tipo de entidad. La **pestaña Entidades** ahora incluye una opción **Ir** a buscar, además de la opción Abrir **en el** Explorador. Ahora puedes usar el Explorador [de amenazas](threat-explorer.md) o la búsqueda [avanzada](../defender-endpoint/advanced-hunting-overview.md) para buscar entidades y amenazas y filtrar los resultados.|
|**Pestaña Acciones**|La pestaña **Acciones** actualizada ahora incluye **una pestaña Acciones pendientes** y una **pestaña Historial de** acciones. Las acciones se pueden aprobar (o rechazar) en un panel lateral que se abre al seleccionar una acción pendiente.|
|**Ficha Evidencia**|Una nueva **pestaña Evidencia** muestra los resultados clave de la entidad relacionados con las acciones. Las acciones relacionadas con cada elemento de evidencia se pueden aprobar (o rechazar) en un panel lateral que se abre al seleccionar una acción pendiente.|
|**Centro de actividades**|El Centro **de acciones** actualizado ( ) reúne acciones pendientes y completadas en [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) correo electrónico, dispositivos e identidades. Para obtener más información, consulte Centro de acciones. (Para obtener más información, vea [The Action center](../defender/m365d-action-center.md).)|
|**Página Incidentes**|La **página Incidentes** ahora correlaciona varias investigaciones para proporcionar una mejor vista consolidada de las investigaciones. ([Obtenga más información sobre incidentes](../defender/incidents-overview.md).)|
|

## <a name="next-steps"></a>Pasos siguientes

- [Ver detalles y resultados de una investigación automatizada](air-view-investigation-results.md#view-details-of-an-investigation)
- [Revisar y aprobar acciones pendientes](air-remediation-actions.md)
