---
title: Listas de remitentes seguros y bloqueados en Exchange Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: Como administrador de Exchange Online o Exchange Online Protection (EOP), puede ayudar a garantizar que un mensaje de correo que pasa a través del servicio no se marque como correo no deseado. Una forma de hacerlo es crear listas de remitentes bloqueados y de remitentes seguros para las personas de su organización.
ms.openlocfilehash: 959af558c32e71e5a4cede2aff7bbcd1dbb092e2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598517"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a><span data-ttu-id="b8417-104">Listas de remitentes seguros y bloqueados en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b8417-104">Safe sender and blocked sender lists in Exchange Online</span></span>

<span data-ttu-id="b8417-p102">Como administrador de Exchange Online o Exchange Online Protection (EOP), puede ayudar a garantizar que un mensaje de correo que pasa a través del servicio no se marque como correo no deseado. Una forma de hacerlo es crear listas de remitentes bloqueados y de remitentes seguros para las personas de su organización.</span><span class="sxs-lookup"><span data-stu-id="b8417-p102">As an Exchange Online or Exchange Online Protection (EOP) administrator, you can help ensure that an email message traveling through the service isn't marked as spam. One way to do this is to create safe sender and blocked sender lists for the people in your organization.</span></span>

<span data-ttu-id="b8417-107">*Vea la versión actualizada de las sugerencias y los procedimientos para trabajar con estas listas como administrador de* [Cómo evitar que el correo electrónico correcto se marque como correo no deseado en Office 365](prevent-email-from-being-marked-as-spam.md).</span><span class="sxs-lookup"><span data-stu-id="b8417-107">*See the updated version of the tips and procedures for how to work with these lists as an admin in* [How to prevent good email from being marked as spam in Office 365](prevent-email-from-being-marked-as-spam.md).</span></span>

<span data-ttu-id="b8417-108">Si no es un administrador y solo desea administrar su propio correo electrónico no deseado en Outlook mediante una lista de remitentes seguros, consulte los pasos de la[información general del filtro de correo electrónico no deseado](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span><span class="sxs-lookup"><span data-stu-id="b8417-108">If you're not an admin, and you just want to manage your own junk email in Outlook by using a safe sender list, check out the steps in the[Overview of the Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span>

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a><span data-ttu-id="b8417-109">¿Qué son los límites de remitentes seguros y bloqueados en Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="b8417-109">What is the safe and blocked sender limits in Exchange Online?</span></span>

<span data-ttu-id="b8417-p103">Los límites de remitentes seguros y bloqueados en Exchange Online difieren de los límites de Outlook y Active Directory. Son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b8417-p103">The safe and blocked sender limits in Exchange Online differ from the Active Directory and Outlook limits. They are:</span></span>

- <span data-ttu-id="b8417-112">Límite de remitentes seguros: 1.024</span><span class="sxs-lookup"><span data-stu-id="b8417-112">Safe sender limit: 1,024</span></span>

- <span data-ttu-id="b8417-113">Límite de remitentes bloqueados: 500</span><span class="sxs-lookup"><span data-stu-id="b8417-113">Blocked sender limit: 500</span></span>

<span data-ttu-id="b8417-114">Nota:</span><span class="sxs-lookup"><span data-stu-id="b8417-114">Note:</span></span>

<span data-ttu-id="b8417-115">Puede experimentar el error que se describe en [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span><span class="sxs-lookup"><span data-stu-id="b8417-115">You may experience the error that is described in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span></span> <span data-ttu-id="b8417-116">Para resolver este problema, desactive la casilla "confiar en mensajes de correo electrónico de mis contactos".</span><span class="sxs-lookup"><span data-stu-id="b8417-116">To resolve this issue, clear the "Trust emails from my contacts" check box.</span></span> <span data-ttu-id="b8417-117">También puede reducir la cantidad de direcciones de correo electrónico que se encuentran en la carpeta contactos predeterminada para que pasen al límite máximo permitido de 1024 en Exchange online que se establece para el atributo "parámetros maxsafesenders".</span><span class="sxs-lookup"><span data-stu-id="b8417-117">Alternatively, decrease the amount of email addresses that are in your default Contacts folder to bring it within the maximum allowed limit of 1024 in Exchange Online that is set for "MaxSafeSenders" attribute.</span></span> <span data-ttu-id="b8417-118">Para obtener más información sobre este atributo y el cmdlet Set-Mailbox, sobre elscript siguiente tema:</span><span class="sxs-lookup"><span data-stu-id="b8417-118">For more information about this attribute and the Set-Mailbox cmdlet, seethe following topic:</span></span>

[<span data-ttu-id="b8417-119">Set-Mailbox</span><span class="sxs-lookup"><span data-stu-id="b8417-119">Set-Mailbox</span></span>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a><span data-ttu-id="b8417-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8417-120">See also</span></span>

[<span data-ttu-id="b8417-121">Filtrado de remitentes en Exchange Server</span><span class="sxs-lookup"><span data-stu-id="b8417-121">Sender filtering in Exchange Server</span></span>](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
