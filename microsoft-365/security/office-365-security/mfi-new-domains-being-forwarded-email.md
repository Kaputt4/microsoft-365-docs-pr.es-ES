---
title: Información de nuevos dominios a los que se reenvía correo electrónico
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Los administradores pueden aprender a usar los nuevos dominios que reenvían el conocimiento del correo electrónico en el centro de administración de Exchange moderno para investigar Cuándo los usuarios de la organización reenvían mensajes a dominios externos a los que nunca se ha reenviado.
ms.openlocfilehash: 62e254e324322aec55d692cfe3128e8e4dd60e4b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200740"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="cf015-103">Nuevos dominios que se reenvían el conocimiento del correo electrónico en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="cf015-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="cf015-104">Aunque puede tener motivos empresariales válidos para reenviar mensajes de correo electrónico a destinatarios externos en dominios específicos, es sospechoso cuando los usuarios de la organización inician repentinamente el reenvío de mensajes a dominios externos y nadie en la organización ha reenviado mensajes a esos dominios antes (nuevos dominios).</span><span class="sxs-lookup"><span data-stu-id="cf015-104">Although you might have valid business reasons to forward email messages to external recipients in specific domains, it's suspicious when users in your organization suddenly start forwarding messages to external domains, and no one in the organization has ever forwarded messages to those domains before (new domains).</span></span> <span data-ttu-id="cf015-105">Esta condición podría indicar que las cuentas de usuario están comprometidas.</span><span class="sxs-lookup"><span data-stu-id="cf015-105">This condition could indicate the user accounts are compromised.</span></span> <span data-ttu-id="cf015-106">Si sospecha que las cuentas se han puesto en peligro, consulte [responder a una cuenta de correo electrónico en peligro](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span><span class="sxs-lookup"><span data-stu-id="cf015-106">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="cf015-107">Los **nuevos dominios que se reenvían** el conocimiento de correo electrónico del [centro de seguridad & cumplimiento](https://protection.office.com) le notifican cuando los usuarios de la organización reenvían mensajes a nuevos dominios.</span><span class="sxs-lookup"><span data-stu-id="cf015-107">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="cf015-108">Esta información sólo aparece cuando se detecta el problema y aparece en la página de [reenvío del informe](view-mail-flow-reports.md#forwarding-report) .</span><span class="sxs-lookup"><span data-stu-id="cf015-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Información de nuevos dominios a los que se reenvía correo electrónico](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="cf015-110">Al hacer clic en el widget, aparece un control flotante donde puede encontrar más detalles sobre los mensajes reenviados, incluido un vínculo al [Informe de reenvío](view-mail-flow-reports.md#forwarding-report).</span><span class="sxs-lookup"><span data-stu-id="cf015-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Control flotante de detalles que aparece después de hacer clic en los nuevos dominios que se reenviaron el conocimiento de correo electrónico](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="cf015-112">También puede obtener acceso a esta página de detalles si selecciona la información después de hacer clic en **ver todo** en el área de **recomendaciones &** información sobre (**Reports** \> **Panel** de informes o <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="cf015-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="cf015-113">Para evitar el reenvío automático de mensajes a dominios externos, configure un dominio remoto para algunos o todos los dominios externos.</span><span class="sxs-lookup"><span data-stu-id="cf015-113">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="cf015-114">Para obtener más información, vea [administrar dominios remotos en Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span><span class="sxs-lookup"><span data-stu-id="cf015-114">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cf015-115">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="cf015-115">Related topics</span></span>

<span data-ttu-id="cf015-116">Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="cf015-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
