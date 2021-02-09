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
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="ac30c-103">Información sobre nuevos dominios que se reenvía de correo electrónico en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="ac30c-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ac30c-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="ac30c-104">**Applies to**</span></span>
- [<span data-ttu-id="ac30c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ac30c-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="ac30c-106">Microsoft Defender para Office 365 plan 1 y plan 2</span><span class="sxs-lookup"><span data-stu-id="ac30c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="ac30c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac30c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="ac30c-108">Existen motivos empresariales válidos para reenviar mensajes de correo electrónico a destinatarios externos en dominios específicos.</span><span class="sxs-lookup"><span data-stu-id="ac30c-108">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="ac30c-109">Sin embargo, es sospechoso cuando los usuarios de su organización comienzan de pronto a reenviar mensajes a un dominio al que nadie de la organización haya reenviado mensajes (un nuevo dominio).</span><span class="sxs-lookup"><span data-stu-id="ac30c-109">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="ac30c-110">Esta condición puede indicar que las cuentas de usuario están en peligro.</span><span class="sxs-lookup"><span data-stu-id="ac30c-110">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="ac30c-111">Si sospecha que las cuentas se han visto comprometidas, consulte [Responder a una cuenta de correo electrónico en peligro.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="ac30c-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="ac30c-112">La **información sobre los nuevos** dominios que se reenvía de correo electrónico en el Centro de seguridad & [Cumplimiento](https://protection.office.com) le notifica cuándo los usuarios de su organización reenván mensajes a nuevos dominios.</span><span class="sxs-lookup"><span data-stu-id="ac30c-112">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="ac30c-113">Esta información solo aparece cuando se detecta el problema y aparece en la [página del informe de reenvío.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="ac30c-113">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Información de nuevos dominios a los que se reenvía correo electrónico](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="ac30c-115">Al hacer clic en el widget, aparece un control flotante donde puede encontrar más detalles sobre los mensajes reenviados, incluido un vínculo al informe [de reenvío.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="ac30c-115">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Menú desplegable de detalles que aparece después de hacer clic en la información de correo electrónico de reenvío de nuevos dominios](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="ac30c-117">También puede acceder a esta página de detalles  cuando seleccione la información después de hacer clic en Ver todo en el área de información **superior &** recomendaciones **(** Panel de informes \>  o <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="ac30c-117">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="ac30c-118">Para evitar el reenvío automático de mensajes a dominios externos, configure un dominio remoto para algunos o todos los dominios externos.</span><span class="sxs-lookup"><span data-stu-id="ac30c-118">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="ac30c-119">Para obtener más información, vea [Administrar dominios remotos en Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)</span><span class="sxs-lookup"><span data-stu-id="ac30c-119">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ac30c-120">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ac30c-120">Related topics</span></span>

<span data-ttu-id="ac30c-121">Para obtener información sobre otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="ac30c-121">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
