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
description: Los administradores pueden obtener información sobre el informe de mensajes reenviados automáticamente en el panel flujo de correo del Centro de & cumplimiento.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c892400152df15adb3dfeb0c747ed7fae034d3d6
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029947"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Información sobre mensajes reenviados automáticamente en el Centro de & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


La **información de** mensajes reenviados automáticamente en el panel flujo de correo del Centro de seguridad y cumplimiento de [&](https://protection.office.com) muestra información sobre los mensajes que se reenvía automáticamente de la organización a los destinatarios de dominios externos. [](mail-flow-insights-v2.md)

![Widget Mensajes reenviados automáticamente en el Centro de & cumplimiento](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Detalles de mensajes reenviados automáticamente

Al hacer clic en el número de mensajes del widget, aparece un panel flotante que muestra más información sobre los mensajes reenviados automáticamente:

- **Mensajes reenviados automáticamente mediante métodos de reenvío:**

  - **Por reglas de flujo de correo**
  - **Por reglas de bandeja de entrada**
  - **Mediante el reenvío SMTP:** este método indica el reenvío automático que los administradores pueden configurar en un buzón como se describe en Configurar el reenvío de correo [electrónico para un buzón.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)
  - Un vínculo al informe [de reenvío](view-mail-flow-reports.md#forwarding-report) para obtener más información.

- **Mensajes reenviados automáticamente por dominios y usuarios:**

  - **Los 5 dominios principales reenviados a**
  - **Nuevos dominios (la semana pasada)**
  - **Principales 5 usuarios de reenvío**
  - **Nuevos usuarios (la semana pasada)**
  - Un vínculo al informe [de modificaciones de reenvío](mfi-new-users-forwarding-email.md#forwarding-modifications-report) para obtener más información.

![Control de detalles del informe de mensajes reenviados automáticamente en el Centro de & cumplimiento](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>Insights

Se generan dos perspectivas en función de los datos del informe:

- [Nuevos usuarios reenviando correo electrónico](mfi-new-users-forwarding-email.md)
- [Nuevos dominios que se reenván de correo electrónico](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>Consulta también

Para obtener información acerca de otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)
