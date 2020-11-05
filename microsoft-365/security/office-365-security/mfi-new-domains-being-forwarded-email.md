---
title: Información de nuevos dominios a los que se reenvía correo electrónico
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Los administradores pueden aprender a usar los nuevos dominios que reenviaron el conocimiento del correo electrónico en el panel de flujo de correo en el centro de seguridad & cumplimiento para investigar Cuándo sus usuarios reenvían mensajes a dominios externos a los que nunca se ha reenviado.
ms.openlocfilehash: f2d8c9229062cbef0ad90b3d0fd843d6588a08dc
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920576"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Nuevos dominios que se reenvían el conocimiento del correo electrónico en el centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Hay razones empresariales válidas para reenviar mensajes de correo electrónico a destinatarios externos en dominios específicos. Sin embargo, es sospechoso cuando los usuarios de la organización inician repentinamente el reenvío de mensajes a un dominio en el que nadie de la organización ha reenviado mensajes a (un dominio nuevo).

Esta condición puede indicar que las cuentas de usuario están en peligro. Si sospecha que las cuentas se han puesto en peligro, consulte [responder a una cuenta de correo electrónico en peligro](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).

Los **nuevos dominios que se reenvían** el conocimiento de correo electrónico del [centro de seguridad & cumplimiento](https://protection.office.com) le notifican cuando los usuarios de la organización reenvían mensajes a nuevos dominios.

Esta información sólo aparece cuando se detecta el problema y aparece en la página de [reenvío del informe](view-mail-flow-reports.md#forwarding-report) .

![Información de nuevos dominios a los que se reenvía correo electrónico](../../media/mfi-new-domains-being-forwarded.png)

Al hacer clic en el widget, aparece un control flotante donde puede encontrar más detalles sobre los mensajes reenviados, incluido un vínculo al [Informe de reenvío](view-mail-flow-reports.md#forwarding-report).

![Control flotante de detalles que aparece después de hacer clic en los nuevos dominios que se reenviaron el conocimiento de correo electrónico](../../media/mfi-new-domains-being-forwarded-details.png)

También puede obtener acceso a esta página de detalles si selecciona la información después de hacer clic en **ver todo** en el área de **recomendaciones &** información sobre ( **Reports** \> **Panel** de informes o <https://protection.office.com/insightdashboard> ).

Para evitar el reenvío automático de mensajes a dominios externos, configure un dominio remoto para algunos o todos los dominios externos. Para obtener más información, vea [administrar dominios remotos en Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).

## <a name="related-topics"></a>Temas relacionados

Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
