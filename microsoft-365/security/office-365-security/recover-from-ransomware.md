---
title: Recuperarse de un ataque de ransomware
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
ms.collection:
- M365-security-compliance
description: Los administradores de Microsoft 365 pueden obtener información sobre cómo recuperarse de un ataque de ransomware.
ms.openlocfilehash: 1471b7b0cacbabaf086e0759e21a46b9cb9929ab
ms.sourcegitcommit: 7a59d83a8660c2344ebdb92e0ea0171c9c2d9498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44811031"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="3bc94-103">Recuperarse de un ataque de ransomware en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3bc94-103">Recover from a ransomware attack in Microsoft 365</span></span>

<span data-ttu-id="3bc94-104">Incluso si toma todas las precauciones para proteger su organización, puede seguir siendo víctima de un ataque de [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) .</span><span class="sxs-lookup"><span data-stu-id="3bc94-104">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="3bc94-105">Ransomware es gran empresa y los ataques se comprueban de forma sofisticada.</span><span class="sxs-lookup"><span data-stu-id="3bc94-105">Ransomware is big business, and the attacks are verify sophisticated.</span></span>

<span data-ttu-id="3bc94-106">Los pasos de este tema le proporcionarán la mejor oportunidad para recuperar datos cifrados por ransomware y ayudarán a detener la propagación de la infección en su organización.</span><span class="sxs-lookup"><span data-stu-id="3bc94-106">The steps in this topic will give you the best chance to recover data that was encrypted by the ransomware, and will help stop the spread of the infection in your organization.</span></span> <span data-ttu-id="3bc94-107">Antes de empezar, tenga en cuenta los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="3bc94-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="3bc94-108">No hay ninguna garantía de que pagar el Ransom devolverá acceso a los archivos.</span><span class="sxs-lookup"><span data-stu-id="3bc94-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="3bc94-109">De hecho, pagar el Ransom puede convertirle en un objetivo para obtener más ransomware.</span><span class="sxs-lookup"><span data-stu-id="3bc94-109">In fact, paying the ransom can make you a target for more ransomware.</span></span> <span data-ttu-id="3bc94-110">Si ya ha pagado, pero ha podido recuperar los archivos correctamente sin tener que usar la resolución del atacante, debe llamar al Banco para ver si pueden bloquear la transacción.</span><span class="sxs-lookup"><span data-stu-id="3bc94-110">If you've already paid, but you were able to successfully recover your files without having to use the attacker's resolution, you should call your bank to see if they can block the transaction.</span></span> <span data-ttu-id="3bc94-111">También le recomendamos que informe sobre el ataque de ransomware a los sitios web de la ley, los informes de fraude de estafa y Microsoft, tal como se describe más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="3bc94-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites and Microsoft as described later in this topic.</span></span>

- <span data-ttu-id="3bc94-112">Es muy importante que responda rápidamente al ataque y a sus consecuencias.</span><span class="sxs-lookup"><span data-stu-id="3bc94-112">It's very important that you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="3bc94-113">Cuanto más tiempo espere, lo menos probable es que pueda recuperar los datos afectados.</span><span class="sxs-lookup"><span data-stu-id="3bc94-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="3bc94-114">Paso 1: comprobar las copias de seguridad</span><span class="sxs-lookup"><span data-stu-id="3bc94-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="3bc94-115">Si tiene copias de seguridad sin conexión, probablemente podrá restaurar los datos cifrados **una vez** que haya quitado la carga de ransomware (malware) de su entorno.</span><span class="sxs-lookup"><span data-stu-id="3bc94-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="3bc94-116">Si no tiene copias de seguridad o si las copias de seguridad también se vieron afectadas por el ransomware, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="3bc94-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-activesync-and-onedrive-sync"></a><span data-ttu-id="3bc94-117">Paso 2: deshabilitar la sincronización de ActiveSync y de OneDrive</span><span class="sxs-lookup"><span data-stu-id="3bc94-117">Step 2: Disable ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="3bc94-118">El punto clave aquí es detener la propagación de cifrado de datos por ransomware.</span><span class="sxs-lookup"><span data-stu-id="3bc94-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="3bc94-119">Si sospecha que el correo electrónico es un objetivo, debe deshabilitar temporalmente el acceso de los usuarios a los buzones.</span><span class="sxs-lookup"><span data-stu-id="3bc94-119">If you suspect that email is a target, you should temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="3bc94-120">Exchange ActiveSync se usa en dispositivos móviles para sincronizar datos entre el dispositivo y el buzón de correo de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3bc94-120">Exchange ActiveSync is used by mobile devices to synchronize data between the device and the Exchange Online mailbox.</span></span>

<span data-ttu-id="3bc94-121">Para deshabilitar ActiveSync para un buzón de correo, consulte [How to Disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span><span class="sxs-lookup"><span data-stu-id="3bc94-121">To disable ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="3bc94-122">Para deshabilitar otros tipos de acceso a un buzón, consulte:</span><span class="sxs-lookup"><span data-stu-id="3bc94-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="3bc94-123">[Habilitar o deshabilitar MAPI para un buzón de correo](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span><span class="sxs-lookup"><span data-stu-id="3bc94-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="3bc94-124">Habilitar o deshabilitar el acceso a POP3 o IMAP4 para un usuario</span><span class="sxs-lookup"><span data-stu-id="3bc94-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="3bc94-125">Pausar la sincronización de OneDrive le ayudará a proteger los datos de la nube para que no se actualicen mediante dispositivos potencialmente infectados.</span><span class="sxs-lookup"><span data-stu-id="3bc94-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="3bc94-126">Para obtener más información, consulte [Cómo pausar y reanudar la sincronización en OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span><span class="sxs-lookup"><span data-stu-id="3bc94-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="3bc94-127">Paso 3: quitar el malware de los dispositivos afectados</span><span class="sxs-lookup"><span data-stu-id="3bc94-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="3bc94-128">Ejecute un análisis antivirus completo con las actualizaciones más recientes en todos los equipos y dispositivos sospechosos para detectar y quitar la carga asociada con el ransomware.</span><span class="sxs-lookup"><span data-stu-id="3bc94-128">Run a full antivirus scan with the latest updates on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span> <span data-ttu-id="3bc94-129">No olvide los dispositivos que sincronizan datos o el destino de las unidades de red asignadas (también deben examinarse los equipos y dispositivos).</span><span class="sxs-lookup"><span data-stu-id="3bc94-129">Don't forget devices that are synchronizing data, or the target of mapped network drives (those computers and devices need to be scanned, too).</span></span>

<span data-ttu-id="3bc94-130">Puede usar [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) o (para clientes más antiguos) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span><span class="sxs-lookup"><span data-stu-id="3bc94-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="3bc94-131">Una alternativa que también le ayudará a quitar ransomware o malware es la [herramienta de eliminación de software malintencionado (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span><span class="sxs-lookup"><span data-stu-id="3bc94-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="3bc94-132">Si estas opciones no funcionan, puedes probar [Windows Defender sin conexión](https://support.microsoft.com/help/17466) o [solucionar problemas de detección y eliminación de malware](https://support.microsoft.com/help/4466982).</span><span class="sxs-lookup"><span data-stu-id="3bc94-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="3bc94-133">Paso 4: recuperar archivos en un equipo o dispositivo limpio</span><span class="sxs-lookup"><span data-stu-id="3bc94-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="3bc94-134">Una vez que haya completado el paso anterior para quitar la carga de ransomware del entorno (lo que impedirá que el ransomware Cifre o quite los archivos), puede usar el [historial de archivos](https://support.microsoft.com/help/17128) en Windows 10 y Windows 8,1 o en la protección del sistema de Windows 7 para intentar recuperar los archivos y carpetas locales.</span><span class="sxs-lookup"><span data-stu-id="3bc94-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="3bc94-135">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="3bc94-135">**Notes**:</span></span>

- <span data-ttu-id="3bc94-136">Algunos ransomware también cifrarán o eliminarán las versiones de copia de seguridad, por lo que no podrá usar el historial de archivos o la protección del sistema para restaurar archivos.</span><span class="sxs-lookup"><span data-stu-id="3bc94-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="3bc94-137">Si esto ocurre, necesita usar copias de seguridad en dispositivos o dispositivos externos que no se vieron afectados por el ransomware o el OneDrive, tal como se describe en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="3bc94-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="3bc94-138">Si una carpeta está sincronizada en OneDrive y no usa la versión más reciente de Windows, es posible que existan algunas limitaciones al usar el historial de archivos.</span><span class="sxs-lookup"><span data-stu-id="3bc94-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="3bc94-139">Paso 5: recuperar los archivos en su OneDrive para la empresa</span><span class="sxs-lookup"><span data-stu-id="3bc94-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="3bc94-140">Los archivos restaurar en OneDrive para la empresa permiten restaurar todo el OneDrive a un punto anterior en el tiempo de los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="3bc94-140">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="3bc94-141">Para obtener más información, vea [restaurar el OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span><span class="sxs-lookup"><span data-stu-id="3bc94-141">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="3bc94-142">Paso 6: recuperar el correo electrónico eliminado</span><span class="sxs-lookup"><span data-stu-id="3bc94-142">Step 6: Recover deleted email</span></span>

<span data-ttu-id="3bc94-143">En el caso poco probable de que ransomware elimine todo el correo electrónico, probablemente pueda recuperar los elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="3bc94-143">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="3bc94-144">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="3bc94-144">For more information, see:</span></span>

- [<span data-ttu-id="3bc94-145">Recuperar mensajes eliminados en el buzón de un usuario</span><span class="sxs-lookup"><span data-stu-id="3bc94-145">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="3bc94-146">Recuperación de elementos eliminados en Outlook para Windows</span><span class="sxs-lookup"><span data-stu-id="3bc94-146">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="3bc94-147">Paso 7: volver a habilitar Exchange ActiveSync y la sincronización de OneDrive</span><span class="sxs-lookup"><span data-stu-id="3bc94-147">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="3bc94-148">Una vez que haya limpiado los equipos y dispositivos y recuperado los datos, puede volver a habilitar la sincronización de ActiveSync y de OneDrive que deshabilitó anteriormente en el [paso 2](#step-2-disable-activesync-and-onedrive-sync).</span><span class="sxs-lookup"><span data-stu-id="3bc94-148">After you've cleaned your computers and devices and recovered your data, you can re-enable ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="3bc94-149">Paso 8 (opcional): bloquear la sincronización de OneDrive para extensiones de archivo específicas</span><span class="sxs-lookup"><span data-stu-id="3bc94-149">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="3bc94-150">Una vez que haya recuperado, puede evitar que los clientes de OneDrive para la empresa sincronicen los tipos de archivo afectados por este ransomware.</span><span class="sxs-lookup"><span data-stu-id="3bc94-150">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="3bc94-151">Para obtener más información, vea [set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="3bc94-151">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="3bc94-152">Informar del ataque</span><span class="sxs-lookup"><span data-stu-id="3bc94-152">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="3bc94-153">Aplicación de la ley de contacto</span><span class="sxs-lookup"><span data-stu-id="3bc94-153">Contact law enforcement</span></span>

<span data-ttu-id="3bc94-154">Debe ponerse en contacto con las agencias de cumplimiento normativo local o federal.</span><span class="sxs-lookup"><span data-stu-id="3bc94-154">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="3bc94-155">Por ejemplo, si está en los Estados Unidos, puede ponerse en contacto con el servicio de oficina, [IC3](http://www.ic3.gov/complaint/default.aspx) o [Secret](http://www.secretservice.gov/)del [FBI local](https://www.fbi.gov/contact-us/field).</span><span class="sxs-lookup"><span data-stu-id="3bc94-155">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="3bc94-156">Enviar un informe al sitio web de informes de fraude de su país</span><span class="sxs-lookup"><span data-stu-id="3bc94-156">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="3bc94-157">Los sitios web de informes de estafa proporcionan información sobre cómo evitar y evitar estafas.</span><span class="sxs-lookup"><span data-stu-id="3bc94-157">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="3bc94-158">También proporcionan mecanismos para informar si ha sido víctima de un timo.</span><span class="sxs-lookup"><span data-stu-id="3bc94-158">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="3bc94-159">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="3bc94-159">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="3bc94-160">Canadá: [centro anti-fraude canadiense](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="3bc94-160">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="3bc94-161">Francia: [Agence Nationale de la Sécurité des Systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="3bc94-161">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="3bc94-162">Alemania: [Bundesamt für Sicherheit en der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="3bc94-162">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="3bc94-163">Irlanda: [una Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="3bc94-163">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="3bc94-164">Nueva Zelanda: [fraudes de asuntos de consumo](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="3bc94-164">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="3bc94-165">Reino Unido: [fraude de acciones](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="3bc94-165">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="3bc94-166">Estados Unidos: [en protección en línea](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="3bc94-166">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="3bc94-167">Si su país no aparece en la lista, pregunte a las agencias de cumplimiento normativo local o federal.</span><span class="sxs-lookup"><span data-stu-id="3bc94-167">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="3bc94-168">Enviar mensajes de correo electrónico a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3bc94-168">Submit email messages to Microsoft</span></span>

<span data-ttu-id="3bc94-169">Puede informar del mensaje de suplantación de identidad (phishing) que contiene ransomware mediante uno de varios métodos.</span><span class="sxs-lookup"><span data-stu-id="3bc94-169">You can report phishing message that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="3bc94-170">Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="3bc94-170">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3bc94-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="3bc94-171">See also</span></span>

- [<span data-ttu-id="3bc94-172">Ransomware</span><span class="sxs-lookup"><span data-stu-id="3bc94-172">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="3bc94-173">Respuesta por ransomware: ¿pagar o no pagar?</span><span class="sxs-lookup"><span data-stu-id="3bc94-173">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="3bc94-174">Norsk de la anhidro responde al ataque de ransomware con transparencia</span><span class="sxs-lookup"><span data-stu-id="3bc94-174">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="3bc94-175">Detección de ransomware y recuperación de los archivos en OneDrive</span><span class="sxs-lookup"><span data-stu-id="3bc94-175">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="3bc94-176">Informe de inteligencia en seguridad de Microsoft</span><span class="sxs-lookup"><span data-stu-id="3bc94-176">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="3bc94-177">Habilitar o deshabilitar macros en archivos de Office</span><span class="sxs-lookup"><span data-stu-id="3bc94-177">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="3bc94-178">Configuración recomendada para EOP y la seguridad de ATP de Office 365</span><span class="sxs-lookup"><span data-stu-id="3bc94-178">Recommended settings for EOP and Office 365 ATP security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [<span data-ttu-id="3bc94-179">Una actualización que merece la pena: la seguridad de next-gen en Windows 10 prueba resistencia contra brotes de ransomware en 2017</span><span class="sxs-lookup"><span data-stu-id="3bc94-179">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="3bc94-180">No hay mas samas: ¿Cuál es el contenido del operando de un modus de ransomware?</span><span class="sxs-lookup"><span data-stu-id="3bc94-180">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="3bc94-181">Malware de bloqueo, suerte para evitarlo</span><span class="sxs-lookup"><span data-stu-id="3bc94-181">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="3bc94-182">MSRT julio de 2016: ransomware CERBER</span><span class="sxs-lookup"><span data-stu-id="3bc94-182">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="3bc94-183">Los tres cabezales del Cerberus-like CERBER ransomware</span><span class="sxs-lookup"><span data-stu-id="3bc94-183">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="3bc94-184">Troldesh ransomware afectado por el código de da Vinci</span><span class="sxs-lookup"><span data-stu-id="3bc94-184">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
