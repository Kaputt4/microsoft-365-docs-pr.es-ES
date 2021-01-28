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
ms.openlocfilehash: eb44f5d577d18fc38333cca5e8d2d862f288a2e0
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029863"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="7e72e-103">Información sobre nuevos dominios que se reenvía de correo electrónico en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="7e72e-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7e72e-104">Existen motivos empresariales válidos para reenviar mensajes de correo electrónico a destinatarios externos en dominios específicos.</span><span class="sxs-lookup"><span data-stu-id="7e72e-104">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="7e72e-105">Sin embargo, es sospechoso cuando los usuarios de su organización comienzan de pronto a reenviar mensajes a un dominio al que nadie de la organización haya reenviado mensajes (un nuevo dominio).</span><span class="sxs-lookup"><span data-stu-id="7e72e-105">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="7e72e-106">Esta condición puede indicar que las cuentas de usuario están en peligro.</span><span class="sxs-lookup"><span data-stu-id="7e72e-106">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="7e72e-107">Si sospecha que las cuentas se han visto comprometidas, consulte [Responder a una cuenta de correo electrónico en peligro.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="7e72e-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="7e72e-108">La **información sobre los nuevos** dominios que se reenvía de correo electrónico en el Centro de seguridad & [Cumplimiento](https://protection.office.com) le notifica cuándo los usuarios de su organización reenván mensajes a nuevos dominios.</span><span class="sxs-lookup"><span data-stu-id="7e72e-108">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="7e72e-109">Esta información solo aparece cuando se detecta el problema y aparece en la [página del informe de reenvío.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="7e72e-109">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Información de nuevos dominios a los que se reenvía correo electrónico](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="7e72e-111">Al hacer clic en el widget, aparece un control flotante donde puede encontrar más detalles sobre los mensajes reenviados, incluido un vínculo al informe [de reenvío.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="7e72e-111">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Menú desplegable de detalles que aparece después de hacer clic en la información de correo electrónico de reenvío de nuevos dominios](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="7e72e-113">También puede acceder a esta página de detalles  cuando seleccione la información después de hacer clic en Ver todo en el área de información **superior &** recomendaciones **(** Panel de informes \>  o <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="7e72e-113">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="7e72e-114">Para evitar el reenvío automático de mensajes a dominios externos, configure un dominio remoto para algunos o todos los dominios externos.</span><span class="sxs-lookup"><span data-stu-id="7e72e-114">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="7e72e-115">Para obtener más información, vea [Administrar dominios remotos en Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)</span><span class="sxs-lookup"><span data-stu-id="7e72e-115">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7e72e-116">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7e72e-116">Related topics</span></span>

<span data-ttu-id="7e72e-117">Para obtener información acerca de otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="7e72e-117">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
