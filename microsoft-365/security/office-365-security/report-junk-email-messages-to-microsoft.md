---
title: Notificar mensajes de correo no deseado, no deseado y suplantación de identidad a Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre las distintas formas de notificar mensajes y archivos buenos y malos a Microsoft para su análisis.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a89ea8a41a31c9544284566fade0e603d48af759
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082821"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="3f8aa-103">Notificar mensajes y archivos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3f8aa-103">Report messages and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3f8aa-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="3f8aa-104">**Applies to**</span></span>
- [<span data-ttu-id="3f8aa-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3f8aa-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3f8aa-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="3f8aa-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3f8aa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3f8aa-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="3f8aa-108">En Microsoft 365 organizaciones con buzones de correo en organizaciones de Exchange Online o independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, tanto los usuarios como los administradores tienen varios métodos diferentes para notificar mensajes de correo electrónico y archivos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3f8aa-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, both users and admins have several different methods for reporting email messages and files to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="3f8aa-109">Método</span><span class="sxs-lookup"><span data-stu-id="3f8aa-109">Method</span></span>|<span data-ttu-id="3f8aa-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="3f8aa-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="3f8aa-111">Usar el Envío para administradores para enviar correo no deseado, de suplantación de identidad, direcciones URL y archivos sospechosos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3f8aa-111">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="3f8aa-112">El método de informes recomendado para administradores de organizaciones con Exchange Online buzones de correo (no disponible en EOP independiente).</span><span class="sxs-lookup"><span data-stu-id="3f8aa-112">The recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="3f8aa-113">Habilitar el mensaje de informe o los complementos de suplantación de identidad de informes</span><span class="sxs-lookup"><span data-stu-id="3f8aa-113">Enable the Report Message or the Report Phishing add-ins</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="3f8aa-114">Funciona con Outlook y Outlook en la Web (anteriormente conocido como Outlook Web App).</span><span class="sxs-lookup"><span data-stu-id="3f8aa-114">Works with Outlook and Outlook on the web (formerly known as Outlook Web App).</span></span> <p> <span data-ttu-id="3f8aa-115">En función de la suscripción, los mensajes que los usuarios notificaron con los complementos están disponibles [](view-email-security-reports.md#user-reported-messages-report)en el portal de envíos de administración, los [resultados](admin-submission.md)de investigación y respuesta [automatizadas (AIR),](air-view-investigation-results.md)el informe de mensajes notificados por el usuario y el [Explorador](threat-explorer-views.md#email--submissions).</span><span class="sxs-lookup"><span data-stu-id="3f8aa-115">Depending on your subscription, messages that users reported with the add-ins are available in [the Admin Submissions portal](admin-submission.md), [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and [Explorer](threat-explorer-views.md#email--submissions).</span></span> <p> <span data-ttu-id="3f8aa-116">Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique.</span><span class="sxs-lookup"><span data-stu-id="3f8aa-116">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="3f8aa-117">Para obtener más información, vea [Directivas de envío de usuarios](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="3f8aa-117">For more information, see [User submissions policies](user-submission.md).</span></span>
|[<span data-ttu-id="3f8aa-118">Informar de falsos positivos y falsos negativos en Outlook</span><span class="sxs-lookup"><span data-stu-id="3f8aa-118">Report false positives and false negatives in Outlook</span></span>](report-false-positives-and-false-negatives.md)|<span data-ttu-id="3f8aa-119">Enviar falsos positivos (correo electrónico bueno bloqueado o enviado a la carpeta de correo no deseado) y falsos negativos (correo electrónico no deseado o suplantación de identidad que se entregó a la bandeja de entrada) a Exchange Online Protection (EOP) mediante la característica Mensaje de informe.</span><span class="sxs-lookup"><span data-stu-id="3f8aa-119">Submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP) using the Report Message feature.</span></span>|
|[<span data-ttu-id="3f8aa-120">Enviar mensajes manualmente a Microsoft para su análisis</span><span class="sxs-lookup"><span data-stu-id="3f8aa-120">Manually submit messages to Microsoft for analysis</span></span>](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|<span data-ttu-id="3f8aa-121">Envíe manualmente mensajes adjuntos a direcciones de correo electrónico específicas de Microsoft para correo no deseado, no correo no deseado y suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="3f8aa-121">Manually send attached messages to specific Microsoft email addresses for spam, not spam, and phishing.</span></span>|
|[<span data-ttu-id="3f8aa-122">Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3f8aa-122">Use mail flow rules to see what users are reporting to Microsoft</span></span>](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|<span data-ttu-id="3f8aa-123">Obtenga información sobre cómo crear una regla de flujo de correo (también conocida como regla de transporte) que le notifica cuándo los usuarios notifican mensajes a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="3f8aa-123">Learn how to create a mail flow rule (also known as a transport rule) that notifies you when users report messages to Microsoft for analysis.</span></span>|
|[<span data-ttu-id="3f8aa-124">Enviar malware y no malware a Microsoft para su análisis</span><span class="sxs-lookup"><span data-stu-id="3f8aa-124">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="3f8aa-125">Use el Inteligencia de seguridad de Microsoft web para enviar datos adjuntos y otros archivos.</span><span class="sxs-lookup"><span data-stu-id="3f8aa-125">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="3f8aa-126">Si los mensajes de correo no deseado o suplantación de identidad se han puesto en cuarentena en lugar de entregarse, los usuarios pueden notificar los mensajes a Microsoft desde cuarentena en el portal Microsoft 365 Defender correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3f8aa-126">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from Quarantine in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="3f8aa-127">Para obtener más información, vea Buscar y liberar mensajes en cuarentena [como un usuario en Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="3f8aa-127">For details, see [Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3f8aa-128">Los datos de envíos a Microsoft residen en el límite Office 365 cumplimiento normativo en los centros de datos de Norteamérica.</span><span class="sxs-lookup"><span data-stu-id="3f8aa-128">Data from submissions to Microsoft resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="3f8aa-129">Los analistas del equipo de ingeniería revisan los datos para ayudar a mejorar la eficacia de los filtros.</span><span class="sxs-lookup"><span data-stu-id="3f8aa-129">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>
