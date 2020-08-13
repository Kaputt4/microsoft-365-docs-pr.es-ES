---
title: Valores de nivel de queja masiva
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre los valores del nivel de cumplimiento masivo (BCL) que se usan en Exchange Online Protection (EOP).
ms.openlocfilehash: 19fa7172bd242852d03822c588e163b7a13f9201
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653214"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="28e6b-103">Nivel de queja masiva (BCL) en EOP</span><span class="sxs-lookup"><span data-stu-id="28e6b-103">Bulk complaint level (BCL) in EOP</span></span>

<span data-ttu-id="28e6b-104">En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP asigna un nivel compatible con masa (BCL) a los mensajes entrantes de los correos masivos.</span><span class="sxs-lookup"><span data-stu-id="28e6b-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="28e6b-105">La BCL se agrega al mensaje en un encabezado X y es similar al [nivel de confianza contra correo no deseado (SCL)](spam-confidence-levels.md) que se usa para identificar mensajes como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="28e6b-105">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="28e6b-106">Una BCL superior indica que un mensaje masivo tiene más probabilidades de generar quejas (y, por lo tanto, es más probable que sea correo no deseado).</span><span class="sxs-lookup"><span data-stu-id="28e6b-106">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="28e6b-107">Microsoft usa orígenes internos y de terceros para identificar el correo masivo y determinar la BCL adecuada.</span><span class="sxs-lookup"><span data-stu-id="28e6b-107">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="28e6b-108">Los remitentes de correo masivo varían en sus patrones de envío, creación de contenido y prácticas de adquisición de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="28e6b-108">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="28e6b-109">Los envíos de correo en masa correctos envían los mensajes deseados con contenido relevante a sus suscriptores.</span><span class="sxs-lookup"><span data-stu-id="28e6b-109">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="28e6b-110">Estos mensajes generan pocas quejas por parte de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="28e6b-110">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="28e6b-111">Otros troyanos de envío masivo de correo electrónico envían mensajes no solicitados muy similares al correo no deseado y generan muchas quejas por parte de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="28e6b-111">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="28e6b-112">Los mensajes de un correo masivo se denominan correo masivo o gris.</span><span class="sxs-lookup"><span data-stu-id="28e6b-112">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="28e6b-113">El filtrado de correo no deseado marca los mensajes como **correo masivo** en función del umbral de BCL (el valor predeterminado o un valor especificado) y toma la acción especificada en el mensaje (la acción predeterminada es entregar el mensaje en la carpeta de correo no deseado del destinatario).</span><span class="sxs-lookup"><span data-stu-id="28e6b-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="28e6b-114">Para obtener más información, vea [configurar directivas contra correo no deseado](configure-your-spam-filter-policies.md) y [¿cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="28e6b-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="28e6b-115">Los umbrales de BCL se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="28e6b-115">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="28e6b-116">BCL</span><span class="sxs-lookup"><span data-stu-id="28e6b-116">BCL</span></span>|<span data-ttu-id="28e6b-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="28e6b-117">Description</span></span>|
|:---:|---|
|<span data-ttu-id="28e6b-118">comprendi</span><span class="sxs-lookup"><span data-stu-id="28e6b-118">0</span></span>|<span data-ttu-id="28e6b-119">El mensaje no es de un remitente de correo masivo.</span><span class="sxs-lookup"><span data-stu-id="28e6b-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="28e6b-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="28e6b-120">1, 2, 3</span></span>|<span data-ttu-id="28e6b-121">El mensaje proviene de un remitente de correo masivo que genera pocas quejas.</span><span class="sxs-lookup"><span data-stu-id="28e6b-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="28e6b-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="28e6b-122">4, 5, 6, 7</span></span>|<span data-ttu-id="28e6b-123">El mensaje proviene de un remitente de correo masivo que genera un número mixto de quejas.</span><span class="sxs-lookup"><span data-stu-id="28e6b-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="28e6b-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="28e6b-124">8, 9</span></span>|<span data-ttu-id="28e6b-125">El mensaje proviene de un remitente masivo que genera un gran número de quejas.</span><span class="sxs-lookup"><span data-stu-id="28e6b-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
