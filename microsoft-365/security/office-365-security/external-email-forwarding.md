---
title: Configurar y controlar el reenvío de correo electrónico externo, el reenvío automático, el acceso 5.7.520 denegado, deshabilitar el reenvío externo, El administrador ha deshabilitado el reenvío externo, la directiva contra correo no deseado saliente
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77f666e5eeceee3f5b324e5b9b6fac721c10e410
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286878"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="d208d-103">Controlar el reenvío automático de correo electrónico externo en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d208d-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d208d-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="d208d-104">**Applies to**</span></span>
- [<span data-ttu-id="d208d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d208d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d208d-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="d208d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="d208d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d208d-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="d208d-108">Como administrador, es posible que tenga requisitos de la empresa para restringir o controlar los mensajes reenviados automáticamente a destinatarios externos (destinatarios fuera de la organización).</span><span class="sxs-lookup"><span data-stu-id="d208d-108">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="d208d-109">El reenvío de correo electrónico puede ser útil, pero también puede suponer un riesgo para la seguridad debido a la posible divulgación de información.</span><span class="sxs-lookup"><span data-stu-id="d208d-109">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="d208d-110">Los atacantes pueden usar esta información para atacar a su organización o socios.</span><span class="sxs-lookup"><span data-stu-id="d208d-110">Attackers might use this information to attack your organization or partners.</span></span>


<span data-ttu-id="d208d-111">Los siguientes tipos de reenvío automático están disponibles en Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="d208d-111">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="d208d-112">Los usuarios pueden configurar [reglas de](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) la Bandeja de entrada para reenviar automáticamente mensajes a remitentes externos (deliberadamente o como resultado de una cuenta comprometida).</span><span class="sxs-lookup"><span data-stu-id="d208d-112">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="d208d-113">Los administradores pueden configurar [el reenvío de](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) buzones (también conocido como reenvío _SMTP)_ para reenviar mensajes automáticamente a destinatarios externos.</span><span class="sxs-lookup"><span data-stu-id="d208d-113">Admins can configure [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="d208d-114">El administrador puede elegir si simplemente reenviar mensajes o conservar copias de mensajes reenviados en el buzón.</span><span class="sxs-lookup"><span data-stu-id="d208d-114">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="d208d-115">Puede usar directivas de filtro de correo no deseado saliente para controlar el reenvío automático a destinatarios externos.</span><span class="sxs-lookup"><span data-stu-id="d208d-115">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="d208d-116">Hay tres opciones de configuración disponibles:</span><span class="sxs-lookup"><span data-stu-id="d208d-116">Three settings are available:</span></span>

- <span data-ttu-id="d208d-117">**Automático:** se bloquea el reenvío externo automático.</span><span class="sxs-lookup"><span data-stu-id="d208d-117">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="d208d-118">El reenvío automático interno de mensajes seguirá funcionando.</span><span class="sxs-lookup"><span data-stu-id="d208d-118">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="d208d-119">Esta configuración es la predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d208d-119">This is the default setting.</span></span>
- <span data-ttu-id="d208d-120">**On:** Se permite y no se restringe el reenvío externo automático.</span><span class="sxs-lookup"><span data-stu-id="d208d-120">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="d208d-121">**Desactivado:** el reenvío externo automático está deshabilitado y dará como resultado un informe de no entrega (también conocido como NDR o mensaje de detección) al remitente.</span><span class="sxs-lookup"><span data-stu-id="d208d-121">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="d208d-122">Para obtener instrucciones sobre cómo configurar estas opciones, vea Configurar el [filtrado de correo no deseado saliente en EOP.](configure-the-outbound-spam-policy.md)</span><span class="sxs-lookup"><span data-stu-id="d208d-122">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="d208d-123">Deshabilitar el reenvío automático deshabilita las reglas de la Bandeja de entrada (usuarios) o el reenvío de buzones (administradores) que redirigen mensajes a direcciones externas.</span><span class="sxs-lookup"><span data-stu-id="d208d-123">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="d208d-124">El reenvío automático de mensajes entre usuarios internos no se ve afectado por la configuración de las directivas de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="d208d-124">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="d208d-125">Puede ver información sobre los usuarios que reenvía automáticamente mensajes a destinatarios externos en el informe de mensajes [reenviados automáticamente.](mfi-auto-forwarded-messages-report.md)</span><span class="sxs-lookup"><span data-stu-id="d208d-125">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="d208d-126">Cómo funciona la configuración de la directiva de filtro de correo no deseado saliente con otros controles de reenvío automático de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="d208d-126">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="d208d-127">Como administrador, es posible que ya haya configurado otros controles para permitir o bloquear el reenvío automático de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d208d-127">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="d208d-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d208d-128">For example:</span></span>

- <span data-ttu-id="d208d-129">[Dominios remotos para](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) permitir o bloquear el reenvío automático de correo electrónico a algunos o todos los dominios externos.</span><span class="sxs-lookup"><span data-stu-id="d208d-129">[Remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="d208d-130">Condiciones y acciones en las reglas [de flujo](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) de correo de Exchange (también conocidas como reglas de transporte) para detectar y bloquear mensajes reenviados automáticamente a destinatarios externos.</span><span class="sxs-lookup"><span data-stu-id="d208d-130">Conditions and actions in Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="d208d-131">La configuración del dominio remoto y las reglas de flujo de correo son independientes de la configuración de las directivas de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="d208d-131">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="d208d-132">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d208d-132">For example:</span></span>

- <span data-ttu-id="d208d-133">Permite el reenvío automático para un dominio remoto, pero bloquea el reenvío automático en las directivas de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="d208d-133">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="d208d-134">En este ejemplo, se bloquean los mensajes reenviados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d208d-134">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="d208d-135">Permite el reenvío automático en directivas de filtro de correo no deseado saliente, pero usa reglas de flujo de correo o configuración de dominio remoto para bloquear el correo electrónico reenviado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d208d-135">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="d208d-136">En este ejemplo, las reglas de flujo de correo o la configuración de dominio remoto bloquearán los mensajes reenviados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d208d-136">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="d208d-137">Esta independencia de características le permite (por ejemplo) permitir el reenvío automático en directivas de filtro de correo no deseado saliente, pero usar dominios remotos para controlar los dominios externos a los que los usuarios pueden reenviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="d208d-137">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="blocked-email-forwarding-messages"></a><span data-ttu-id="d208d-138">Mensajes de reenvío de correo electrónico bloqueados</span><span class="sxs-lookup"><span data-stu-id="d208d-138">Blocked email forwarding messages</span></span>

<span data-ttu-id="d208d-139">Cuando se detecta que un mensaje se [](configure-the-outbound-spam-policy.md) reenvía automáticamente y la directiva de filtro de correo no deseado saliente bloquea esa actividad, el mensaje se devuelve al remitente en un NDR que contiene la siguiente información: </span><span class="sxs-lookup"><span data-stu-id="d208d-139">When a message is detected as automatically forwarded, and the [outbound spam filter](configure-the-outbound-spam-policy.md) policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
