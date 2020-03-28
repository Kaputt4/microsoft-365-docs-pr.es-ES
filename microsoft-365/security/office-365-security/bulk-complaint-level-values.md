---
title: Valores de nivel de queja masiva, correo masivo, niveles de BCL, cómo funciona BCL, clasificaciones BCL, antispam, encabezado contra correo electrónico no deseado, filtrado de correo masivo, detener correo masivo
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Obtenga información sobre los valores del nivel de cumplimiento masivo (BCL) en Office 365.
ms.openlocfilehash: aa839fc1bcab141fe71c76e7f27b4f6bb23048b2
ms.sourcegitcommit: ce6121a8e3ca7438071d73b0c76e2b6f33ac1cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "43030157"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a><span data-ttu-id="c112e-103">Nivel de queja masiva (BCL) en Office 365</span><span class="sxs-lookup"><span data-stu-id="c112e-103">Bulk complaint level (BCL) in Office 365</span></span>

<span data-ttu-id="c112e-104">Los remitentes de correo masivo varían en sus patrones de envío, creación de contenido y prácticas de adquisición de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="c112e-104">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="c112e-105">Algunos son buenos correos masivos que envían mensajes deseados con contenido relevante a sus suscriptores.</span><span class="sxs-lookup"><span data-stu-id="c112e-105">Some are good bulk mailers that send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="c112e-106">Estos mensajes generan pocas quejas por parte de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="c112e-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="c112e-107">Otros troyanos de envío masivo de correo electrónico envían mensajes no solicitados muy similares al correo no deseado y generan muchas quejas por parte de los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="c112e-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="c112e-108">Los mensajes de un envío masivo de correo se conoce como correo masivo o de correo gris.</span><span class="sxs-lookup"><span data-stu-id="c112e-108">Messages from a bulk mailer is known as bulk mail or gray mail.</span></span>

<span data-ttu-id="c112e-109">Para distinguir mensajes de distintos tipos de correo masivo, el correo electrónico entrante de correo masivo a Office 365 (Exchange online o Exchange Online Protection (EOP) sin buzones de correo de Exchange Online) tiene asignado un nivel de queja masiva (BCL) que se agrega a mensaje en un encabezado X.</span><span class="sxs-lookup"><span data-stu-id="c112e-109">To distinguish messages from different types of bulk mailers, inbound email from bulk mailers to Office 365 (Exchange Online or standalone Exchange Online Protection (EOP) without Exchange Online mailboxes) is assigned a bulk complaint level (BCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="c112e-110">La BCL es similar al [nivel de confianza contra correo no deseado (SCL)](spam-confidence-levels.md) que se usa para identificar mensajes como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="c112e-110">The BCL is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="c112e-111">Una BCL superior indica que un mensaje masivo tiene más probabilidades de generar quejas (y, por lo tanto, es más probable que sea correo no deseado).</span><span class="sxs-lookup"><span data-stu-id="c112e-111">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="c112e-112">Microsoft usa orígenes internos y de terceros para identificar el correo masivo y determinar la BCL adecuada.</span><span class="sxs-lookup"><span data-stu-id="c112e-112">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

 <span data-ttu-id="c112e-113">El filtrado de correo no deseado marca los mensajes como **correo masivo** en función del umbral de BCL (el valor predeterminado o un valor especificado) y toma la acción especificada en el mensaje (la acción predeterminada es entregar el mensaje en la carpeta de correo no deseado del destinatario).</span><span class="sxs-lookup"><span data-stu-id="c112e-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="c112e-114">Para obtener más información, vea [configurar directivas contra correo no deseado en Office 365](configure-your-spam-filter-policies.md) y [¿cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="c112e-114">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="c112e-115">Los umbrales de BCL se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c112e-115">The BCL thresholds are described in the following table.</span></span>

|||
|:---:|---|
|<span data-ttu-id="c112e-116">**BCL**</span><span class="sxs-lookup"><span data-stu-id="c112e-116">**BCL**</span></span>|<span data-ttu-id="c112e-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c112e-117">**Description**</span></span>|
|<span data-ttu-id="c112e-118">comprendi</span><span class="sxs-lookup"><span data-stu-id="c112e-118">0</span></span>|<span data-ttu-id="c112e-119">El mensaje no es de un remitente de correo masivo.</span><span class="sxs-lookup"><span data-stu-id="c112e-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="c112e-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="c112e-120">1, 2, 3</span></span>|<span data-ttu-id="c112e-121">El mensaje proviene de un remitente de correo masivo que genera pocas quejas.</span><span class="sxs-lookup"><span data-stu-id="c112e-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="c112e-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="c112e-122">4, 5, 6, 7</span></span>|<span data-ttu-id="c112e-123">El mensaje proviene de un remitente de correo masivo que genera un número mixto de quejas.</span><span class="sxs-lookup"><span data-stu-id="c112e-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="c112e-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="c112e-124">8, 9</span></span>|<span data-ttu-id="c112e-125">El mensaje proviene de un remitente masivo que genera un gran número de quejas.</span><span class="sxs-lookup"><span data-stu-id="c112e-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
