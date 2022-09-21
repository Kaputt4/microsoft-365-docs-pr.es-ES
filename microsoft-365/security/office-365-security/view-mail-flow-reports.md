---
title: Visualización de informes de flujo de correo en el panel Informes
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre los informes de flujo de correo que están disponibles en el panel Informes del Centro de cumplimiento de seguridad &.
ms.custom: ''
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 26a6211e86266dad2705eb7024ad8a4b86e63e25
ms.sourcegitcommit: 95ac076310ab9006ed92c69938f7ae771cd10826
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67851048"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a>Ver informes de flujo de correo en el panel Informes del Centro de cumplimiento de seguridad &

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> La mayoría de los informes de este artículo también están disponibles en el portal de Microsoft 365 Defender o en el Centro de administración de Exchange (EAC). Para obtener más información, consulte los siguientes temas:
>
> - [Informes de flujo de correo en el nuevo Centro de administración de Exchange](/exchange/monitoring/mail-flow-reports/mail-flow-reports)
> - [Visualización de informes de seguridad de correo electrónico en el portal de Microsoft 365 Defender](view-email-security-reports.md)

Además de los informes de flujo de correo que están disponibles en el [panel Flujo de correo](mail-flow-insights-v2.md) del Centro de cumplimiento de seguridad &, hay una variedad de informes de flujo de correo adicionales disponibles en el panel Informes para ayudarle a supervisar su organización de Microsoft 365.

Si tiene los [permisos necesarios](#what-permissions-are-needed-to-view-these-reports), puede ver estos informes en el Centro de cumplimiento de seguridad & en <https://protection.office.com> en el **Panel** **de informes**\>. Para ir directamente al panel Informes, abra <https://protection.office.com/insightdashboard>.

:::image type="content" source="../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png" alt-text="Panel Informes del Centro de cumplimiento de & de seguridad" lightbox="../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png":::

## <a name="connector-report"></a>Informe del conector

> [!NOTE]
> Este informe se ha reemplazado por el **informe Mensajes entrantes** y el **informe Mensajes salientes** en el EAC. Para obtener más información, vea [Mensajes entrantes e Informes de mensajes salientes en el nuevo EAC](/exchange/monitoring/mail-flow-reports/mfr-inbound-messages-and-outbound-messages-reports).

## <a name="exchange-transport-rule-report"></a>Informe de reglas de transporte de Exchange

El **informe de reglas de transporte de Exchange** muestra el efecto de las reglas de flujo de correo (también conocidas como reglas de transporte) en los mensajes entrantes y salientes de la organización.

Para ver el informe, abra el Centro de cumplimiento de seguridad & en <https://protection.office.com>, vaya al **Panel** de **informes** \> y seleccione **Regla de transporte de Exchange**. Para ir directamente al informe, abra <https://security.microsoft.com/reports/ETRRuleReport>.

:::image type="content" source="../../media/scc-transport-rule-report-widget.png" alt-text="Widget de regla de transporte de Exchange en el panel Informes" lightbox="../../media/scc-transport-rule-report-widget.png":::

> [!NOTE]
> El **informe de reglas de transporte de Exchange** ya está disponible en el EAC. Para obtener más información, vea [Informe de reglas de transporte de Exchange en el nuevo EAC](/exchange/monitoring/mail-flow-reports/mfr-exchange-transport-rule-report).

## <a name="forwarding-report"></a>Informe de reenvío

> [!NOTE]
> El **informe de reenvío** ya está disponible en el EAC. Para obtener más información, vea [Informe de mensajes reenviados automáticamente en el nuevo EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).

## <a name="mailflow-status-report"></a>Informe de estado de flujo de correo

El **informe de estado de Flujo de** correo es similar al [informe de correo electrónico enviado y recibido](#sent-and-received-email-report), con información adicional sobre el correo electrónico permitido o bloqueado en el perímetro. Este es el único informe que contiene información de protección perimetral y muestra cuánto correo electrónico se bloquea antes de que se le permita entrar en el servicio para su evaluación por Exchange Online Protection (EOP). Es importante comprender que si se envía un mensaje a cinco destinatarios, lo contamos como cinco mensajes diferentes y no como un mensaje.

Para ver el informe, abra el [Centro de cumplimiento de seguridad &](https://protection.office.com), vaya al **Panel de** **informes** \> y seleccione **Informe de estado de flujo de correo**. Para ir directamente al **informe de estado de flujo de correo**, abra <https://security.microsoft.com/reports/mailflowStatusReport>.

:::image type="content" source="../../media/scc-mail-flow-status-report-widget.png" alt-text="Widget de informe de estado de flujo de correo en el panel Informes" lightbox="../../media/scc-mail-flow-status-report-widget.png":::

> [!NOTE]
> Al hacer clic en el widget de este informe en el Centro de cumplimiento de seguridad & (protection.office.com) ahora se le lleva al informe completo en el portal de Microsoft 365 Defender (security.microsoft.com). Para obtener más información sobre el informe, consulte [Informe de estado de flujo de correo](view-email-security-reports.md#mailflow-status-report).

## <a name="sent-and-received-email-report"></a>Informe de correo electrónico enviado y recibido

> [!NOTE]
> Este informe se ha reemplazado por el [informe de estado de Flujo de correo](#mailflow-status-report).

## <a name="top-senders-and-recipients-report"></a>Informe de remitentes y destinatarios principales

Los **principales remitentes y destinatarios** muestran los principales remitentes de mensajes de su organización, así como los destinatarios principales de los mensajes detectados por EOP y las características de protección de Defender para Office 365.

Para ver el informe, abra el Centro de cumplimiento de seguridad & en <https://protection.office.com>, vaya al **Panel** de **informes** \> y seleccione **Principales remitentes y destinatarios**. Para ir directamente al informe, abra una de las siguientes direcciones URL:

- Defender para Office 365:<https://protection.office.com/TopSenderRecipientsATP>
- EOP: <https://protection.office.com/TopSenderRecipients>

:::image type="content" source="../../media/scc-top-senders-and-recipients-widget.png" alt-text="Widget Remitentes y destinatarios principales en el panel Informes" lightbox="../../media/scc-top-senders-and-recipients-widget.png":::

> [!NOTE]
> Aunque al hacer clic en el widget de este informe en el Centro de cumplimiento de seguridad & le lleva a una página de protection.office.com, el contenido de la página procede del portal de Microsoft 365 Defender. Para obtener más información sobre el informe, vea [Informe de remitentes y destinatarios principales](view-email-security-reports.md#top-senders-and-recipients-report).

## <a name="what-permissions-are-needed-to-view-these-reports"></a>¿Qué permisos se necesitan para ver estos informes?

Para ver y usar los informes descritos en este artículo, debe ser miembro de uno de los siguientes grupos de roles en el Centro de cumplimiento de seguridad &:

- **Administración de organizaciones**
- **Administrador de seguridad**
- **Lector de seguridad**
- **Lector global**

Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

> [!NOTE]
> Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

