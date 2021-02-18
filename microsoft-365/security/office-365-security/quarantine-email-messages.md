---
title: Mensajes de correo electrónico en cuarentena
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre la cuarentena en Exchange Online Protection (EOP) que contiene mensajes potencialmente peligrosos o no deseados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 47742008af9c1cd0a0a17df9e43ebc0228a825b0
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288770"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="1cc3d-103">Mensajes de correo electrónico en cuarentena en EOP</span><span class="sxs-lookup"><span data-stu-id="1cc3d-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1cc3d-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="1cc3d-104">**Applies to**</span></span>
- [<span data-ttu-id="1cc3d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1cc3d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1cc3d-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="1cc3d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="1cc3d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1cc3d-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="1cc3d-108">En organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, la cuarentena está disponible para contener mensajes potencialmente peligrosos o no deseados.</span><span class="sxs-lookup"><span data-stu-id="1cc3d-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="1cc3d-109">Las directivas antimalware ponen automáticamente en cuarentena un mensaje si *se* encuentra algún dato adjunto que contenga malware.</span><span class="sxs-lookup"><span data-stu-id="1cc3d-109">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="1cc3d-110">Para obtener más información, vea [Configurar directivas antimalware en EOP.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="1cc3d-110">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="1cc3d-111">De forma predeterminada, las políticas contra correo no deseado ponen en cuarentena los mensajes de suplantación de identidad y entregan mensajes de correo no deseado y de correo masivo a la carpeta de correo no deseado del usuario.</span><span class="sxs-lookup"><span data-stu-id="1cc3d-111">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="1cc3d-112">Pero también puede crear y personalizar directivas contra correo no deseado para poner en cuarentena los mensajes de correo no deseado y de correo masivo.</span><span class="sxs-lookup"><span data-stu-id="1cc3d-112">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="1cc3d-113">Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1cc3d-113">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="1cc3d-114">Tanto los usuarios como los administradores pueden trabajar con mensajes en cuarentena:</span><span class="sxs-lookup"><span data-stu-id="1cc3d-114">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="1cc3d-115">Los administradores pueden trabajar con todos los tipos de mensajes en cuarentena para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="1cc3d-115">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="1cc3d-116">Solo los administradores pueden trabajar con mensajes que se han puesto en cuarentena como malware, suplantación de identidad de confianza alta o como resultado de reglas de flujo de correo (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="1cc3d-116">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="1cc3d-117">Para más información, consulte [Administrar mensajes en cuarentena y archivos como administrador en EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="1cc3d-117">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="1cc3d-118">Los usuarios pueden trabajar con mensajes en cuarentena donde son un destinatario si el mensaje se ha puesto en cuarentena como correo no deseado, correo masivo o suplantación de identidad (a partir de abril de 2020).</span><span class="sxs-lookup"><span data-stu-id="1cc3d-118">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="1cc3d-119">Para obtener más información, vea [Buscar y liberar mensajes en cuarentena como un usuario en EOP.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="1cc3d-119">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="1cc3d-120">Para evitar que los usuarios puedan administrar sus propios mensajes  de suplantación de identidad en cuarentena, los administradores pueden configurar una acción diferente para el veredicto de filtrado de correo electrónico de suplantación de identidad en las directivas contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="1cc3d-120">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="1cc3d-121">Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1cc3d-121">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="1cc3d-122">Los administradores y usuarios pueden notificar falsos positivos a Microsoft en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="1cc3d-122">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="1cc3d-123">Para obtener más información acerca de la cuarentena, consulte [Preguntas más frecuentes sobre cuarentena.](quarantine-faq.md)</span><span class="sxs-lookup"><span data-stu-id="1cc3d-123">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
