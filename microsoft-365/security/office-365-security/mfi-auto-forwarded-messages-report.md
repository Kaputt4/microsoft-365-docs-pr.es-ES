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
description: Los administradores pueden obtener información sobre el informe de mensajes reenviados automáticamente en el panel flujo de correo del Centro de & cumplimiento.
ms.technology: mdo
ms.prod: m365-security
ms.collection: M365-security-compliance
ms.openlocfilehash: 05ad934fbc7736c0cfbb86f7411a2ca73705112f
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2022
ms.locfileid: "63680168"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Información de mensajes reenviados automáticamente en el Centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

La **información de mensajes** reenviados automáticamente [](mail-flow-insights-v2.md) en el panel flujo de correo del Centro de seguridad [& cumplimiento](https://protection.office.com) muestra información sobre los mensajes que se reenvía automáticamente desde su organización a los destinatarios de dominios externos.

![Widget De mensajes reenviados automáticamente en el Centro de seguridad & cumplimiento.](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Detalles de mensajes reenviados automáticamente

Al hacer clic en el número de mensajes del widget, aparece un panel flotante que muestra más información sobre los mensajes reenviados automáticamente:

- **Reenviar automáticamente los mensajes mediante métodos de reenvío**:

  - **Por reglas de flujo de correo**
  - **Por reglas de la Bandeja de entrada**
  - **Mediante reenvío SMTP**: este método indica el reenvío automático que los administradores pueden configurar en un buzón, tal como se describe en [Configure email forwarding for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).
  - Un vínculo al informe [de reenvío](view-mail-flow-reports.md#forwarding-report) para obtener más información.

- **Mensajes reenviados automáticamente por dominios y usuarios**:

  - **Principales 5 dominios reenviados a**
  - **Nuevos dominios (la semana pasada)**
  - **Principales 5 usuarios de reenvío**
  - **Nuevos usuarios (la semana pasada)**
  - Un vínculo al informe [de modificaciones de reenvío](mfi-new-users-forwarding-email.md#forwarding-modifications-report) para obtener más información.

![Control de detalles para el informe De mensajes reenviados automáticamente en el Centro de seguridad & cumplimiento.](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>Insights

Se generan dos perspectivas en función de los datos del informe:

- [Nuevos usuarios reenviar correo electrónico](mfi-new-users-forwarding-email.md)
- [Nuevos dominios que se reenvía correo electrónico](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>Consulte también

Para obtener información sobre otras perspectivas en el panel flujo de correo, vea Información sobre el flujo de correo en el [Centro de seguridad & cumplimiento](mail-flow-insights-v2.md).