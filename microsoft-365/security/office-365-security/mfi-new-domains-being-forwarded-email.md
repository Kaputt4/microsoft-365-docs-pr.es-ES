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
description: Los administradores pueden aprender a usar la información de correo electrónico nuevos dominios que se reenvía en el panel flujo de correo del Centro de seguridad y cumplimiento de & para investigar cuándo sus usuarios reenvía mensajes a dominios externos a los que nunca se ha reenviado.
ms.technology: mdo
ms.prod: m365-security
ms.collection: M365-security-compliance
ms.openlocfilehash: e23d63a519bf69f94ce4990d8851d673826dcb5c
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64475089"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Nuevos dominios que se reenvía información de correo electrónico en el Centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Existen motivos empresariales válidos para reenviar mensajes de correo electrónico a destinatarios externos en dominios específicos. Sin embargo, es sospechoso cuando los usuarios de la organización comienzan de repente a reenviar mensajes a un dominio al que nadie de la organización haya reenviado mensajes (un nuevo dominio).

Esta condición puede indicar que las cuentas de usuario están en peligro. Si sospecha que las cuentas se han visto comprometidas, consulte [Responder a una cuenta de correo electrónico comprometida](responding-to-a-compromised-email-account.md).

La **información de correo** electrónico nuevos dominios que se reenvía en el [Centro de seguridad & cumplimiento](https://protection.office.com) le notifica cuándo los usuarios de su organización reenvía mensajes a nuevos dominios.

Esta información solo aparece cuando se detecta el problema y aparece en la página [Informe de reenvío](view-mail-flow-reports.md#forwarding-report) .

:::image type="content" source="../../media/mfi-new-domains-being-forwarded.png" alt-text="La información de correo electrónico de nuevos dominios que se reenvía" lightbox="../../media/mfi-new-domains-being-forwarded.png":::


Al hacer clic en el widget, aparece un control flotante donde puede encontrar más detalles sobre los mensajes reenviados, incluido un vínculo al informe [de reenvío](view-mail-flow-reports.md#forwarding-report).

:::image type="content" source="../../media/mfi-new-domains-being-forwarded-details.png" alt-text="El menú desplegable Detalles que aparece después de hacer clic en los nuevos dominios que se reenvía la información de correo electrónico" lightbox="../../media/mfi-new-domains-being-forwarded-details.png":::

También puede acceder a esta página de detalles al seleccionar la información después de hacer clic  en Ver todo en  el área Principales & **recomendaciones en (** \> Panel de **informes o ).** <https://protection.office.com/insightdashboard>

Para evitar el reenvío automático de mensajes a dominios externos, configure un dominio remoto para algunos o todos los dominios externos. Para obtener más información, vea [Manage remote domains in Exchange Online](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).

## <a name="related-topics"></a>Temas relacionados

Para obtener información sobre otras perspectivas en el panel flujo de correo, vea Información sobre el flujo de correo en el [Centro de seguridad & cumplimiento](mail-flow-insights-v2.md).