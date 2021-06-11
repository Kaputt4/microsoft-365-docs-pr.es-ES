---
title: ¿Cuál &apos; es la diferencia entre el correo no deseado y el correo masivo?
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
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre las diferencias entre el correo no deseado (correo no deseado) y el correo masivo (correo gris) en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fc9c94946c3da2f9a14f45070a86c557a5c7dc85
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207554"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="de789-103">¿Cuál es la diferencia entre el correo no deseado y el correo masivo en EOP?</span><span class="sxs-lookup"><span data-stu-id="de789-103">What's the difference between junk email and bulk email in EOP?</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="de789-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="de789-104">**Applies to**</span></span>
- [<span data-ttu-id="de789-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="de789-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="de789-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="de789-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="de789-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="de789-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="de789-108">En Microsoft 365 organizaciones con buzones en organizaciones de Exchange Online o independientes de Exchange Online Protection (EOP) sin buzones de correo de Exchange Online, los clientes a veces preguntan: "¿cuál es la diferencia entre el correo electrónico no deseado y el correo masivo?".</span><span class="sxs-lookup"><span data-stu-id="de789-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="de789-109">En este tema se explica la diferencia y se describen los controles que están disponibles en EOP.</span><span class="sxs-lookup"><span data-stu-id="de789-109">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="de789-110">**El correo no** deseado es correo no deseado, que son mensajes no solicitados y universalmente no deseados (cuando se identifican correctamente).</span><span class="sxs-lookup"><span data-stu-id="de789-110">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="de789-111">De forma predeterminada, EOP rechaza el correo no deseado en función de la reputación del servidor de correo electrónico de origen.</span><span class="sxs-lookup"><span data-stu-id="de789-111">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="de789-112">Si un mensaje pasa la inspección IP de origen, se envía al filtrado de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="de789-112">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="de789-113">Si el mensaje se clasifica como correo no deseado mediante el filtrado de correo no deseado, el mensaje se entrega (de forma predeterminada) a los destinatarios previstos y se mueve a su carpeta correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="de789-113">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="de789-114">Puede configurar las acciones que deben realizarse en los veredictos de filtrado de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="de789-114">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="de789-115">Para obtener instrucciones, vea [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="de789-115">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="de789-116">Si no está de acuerdo con el veredicto de filtrado de correo no deseado, puede notificar mensajes que considere correo no deseado o no deseado a Microsoft de varias maneras, como se describe en Notificar mensajes y archivos a [Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="de789-116">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="de789-117">**El correo electrónico masivo** (también conocido como _correo gris),_ es más difícil de clasificar.</span><span class="sxs-lookup"><span data-stu-id="de789-117">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="de789-118">Mientras que el correo no deseado es una amenaza constante, el correo masivo suele ser anuncios únicos o mensajes de marketing.</span><span class="sxs-lookup"><span data-stu-id="de789-118">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="de789-119">Algunos usuarios quieren mensajes de correo electrónico masivos (y de hecho, se han registrado deliberadamente para recibirlos), mientras que otros usuarios consideran que el correo electrónico masivo es correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="de789-119">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="de789-120">Por ejemplo, algunos usuarios desean recibir mensajes de publicidad de Contoso Corporation o invitaciones a una próxima conferencia sobre ciberseguridad, mientras que otros usuarios consideran que estos mismos mensajes son correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="de789-120">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="de789-121">Para obtener más información acerca de cómo se identifica el correo electrónico masivo, vea [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="de789-121">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="de789-122">Cómo administrar el correo masivo</span><span class="sxs-lookup"><span data-stu-id="de789-122">How to manage bulk email</span></span>

<span data-ttu-id="de789-123">Debido a la reacción mixta al correo electrónico masivo, no hay una guía universal que se aplique a todas las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="de789-123">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="de789-124">Las policías contra correo no deseado tienen un umbral BCL predeterminado que se usa para identificar el correo electrónico masivo como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="de789-124">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="de789-125">Los administradores pueden aumentar o disminuir el umbral.</span><span class="sxs-lookup"><span data-stu-id="de789-125">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="de789-126">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="de789-126">For more information, see the following topics:</span></span>

- <span data-ttu-id="de789-127">[Configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="de789-127">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="de789-128">Configuración de directiva contra correo no deseado de EOP</span><span class="sxs-lookup"><span data-stu-id="de789-128">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

<span data-ttu-id="de789-129">Otra opción que es fácil de pasar por alto: si un usuario se queja de recibir correo electrónico masivo, pero los mensajes son de remitentes de confianza que pasan el filtrado de correo no deseado en EOP, haga que el usuario compruebe si hay una opción de cancelación de suscripción en el mensaje de correo electrónico masivo.</span><span class="sxs-lookup"><span data-stu-id="de789-129">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
