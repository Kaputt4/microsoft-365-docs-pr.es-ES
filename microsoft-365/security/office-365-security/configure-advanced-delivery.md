---
title: Configurar la entrega de simulaciones de suplantación de identidad de terceros a usuarios y mensajes sin filtrar a buzones de SecOps
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Los administradores pueden aprender a usar la directiva de entrega avanzada en Exchange Online Protection (EOP) para identificar mensajes que no deben filtrarse en escenarios compatibles específicos (simulaciones de suplantación de identidad de terceros y mensajes entregados a buzones de operaciones de seguridad (SecOps).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bebc094b56a20a43f92d1acf8d374110de43d71
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594126"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>Configurar la entrega de simulaciones de suplantación de identidad de terceros a usuarios y mensajes sin filtrar a buzones de SecOps

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> La característica que se describe en este artículo está en Versión preliminar, no está disponible para todos y está sujeta a cambios.

Para mantener la organización segura de forma [predeterminada,](secure-by-default.md)Exchange Online Protection (EOP) no permite listas seguras ni desvío de filtrado de mensajes que resulte en veredictos de phishing de elevada confianza o malware. Pero hay escenarios específicos que requieren la entrega de mensajes sin filtrar. Por ejemplo:

- **Simulaciones de suplantación** de identidad de terceros: los ataques simulados pueden ayudarle a identificar usuarios vulnerables antes de que un ataque real impacte en su organización.
- Buzones de operaciones de seguridad **(SecOps):** buzones dedicados que usan los equipos de seguridad para recopilar y analizar mensajes sin filtrar (tanto buenos como malos).

Use la directiva _de entrega avanzada_ en Microsoft 365 para evitar que estos mensajes en estos _escenarios específicos_ se filtren <sup>\*</sup> . La directiva de entrega avanzada garantiza que los mensajes en estos escenarios no se filtran:

- Los filtros de EOP y Microsoft Defender Office 365 realizar ninguna acción en estos mensajes.<sup>\*</sup>
- [La purga de hora cero (ZAP)](zero-hour-auto-purge.md) para correo no deseado y suplantación de identidad no realiza ninguna acción en estos mensajes.<sup>\*</sup>
- [Las alertas predeterminadas](alerts.md) del sistema no se desencadenan para estos escenarios.
- [AIR y la agrupación en clústeres en Defender para Office 365](office-365-air.md) omite estos mensajes.
- Específicamente para simulaciones de suplantación de identidad de terceros:
  - [Los envíos de](admin-submission.md) administrador generan una respuesta automática que indica que el mensaje forma parte de una campaña de simulación de suplantación de identidad (phishing) y no es una amenaza real. Las alertas y AIR no se desencadenarán.
  - [Caja fuerte vínculos en Defender para Office 365](safe-links.md) no bloquea ni detona las direcciones URL identificadas específicamente en estos mensajes.
  - [Caja fuerte datos adjuntos en Defender para Office 365](safe-attachments.md) no detonan datos adjuntos en estos mensajes.

<sup>\*</sup> No puede omitir el filtrado de malware o ZAP para malware.

Los mensajes identificados por la directiva de entrega avanzada no son amenazas de seguridad, por lo que los mensajes se marcan como invalidaciones del sistema. Los administradores pueden filtrar y analizar estas invalidaciones del sistema en las siguientes experiencias:

- [Explorador de amenazas/detecciones en tiempo real en Defender para Office 365 plan 2](threat-explorer.md)
- La [entidad Email Page en el Explorador de amenazas/Detecciones en tiempo real](mdo-email-entity-page.md)
- Informe [de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)
- [Búsqueda avanzada en Microsoft Defender para endpoint](../defender-endpoint/advanced-hunting-overview.md)
- [Vistas de campañas](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la **página Entrega avanzada,** abra <https://protection.office.com/advanceddelivery> .

- Debe tener asignados permisos antes de poder realizar los procedimientos descritos en este artículo:
  - Para crear, modificar o quitar la configuración de la directiva de  entrega avanzada, debe ser miembro del grupo de roles  Administrador de seguridad en el Centro de cumplimiento de seguridad **&** y miembro del grupo de roles Administración de la **organización en Exchange Online**.  
  - Para obtener acceso de solo lectura a la directiva de entrega avanzada, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.

  Para obtener más información, vea [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).

## <a name="use-the-security--compliance-center-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Usar el Centro de seguridad & cumplimiento para configurar simulaciones de suplantación de identidad de terceros en la directiva de entrega avanzada

1. En el Centro de seguridad & cumplimiento, vaya a **Administración de amenazas** \> **Entrega** avanzada de \> **directiva**.

2. En la **página Entrega avanzada,** seleccione la pestaña **Simulación de suplantación** de identidad y, a continuación, haga clic **en Editar**.

3. En el flyout de simulación **de suplantación** de identidad de terceros que se abre, configure las siguientes opciones:

   - **Dominio de envío:** se requiere al menos un dominio de dirección de correo electrónico (por ejemplo, contoso.com). Puede agregar hasta 10 entradas.
   - **Enviar IP:** se requiere al menos una dirección IPv4 válida. Puede agregar hasta 10 entradas. Los valores admitidos son:
     - IP única: por ejemplo, 192.168.1.1.
     - Intervalo IP: por ejemplo, 192.168.0.1-192.168.0.254.
     - IP cidr: por ejemplo, 192.168.0.1/25.
   - **Direcciones URL de simulación** para permitir: Opcionalmente, escriba direcciones URL específicas que forman parte de la campaña de simulación de suplantación de identidad que no se debe bloquear ni detonar. Puede agregar hasta 10 entradas.

4. Cuando haya terminado, haga clic en **Guardar.**

Las entradas de simulación de suplantación de identidad de terceros que configuró se muestran en la pestaña **Simulación de suplantación de** identidad. Para realizar cambios, haga clic **en Editar** en la pestaña.

## <a name="use-the-security--compliance-center-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>Usar el Centro de seguridad & cumplimiento para configurar buzones de SecOps en la directiva de entrega avanzada

1. En el Centro de & cumplimiento, vaya a **Administración de** amenazas \>  \> **Entrega avanzada**.

2. En la **página Entrega avanzada,** seleccione la **pestaña Buzón de SecOps** y, a continuación, haga clic **en Editar**.

3. En el menú desplegable del buzón de **SecOps** que se abre, escriba las direcciones de correo electrónico de los buzones de correo Exchange Online que desea designar como buzones de SecOps. Los grupos de distribución no están permitidos.

4. Cuando haya terminado, haga clic en **Guardar**.

Las entradas de buzón de SecOps que configuró se muestran en la **pestaña Buzón de SecOps.** Para realizar cambios, haga clic **en Editar** en la pestaña.

## <a name="additional-scenarios-that-require-filtering-bypass"></a>Escenarios adicionales que requieren la omisión de filtrado

Además de los dos escenarios con los que la directiva de entrega avanzada puede ayudarle, hay otros escenarios que pueden requerir omitir el filtrado:

- **Filtros de terceros:** si el registro  MX de su dominio no apunta a Office 365 (los mensajes se enruta en otro lugar primero), [la](secure-by-default.md) seguridad de forma predeterminada no *está disponible*.

  Para omitir el filtrado de Microsoft para los mensajes que ya han sido evaluados por el filtrado de terceros, use reglas de flujo de correo (también conocidas como reglas de transporte), vea Usar reglas de flujo de correo para establecer el [SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)en mensajes .

- **Falsos positivos** en revisión: es posible que desee permitir temporalmente que determinados mensajes que Microsoft sigue analizando a través de [envíos](admin-submission.md) de administrador informen de mensajes buenos conocidos que se marcan incorrectamente como incorrectos para Microsoft (falsos positivos). Al igual que con todas las invalidaciones, se recomienda **_encarecidamente_** que estas asignaciones se puedan realizar temporalmente.
