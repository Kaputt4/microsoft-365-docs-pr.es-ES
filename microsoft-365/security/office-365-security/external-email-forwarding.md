---
title: Configurar y controlar el reenvío externo de correo electrónico, el reenvío automático, 5.7.520 acceso denegado, deshabilitar el reenvío externo, el administrador deshabilitó el reenvío externo, la Directiva de correo no deseado saliente
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: c0a3849d330b508630eb60c7ee24cd8b498a32b8
ms.sourcegitcommit: 260c69fa31a898428d51cfdbd762c5f0213c403c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "48417226"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a><span data-ttu-id="8cf2b-103">Configurar el reenvío externo de correo electrónico en Office 365</span><span class="sxs-lookup"><span data-stu-id="8cf2b-103">Configuring external email forwarding in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="8cf2b-104">El reenvío externo se controla mediante la *Directiva de correo no deseado saliente* y se establece en el ámbito de los usuarios en función de la configuración configurada.</span><span class="sxs-lookup"><span data-stu-id="8cf2b-104">External forwarding is controlled by the *outbound anti-spam policy* and scoped to users based on the configured setting.</span></span> <span data-ttu-id="8cf2b-105">Actualmente se admite la configuración de 3:</span><span class="sxs-lookup"><span data-stu-id="8cf2b-105">Currently 3 settings are supported:</span></span>

- <span data-ttu-id="8cf2b-106">**Automático** : esto está controlado por el sistema: permite el filtrado de correo no deseado saliente para controlar el reenvío de correo electrónico externo automático.</span><span class="sxs-lookup"><span data-stu-id="8cf2b-106">**Automatic** – This is system-controlled: It allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="8cf2b-107">Esta configuración es la predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8cf2b-107">This is the default setting.</span></span>

- <span data-ttu-id="8cf2b-108">**Activado** : el reenvío externo automático se permite y no está restringido.</span><span class="sxs-lookup"><span data-stu-id="8cf2b-108">**On** – Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="8cf2b-109">**Desactivado** : el reenvío externo automático está deshabilitado y dará como resultado un informe de no entrega (NDR) al usuario final.</span><span class="sxs-lookup"><span data-stu-id="8cf2b-109">**Off** – Automatic external forwarding is disabled and will result in a Non-delivery report (NDR) to the end user.</span></span>

<span data-ttu-id="8cf2b-110">Para obtener más información sobre cómo configurar estas opciones, vea [configurar el filtrado de correo no deseado saliente en EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) .</span><span class="sxs-lookup"><span data-stu-id="8cf2b-110">See [Configure outbound spam filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) for more information on how to configure these settings.</span></span>

> [!NOTE]
> <span data-ttu-id="8cf2b-111">Al deshabilitar el reenvío automático también se deshabilitan las reglas de la bandeja de entrada que redirigen mensajes a direcciones externas.</span><span class="sxs-lookup"><span data-stu-id="8cf2b-111">Disabling automatic forwarding will also disable Inbox rules that redirect messages to external addresses.</span></span>

## <a name="controlling-external-email-forwarding"></a><span data-ttu-id="8cf2b-112">Controlar el reenvío de correo electrónico externo</span><span class="sxs-lookup"><span data-stu-id="8cf2b-112">Controlling external email forwarding</span></span>

<span data-ttu-id="8cf2b-113">Como administrador de una organización, es posible que los requisitos de la compañía tengan que restringir o controlar quién puede reenviar automáticamente los correos electrónicos con las reglas de la bandeja de entrada o el reenvío SMTP, fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="8cf2b-113">As an admin of an organization you may have company requirements to restrict or control who is able to automatically forward emails using inbox rules, or SMTP forwarding, outside of the organization.</span></span> <span data-ttu-id="8cf2b-114">El reenvío de correo electrónico puede ser una característica útil, pero también puede suponer un riesgo a través de la posible revelación de información, incluso proporcionando información a los atacantes que pueden aprovecharse para atacar a la organización o a sus asociados.</span><span class="sxs-lookup"><span data-stu-id="8cf2b-114">Email forwarding can be a useful feature, but can also pose a risk through the potential disclosure of information, even by providing information to attackers that can be leveraged to attack the organization or its partners.</span></span>

<span data-ttu-id="8cf2b-115">Office 365 no permite el reenvío externo automático por reglas de la bandeja de entrada o por la configuración de buzón de correo, lo que proporciona una directiva predeterminada segura.</span><span class="sxs-lookup"><span data-stu-id="8cf2b-115">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mail box configuration, which provides a secure default policy.</span></span> <span data-ttu-id="8cf2b-116">Sin embargo, el administrador puede modificar esta configuración para todos o algunos de los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="8cf2b-116">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="8cf2b-117">El reenvío de mensajes entre usuarios internos no se ve afectado por esta modificación.</span><span class="sxs-lookup"><span data-stu-id="8cf2b-117">Forwarding messages between internal users isn't affected by such a modification.</span></span>

> [!NOTE]
> <span data-ttu-id="8cf2b-118">Deshabilitar el reenvío automático a direcciones externas en Office 365 se está implementando en fases con detalles que se comunican a través de las publicaciones del [centro de mensajes](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) .</span><span class="sxs-lookup"><span data-stu-id="8cf2b-118">Disabling automatic forwarding to external addresses in Office 365 is being rolled out in phases with details communicated via [Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) posts.</span></span> <span data-ttu-id="8cf2b-119">Para ayudar a los administradores a preparar estos cambios, pídales que modifiquen las directivas con anticipación para asegurarse de que no hay interrupciones para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="8cf2b-119">To help administrators prepare for these changes have them modify policies ahead of time to ensure there is no disruption to their users.</span></span>

<span data-ttu-id="8cf2b-120">Puede encontrar más información acerca de los usuarios que usan el reenvío automático (reglas de la bandeja de entrada o reenvío SMTP) en el [Informe de mensajes reenviados automáticamente](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="8cf2b-120">More information about users that are using automatic forwarding (inbox rules or SMTP forwarding) in your organization can be found in the [auto-forwarded messages report](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).</span></span>

## <a name="how-does-this-policy-work-with-other-automatic-forwarding-controls"></a><span data-ttu-id="8cf2b-121">Cómo funciona esta directiva con otros controles de reenvío automático</span><span class="sxs-lookup"><span data-stu-id="8cf2b-121">How does this policy work with other automatic forwarding controls</span></span>

<span data-ttu-id="8cf2b-122">Como administrador, es posible que ya tenga otros tipos de controles en su ubicación, lo que bloquea el reenvío automático en [dominios remotos](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) y el uso de una regla de transporte de Exchange (ETR).</span><span class="sxs-lookup"><span data-stu-id="8cf2b-122">As an admin, you may already have other types of controls in place, such blocking automatic forwarding in [remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) and the use of an Exchange Transport Rule (ETR).</span></span> <span data-ttu-id="8cf2b-123">Ambos controles son independientes de esta característica, por ejemplo, si se permite el reenvío automático para un dominio remoto, pero se bloquea el desvío automático a través de la Directiva de correo no deseado saliente, el resultado será que el mensaje reenviado automáticamente está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="8cf2b-123">Both of these controls are independent of this particular feature, for example if you allow automatic forwarding for a remote domain, but block automatic forwarding via the outbound spam policy the result will be that the automatically forwarded message is blocked.</span></span> <span data-ttu-id="8cf2b-124">De forma similar, si se permite el reenvío automático en la Directiva de correo no deseado saliente, pero se bloquea en un dominio de ETR o remoto, cualquiera de estos controles bloqueará el mensaje.</span><span class="sxs-lookup"><span data-stu-id="8cf2b-124">Similarly if you allow automatic forwarding in the outbound spam policy but block it in an ETR or remote domain then the message will be blocked by either of these controls.</span></span> <span data-ttu-id="8cf2b-125">Esto le permite, por ejemplo, permitir el reenvío automático en la Directiva de correo no deseado saliente y usar dominios remotos para controlar los dominios a los que los usuarios pueden reenviar mensajes automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8cf2b-125">This allows you to, for example, allow automatic forwarding in the outbound spam policy and utilize remote domains to control the domains that users can automatic forward messages to.</span></span>


## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="8cf2b-126">Mensaje de reenvío de correo electrónico bloqueado</span><span class="sxs-lookup"><span data-stu-id="8cf2b-126">The blocked email forwarding message</span></span>

<span data-ttu-id="8cf2b-127">Cuando se detecta un mensaje como reenviado automáticamente y la directiva organizativa *bloquea* dicha actividad, se generará un **Informe de no entrega (NDR)** para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="8cf2b-127">When a message is detected as automatically forwarded and the organizational policy *blocks* that activity a **Non-delivery report (NDR)** will be generated back to the end user.</span></span> <span data-ttu-id="8cf2b-128">El informe indicará que el mensaje no se entregó.</span><span class="sxs-lookup"><span data-stu-id="8cf2b-128">The report will indicate the message was not delivered.</span></span> <span data-ttu-id="8cf2b-129">El NDR tendrá el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="8cf2b-129">The NDR will have the following format:</span></span> 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
