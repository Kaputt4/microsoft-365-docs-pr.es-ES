---
title: Información de mensajes reenviados automáticamente
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Los administradores pueden obtener información sobre el informe de mensajes reenviados automáticamente en el panel Flujo de correo del Centro de cumplimiento de seguridad &.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.collection: m365-security
search.appverid: met150
ms.openlocfilehash: 5de545c15daea2e4107093997abce3a86a2d22d8
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68084031"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Información de mensajes reenviados automáticamente en el Centro de cumplimiento de seguridad &

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

La información de **mensajes reenviados** automáticamente en el [panel Flujo de correo](mail-flow-insights-v2.md) del [Centro de cumplimiento de seguridad &](https://protection.office.com) muestra información sobre los mensajes que se reenvía automáticamente desde su organización a los destinatarios de dominios externos.

:::image type="content" source="../../media/mfi-auto-forwarded-messages.png" alt-text="El widget es decir, mensajes reenviados automáticamente en el Centro de cumplimiento de seguridad &" lightbox="../../media/mfi-auto-forwarded-messages.png":::

## <a name="auto-forwarded-messages-details"></a>Detalles de mensajes reenviados automáticamente

Al hacer clic en el número de mensajes del widget, aparece un panel flotante que muestra más información sobre los mensajes reenviados automáticamente:

- **Mensajes reenviados automáticamente mediante métodos de reenvío**:

  - **Por reglas de flujo de correo**
  - **Por reglas de bandeja de entrada**
  - **Por reenvío SMTP**: este método indica el reenvío automático que los administradores pueden configurar en un buzón, como se describe en [Configuración del reenvío de correo electrónico para un buzón](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).
  - Vínculo al [informe de reenvío](view-mail-flow-reports.md#forwarding-report) para obtener más detalles.

- **Mensajes reenviados automáticamente por dominios y usuarios**:

  - **5 dominios principales reenviados a**
  - **Nuevos dominios (la semana pasada)**
  - **Los 5 principales usuarios de reenvío**
  - **Nuevos usuarios (la semana pasada)**
  - Vínculo al [informe de modificaciones de reenvío](mfi-new-users-forwarding-email.md#forwarding-modifications-report) para obtener más detalles.

:::image type="content" source="../../media/mfi-auto-forwarded-messages-details.png" alt-text="Widget Mensajes reenviados automáticamente en el Centro de cumplimiento de seguridad &" lightbox="../../media/mfi-auto-forwarded-messages-details.png":::

## <a name="insights"></a>Insights

Se generan dos conclusiones basadas en los datos del informe:

- [Nuevos usuarios que reenvía correo electrónico](mfi-new-users-forwarding-email.md)
- [Nuevos dominios que se reenvía por correo electrónico](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>Vea también

Para obtener información sobre otras conclusiones en el panel Flujo de correo, consulte [Información de flujo de correo en el Centro de cumplimiento de seguridad &](mail-flow-insights-v2.md).
