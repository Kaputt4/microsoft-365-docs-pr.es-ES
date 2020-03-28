---
title: Informar a Microsoft de correo no deseado, mensajes de correo no deseado y mensajes de suplantación de identidad
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 'El complemento de notificación de correo no deseado de Microsoft para Microsoft Office Outlook permite notificar mensajes de correo no deseado de varias formas:'
ms.openlocfilehash: b7e7ed56f171ee3b74b36ed7c10c46286fb1e570
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033667"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="f4a45-103">Mensajes de informes y archivos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f4a45-103">Report messages and files to Microsoft</span></span>

<span data-ttu-id="f4a45-104">Los usuarios y administradores de Office 365 organizaciones con buzones en Exchange online o las organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online para enviar mensajes de correo electrónico tienen varios métodos diferentes para los mensajes de informes y archivos a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f4a45-104">Users and admins in Office 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes to submit email messages have several different methods for reporting messages and files to Microsoft.</span></span>

|||
|---|---|
|<span data-ttu-id="f4a45-105">**Método**</span><span class="sxs-lookup"><span data-stu-id="f4a45-105">**Method**</span></span>|<span data-ttu-id="f4a45-106">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f4a45-106">**Description**</span></span>|
|[<span data-ttu-id="f4a45-107">Usar el envío de administración para enviar sospechoso de correo no deseado, phish, direcciones URL y archivos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f4a45-107">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="f4a45-108">Este es el método de creación de informes recomendado para administradores de organizaciones con buzones de Exchange Online (no disponible en EOP independiente).</span><span class="sxs-lookup"><span data-stu-id="f4a45-108">This is the recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="f4a45-109">Habilitar el complemento de mensajes de informe en Office 365</span><span class="sxs-lookup"><span data-stu-id="f4a45-109">Enable the Report Message add-in in Office 365</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="f4a45-110">Funciona con Outlook, Outlook para Mac y Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="f4a45-110">Works with Outlook, Outlook for Mac, and Outlook on the web.</span></span> <span data-ttu-id="f4a45-111">Este es el complemento recomendado.</span><span class="sxs-lookup"><span data-stu-id="f4a45-111">This is the recommended add-in.</span></span> <br/><br/> <span data-ttu-id="f4a45-112">En función de su licencia, los mensajes que se han notificado están disponibles en los [resultados de investigación y respuesta automatizada (Air)](air-view-investigation-results.md), el [Informe de mensajes notificados por el usuario](view-email-security-reports.md#user-reported-messages-report) y el explorador de [amenazas](threat-explorer-views.md#email--submissions).</span><span class="sxs-lookup"><span data-stu-id="f4a45-112">Depending on your license, the reported messages are available in [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report) and [Threat Explorer](threat-explorer-views.md#email--submissions).</span></span>|
|[<span data-ttu-id="f4a45-113">Instalar y usar el complemento de notificación de correo no deseado para Microsoft Outlook en Office 365</span><span class="sxs-lookup"><span data-stu-id="f4a45-113">Install and use the Junk Email Reporting add-in for Microsoft Outlook in Office 365</span></span>](junk-email-reporting-add-in-for-microsoft-outlook.md)|<span data-ttu-id="f4a45-114">Solo funciona en Outlook.</span><span class="sxs-lookup"><span data-stu-id="f4a45-114">Only works in Outlook.</span></span>|
|[<span data-ttu-id="f4a45-115">Informar del correo electrónico no deseado y de suplantación de identidad en Outlook en la web en Office 365</span><span class="sxs-lookup"><span data-stu-id="f4a45-115">Report junk and phishing email in Outlook on the web in Office 365</span></span>](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|<span data-ttu-id="f4a45-116">Use las funciones integradas en Outlook en la web para las organizaciones con buzones de Exchange Online (no disponible en EOP independiente).</span><span class="sxs-lookup"><span data-stu-id="f4a45-116">Use the built-in capabilities in Outlook on the web for organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="f4a45-117">Enviar malware y no malware a Microsoft para su análisis</span><span class="sxs-lookup"><span data-stu-id="f4a45-117">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="f4a45-118">Usar el sitio de inteligencia en seguridad de Microsoft para enviar datos adjuntos y otros archivos.</span><span class="sxs-lookup"><span data-stu-id="f4a45-118">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="f4a45-119">Si los mensajes de correo no deseado o de suplantación de identidad se han puesto en cuarentena en lugar de entregarse, los usuarios pueden informar de los mensajes a Microsoft del portal de cuarentena en el centro de seguridad & cumplimiento de Office 365.</span><span class="sxs-lookup"><span data-stu-id="f4a45-119">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from the Quarantine portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="f4a45-120">Para obtener más información, vea [Buscar y liberar mensajes en cuarentena como un usuario en Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="f4a45-120">For details, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>