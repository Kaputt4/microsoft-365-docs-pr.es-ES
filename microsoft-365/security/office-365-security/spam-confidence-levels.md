---
title: Nivel de confianza de correo no deseado
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre el nivel de confianza contra correo no deseado (SCL) que se aplica a los mensajes en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e4fc20b7d7db5b85b5bdde02ab720fa26af2a4b5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167160"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="c8c47-103">Nivel de confianza contra correo no deseado (SCL) en EOP</span><span class="sxs-lookup"><span data-stu-id="c8c47-103">Spam confidence level (SCL) in EOP</span></span>

<span data-ttu-id="c8c47-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="c8c47-104">**Applies to**</span></span>
- [<span data-ttu-id="c8c47-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c8c47-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="c8c47-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c8c47-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="c8c47-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c8c47-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c8c47-108">En organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, los mensajes entrantes pasan por el filtrado de correo no deseado en EOP y se les asigna una puntuación de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="c8c47-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="c8c47-109">Esa puntuación se asigna a un nivel individual de confianza contra correo no deseado (SCL) que se agrega al mensaje en un encabezado X.</span><span class="sxs-lookup"><span data-stu-id="c8c47-109">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="c8c47-110">Un SCL superior indica que es más probable que un mensaje sea correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="c8c47-110">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="c8c47-111">EOP realiza una acción en el mensaje basado en el SCL.</span><span class="sxs-lookup"><span data-stu-id="c8c47-111">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="c8c47-112">En la tabla siguiente se describen los medios de SCL y las acciones predeterminadas que se toman en los mensajes.</span><span class="sxs-lookup"><span data-stu-id="c8c47-112">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="c8c47-113">Para obtener más información acerca de las acciones que puede realizar en los mensajes según el veredicto de filtrado de correo no deseado, vea Configurar directivas contra correo no deseado [en EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c8c47-113">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="c8c47-114">SCL</span><span class="sxs-lookup"><span data-stu-id="c8c47-114">SCL</span></span>|<span data-ttu-id="c8c47-115">Definición</span><span class="sxs-lookup"><span data-stu-id="c8c47-115">Definition</span></span>|<span data-ttu-id="c8c47-116">Acción predeterminada</span><span class="sxs-lookup"><span data-stu-id="c8c47-116">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="c8c47-117">-1</span><span class="sxs-lookup"><span data-stu-id="c8c47-117">-1</span></span>|<span data-ttu-id="c8c47-118">El mensaje omitió el filtrado de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="c8c47-118">The message skipped spam filtering.</span></span> <span data-ttu-id="c8c47-119">Por ejemplo, el mensaje es de un remitente seguro, se envió a un destinatario seguro o es de un servidor de origen de correo electrónico en la lista de direcciones IP permitidos.</span><span class="sxs-lookup"><span data-stu-id="c8c47-119">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="c8c47-120">Para obtener más información, vea [Crear listas de remitentes seguros en EOP.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="c8c47-120">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="c8c47-121">Se entrega el mensaje a la bandeja de entrada de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="c8c47-121">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="c8c47-122">0, 1</span><span class="sxs-lookup"><span data-stu-id="c8c47-122">0, 1</span></span>|<span data-ttu-id="c8c47-123">El filtrado de correo no deseado determinó que el mensaje no era correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="c8c47-123">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="c8c47-124">Se entrega el mensaje a la bandeja de entrada de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="c8c47-124">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="c8c47-125">5, 6</span><span class="sxs-lookup"><span data-stu-id="c8c47-125">5, 6</span></span>|<span data-ttu-id="c8c47-126">El filtrado de correo no deseado marcó el mensaje como **correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="c8c47-126">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="c8c47-127">El mensaje se entrega a la carpeta de Correo no deseado de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="c8c47-127">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="c8c47-128">9 </span><span class="sxs-lookup"><span data-stu-id="c8c47-128">9</span></span>|<span data-ttu-id="c8c47-129">El filtrado de correo no deseado marcó el mensaje **como correo no deseado de confianza alta**</span><span class="sxs-lookup"><span data-stu-id="c8c47-129">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="c8c47-130">El mensaje se entrega a la carpeta de Correo no deseado de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="c8c47-130">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="c8c47-131">Observará que el filtrado de correo no deseado no usa SCL 2, 3, 4, 7 y 8.</span><span class="sxs-lookup"><span data-stu-id="c8c47-131">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="c8c47-132">Puede usar reglas de flujo de correo (también conocidas como reglas de transporte) para marcar el SCL en los mensajes.</span><span class="sxs-lookup"><span data-stu-id="c8c47-132">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="c8c47-133">Si usa una regla de flujo de correo para establecer el SCL, los valores 5 o 6 desencadenan la acción de filtrado de correo no deseado para correo no deseado y los valores 7, 8 o 9 desencadenan la acción de filtrado de correo no deseado para correo no deseado de confianza **alta.**</span><span class="sxs-lookup"><span data-stu-id="c8c47-133">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="c8c47-134">Para obtener más información, vea Usar reglas de flujo de correo para establecer el nivel de confianza contra correo no deseado [(SCL) en los mensajes.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)</span><span class="sxs-lookup"><span data-stu-id="c8c47-134">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="c8c47-135">Al igual que el SCL, el nivel de queja masiva (BCL) identifica el correo electrónico masivo no deseado (también conocido como _correo gris)._</span><span class="sxs-lookup"><span data-stu-id="c8c47-135">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="c8c47-136">Un BCL superior indica que es más probable que un mensaje de correo masivo generen quejas (y, por lo tanto, es más probable que sea correo no deseado).</span><span class="sxs-lookup"><span data-stu-id="c8c47-136">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="c8c47-137">El umbral BCL se configura en directivas contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="c8c47-137">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="c8c47-138">Para obtener más información, vea Configure [anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP ,](bulk-complaint-level-values.md)and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span><span class="sxs-lookup"><span data-stu-id="c8c47-138">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

****

<span data-ttu-id="c8c47-139">![¿El icono corto de LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Nuevo en Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="c8c47-139">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="c8c47-140">Descubra cursos de vídeo gratuitos para administradores **de Microsoft 365** y profesionales de TI, que LinkedIn Learning le ofrece.</span><span class="sxs-lookup"><span data-stu-id="c8c47-140">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>
