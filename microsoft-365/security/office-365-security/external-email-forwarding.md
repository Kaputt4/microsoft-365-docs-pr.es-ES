---
title: Configurar y controlar el reenvío externo de correo electrónico, el reenvío automático, 5.7.520 acceso denegado, deshabilitar el reenvío externo, el administrador deshabilitó el reenvío externo, la Directiva de correo no deseado saliente
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 76cd560c3b97bb67d25d2e4ff2c219669c3d4f0d
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658886"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="f99c6-103">Controlar el reenvío de correo electrónico externo automático en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f99c6-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f99c6-104">Como administrador, puede tener los requisitos de la compañía para restringir o controlar los mensajes reenviados automáticamente a los destinatarios externos (destinatarios fuera de la organización).</span><span class="sxs-lookup"><span data-stu-id="f99c6-104">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="f99c6-105">El reenvío de correo electrónico puede resultar útil, pero también puede suponer un riesgo de seguridad debido a la posible revelación de información.</span><span class="sxs-lookup"><span data-stu-id="f99c6-105">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="f99c6-106">Los atacantes podrían usar esta información para atacar a su organización o a sus socios.</span><span class="sxs-lookup"><span data-stu-id="f99c6-106">Attackers might use this information to attack your organization or partners.</span></span>

<span data-ttu-id="f99c6-107">Los siguientes tipos de reenvío automático están disponibles en Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="f99c6-107">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="f99c6-108">Los usuarios pueden configurar [las reglas](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) de la bandeja de entrada para reenviar mensajes de forma automática a los remitentes externos (deliberadamente o como resultado de una cuenta en peligro).</span><span class="sxs-lookup"><span data-stu-id="f99c6-108">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="f99c6-109">Los administradores pueden configurar el [reenvío de buzón](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (también conocido como reenvío _SMTP_) para reenviar mensajes automáticamente a los destinatarios externos.</span><span class="sxs-lookup"><span data-stu-id="f99c6-109">Admins can configure [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="f99c6-110">El administrador puede elegir si simplemente reenviar los mensajes o conservar copias de los mensajes reenviados en el buzón.</span><span class="sxs-lookup"><span data-stu-id="f99c6-110">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="f99c6-111">Puede usar las directivas de filtro de correo no deseado saliente para controlar el reenvío automático a los destinatarios externos.</span><span class="sxs-lookup"><span data-stu-id="f99c6-111">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="f99c6-112">Hay tres opciones de configuración disponibles:</span><span class="sxs-lookup"><span data-stu-id="f99c6-112">Three settings are available:</span></span>

- <span data-ttu-id="f99c6-113">**Automático**: el reenvío externo automático está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="f99c6-113">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="f99c6-114">El reenvío automático interno de los mensajes seguirá funcionando.</span><span class="sxs-lookup"><span data-stu-id="f99c6-114">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="f99c6-115">Esta configuración es la predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f99c6-115">This is the default setting.</span></span>
- <span data-ttu-id="f99c6-116">**On**: el reenvío externo automático está permitido y no está restringido.</span><span class="sxs-lookup"><span data-stu-id="f99c6-116">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="f99c6-117">**Desactivado**: el reenvío externo automático está deshabilitado y dará como resultado un informe de no entrega (también conocido como mensaje NDR o de devolución) al remitente.</span><span class="sxs-lookup"><span data-stu-id="f99c6-117">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="f99c6-118">Para obtener instrucciones sobre cómo configurar estas opciones, vea [configurar el filtrado de correo no deseado saliente en EOP](configure-the-outbound-spam-policy.md).</span><span class="sxs-lookup"><span data-stu-id="f99c6-118">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="f99c6-119">Al deshabilitar el reenvío automático se deshabilita cualquier regla de la bandeja de entrada (usuarios) o reenvío de buzón (administradores) que redirigen mensajes a direcciones externas.</span><span class="sxs-lookup"><span data-stu-id="f99c6-119">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="f99c6-120">El reenvío automático de mensajes entre usuarios internos no se ve afectado por la configuración de las directivas de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="f99c6-120">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="f99c6-121">Puede ver información sobre los usuarios que reenvían automáticamente los mensajes a los destinatarios externos en el [Informe de mensajes reenviados automáticamente](mfi-auto-forwarded-messages-report.md).</span><span class="sxs-lookup"><span data-stu-id="f99c6-121">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="f99c6-122">Cómo funciona la configuración de la Directiva de filtro de correo no deseado saliente con otros controles de reenvío de correo electrónico automático</span><span class="sxs-lookup"><span data-stu-id="f99c6-122">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="f99c6-123">Como administrador, es posible que ya haya configurado otros controles para permitir o bloquear el reenvío automático de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f99c6-123">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="f99c6-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f99c6-124">For example:</span></span>

- <span data-ttu-id="f99c6-125">[Dominios remotos](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) para permitir o bloquear el reenvío automático de correo electrónico a algunos o todos los dominios externos.</span><span class="sxs-lookup"><span data-stu-id="f99c6-125">[Remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="f99c6-126">Condiciones y acciones de [las reglas de flujo de correo](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) de Exchange (también conocidas como reglas de transporte) para detectar y bloquear mensajes reenviados automáticamente a destinatarios externos.</span><span class="sxs-lookup"><span data-stu-id="f99c6-126">Conditions and actions in Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="f99c6-127">La configuración del dominio remoto y las reglas de flujo de correo son independientes de la configuración en las directivas de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="f99c6-127">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="f99c6-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f99c6-128">For example:</span></span>

- <span data-ttu-id="f99c6-129">Permite el reenvío automático para un dominio remoto, pero bloquea el reenvío automático en las directivas de filtro de correo no deseado saliente.</span><span class="sxs-lookup"><span data-stu-id="f99c6-129">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="f99c6-130">En este ejemplo, los mensajes reenviados automáticamente están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="f99c6-130">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="f99c6-131">Permite el reenvío automático en las directivas de filtro de correo no deseado saliente, pero usa reglas de flujo de correo o la configuración de dominio remoto para bloquear el correo electrónico reenviado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f99c6-131">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="f99c6-132">En este ejemplo, las reglas de flujo de correo o la configuración de dominio remoto bloquearán los mensajes que se reenviarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f99c6-132">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="f99c6-133">Esta independencia de características le permite (por ejemplo) permitir el reenvío automático en las directivas de filtro de correo no deseado salientes, pero usa dominios remotos para controlar los dominios externos a los que los usuarios pueden reenviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="f99c6-133">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="f99c6-134">Mensaje de reenvío de correo electrónico bloqueado</span><span class="sxs-lookup"><span data-stu-id="f99c6-134">The blocked email forwarding message</span></span>

<span data-ttu-id="f99c6-135">Cuando se detecta un mensaje como reenviado automáticamente y la Directiva de la organización *bloquea* dicha actividad, el mensaje se devuelve al remitente en un NDR que contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="f99c6-135">When a message is detected as automatically forwarded, and the organizational policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
