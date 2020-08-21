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
ms.openlocfilehash: 8d1a3ffe5ffc16a7793826b98b130121b8e68599
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827032"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Mensajes reenviados automáticamente información sobre el centro de seguridad & cumplimiento

La introducción a los **mensajes reenviados automáticamente** del [Panel flujo de correo](mail-flow-insights-v2.md) del centro de seguridad & cumplimiento muestra información acerca de los mensajes que se reenvían automáticamente desde la organización a los destinatarios de dominios externos.

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

## <a name="see-also"></a>Consulte también

Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
