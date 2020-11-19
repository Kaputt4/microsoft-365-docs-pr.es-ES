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
ms.openlocfilehash: a72ffd001ea22972d9dc6c00af8a4dd7881386b7
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356960"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="874c8-103">Nuevos dominios que se reenvían el conocimiento del correo electrónico en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="874c8-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="874c8-104">Hay razones empresariales válidas para reenviar mensajes de correo electrónico a destinatarios externos en dominios específicos.</span><span class="sxs-lookup"><span data-stu-id="874c8-104">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="874c8-105">Sin embargo, es sospechoso cuando los usuarios de la organización inician repentinamente el reenvío de mensajes a un dominio en el que nadie de la organización ha reenviado mensajes a (un dominio nuevo).</span><span class="sxs-lookup"><span data-stu-id="874c8-105">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="874c8-106">Esta condición puede indicar que las cuentas de usuario están en peligro.</span><span class="sxs-lookup"><span data-stu-id="874c8-106">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="874c8-107">Si sospecha que las cuentas se han puesto en peligro, consulte [responder a una cuenta de correo electrónico en peligro](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="874c8-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="874c8-108">Los **nuevos dominios que se reenvían** el conocimiento de correo electrónico del [centro de seguridad & cumplimiento](https://protection.office.com) le notifican cuando los usuarios de la organización reenvían mensajes a nuevos dominios.</span><span class="sxs-lookup"><span data-stu-id="874c8-108">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="874c8-109">Esta información sólo aparece cuando se detecta el problema y aparece en la página de [reenvío del informe](view-mail-flow-reports.md#forwarding-report) .</span><span class="sxs-lookup"><span data-stu-id="874c8-109">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Información de nuevos dominios a los que se reenvía correo electrónico](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="874c8-111">Al hacer clic en el widget, aparece un control flotante donde puede encontrar más detalles sobre los mensajes reenviados, incluido un vínculo al [Informe de reenvío](view-mail-flow-reports.md#forwarding-report).</span><span class="sxs-lookup"><span data-stu-id="874c8-111">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Control flotante de detalles que aparece después de hacer clic en los nuevos dominios que se reenviaron el conocimiento de correo electrónico](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="874c8-113">También puede obtener acceso a esta página de detalles si selecciona la información después de hacer clic en **ver todo** en el área de **recomendaciones &** información sobre (**Reports** \> **Panel** de informes o <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="874c8-113">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="874c8-114">Para evitar el reenvío automático de mensajes a dominios externos, configure un dominio remoto para algunos o todos los dominios externos.</span><span class="sxs-lookup"><span data-stu-id="874c8-114">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="874c8-115">Para obtener más información, vea [administrar dominios remotos en Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span><span class="sxs-lookup"><span data-stu-id="874c8-115">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="874c8-116">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="874c8-116">Related topics</span></span>

<span data-ttu-id="874c8-117">Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="874c8-117">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
