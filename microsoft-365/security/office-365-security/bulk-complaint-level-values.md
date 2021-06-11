---
title: Valores de nivel de queja masiva
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre los valores de nivel de queja masiva (BCL) que se usan en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11f884ec6b32795deba09c0f1ba88055a6422e9b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537948"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="f47d4-103">Nivel de queja masiva (BCL) en EOP</span><span class="sxs-lookup"><span data-stu-id="f47d4-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f47d4-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="f47d4-104">**Applies to**</span></span>
- [<span data-ttu-id="f47d4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f47d4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f47d4-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="f47d4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f47d4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f47d4-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f47d4-108">En Microsoft 365 organizaciones con buzones en organizaciones de Exchange Online o independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, EOP asigna un nivel de queja masiva (BCL) a los mensajes entrantes de los buzones masivos.</span><span class="sxs-lookup"><span data-stu-id="f47d4-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk complaint level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="f47d4-109">El BCL se agrega al mensaje en un encabezado X y es similar al nivel de confianza de correo no deseado [(SCL)](spam-confidence-levels.md) que se usa para identificar mensajes como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="f47d4-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="f47d4-110">Un BCL más alto indica que un mensaje masivo es más probable que genere quejas (y, por lo tanto, es más probable que sea correo no deseado).</span><span class="sxs-lookup"><span data-stu-id="f47d4-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="f47d4-111">Microsoft usa orígenes internos y de terceros para identificar el correo masivo y determinar el BCL adecuado.</span><span class="sxs-lookup"><span data-stu-id="f47d4-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="f47d4-112">Los remitentes masivos varían en sus patrones de envío, creación de contenido y prácticas de adquisición de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="f47d4-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="f47d4-113">Los buenos carteros masivos envían mensajes deseados con contenido relevante a sus suscriptores.</span><span class="sxs-lookup"><span data-stu-id="f47d4-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="f47d4-114">Estos mensajes generan pocas quejas por parte de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="f47d4-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="f47d4-115">Otros troyanos de envío masivo de correo electrónico envían mensajes no solicitados muy similares al correo no deseado y generan muchas quejas por parte de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="f47d4-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="f47d4-116">Los mensajes de un correo masivo se conocen como correo masivo o correo gris.</span><span class="sxs-lookup"><span data-stu-id="f47d4-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="f47d4-117">El filtrado de  correo no deseado marca los mensajes como correo electrónico masivo en función del umbral BCL (el valor predeterminado o un valor que especifique) y realiza la acción especificada en el mensaje (la acción predeterminada es entregar el mensaje a la carpeta correo no deseado del destinatario).</span><span class="sxs-lookup"><span data-stu-id="f47d4-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="f47d4-118">Para obtener más información, vea [Configure anti-spam policies](configure-your-spam-filter-policies.md) y [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="f47d4-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="f47d4-119">Puede usar la lista de inquilinos permitidos o bloqueados para configurar excepciones para el filtrado masivo de correo.</span><span class="sxs-lookup"><span data-stu-id="f47d4-119">You can use the Tenant Allow/Block List to configure exceptions for bulk mail filtering.</span></span> <span data-ttu-id="f47d4-120">Los mensajes de remitentes de los dominios especificados no reciben la acción para el veredicto de filtrado de **correo** no deseado masivo en directivas contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="f47d4-120">Messages from senders in the specified domains don't receive the action for the **Bulk email** spam filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="f47d4-121">Para obtener más información, vea [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span><span class="sxs-lookup"><span data-stu-id="f47d4-121">For more information, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

<span data-ttu-id="f47d4-122">Los umbrales BCL se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f47d4-122">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="f47d4-123">BCL</span><span class="sxs-lookup"><span data-stu-id="f47d4-123">BCL</span></span>|<span data-ttu-id="f47d4-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="f47d4-124">Description</span></span>|
|:---:|---|
|<span data-ttu-id="f47d4-125">0</span><span class="sxs-lookup"><span data-stu-id="f47d4-125">0</span></span>|<span data-ttu-id="f47d4-126">El mensaje no es de un remitente de correo masivo.</span><span class="sxs-lookup"><span data-stu-id="f47d4-126">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="f47d4-127">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="f47d4-127">1, 2, 3</span></span>|<span data-ttu-id="f47d4-128">El mensaje proviene de un remitente de correo masivo que genera pocas quejas.</span><span class="sxs-lookup"><span data-stu-id="f47d4-128">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="f47d4-129">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f47d4-129">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="f47d4-130">El mensaje proviene de un remitente de correo masivo que genera un número mixto de quejas.</span><span class="sxs-lookup"><span data-stu-id="f47d4-130">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="f47d4-131">8, 9</span><span class="sxs-lookup"><span data-stu-id="f47d4-131">8, 9</span></span>|<span data-ttu-id="f47d4-132">El mensaje es de un remitente masivo que genera un gran número de quejas.</span><span class="sxs-lookup"><span data-stu-id="f47d4-132">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="f47d4-133"><sup>\*</sup> Este es el valor de umbral predeterminado que se usa en las directivas contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="f47d4-133"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
