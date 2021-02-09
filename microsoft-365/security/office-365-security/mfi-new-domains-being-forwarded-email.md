---
title: Información de nuevos dominios a los que se reenvía correo electrónico
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Los administradores pueden aprender a usar la información sobre los nuevos dominios a los que se reenvía el correo electrónico en el panel flujo de correo del Centro de seguridad & Cumplimiento para investigar cuándo sus usuarios reenvía mensajes a dominios externos a los que nunca se ha reenviado.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a4429f1657861091082fdfaedb52c85cec3a0cc1
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150611"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Información sobre nuevos dominios que se reenvía de correo electrónico en el Centro de & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plan 1 y plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Existen motivos empresariales válidos para reenviar mensajes de correo electrónico a destinatarios externos en dominios específicos. Sin embargo, es sospechoso cuando los usuarios de su organización comienzan de pronto a reenviar mensajes a un dominio al que nadie de la organización haya reenviado mensajes (un nuevo dominio).

Esta condición puede indicar que las cuentas de usuario están en peligro. Si sospecha que las cuentas se han visto comprometidas, consulte [Responder a una cuenta de correo electrónico en peligro.](responding-to-a-compromised-email-account.md)

La **información sobre los nuevos** dominios que se reenvía de correo electrónico en el Centro de seguridad & [Cumplimiento](https://protection.office.com) le notifica cuándo los usuarios de su organización reenván mensajes a nuevos dominios.

Esta información solo aparece cuando se detecta el problema y aparece en la [página del informe de reenvío.](view-mail-flow-reports.md#forwarding-report)

![Información de nuevos dominios a los que se reenvía correo electrónico](../../media/mfi-new-domains-being-forwarded.png)

Al hacer clic en el widget, aparece un control flotante donde puede encontrar más detalles sobre los mensajes reenviados, incluido un vínculo al informe [de reenvío.](view-mail-flow-reports.md#forwarding-report)

![Menú desplegable de detalles que aparece después de hacer clic en la información de correo electrónico de reenvío de nuevos dominios](../../media/mfi-new-domains-being-forwarded-details.png)

También puede acceder a esta página de detalles  cuando seleccione la información después de hacer clic en Ver todo en el área de información **superior &** recomendaciones **(** Panel de informes \>  o <https://protection.office.com/insightdashboard> ).

Para evitar el reenvío automático de mensajes a dominios externos, configure un dominio remoto para algunos o todos los dominios externos. Para obtener más información, vea [Administrar dominios remotos en Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)

## <a name="related-topics"></a>Temas relacionados

Para obtener información sobre otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)
