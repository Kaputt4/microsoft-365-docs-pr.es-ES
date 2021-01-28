---
title: Preguntas más frecuentes sobre los mensajes en cuarentena
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden ver las preguntas más frecuentes y las respuestas sobre los mensajes en cuarentena en Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: abd2304e83d2814cab55d13312535bd94308d8be
ms.sourcegitcommit: b3bb5bf5efa197ef8b16a33401b0b4f5663d3aa0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2021
ms.locfileid: "50032606"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="1b99d-103">Preguntas más frecuentes sobre los mensajes en cuarentena</span><span class="sxs-lookup"><span data-stu-id="1b99d-103">Quarantined messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="1b99d-104">En este tema se proporcionan preguntas y respuestas más frecuentes sobre los mensajes de correo electrónico en cuarentena para organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1b99d-104">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="1b99d-105">Para obtener preguntas y respuestas acerca de la protección contra correo no deseado, consulte preguntas más frecuentes sobre protección contra [correo no deseado.](anti-spam-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="1b99d-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="1b99d-106">Para obtener preguntas y respuestas acerca de la protección antimalware, consulte preguntas más frecuentes sobre protección [antimalware.](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="1b99d-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="1b99d-107">Para obtener preguntas y respuestas acerca de la protección contra la suplantación, consulte preguntas más frecuentes sobre la protección contra la [suplantación de seguridad.](anti-spoofing-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="1b99d-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="1b99d-108">¿Cómo puedo administrar los mensajes que se han puesto en cuarentena en busca de malware?</span><span class="sxs-lookup"><span data-stu-id="1b99d-108">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="1b99d-109">Solo los administradores pueden administrar los mensajes que se han puesto en cuarentena por malware.</span><span class="sxs-lookup"><span data-stu-id="1b99d-109">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="1b99d-110">Para obtener más información, vea [Administrar mensajes y archivos en cuarentena como administrador.](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="1b99d-110">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="1b99d-111">¿Cómo poner en cuarentena el correo no deseado?</span><span class="sxs-lookup"><span data-stu-id="1b99d-111">How do I quarantine spam?</span></span>

<span data-ttu-id="1b99d-112">De forma predeterminada, los mensajes clasificados como correo no deseado o correo electrónico masivo mediante el filtrado de correo no deseado se entregan en el buzón del usuario y se mueven a la carpeta de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="1b99d-112">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="1b99d-113">Sin embargo, puede crear y configurar directivas contra correo no deseado para poner en cuarentena los mensajes de correo no deseado o de correo masivo en su lugar.</span><span class="sxs-lookup"><span data-stu-id="1b99d-113">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="1b99d-114">Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1b99d-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="1b99d-115">¿Cómo puedo dar acceso a los usuarios a la cuarentena?</span><span class="sxs-lookup"><span data-stu-id="1b99d-115">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="1b99d-116">Un usuario debe tener una cuenta válida para tener acceso a sus propios mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="1b99d-116">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="1b99d-117">EOP independiente requiere que los usuarios se represente como usuarios de correo en EOP (creados manualmente o creados mediante la sincronización de directorios).</span><span class="sxs-lookup"><span data-stu-id="1b99d-117">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="1b99d-118">Para obtener más información acerca de la administración de usuarios en entornos de EOP independientes, vea Administrar usuarios [de correo en EOP.](manage-mail-users-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="1b99d-118">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="1b99d-119">¿A qué mensajes pueden acceder los usuarios finales en cuarentena?</span><span class="sxs-lookup"><span data-stu-id="1b99d-119">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="1b99d-120">Los usuarios pueden acceder a correo no deseado, correo electrónico masivo y mensajes de suplantación de identidad (a partir de abril de 2020) en los que son destinatarios.</span><span class="sxs-lookup"><span data-stu-id="1b99d-120">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="1b99d-121">Los usuarios finales no pueden acceder a malware en cuarentena, suplantación de identidad de alta confianza o mensajes que se han puesto en cuarentena debido a la acción Entregar el mensaje a la cuarentena hospedada en reglas de flujo de correo (también conocidas como reglas de transporte). </span><span class="sxs-lookup"><span data-stu-id="1b99d-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="1b99d-122">Para obtener más información acerca de los usuarios que tienen acceso a mensajes en cuarentena, vea Buscar y liberar mensajes [en cuarentena como un usuario.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="1b99d-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="1b99d-123">¿Durante cuánto tiempo se mantienen los mensajes en cuarentena?</span><span class="sxs-lookup"><span data-stu-id="1b99d-123">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="1b99d-124">Puede configurar cuánto tiempo se mantienen en cuarentena los mensajes de correo no deseado, de suplantación de identidad y de correo masivo mediante directivas contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="1b99d-124">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="1b99d-125">El valor predeterminado es 30 días, que también es el máximo.</span><span class="sxs-lookup"><span data-stu-id="1b99d-125">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="1b99d-126">Para obtener más información, vea [Configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="1b99d-126">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="1b99d-127">Para los mensajes que fueron puestos en cuarentena por la acción de regla de flujo de correo Entregar el mensaje a la cuarentena hospedada, los mensajes se mantienen en cuarentena durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="1b99d-127">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="1b99d-128">No puede configurar esta duración.</span><span class="sxs-lookup"><span data-stu-id="1b99d-128">You can't configure this duration.</span></span>

<span data-ttu-id="1b99d-129">Una vez expirado el período de tiempo, los mensajes se eliminan y no se pueden recuperar.</span><span class="sxs-lookup"><span data-stu-id="1b99d-129">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="1b99d-130">¿Puedo liberar o informar de más de un mensaje en cuarentena a la vez?</span><span class="sxs-lookup"><span data-stu-id="1b99d-130">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="1b99d-131">En el Centro de & cumplimiento, puede seleccionar y liberar hasta 100 mensajes a la vez.</span><span class="sxs-lookup"><span data-stu-id="1b99d-131">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="1b99d-132">Los administradores pueden usar los cmdlets [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) y [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) en Exchange Online PowerShell o EOP PowerShell independiente para buscar y liberar mensajes en cuarentena de forma masiva y para notificar falsos positivos en masa.</span><span class="sxs-lookup"><span data-stu-id="1b99d-132">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="1b99d-133">¿Se admiten caracteres comodín al buscar mensajes en cuarentena?</span><span class="sxs-lookup"><span data-stu-id="1b99d-133">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="1b99d-134">¿Puedo buscar mensajes en cuarentena para un dominio específico?</span><span class="sxs-lookup"><span data-stu-id="1b99d-134">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="1b99d-135">Los caracteres comodín no se admiten en el Centro de & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="1b99d-135">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="1b99d-136">Por ejemplo, al buscar un remitente, debe especificar la dirección de correo electrónico completa.</span><span class="sxs-lookup"><span data-stu-id="1b99d-136">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="1b99d-137">Sin embargo, puede usar caracteres comodín en Exchange Online PowerShell o EOP PowerShell independiente.</span><span class="sxs-lookup"><span data-stu-id="1b99d-137">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="1b99d-138">Por ejemplo, copie el siguiente código de PowerShell en el Bloc de notas y guarde el archivo como .ps1 en una ubicación que sea fácil de encontrar (por ejemplo, C:\Data\QuarantineRelease.ps1).</span><span class="sxs-lookup"><span data-stu-id="1b99d-138">For example, copy the following PowerShell code into NotePad and save the file as .ps1 in a location that's easy for you to find (for example, C:\Data\QuarantineRelease.ps1).</span></span>

<span data-ttu-id="1b99d-139">A continuación, después de conectarse a [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) o [Exchange Online Protection PowerShell,](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)ejecute el siguiente comando para ejecutar el script:</span><span class="sxs-lookup"><span data-stu-id="1b99d-139">Then, after you connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) or [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell), run the following command to run the script:</span></span>

```powershell
& C:\Data\QuarantineRelease.ps1
```

<span data-ttu-id="1b99d-140">El script realiza las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="1b99d-140">The script does the following actions:</span></span>

- <span data-ttu-id="1b99d-141">Busque mensajes no publicados que se han puesto en cuarentena como correo no deseado de todos los remitentes del dominio fabrikam.</span><span class="sxs-lookup"><span data-stu-id="1b99d-141">Find unreleased messages that were quarantined as spam from all senders in the fabrikam domain.</span></span> <span data-ttu-id="1b99d-142">El número máximo de resultados es 50 000 (50 páginas de 1000 resultados).</span><span class="sxs-lookup"><span data-stu-id="1b99d-142">The maximum number of results is 50,000 (50 pages of 1000 results).</span></span>
- <span data-ttu-id="1b99d-143">Guarde los resultados en un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="1b99d-143">Save the results to a CSV file.</span></span>
- <span data-ttu-id="1b99d-144">Liberar los mensajes en cuarentena correspondientes a todos los destinatarios originales.</span><span class="sxs-lookup"><span data-stu-id="1b99d-144">Release the matching quarantined messages to all original recipients.</span></span>

```powershell
$Page = 1
$List = $null

Do
{
Write-Host "Getting Page " $Page

$List = (Get-QuarantineMessage -Type Spam -PageSize 1000 -Page $Page | where {$_.Released -like "False" -and $_.SenderAddress -like "*fabrikam.com"})
Write-Host "                     " $List.count " rows in this page match"
Write-Host "                                                             Exporting list to appended CSV for logging"
$List | Export-Csv -Path "C:\Data\Quarantined Message Matches.csv" -Append -NoTypeInformation

Write-Host "Releasing page " $Page
$List | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}

$Page = $Page + 1

} Until ($Page -eq 50)
```

<span data-ttu-id="1b99d-145">Después de liberar un mensaje, no puede liberarlo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="1b99d-145">After you release a message, you can't release it again.</span></span>
