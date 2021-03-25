---
title: Notificar correo electrónico no deseado y suplantación de identidad en Outlook para iOS y Android
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre las opciones de informes de correo electrónico de correo no deseado integrado, no correo no deseado y suplantación de identidad en Outlook para iOS y Android.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2c95f7b32d0d395e164d218c994b1608d36018d5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207407"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="03af2-103">Notificar correo electrónico no deseado y suplantación de identidad en Outlook para iOS y Android en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="03af2-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="03af2-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="03af2-104">**Applies to**</span></span>
- [<span data-ttu-id="03af2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="03af2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="03af2-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="03af2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="03af2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03af2-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="03af2-108">En las organizaciones de Microsoft 365 con buzones en Exchange Online o buzones locales con autenticación moderna [híbrida,](../../enterprise/hybrid-modern-auth-overview.md)puede enviar falsos positivos (correo electrónico bueno marcado como correo no deseado), falsos negativos (correo electrónico no permitido) y mensajes de suplantación de identidad a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="03af2-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="03af2-109">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="03af2-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="03af2-110">Para obtener la mejor experiencia de envío de usuarios, se recomienda usar el mensaje de informe y los complementos de suplantación de identidad de informes. Vea [Habilitar el complemento Mensaje de informe y](./enable-the-report-message-add-in.md) Habilitar el complemento de suplantación de identidad [de informes](./enable-the-report-phish-add-in.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="03af2-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](./enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](./enable-the-report-phish-add-in.md) for more information.</span></span>

- <span data-ttu-id="03af2-111">Si es administrador de una organización con buzones de Exchange Online, le recomendamos que use el portal de envíos en el Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="03af2-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="03af2-112">Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="03af2-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="03af2-113">Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique.</span><span class="sxs-lookup"><span data-stu-id="03af2-113">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="03af2-114">Para obtener más información, vea [User Submissions policies](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="03af2-114">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="03af2-115">Para obtener más información acerca de cómo notificar mensajes a Microsoft, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="03af2-115">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="03af2-116">Si los informes de correo no deseado están deshabilitados para Outlook en la directiva de envío de usuarios, los mensajes de correo no deseado o de suplantación de identidad se mueven a la carpeta de correo no deseado y no se notifican a su administrador o Microsoft.</span><span class="sxs-lookup"><span data-stu-id="03af2-116">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>