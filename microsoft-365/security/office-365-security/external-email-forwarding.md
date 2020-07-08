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
ms.openlocfilehash: 88c3dae4f5a6786fe4eddea0d5e1c61dda837a87
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080118"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a><span data-ttu-id="a2dcf-103">Configurar el reenvío externo de correo electrónico en Office 365</span><span class="sxs-lookup"><span data-stu-id="a2dcf-103">Configuring external email forwarding in Office 365</span></span>

<span data-ttu-id="a2dcf-104">El reenvío externo se controla mediante la *Directiva de correo no deseado saliente* y se establece en el ámbito de los usuarios en función de la configuración configurada.</span><span class="sxs-lookup"><span data-stu-id="a2dcf-104">External forwarding is controlled by the *outbound anti-spam policy* and scoped to users based on the configured setting.</span></span> <span data-ttu-id="a2dcf-105">Actualmente se admite la configuración de 3:</span><span class="sxs-lookup"><span data-stu-id="a2dcf-105">Currently 3 settings are supported:</span></span>

- <span data-ttu-id="a2dcf-106">**Automático** : en este modo, el sistema es responsable de decidir si se permite o no un mensaje reenviado.</span><span class="sxs-lookup"><span data-stu-id="a2dcf-106">**Automatic** – In this mode the system is responsible for deciding if a forwarded message is allowed or not.</span></span>  <span data-ttu-id="a2dcf-107">Este es el modo predeterminado y, en este modo, el sistema bloqueará el reenvío externo automático.</span><span class="sxs-lookup"><span data-stu-id="a2dcf-107">This is the default mode and in this mode the system will block automatic external forwarding.</span></span>

- <span data-ttu-id="a2dcf-108">**Activado** : el reenvío externo automático se permite y no está restringido.</span><span class="sxs-lookup"><span data-stu-id="a2dcf-108">**On** – Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="a2dcf-109">**Desactivado** : el reenvío externo automático está deshabilitado y dará como resultado un informe de no entrega (NDR) al usuario final.</span><span class="sxs-lookup"><span data-stu-id="a2dcf-109">**Off** – Automatic external forwarding is disabled and will result in a Non-delivery report (NDR) to the end user.</span></span>

<span data-ttu-id="a2dcf-110">Para obtener más información sobre cómo configurar estas opciones, vea [configurar el filtrado de correo no deseado saliente en EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide) .</span><span class="sxs-lookup"><span data-stu-id="a2dcf-110">See [Configure outbound spam filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide) for more information on how to configure these settings.</span></span>

## <a name="controlling-external-email-forwarding"></a><span data-ttu-id="a2dcf-111">Controlar el reenvío de correo electrónico externo</span><span class="sxs-lookup"><span data-stu-id="a2dcf-111">Controlling external email forwarding</span></span>

<span data-ttu-id="a2dcf-112">Como administrador de una organización, es posible que los requisitos de la compañía tengan que restringir o controlar quién puede reenviar automáticamente los correos electrónicos con las reglas de la bandeja de entrada o el reenvío SMTP, fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="a2dcf-112">As an admin of an organization you may have company requirements to restrict or control who is able to automatically forward emails using inbox rules, or SMTP forwarding, outside of the organization.</span></span> <span data-ttu-id="a2dcf-113">El reenvío de correo electrónico puede ser una característica útil, pero también puede suponer un riesgo a través de la posible revelación de información, incluso proporcionando información a los atacantes que pueden aprovecharse para atacar a la organización o a sus asociados.</span><span class="sxs-lookup"><span data-stu-id="a2dcf-113">Email forwarding can be a useful feature, but can also pose a risk through the potential disclosure of information, even by providing information to attackers that can be leveraged to attack the organization or its partners.</span></span>

<span data-ttu-id="a2dcf-114">Office 365 no permite el reenvío externo automático por reglas de la bandeja de entrada o por la configuración de buzón de correo, lo que proporciona una directiva predeterminada segura.</span><span class="sxs-lookup"><span data-stu-id="a2dcf-114">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mail box configuration, which provides a secure default policy.</span></span> <span data-ttu-id="a2dcf-115">Sin embargo, el administrador puede modificar esta configuración para todos o algunos de los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="a2dcf-115">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="a2dcf-116">El reenvío de mensajes entre usuarios internos no se ve afectado por esta modificación.</span><span class="sxs-lookup"><span data-stu-id="a2dcf-116">Forwarding messages between internal users isn't affected by such a modification.</span></span>

> [!NOTE]
> <span data-ttu-id="a2dcf-117">Deshabilitar el reenvío automático a direcciones externas en Office 365 se está implementando en fases con detalles que se comunican a través de las publicaciones del [centro de mensajes](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) .</span><span class="sxs-lookup"><span data-stu-id="a2dcf-117">Disabling automatic forwarding to external addresses in Office 365 is being rolled out in phases with details communicated via [Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) posts.</span></span> <span data-ttu-id="a2dcf-118">Para ayudar a los administradores a preparar estos cambios, pídales que modifiquen las directivas con anticipación para asegurarse de que no hay interrupciones para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="a2dcf-118">To help administrators prepare for these changes have them modify policies ahead of time to ensure there is no disruption to their users.</span></span>

<span data-ttu-id="a2dcf-119">Puede encontrar más información acerca de los usuarios que usan el reenvío automático (reglas de la bandeja de entrada o reenvío SMTP) en el [Informe de mensajes reenviados automáticamente](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="a2dcf-119">More information about users that are using automatic forwarding (inbox rules or SMTP forwarding) in your organization can be found in the [auto-forwarded messages report](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide).</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="a2dcf-120">Mensaje de reenvío de correo electrónico bloqueado</span><span class="sxs-lookup"><span data-stu-id="a2dcf-120">The blocked email forwarding message</span></span>

<span data-ttu-id="a2dcf-121">Cuando se detecta un mensaje como reenviado automáticamente y la directiva organizativa *bloquea* dicha actividad, se generará un **Informe de no entrega (NDR)** para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="a2dcf-121">When a message is detected as automatically forwarded and the organizational policy *blocks* that activity a **Non-delivery report (NDR)** will be generated back to the end user.</span></span> <span data-ttu-id="a2dcf-122">El informe indicará que el mensaje no se entregó.</span><span class="sxs-lookup"><span data-stu-id="a2dcf-122">The report will indicate the message was not delivered.</span></span> <span data-ttu-id="a2dcf-123">El NDR tendrá el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="a2dcf-123">The NDR will have the following format:</span></span> 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
