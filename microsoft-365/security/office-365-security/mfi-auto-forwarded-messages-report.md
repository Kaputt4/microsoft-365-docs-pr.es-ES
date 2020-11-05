---
title: Información de mensajes reenviados automáticamente
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Los administradores pueden obtener información sobre el informe de mensajes reenviados automáticamente en el panel de flujo de correo en el centro de seguridad & cumplimiento.
ms.openlocfilehash: 28cb593d56d0b0054c8c8cbe4596d4f7df6442ab
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920601"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Mensajes reenviados automáticamente información sobre el centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


La introducción a los **mensajes reenviados automáticamente** del [Panel flujo de correo](mail-flow-insights-v2.md) del [centro de seguridad & cumplimiento](https://protection.office.com) muestra información acerca de los mensajes que se reenvían automáticamente desde la organización a los destinatarios de dominios externos.

![Widget de mensajes reenviados automáticamente en el centro de seguridad & cumplimiento](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Detalles de los mensajes reenviados automáticamente

Al hacer clic en el número de mensajes del widget, aparece un panel de control flotante que muestra más información sobre los mensajes reenviados automáticamente:

- Mensajes reenviados **automáticamente mediante métodos de reenvío** :

  - **Por reglas de flujo de correo**
  - **Por reglas de la bandeja de entrada**
  - **Por el reenvío SMTP** : este método indica el reenvío automático que los administradores pueden configurar en un buzón como se describe en [configurar el reenvío de correo electrónico para un buzón](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).
  - Un vínculo al [Informe de reenvío](view-mail-flow-reports.md#forwarding-report) para obtener más información.

- **Mensajes reenviados automáticamente por dominios y usuarios** :

  - **Los 5 primeros dominios se reenvían a**
  - **Nuevos dominios (última semana)**
  - **5 principales usuarios de reenvío**
  - **Nuevos usuarios (última semana)**
  - Un vínculo al [Informe de modificaciones de reenvío](mfi-new-users-forwarding-email.md#forwarding-modifications-report) para obtener más información.

![Control flotante de detalles del informe de mensajes reenviados automáticamente en el centro de seguridad & cumplimiento](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>Información

Se generan dos perspectivas en función de los datos del informe:

- [Reenviar correo electrónico a los nuevos usuarios](mfi-new-users-forwarding-email.md)
- [Nuevos dominios que se reenvían correo electrónico](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>Vea también

Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
