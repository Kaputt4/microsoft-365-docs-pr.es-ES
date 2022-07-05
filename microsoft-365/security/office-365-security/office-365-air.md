---
title: Investigación y respuesta automatizadas en Microsoft Defender para Office 365
keywords: AIR, autoIR, Microsoft Defender para punto de conexión, automatizado, investigación, respuesta, corrección, amenazas, avanzado, amenaza, protección
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 01/29/2021
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Empiece a usar funcionalidades automatizadas de investigación y respuesta en Microsoft Defender para Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0fda154f8eb52ddab024a7f5bb02f980c9a05894
ms.sourcegitcommit: 44ece87e3e0c0c851dfc1e77211ac3e5e4a5b973
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/05/2022
ms.locfileid: "66617160"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Investigación y respuesta automatizadas (AIR) en Microsoft Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender para Office 365](defender-for-office-365.md) incluye eficaces funcionalidades de investigación y respuesta automatizadas (AIR) que pueden ahorrar tiempo y esfuerzo al equipo de operaciones de seguridad. A medida que se desencadenan alertas, depende del equipo de operaciones de seguridad revisar, priorizar y responder a esas alertas. Mantenerse al día con el volumen de alertas entrantes puede ser abrumador. Automatizar algunas de esas tareas puede ayudar.

AIR permite al equipo de operaciones de seguridad operar de forma más eficaz y eficaz. Las funcionalidades de AIR incluyen procesos de investigación automatizados en respuesta a amenazas conocidas que existen actualmente. Las acciones de corrección adecuadas esperan la aprobación, lo que permite al equipo de operaciones de seguridad responder eficazmente a las amenazas detectadas. Con AIR, el equipo de operaciones de seguridad puede centrarse en tareas de mayor prioridad sin perder de vista las alertas importantes que se desencadenan.

Este artículo describe:

- El [flujo general de AIR](#the-overall-flow-of-air);
- [Cómo obtener AIR](#how-to-get-air); Y
- Permisos [necesarios](#required-permissions-to-use-air-capabilities) para configurar o usar funcionalidades de AIR.
- Cambios que llegarán próximamente al portal de Microsoft 365 Defender

En este artículo también se incluyen [los pasos siguientes](#next-steps) y los recursos para obtener más información.

## <a name="the-overall-flow-of-air"></a>El flujo general de AIR

Se desencadena una alerta y un cuaderno de estrategias de seguridad inicia una investigación automatizada, lo que da como resultado resultados y acciones recomendadas. Este es el flujo general de AIR, paso a paso:

1. Una investigación automatizada se inicia de una de las siguientes maneras:
   - Una [alerta se desencadena](#which-alert-policies-trigger-automated-investigations) por algo sospechoso en el correo electrónico (como un mensaje, datos adjuntos, dirección URL o cuenta de usuario en peligro). Se crea un incidente y comienza una investigación automatizada; O
   - Un analista de seguridad [inicia una investigación automatizada](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) mientras usa [el Explorador](threat-explorer.md).
2. Mientras se ejecuta una investigación automatizada, recopila datos sobre el correo electrónico en cuestión y las entidades relacionadas con ese correo electrónico. Estas entidades pueden incluir archivos, direcciones URL y destinatarios. El ámbito de la investigación puede aumentar a medida que se desencadenan alertas nuevas y relacionadas.
3. Durante y después de una investigación automatizada, los [detalles y los resultados](air-view-investigation-results.md) están disponibles para su visualización. Los resultados incluyen [las acciones recomendadas](air-remediation-actions.md) que se pueden realizar para responder a las amenazas encontradas y corregirlas.
4. El equipo de operaciones de seguridad revisa los [resultados y las recomendaciones](air-view-investigation-results.md) de la investigación, y [aprueba o rechaza las acciones de corrección](air-review-approve-pending-completed-actions.md).
5. A medida que se aprueban (o rechazan) las acciones de corrección pendientes, se completa la investigación automatizada.

En Microsoft Defender para Office 365, no se realizan acciones de corrección automáticamente. Solo se realizan acciones de corrección tras obtener la aprobación del equipo de seguridad de su organización. Las funcionalidades de AIR ahorran tiempo al equipo de operaciones de seguridad mediante la identificación de acciones de corrección y la entrega de los detalles necesarios para tomar una decisión informada.

Durante y después de cada investigación automatizada, el equipo de operaciones de seguridad puede:

- [Ver detalles sobre una alerta relacionada con una investigación](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [Ver los detalles de los resultados de una investigación](air-view-investigation-results.md#view-details-of-an-investigation)
- [Revisar y aprobar acciones como resultado de una investigación](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Para obtener información general más detallada, consulte [Funcionamiento de AIR](automated-investigation-response-office.md).

## <a name="how-to-get-air"></a>Cómo obtener AIR

Las funcionalidades de AIR se incluyen en [Microsoft Defender para Office 365](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2), siempre que se configuren las directivas y las alertas. ¿Necesitas ayuda? Siga las instrucciones de [Protección contra amenazas](protect-against-threats.md) para configurar o configurar las siguientes opciones de protección:

- [Registro de auditoría](../../compliance/turn-audit-log-search-on-or-off.md) (debe estar activado)
- [Protección contra malware](protect-against-threats.md#part-1---anti-malware-protection-in-eop)
- [Protección contra phishing](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)
- [Protección contra correo no deseado](protect-against-threats.md#part-3---anti-spam-protection-in-eop)
- [Habilitar vínculos seguros y datos adjuntos seguros](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)

Además, asegúrese de [revisar las directivas de alerta de su organización](../../compliance/alert-policies.md), especialmente las [directivas predeterminadas de la categoría Administración de amenazas](../../compliance/alert-policies.md#default-alert-policies).

## <a name="which-alert-policies-trigger-automated-investigations"></a>¿Qué directivas de alerta desencadenan investigaciones automatizadas?

Microsoft 365 proporciona muchas directivas de alertas integradas que ayudan a identificar el abuso de permisos de administrador de Exchange, la actividad de malware, las posibles amenazas externas e internas y los riesgos de gobernanza de la información. Varias de las [directivas de alerta predeterminadas](../../compliance/alert-policies.md#default-alert-policies) pueden desencadenar investigaciones automatizadas. En la tabla siguiente se describen las alertas que desencadenan investigaciones automatizadas, su gravedad en el portal de Microsoft 365 Defender y cómo se generan:

|Alerta|Severity|Cómo se genera la alerta|
|---|---|---|
|Se detectó un clic de dirección URL potencialmente malintencionado|**Alto**|Esta alerta se genera cuando se produce cualquiera de las siguientes acciones: <ul><li>Un usuario protegido por [vínculos seguros](safe-links.md) de su organización hace clic en un vínculo malintencionado</li><li>Los cambios de veredicto de las direcciones URL se identifican mediante Microsoft Defender para Office 365</li><li>Los usuarios invalidan las páginas de advertencia de Vínculos seguros (en función de la [directiva de vínculos seguros](set-up-safe-links-policies.md) de su organización.</li></ul> <p> Para obtener más información sobre los eventos que desencadenan esta alerta, consulte [Configuración de directivas de vínculos seguros](set-up-safe-links-policies.md).|
|Un usuario notifica un mensaje de correo electrónico como malware o phish|**Informativo**|Esta alerta se genera cuando los usuarios de su organización notifican mensajes como correo electrónico de suplantación de identidad mediante el [complemento Mensaje](enable-the-report-message-add-in.md) de informe o el [complemento De suplantación de identidad](enable-the-report-phish-add-in.md) de informe.|
|Los mensajes de correo electrónico que contienen malware se quitan después de la entrega|**Informativo**|Esta alerta se genera cuando los mensajes de correo electrónico que contienen malware se entregan a los buzones de su organización. Si se produce este evento, Microsoft quita los mensajes infectados de Exchange Online buzones mediante [la purga automática de cero horas (ZAP).](zero-hour-auto-purge.md)|
|Los mensajes de correo electrónico que contienen direcciones URL de phish se quitan después de la entrega|**Informativo**|Esta alerta se genera cuando los mensajes que contienen phish se entregan a los buzones de su organización. Si se produce este evento, Microsoft quita los mensajes infectados de Exchange Online buzones mediante [ZAP](zero-hour-auto-purge.md).|
|Se detectan patrones de envío de correo electrónico sospechosos|**Medio**|Esta alerta se genera cuando alguien de su organización ha enviado un correo electrónico sospechoso y corre el riesgo de que se le restrinja el envío de correo electrónico. La alerta es una advertencia temprana para el comportamiento que podría indicar que la cuenta está en peligro, pero no lo suficientemente grave como para restringir al usuario. <p> Aunque es poco frecuente, una alerta generada por esta directiva puede ser una anomalía. Sin embargo, es una buena idea [comprobar si la cuenta de usuario está en peligro](responding-to-a-compromised-email-account.md).|
|Un usuario tiene restringido el envío de correo electrónico.|**Alto**|Esta alerta se genera cuando a alguien de su organización se le restringe el envío de correo saliente. Esta alerta suele producirse cuando una [cuenta de correo electrónico está en peligro](responding-to-a-compromised-email-account.md). <p> Para obtener más información sobre los usuarios restringidos, consulte [Eliminación de usuarios bloqueados del portal Usuarios restringidos de Microsoft 365](removing-user-from-restricted-users-portal-after-spam.md).|

> [!TIP]
> Para obtener más información sobre las directivas de alerta o editar la configuración predeterminada, consulte [Directivas de alerta en el portal de cumplimiento Microsoft Purview](../../compliance/alert-policies.md).

## <a name="required-permissions-to-use-air-capabilities"></a>Permisos necesarios para usar las funcionalidades de AIR

Los permisos se conceden a través de determinados roles, como los que se describen en la tabla siguiente:

|Tarea|Rol(s) requerido(s)|
|---|---|
|Configuración de las características de AIR|Uno de los siguientes roles: <ul><li>Administrador global</li><li>Administrador de seguridad</li></ul> <p> Estos roles se pueden asignar en [Azure Active Directory](/azure/active-directory/roles/permissions-reference) o en el [portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).|
|Iniciar una investigación automatizada <p> --- o --- <p> Aprobar o rechazar las acciones recomendadas|Uno de los siguientes roles, asignados en [Azure Active Directory](/azure/active-directory/roles/permissions-reference) o en el [portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md): <ul><li>Administrador global</li><li>Administrador de seguridad</li><li>Operador de seguridad</li><li>Lector de seguridad <br> --- y --- </li><li>Buscar y purgar (este rol solo se asigna en el [portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md). Es posible que tenga que crear un nuevo grupo de roles de **colaboración & correo electrónico** y agregar el rol Buscar y purgar a ese nuevo grupo de roles.</li></ul>|

## <a name="required-licenses"></a>Licencias necesarias

Microsoft Defender para Office 365 licencias [del plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) deben asignarse a:

- Administradores de seguridad (incluidos los administradores globales)
- El equipo de operaciones de seguridad de su organización (incluidos los lectores de seguridad y los que tienen el rol **Buscar y purgar** )
- Usuarios finales

## <a name="changes-are-coming-soon-in-your-microsoft-365-defender-portal"></a>Los cambios llegarán próximamente en el portal de Microsoft 365 Defender

Si ya usa funcionalidades de AIR en Microsoft Defender para Office 365, va a ver algunos cambios en el [portal de Microsoft 365 Defender mejorado](../defender/microsoft-365-defender-portal.md).

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Centro de acciones unificadas" lightbox="../../media/m3d-action-center-unified.png":::

El portal <https://security.microsoft.com> de Microsoft 365 Defender nuevo y mejorado reúne las funcionalidades de AIR en [Microsoft Defender para Office 365](defender-for-office-365.md) y en [Microsoft Defender para punto de conexión](../defender-endpoint/automated-investigations.md). Con estas actualizaciones y mejoras, su equipo de operaciones de seguridad podrá ver detalles sobre investigaciones automatizadas y acciones de corrección en todos sus correos electrónicos, contenido de colaboración, cuentas de usuario y dispositivos, todo en un mismo sitio.

> [!TIP]
> El nuevo portal de Microsoft 365 Defender reemplaza a los siguientes centros de administración:
>
> - Centro de cumplimiento de seguridad & (<https://protection.office.com>)
> - Microsoft 365 Defender (<https://security.microsoft.com>)
>
> Además de cambiar la dirección URL, hay una nueva apariencia, diseñada para proporcionar a su equipo de seguridad una experiencia más simplificada, con visibilidad para más detecciones de amenazas en un solo lugar.

### <a name="what-to-expect"></a>Qué esperar

En la tabla siguiente se enumeran los cambios y mejoras que llegan a AIR en Microsoft Defender para Office 365.

|Item|¿Qué está cambiando?|
|---|---|
|**Página Investigaciones**|La página **Investigaciones** actualizada es más coherente con lo que se ve en [Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations). Verá algunos cambios generales de formato y estilo que se alinean con la nueva vista **Investigaciones** unificada. Por ejemplo, el gráfico de investigación tiene un formato más unificado.|
|**Pestaña Usuarios**|La pestaña **Usuarios** ahora es la pestaña **Buzones** . Los detalles sobre los usuarios aparecen en la pestaña **Buzón** .|
|**Pestaña Correo electrónico**|Se ha quitado la pestaña **Correo electrónico** ; visite la pestaña **Entidades** para ver una lista de elementos de clúster de correo electrónico y correo electrónico.|
|**Pestaña Entidades**|La pestaña **Entidades** tiene un estilo de tabulación que incluye una vista de resumen completo y la capacidad de filtrar por tipo de entidad. La pestaña **Entidades** ahora incluye una opción **de búsqueda Go** además de la opción **Abrir en el Explorador** . Ahora puede usar [el Explorador](threat-explorer.md) o [la búsqueda avanzada](../defender-endpoint/advanced-hunting-overview.md) para buscar entidades y amenazas, y filtrar los resultados.|
|**Pestaña Acciones**|La pestaña **Acciones** actualizada ahora incluye una pestaña **Acciones pendientes** y una pestaña **Historial de acciones** . Las acciones se pueden aprobar (o rechazar) en un panel lateral que se abre al seleccionar una acción pendiente.|
|**Pestaña Evidencia**|Una nueva pestaña **Evidencia** muestra los resultados clave de la entidad relacionados con las acciones. Las acciones relacionadas con cada elemento de evidencia se pueden aprobar (o rechazar) en un panel lateral que se abre al seleccionar una acción pendiente.|
|**Centro de acciones**|El **Centro de acciones** actualizado (<https://security.microsoft.com/action-center>) reúne las acciones pendientes y completadas en el correo electrónico, los dispositivos y las identidades. Para obtener más información, consulte Centro de acciones. (Para obtener más información, consulte [El Centro de acciones](../defender/m365d-action-center.md)).|
|**Página Incidentes**|La página **Incidentes** ahora correlaciona varias investigaciones para proporcionar una vista mejor consolidada de las investigaciones. ([Obtenga más información sobre los incidentes](../defender/incidents-overview.md)).|

## <a name="next-steps"></a>Pasos siguientes

- [Ver detalles y resultados de una investigación automatizada](air-view-investigation-results.md#view-details-of-an-investigation)
- [Revisión y aprobación de acciones pendientes](air-remediation-actions.md)
