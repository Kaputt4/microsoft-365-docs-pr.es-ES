---
title: ¿Cuál &apos; es la diferencia entre correo electrónico no deseado y correo electrónico masivo?
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
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre las diferencias entre el correo electrónico no deseado y el correo electrónico masivo (correo en gris) en Exchange Online Protection (EOP).
ms.openlocfilehash: c1f5ca724f7a41d9fc11ed0c93f52a79a6ecc8e5
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819441"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="578dd-103">¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo en EOP?</span><span class="sxs-lookup"><span data-stu-id="578dd-103">What's the difference between junk email and bulk email in EOP?</span></span>

<span data-ttu-id="578dd-104">En los clientes de Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, los clientes preguntan a veces: "¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?"</span><span class="sxs-lookup"><span data-stu-id="578dd-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="578dd-105">En este tema se explica la diferencia y se describen los controles que están disponibles en EOP.</span><span class="sxs-lookup"><span data-stu-id="578dd-105">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="578dd-106">El **correo no deseado** es correo no deseado, que son mensajes no solicitados y universales no deseados (cuando se identifica correctamente).</span><span class="sxs-lookup"><span data-stu-id="578dd-106">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="578dd-107">De forma predeterminada, EOP rechaza el correo no deseado en función de la reputación del servidor de correo electrónico de origen.</span><span class="sxs-lookup"><span data-stu-id="578dd-107">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="578dd-108">Si un mensaje pasa la inspección IP de origen, se envía al filtrado de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="578dd-108">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="578dd-109">Si el mensaje se clasifica como correo no deseado por el filtrado de correo no deseado, el mensaje se entrega (de forma predeterminada) a los destinatarios correspondientes y se mueve a la carpeta de correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="578dd-109">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="578dd-110">Puede configurar las acciones que se deben realizar en los veredictos del filtrado de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="578dd-110">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="578dd-111">Para obtener instrucciones, vea [configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="578dd-111">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="578dd-112">Si no está de acuerdo con el veredicto de filtrado de correo no deseado, puede informar de los mensajes que considera que son correo no deseado o correo no deseado de Microsoft de varias maneras, como se describe en [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="578dd-112">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="578dd-113">El **correo electrónico masivo** (también conocido como _correo gris_) es más difícil de clasificar.</span><span class="sxs-lookup"><span data-stu-id="578dd-113">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="578dd-114">Mientras que el correo no deseado es una amenaza constante, el correo electrónico masivo suele ser un mensaje publicitario de solo una vez o de marketing.</span><span class="sxs-lookup"><span data-stu-id="578dd-114">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="578dd-115">Algunos usuarios quieren mensajes de correo electrónico masivo (y, de hecho, se han registrado deliberadamente para recibirlos), mientras que otros usuarios consideran el correo electrónico masivo como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="578dd-115">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="578dd-116">Por ejemplo, algunos usuarios quieren recibir mensajes publicitarios de Contoso Corporation o invitaciones a una próxima Conferencia en la seguridad del ciberespacio, mientras que otros usuarios consideran que estos mismos mensajes son correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="578dd-116">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="578dd-117">Para obtener más información acerca de cómo se identifica el correo masivo, consulte [bulk reclamo LEVEL (BCL) in EOP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="578dd-117">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="578dd-118">Cómo administrar el correo masivo</span><span class="sxs-lookup"><span data-stu-id="578dd-118">How to manage bulk email</span></span>

<span data-ttu-id="578dd-119">Debido a la reacción mixta del correo electrónico masivo, no hay ninguna orientación universal que se aplique a todas las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="578dd-119">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="578dd-120">Las directivas contra el correo no deseado tienen un umbral de BCL predeterminado que se usa para identificar correo masivo como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="578dd-120">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="578dd-121">Los administradores pueden aumentar o disminuir el umbral.</span><span class="sxs-lookup"><span data-stu-id="578dd-121">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="578dd-122">Para obtener más información, vea los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="578dd-122">For more information, see the following topics:</span></span>

- <span data-ttu-id="578dd-123">[Configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="578dd-123">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="578dd-124">Configuración de la Directiva contra correo no deseado de EOP</span><span class="sxs-lookup"><span data-stu-id="578dd-124">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="578dd-125">Otra opción que es fácil de pasar por alto: Si un usuario se queja de recibir correo masivo en masa, pero los mensajes son de remitentes de confianza que superan el filtrado de correo no deseado en EOP, pida al usuario que compruebe si hay una opción para cancelar la suscripción en el mensaje de correo electrónico masivo.</span><span class="sxs-lookup"><span data-stu-id="578dd-125">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
