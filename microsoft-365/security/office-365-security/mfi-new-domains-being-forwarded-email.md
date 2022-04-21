---
title: Información de nuevos dominios a los que se reenvía correo electrónico
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
ms.assetid: ''
description: Los administradores pueden aprender a usar la información de correo electrónico Nuevos dominios que se reenvían en el panel Flujo de correo del Centro de cumplimiento de seguridad & para investigar cuándo sus usuarios reenvían mensajes a dominios externos a los que nunca se han reenviado.
ms.technology: mdo
ms.prod: m365-security
ms.collection: M365-security-compliance
ms.openlocfilehash: 1dbcf83d234611af1d209d83191cee24f5bee579
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64974353"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Información de correo electrónico de nuevos dominios reenviados en el Centro de cumplimiento de seguridad &

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Hay motivos empresariales válidos para reenviar mensajes de correo electrónico a destinatarios externos en dominios específicos. Sin embargo, es sospechoso que los usuarios de su organización empiecen a reenviar mensajes de repente a un dominio en el que nadie de la organización haya reenviado mensajes a (un nuevo dominio).

Esta condición podría indicar que las cuentas de usuario están en peligro. Si sospecha que las cuentas se han puesto en peligro, consulte [Respuesta a una cuenta de correo electrónico en peligro](responding-to-a-compromised-email-account.md).

La información de **correo electrónico Nuevos dominios que se reenvía** en el [Centro de cumplimiento de seguridad &](https://protection.office.com) le notifica cuando los usuarios de su organización reenvía mensajes a nuevos dominios.

Esta información aparece solo cuando se detecta el problema y aparece en la página [del informe de reenvío](view-mail-flow-reports.md#forwarding-report) .

:::image type="content" source="../../media/mfi-new-domains-being-forwarded.png" alt-text="Información de correo electrónico de nuevos dominios que se reenvía" lightbox="../../media/mfi-new-domains-being-forwarded.png":::

Al hacer clic en el widget, aparece un control flotante donde puede encontrar más detalles sobre los mensajes reenviados, incluido un vínculo al [informe de reenvío](view-mail-flow-reports.md#forwarding-report).

:::image type="content" source="../../media/mfi-new-domains-being-forwarded-details.png" alt-text="El control flotante Detalles que aparece después de hacer clic en la información de correo electrónico Nuevos dominios que se reenvía" lightbox="../../media/mfi-new-domains-being-forwarded-details.png":::

También puede acceder a esta página de detalles al seleccionar la información después de hacer clic en **Ver todo** en el área **Conclusiones principales & recomendaciones** en (**Panel de** **informes** \> o <https://protection.office.com/insightdashboard>).

Para evitar el reenvío automático de mensajes a dominios externos, configure un dominio remoto para algunos o todos los dominios externos. Para obtener más información, consulte [Administración de dominios remotos en Exchange Online](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).

## <a name="related-topics"></a>Temas relacionados

Para obtener información sobre otras conclusiones en el panel Flujo de correo, consulte [Información de flujo de correo en el Centro de cumplimiento de seguridad &](mail-flow-insights-v2.md).
