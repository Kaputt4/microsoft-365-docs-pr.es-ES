---
title: Recuperarse de un ataque de ransomware
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365 administradores pueden aprender a recuperarse de un ataque de ransomware.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 473591a02b78043153d505dda6dd7ef5ac6e3961
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789056"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="a39bb-103">Recuperarse de un ataque de ransomware en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a39bb-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a39bb-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="a39bb-104">**Applies to**</span></span>
- [<span data-ttu-id="a39bb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a39bb-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a39bb-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a39bb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a39bb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a39bb-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a39bb-108">Incluso si toma todas las precauciones para proteger su organización, todavía puede ser víctima de un [ataque de ransomware.](/windows/security/threat-protection/intelligence/ransomware-malware)</span><span class="sxs-lookup"><span data-stu-id="a39bb-108">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="a39bb-109">El ransomware es una gran empresa y los ataques son muy sofisticados.</span><span class="sxs-lookup"><span data-stu-id="a39bb-109">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="a39bb-110">Los pasos de este artículo le darán la mejor oportunidad de recuperar datos y detener la propagación interna de la infección.</span><span class="sxs-lookup"><span data-stu-id="a39bb-110">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="a39bb-111">Antes de empezar, tenga en cuenta los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="a39bb-111">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="a39bb-112">No hay ninguna garantía de que el pago del rescate devolverá el acceso a los archivos.</span><span class="sxs-lookup"><span data-stu-id="a39bb-112">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="a39bb-113">De hecho, pagar el rescate puede convertirte en un objetivo para más ransomware.</span><span class="sxs-lookup"><span data-stu-id="a39bb-113">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="a39bb-114">Si ya pagó, pero se recuperó sin usar la solución del atacante, póngase en contacto con su banco para ver si pueden bloquear la transacción.</span><span class="sxs-lookup"><span data-stu-id="a39bb-114">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="a39bb-115">También recomendamos que informe del ataque de ransomware a las fuerzas del orden, a los sitios web de informes de estafas y a Microsoft, tal como se describe más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="a39bb-115">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="a39bb-116">Es importante que respondas rápidamente al ataque y sus consecuencias.</span><span class="sxs-lookup"><span data-stu-id="a39bb-116">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="a39bb-117">Cuanto más tiempo espere, menos probable es que pueda recuperar los datos afectados.</span><span class="sxs-lookup"><span data-stu-id="a39bb-117">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="a39bb-118">Paso 1: Comprobar las copias de seguridad</span><span class="sxs-lookup"><span data-stu-id="a39bb-118">Step 1: Verify your backups</span></span>

<span data-ttu-id="a39bb-119">Si tiene copias de seguridad sin conexión, probablemente pueda restaurar los datos cifrados después de haber quitado la carga de ransomware (malware) del entorno. </span><span class="sxs-lookup"><span data-stu-id="a39bb-119">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="a39bb-120">Si no tiene copias de seguridad o si las copias de seguridad también se vieron afectadas por el ransomware, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="a39bb-120">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="a39bb-121">Paso 2: Deshabilitar Exchange ActiveSync y OneDrive sincronización</span><span class="sxs-lookup"><span data-stu-id="a39bb-121">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="a39bb-122">El punto clave aquí es detener la propagación del cifrado de datos por el ransomware.</span><span class="sxs-lookup"><span data-stu-id="a39bb-122">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="a39bb-123">Si sospecha que el correo electrónico es un destino del cifrado ransomware, deshabilite temporalmente el acceso de los usuarios a los buzones.</span><span class="sxs-lookup"><span data-stu-id="a39bb-123">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="a39bb-124">Exchange ActiveSync sincroniza los datos entre dispositivos y Exchange Online buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="a39bb-124">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="a39bb-125">Para deshabilitar Exchange ActiveSync para un buzón, vea [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span><span class="sxs-lookup"><span data-stu-id="a39bb-125">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="a39bb-126">Para deshabilitar otros tipos de acceso a un buzón, vea:</span><span class="sxs-lookup"><span data-stu-id="a39bb-126">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="a39bb-127">[Habilitar o deshabilitar MAPI para un buzón](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span><span class="sxs-lookup"><span data-stu-id="a39bb-127">[Enable or disable MAPI for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="a39bb-128">Habilitar o deshabilitar el acceso POP3 o IMAP4 para un usuario</span><span class="sxs-lookup"><span data-stu-id="a39bb-128">Enable or Disable POP3 or IMAP4 access for a user</span></span>](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="a39bb-129">La pausa OneDrive sincronización ayudará a proteger los datos de la nube de que los dispositivos potencialmente infectados actualicen los datos de la nube.</span><span class="sxs-lookup"><span data-stu-id="a39bb-129">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="a39bb-130">Para obtener más información, [vea How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span><span class="sxs-lookup"><span data-stu-id="a39bb-130">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="a39bb-131">Paso 3: Quitar el malware de los dispositivos afectados</span><span class="sxs-lookup"><span data-stu-id="a39bb-131">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="a39bb-132">Ejecute un examen antivirus completo y actual en todos los equipos y dispositivos sospechosos para detectar y quitar la carga que está asociada con el ransomware.</span><span class="sxs-lookup"><span data-stu-id="a39bb-132">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="a39bb-133">No olvide examinar los dispositivos que sincronizan datos o los destinos de las unidades de red asignadas.</span><span class="sxs-lookup"><span data-stu-id="a39bb-133">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="a39bb-134">Puede usar [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) o (para clientes más [antiguos) Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span><span class="sxs-lookup"><span data-stu-id="a39bb-134">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="a39bb-135">Una alternativa que también le ayudará a eliminar ransomware o malware es la Herramienta de eliminación de software malintencionado [(MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)</span><span class="sxs-lookup"><span data-stu-id="a39bb-135">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="a39bb-136">Si estas opciones no funcionan, puedes probar Windows Defender [sin](https://support.microsoft.com/help/17466) conexión o solucionar problemas con la detección [y eliminación de malware](https://support.microsoft.com/help/4466982).</span><span class="sxs-lookup"><span data-stu-id="a39bb-136">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="a39bb-137">Paso 4: Recuperar archivos en un equipo o dispositivo limpiado</span><span class="sxs-lookup"><span data-stu-id="a39bb-137">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="a39bb-138">Después de completar el paso anterior para quitar la carga ransomware del entorno (lo que impedirá [](https://support.microsoft.com/help/17128) que el ransomware cifre o quite los archivos), puede usar el Historial de archivos en Windows 10 y Windows 8.1 o Protección del sistema en Windows 7 para intentar recuperar los archivos y carpetas locales.</span><span class="sxs-lookup"><span data-stu-id="a39bb-138">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="a39bb-139">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="a39bb-139">**Notes**:</span></span>

- <span data-ttu-id="a39bb-140">Algunos ransomware también cifrarán o eliminarán las versiones de copia de seguridad, por lo que no puede usar el historial de archivos o la protección del sistema para restaurar archivos.</span><span class="sxs-lookup"><span data-stu-id="a39bb-140">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="a39bb-141">Si esto sucede, necesitas usar copias de seguridad en unidades externas o dispositivos que no se vieron afectados por el ransomware o OneDrive como se describe en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="a39bb-141">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="a39bb-142">Si una carpeta está sincronizada OneDrive y no está usando la versión más reciente de Windows, puede haber algunas limitaciones con el Historial de archivos.</span><span class="sxs-lookup"><span data-stu-id="a39bb-142">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="a39bb-143">Paso 5: Recuperar los archivos en el OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="a39bb-143">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="a39bb-144">Restaurar archivos en OneDrive para la Empresa permite restaurar toda la OneDrive a un punto anterior en el tiempo en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="a39bb-144">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="a39bb-145">Para obtener más información, consulte [Restaurar su OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span><span class="sxs-lookup"><span data-stu-id="a39bb-145">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="a39bb-146">Paso 6: Recuperar correo electrónico eliminado</span><span class="sxs-lookup"><span data-stu-id="a39bb-146">Step 6: Recover deleted email</span></span>

<span data-ttu-id="a39bb-147">En el caso excepcional de que el ransomware eliminó todo el correo electrónico, probablemente puede recuperar los elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="a39bb-147">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="a39bb-148">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="a39bb-148">For more information, see:</span></span>

- [<span data-ttu-id="a39bb-149">Recuperar mensajes eliminados en el buzón de un usuario</span><span class="sxs-lookup"><span data-stu-id="a39bb-149">Recover deleted messages in a user's mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="a39bb-150">Recuperación de elementos eliminados en Outlook para Windows</span><span class="sxs-lookup"><span data-stu-id="a39bb-150">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="a39bb-151">Paso 7: Volver a habilitar Exchange ActiveSync y OneDrive sincronización</span><span class="sxs-lookup"><span data-stu-id="a39bb-151">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="a39bb-152">Después de limpiar los equipos y dispositivos y recuperar los datos, puede volver a habilitar Exchange ActiveSync y OneDrive que deshabilitó anteriormente en el paso [2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span><span class="sxs-lookup"><span data-stu-id="a39bb-152">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="a39bb-153">Paso 8 (opcional): bloquear OneDrive sincronización para extensiones de archivo específicas</span><span class="sxs-lookup"><span data-stu-id="a39bb-153">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="a39bb-154">Después de recuperarse, puede impedir que los OneDrive para la Empresa sincronicen los tipos de archivo que se vieron afectados por este ransomware.</span><span class="sxs-lookup"><span data-stu-id="a39bb-154">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="a39bb-155">Para obtener más información, [vea Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="a39bb-155">For more information, see [Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="a39bb-156">Informar del ataque</span><span class="sxs-lookup"><span data-stu-id="a39bb-156">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="a39bb-157">Póngase en contacto con las fuerzas del orden</span><span class="sxs-lookup"><span data-stu-id="a39bb-157">Contact law enforcement</span></span>

<span data-ttu-id="a39bb-158">Debe ponerse en contacto con las agencias de seguridad locales o federales.</span><span class="sxs-lookup"><span data-stu-id="a39bb-158">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="a39bb-159">Por ejemplo, si se encuentra en Estados Unidos, puede ponerse en contacto con la oficina de campo local del [FBI,](https://www.fbi.gov/contact-us/field) [ic3](http://www.ic3.gov/complaint/default.aspx) o [servicio secreto](http://www.secretservice.gov/).</span><span class="sxs-lookup"><span data-stu-id="a39bb-159">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="a39bb-160">Enviar un informe al sitio web de informes de estafas de su país</span><span class="sxs-lookup"><span data-stu-id="a39bb-160">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="a39bb-161">Los sitios web de informes de estafas proporcionan información sobre cómo evitar y evitar estafas.</span><span class="sxs-lookup"><span data-stu-id="a39bb-161">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="a39bb-162">También proporcionan mecanismos para informar si fue víctima de una estafa.</span><span class="sxs-lookup"><span data-stu-id="a39bb-162">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="a39bb-163">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="a39bb-163">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="a39bb-164">Canadá: [Centro canadiense de lucha contra el fraude](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="a39bb-164">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="a39bb-165">Francia: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="a39bb-165">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="a39bb-166">Alemania: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="a39bb-166">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="a39bb-167">Irlanda: [Una Síochána de Garda](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="a39bb-167">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="a39bb-168">Nueva Zelanda: [estafas de asuntos de consumidores](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="a39bb-168">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="a39bb-169">Suiza [Nationales Zentrum für Cybersicherheit NCSC](https://www.ncsc.admin.ch/ncsc/de/home.html)</span><span class="sxs-lookup"><span data-stu-id="a39bb-169">Switzerland [Nationales Zentrum für Cybersicherheit NCSC](https://www.ncsc.admin.ch/ncsc/de/home.html)</span></span>

- <span data-ttu-id="a39bb-170">Reino Unido: [fraude de acción](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="a39bb-170">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="a39bb-171">Estados Unidos: [On Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="a39bb-171">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="a39bb-172">Si su país no aparece en la lista, pregúntele a las agencias de seguridad locales o federales.</span><span class="sxs-lookup"><span data-stu-id="a39bb-172">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="a39bb-173">Enviar mensajes de correo electrónico a Microsoft</span><span class="sxs-lookup"><span data-stu-id="a39bb-173">Submit email messages to Microsoft</span></span>

<span data-ttu-id="a39bb-174">Puede notificar mensajes de suplantación de identidad que contienen ransomware mediante uno de varios métodos.</span><span class="sxs-lookup"><span data-stu-id="a39bb-174">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="a39bb-175">Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="a39bb-175">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a39bb-176">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a39bb-176">See also</span></span>

- [<span data-ttu-id="a39bb-177">Ransomware</span><span class="sxs-lookup"><span data-stu-id="a39bb-177">Ransomware</span></span>](/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="a39bb-178">Respuesta ransomware: ¿pagar o no pagar?</span><span class="sxs-lookup"><span data-stu-id="a39bb-178">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="a39bb-179">Norsk Hydro responde al ataque ransomware con transparencia</span><span class="sxs-lookup"><span data-stu-id="a39bb-179">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="a39bb-180">Detección de ransomware y recuperación de archivos en OneDrive</span><span class="sxs-lookup"><span data-stu-id="a39bb-180">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="a39bb-181">Inteligencia de seguridad de Microsoft Informe</span><span class="sxs-lookup"><span data-stu-id="a39bb-181">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="a39bb-182">Habilitar o deshabilitar macros en Office archivos</span><span class="sxs-lookup"><span data-stu-id="a39bb-182">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="a39bb-183">Configuración recomendada para EOP y Microsoft Defender para Office 365 seguridad</span><span class="sxs-lookup"><span data-stu-id="a39bb-183">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365.md)

- [<span data-ttu-id="a39bb-184">Una actualización digna: la seguridad de próxima generación en Windows 10 resistente frente a los brotes de ransomware en 2017</span><span class="sxs-lookup"><span data-stu-id="a39bb-184">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="a39bb-185">No mas, Samas: ¿Qué hay en el modus operandi de este ransomware?</span><span class="sxs-lookup"><span data-stu-id="a39bb-185">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="a39bb-186">Malware locky, con suerte de evitarlo</span><span class="sxs-lookup"><span data-stu-id="a39bb-186">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="a39bb-187">MSRT july 2016: Cerber ransomware</span><span class="sxs-lookup"><span data-stu-id="a39bb-187">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="a39bb-188">Las tres cabezas del ransomware Cerberus-like Cerber</span><span class="sxs-lookup"><span data-stu-id="a39bb-188">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="a39bb-189">Ransomware Troldesh influenciado por (el) código Da Vinci</span><span class="sxs-lookup"><span data-stu-id="a39bb-189">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
