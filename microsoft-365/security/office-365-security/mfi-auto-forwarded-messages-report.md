---
title: Información de mensajes reenviados automáticamente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Los administradores pueden obtener información sobre el informe de mensajes reenviados automáticamente en el panel de flujo de correo en el centro de seguridad & cumplimiento.
ms.openlocfilehash: b5255a95718fa6624c85e93a19c8accf9c3dcdb2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199364"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Mensajes reenviados automáticamente información sobre el centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


La introducción a los **mensajes reenviados automáticamente** del [Panel flujo de correo](mail-flow-insights-v2.md) del [centro de seguridad & cumplimiento](https://protection.office.com) muestra información acerca de los mensajes que se reenvían automáticamente desde la organización a los destinatarios de dominios externos.

![Widget de mensajes reenviados automáticamente en el centro de seguridad & cumplimiento](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Detalles de los mensajes reenviados automáticamente

Al hacer clic en el número de mensajes del widget, aparece un panel de control flotante que muestra más información sobre los mensajes reenviados automáticamente:

- Mensajes reenviados **automáticamente mediante métodos de reenvío**:

  - **Por reglas de flujo de correo**
  - **Por reglas de la bandeja de entrada**
  - **Por el reenvío SMTP**
  - Un vínculo al [Informe de reenvío](view-mail-flow-reports.md#forwarding-report) para obtener más información.

- **Mensajes reenviados automáticamente por dominios y usuarios**:

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
