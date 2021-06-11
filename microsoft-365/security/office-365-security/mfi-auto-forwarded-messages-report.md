---
title: Información de mensajes reenviados automáticamente
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Los administradores pueden obtener información sobre el informe de mensajes reenviados automáticamente en el panel flujo de correo del Centro de seguridad & cumplimiento.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1882c0506093816e9bb85ae3ba90decd4e0e0d74
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207326"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Información de mensajes reenviados automáticamente en el Centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

La **información de mensajes** reenviados automáticamente en el panel flujo de correo del Centro de seguridad & cumplimiento muestra información sobre los mensajes que se reenvía automáticamente desde su organización [a](https://protection.office.com) los destinatarios de dominios externos. [](mail-flow-insights-v2.md)

![Widget de mensajes reenviados automáticamente en el Centro de seguridad & cumplimiento](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Detalles de mensajes reenviados automáticamente

Al hacer clic en el número de mensajes del widget, aparece un panel flotante que muestra más información sobre los mensajes reenviados automáticamente:

- **Mensajes reenviados automáticamente mediante métodos de reenvío:**

  - **Por reglas de flujo de correo**
  - **Por reglas de la Bandeja de entrada**
  - **Mediante reenvío SMTP:** este método indica el reenvío automático que los administradores pueden configurar en un buzón, tal como se describe en [Configure email forwarding for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).
  - Un vínculo al informe [de reenvío](view-mail-flow-reports.md#forwarding-report) para obtener más información.

- **Mensajes reenviados automáticamente por dominios y usuarios:**

  - **Principales 5 dominios reenviados a**
  - **Nuevos dominios (la semana pasada)**
  - **Principales 5 usuarios de reenvío**
  - **Nuevos usuarios (la semana pasada)**
  - Un vínculo al informe [de modificaciones de reenvío](mfi-new-users-forwarding-email.md#forwarding-modifications-report) para obtener más información.

![Control de detalles del informe de mensajes reenviados automáticamente en el Centro de seguridad y & cumplimiento](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>Insights

Se generan dos perspectivas en función de los datos del informe:

- [Nuevos usuarios reenviar correo electrónico](mfi-new-users-forwarding-email.md)
- [Nuevos dominios que se reenvía correo electrónico](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>Consulte también

Para obtener información acerca de otras perspectivas en el panel flujo de correo, vea [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).