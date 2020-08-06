---
title: Nuevos dominios que se reenvían el conocimiento de correo electrónico
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Los administradores pueden aprender a usar los nuevos dominios que reenvían el conocimiento del correo electrónico en el centro de administración de Exchange moderno para investigar Cuándo los usuarios de la organización reenvían mensajes a dominios externos a los que nunca se ha reenviado.
ms.openlocfilehash: 81a596d48696f28d62d68594f27081435487d17f
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578445"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Nuevos dominios que se reenvían el conocimiento del correo electrónico en el centro de seguridad & cumplimiento

Aunque puede tener motivos empresariales válidos para reenviar mensajes de correo electrónico a destinatarios externos en dominios específicos, es sospechoso cuando los usuarios de la organización inician repentinamente el reenvío de mensajes a dominios externos y nadie en la organización ha reenviado mensajes a esos dominios antes (nuevos dominios). Esta condición podría indicar que las cuentas de usuario están comprometidas. Si sospecha que las cuentas se han puesto en peligro, consulte [responder a una cuenta de correo electrónico en peligro](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).

El **nuevo dominio que se va a reenviar** le informa de que los usuarios de su organización reenvían mensajes a nuevos dominios.

Esta información sólo aparece cuando se detecta el problema y aparece en la página de [reenvío del informe](view-mail-flow-reports.md#forwarding-report) .

![Nuevos dominios que se reenvían el conocimiento de correo electrónico](../../media/mfi-new-domains-being-forwarded.png)

Al hacer clic en el widget, aparece un control flotante donde puede encontrar más detalles sobre los mensajes reenviados, incluido un vínculo al [Informe de reenvío](view-mail-flow-reports.md#forwarding-report).

![Control flotante de detalles que aparece después de hacer clic en los nuevos dominios que se reenviaron el conocimiento de correo electrónico](../../media/mfi-new-domains-being-forwarded-details.png)

También puede obtener acceso a esta página de detalles si selecciona la información después de hacer clic en **ver todo** en el área de **recomendaciones &** información sobre (**Reports** \> **Panel** de informes o <https://protection.office.com/insightdashboard> ).

Para evitar el reenvío automático de mensajes a dominios externos, configure un dominio remoto para algunos o todos los dominios externos. Para obtener más información, vea [administrar dominios remotos en Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).

## <a name="related-topics"></a>Temas relacionados

Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
