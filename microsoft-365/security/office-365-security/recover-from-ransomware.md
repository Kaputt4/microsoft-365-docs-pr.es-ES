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
description: Los administradores de Office 365 pueden obtener información sobre cómo recuperarse de un ataque de ransomware.
ms.openlocfilehash: 04cfd2f2417b0c2e084a88f9ee156521339b18c4
ms.sourcegitcommit: e47694dedf7e213167d3d979a44c07c668bba543
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41932381"
---
# <a name="recover-from-a-ransomware-attack-in-office-365"></a><span data-ttu-id="69875-103">Recuperarse de un ataque de ransomware en Office 365</span><span class="sxs-lookup"><span data-stu-id="69875-103">Recover from a ransomware attack in Office 365</span></span>

<span data-ttu-id="69875-104">Incluso si toma todas las precauciones para proteger su organización de Office 365, todavía puede caer en la víctima de un ataque de [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) .</span><span class="sxs-lookup"><span data-stu-id="69875-104">Even if you take every precaution to protect your Office 365 organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="69875-105">Ransomware es gran empresa y los ataques se comprueban de forma sofisticada.</span><span class="sxs-lookup"><span data-stu-id="69875-105">Ransomware is big business, and the attacks are verify sophisticated.</span></span>

<span data-ttu-id="69875-106">Los pasos de este tema le proporcionarán la mejor oportunidad para recuperar datos cifrados por ransomware y ayudarán a detener la propagación de la infección en su organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="69875-106">The steps in this topic will give you the best chance to recover data that was encrypted by the ransomware, and will help stop the spread of the infection in your Office 365 organization.</span></span> <span data-ttu-id="69875-107">Antes de empezar, tenga en cuenta los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="69875-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="69875-108">No hay ninguna garantía de que pagar el Ransom devolverá acceso a los archivos.</span><span class="sxs-lookup"><span data-stu-id="69875-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="69875-109">De hecho, pagar el Ransom puede convertirle en un objetivo para obtener más ransomware.</span><span class="sxs-lookup"><span data-stu-id="69875-109">In fact, paying the ransom can make you a target for more ransomware.</span></span> <span data-ttu-id="69875-110">Si ya ha pagado, pero ha podido recuperar los archivos correctamente sin tener que usar la resolución del atacante, debe llamar al Banco para ver si pueden bloquear la transacción.</span><span class="sxs-lookup"><span data-stu-id="69875-110">If you've already paid, but you were able to successfully recover your files without having to use the attacker's resolution, you should call your bank to see if they can block the transaction.</span></span> <span data-ttu-id="69875-111">También le recomendamos que informe sobre el ataque de ransomware a los sitios web de la ley, los informes de fraude de estafa y Microsoft, tal como se describe más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="69875-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites and Microsoft as described later in this topic.</span></span>

- <span data-ttu-id="69875-112">Es muy importante que responda rápidamente al ataque y a sus consecuencias.</span><span class="sxs-lookup"><span data-stu-id="69875-112">It's very important that you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="69875-113">Cuanto más tiempo espere, lo menos probable es que pueda recuperar los datos afectados.</span><span class="sxs-lookup"><span data-stu-id="69875-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="69875-114">Paso 1: comprobar las copias de seguridad</span><span class="sxs-lookup"><span data-stu-id="69875-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="69875-115">Si tiene copias de seguridad sin conexión, probablemente podrá restaurar los datos cifrados **una vez** que haya quitado la carga de ransomware (malware) de su entorno.</span><span class="sxs-lookup"><span data-stu-id="69875-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="69875-116">Si no tiene copias de seguridad o si las copias de seguridad también se vieron afectadas por el ransomware, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="69875-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-activesync-and-onedrive-sync"></a><span data-ttu-id="69875-117">Paso 2: deshabilitar la sincronización de ActiveSync y de OneDrive</span><span class="sxs-lookup"><span data-stu-id="69875-117">Step 2: Disable ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="69875-118">El punto clave aquí es detener la propagación de cifrado de datos por ransomware.</span><span class="sxs-lookup"><span data-stu-id="69875-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="69875-119">Si sospecha que el correo electrónico es un objetivo, debe deshabilitar temporalmente el acceso de los usuarios a los buzones.</span><span class="sxs-lookup"><span data-stu-id="69875-119">If you suspect that email is a target, you should temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="69875-120">Exchange ActiveSync se usa en dispositivos móviles para sincronizar datos entre el dispositivo y el buzón de correo de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="69875-120">Exchange ActiveSync is used by mobile devices to synchronize data between the device and the Exchange Online mailbox.</span></span>

<span data-ttu-id="69875-121">Para deshabilitar ActiveSync para un buzón de correo, vea [cómo deshabilitar Exchange ActiveSync para los usuarios en Office 365](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="69875-121">To disable ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Office 365](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365).</span></span>

<span data-ttu-id="69875-122">Para deshabilitar otros tipos de acceso a un buzón, consulte:</span><span class="sxs-lookup"><span data-stu-id="69875-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="69875-123">[Habilitar o deshabilitar MAPI para un buzón de correo](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span><span class="sxs-lookup"><span data-stu-id="69875-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="69875-124">Habilitar o deshabilitar el acceso a POP3 o IMAP4 para un usuario</span><span class="sxs-lookup"><span data-stu-id="69875-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="69875-125">Pausar la sincronización de OneDrive le ayudará a proteger los datos de la nube para que no se actualicen mediante dispositivos potencialmente infectados.</span><span class="sxs-lookup"><span data-stu-id="69875-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="69875-126">Para obtener más información, consulte [Cómo pausar y reanudar la sincronización en OneDrive](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span><span class="sxs-lookup"><span data-stu-id="69875-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="69875-127">Paso 3: quitar el malware de los dispositivos afectados</span><span class="sxs-lookup"><span data-stu-id="69875-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="69875-128">Ejecute un análisis antivirus completo con las actualizaciones más recientes en todos los equipos y dispositivos sospechosos para detectar y quitar la carga asociada con el ransomware.</span><span class="sxs-lookup"><span data-stu-id="69875-128">Run a full antivirus scan with the latest updates on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span> <span data-ttu-id="69875-129">No olvide los dispositivos que sincronizan datos o el destino de las unidades de red asignadas (también deben examinarse los equipos y dispositivos).</span><span class="sxs-lookup"><span data-stu-id="69875-129">Don't forget devices that are synchronizing data, or the target of mapped network drives (those computers and devices need to be scanned, too).</span></span>

<span data-ttu-id="69875-130">Puede usar [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) o (para clientes más antiguos) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span><span class="sxs-lookup"><span data-stu-id="69875-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="69875-131">Una alternativa que también le ayudará a quitar ransomware o malware es la [herramienta de eliminación de software malintencionado (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span><span class="sxs-lookup"><span data-stu-id="69875-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="69875-132">Si estas opciones no funcionan, puedes probar [Windows Defender sin conexión](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc) o [solucionar problemas de detección y eliminación de malware](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware).</span><span class="sxs-lookup"><span data-stu-id="69875-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="69875-133">Paso 4: recuperar archivos en un equipo o dispositivo limpio</span><span class="sxs-lookup"><span data-stu-id="69875-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="69875-134">Una vez que haya completado el paso anterior para quitar la carga de ransomware del entorno (lo que impedirá que el ransomware Cifre o quite los archivos), puede usar el [historial de archivos](https://support.microsoft.com/help/17128/windows-8-file-history) en Windows 10 y Windows 8,1 o en la protección del sistema de Windows 7 para intentar recuperar los archivos y carpetas locales.</span><span class="sxs-lookup"><span data-stu-id="69875-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128/windows-8-file-history) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="69875-135">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="69875-135">**Notes**:</span></span>

- <span data-ttu-id="69875-136">Algunos ransomware también cifrarán o eliminarán las versiones de copia de seguridad, por lo que no podrá usar el historial de archivos o la protección del sistema para restaurar archivos.</span><span class="sxs-lookup"><span data-stu-id="69875-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="69875-137">Si esto ocurre, necesita usar copias de seguridad en dispositivos o dispositivos externos que no se vieron afectados por el ransomware o el OneDrive, tal como se describe en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="69875-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="69875-138">Si una carpeta está sincronizada en OneDrive y no usa la versión más reciente de Windows, es posible que existan algunas limitaciones al usar el historial de archivos.</span><span class="sxs-lookup"><span data-stu-id="69875-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="69875-139">Paso 5: recuperar los archivos en su OneDrive para la empresa</span><span class="sxs-lookup"><span data-stu-id="69875-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="69875-140">OneDrive para la empresa le permitirá recuperar los archivos que haya almacenado en él.</span><span class="sxs-lookup"><span data-stu-id="69875-140">OneDrive for Business will allow you to recover any files you have stored in it.</span></span> <span data-ttu-id="69875-141">Tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="69875-141">You have two options:</span></span>

- <span data-ttu-id="69875-142">Use el [sitio web de OneDrive](https://support.office.com/article/159cad6d-d76e-4981-88ef-de6e96c93893).</span><span class="sxs-lookup"><span data-stu-id="69875-142">Use the [OneDrive website](https://support.office.com/article/159cad6d-d76e-4981-88ef-de6e96c93893).</span></span>

- <span data-ttu-id="69875-143">Si se ha visto afectado un gran número de archivos, puede crear una solicitud de soporte técnico para una "restauración de la colección de sitios".</span><span class="sxs-lookup"><span data-stu-id="69875-143">If a large number of files were affected, you can create a support request for a "Site Collection Restore".</span></span> <span data-ttu-id="69875-144">Esta solicitud puede restaurar archivos de hasta 14 días en el pasado.</span><span class="sxs-lookup"><span data-stu-id="69875-144">This request can restore files from up to 14 days in the past.</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="69875-145">Paso 6: recuperar el correo electrónico eliminado</span><span class="sxs-lookup"><span data-stu-id="69875-145">Step 6: Recover deleted email</span></span>

<span data-ttu-id="69875-146">En el caso poco probable de que ransomware elimine todo el correo electrónico, probablemente pueda recuperar los elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="69875-146">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="69875-147">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="69875-147">For more information, see:</span></span>

- [<span data-ttu-id="69875-148">Recuperar mensajes eliminados en el buzón de un usuario</span><span class="sxs-lookup"><span data-stu-id="69875-148">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="69875-149">Recuperación de elementos eliminados en Outlook para Windows</span><span class="sxs-lookup"><span data-stu-id="69875-149">Recover deleted items in Outlook for Windows</span></span>](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="69875-150">Paso 7: volver a habilitar Exchange ActiveSync y la sincronización de OneDrive</span><span class="sxs-lookup"><span data-stu-id="69875-150">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="69875-151">Una vez que haya limpiado los equipos y dispositivos y recuperado los datos, puede volver a habilitar la sincronización de ActiveSync y de OneDrive que deshabilitó anteriormente en el [paso 2](#step-2-disable-activesync-and-onedrive-sync).</span><span class="sxs-lookup"><span data-stu-id="69875-151">After you've cleaned your computers and devices and recovered your data, you can re-enable ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="69875-152">Paso 8 (opcional): bloquear la sincronización de OneDrive para extensiones de archivo específicas</span><span class="sxs-lookup"><span data-stu-id="69875-152">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="69875-153">Una vez que haya recuperado, puede evitar que los clientes de OneDrive para la empresa sincronicen los tipos de archivo afectados por este ransomware.</span><span class="sxs-lookup"><span data-stu-id="69875-153">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="69875-154">Para obtener más información, vea [set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="69875-154">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="69875-155">Informar del ataque</span><span class="sxs-lookup"><span data-stu-id="69875-155">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="69875-156">Aplicación de la ley de contacto</span><span class="sxs-lookup"><span data-stu-id="69875-156">Contact law enforcement</span></span>

<span data-ttu-id="69875-157">Debe ponerse en contacto con las agencias de cumplimiento normativo local o federal.</span><span class="sxs-lookup"><span data-stu-id="69875-157">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="69875-158">Por ejemplo, si está en los Estados Unidos, puede ponerse en contacto con el servicio de oficina, [IC3](http://www.ic3.gov/complaint/default.aspx) o [Secret](http://www.secretservice.gov/)del [FBI local](https://www.fbi.gov/contact-us/field).</span><span class="sxs-lookup"><span data-stu-id="69875-158">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="69875-159">Enviar un informe al sitio web de informes de fraude de su país</span><span class="sxs-lookup"><span data-stu-id="69875-159">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="69875-160">Los sitios web de informes de estafa proporcionan información sobre cómo evitar y evitar estafas.</span><span class="sxs-lookup"><span data-stu-id="69875-160">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="69875-161">También proporcionan mecanismos para informar si ha sido víctima de un timo.</span><span class="sxs-lookup"><span data-stu-id="69875-161">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="69875-162">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="69875-162">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="69875-163">Canadá: [centro anti-fraude canadiense](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="69875-163">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="69875-164">Francia: [Agence Nationale de la Sécurité des Systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="69875-164">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="69875-165">Alemania: [Bundesamt für Sicherheit en der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="69875-165">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="69875-166">Irlanda: [una Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="69875-166">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="69875-167">Nueva Zelanda: [fraudes de asuntos de consumo](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="69875-167">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="69875-168">Reino Unido: [fraude de acciones](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="69875-168">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="69875-169">Estados Unidos: [en protección en línea](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="69875-169">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="69875-170">Si su país no aparece en la lista, pregunte a las agencias de cumplimiento normativo local o federal.</span><span class="sxs-lookup"><span data-stu-id="69875-170">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="69875-171">Enviar mensajes de correo electrónico a Microsoft</span><span class="sxs-lookup"><span data-stu-id="69875-171">Submit email messages to Microsoft</span></span>

<span data-ttu-id="69875-172">Puede informar sobre mensajes de suplantación de identidad (phishing) que contengan ransomware siguiendo las instrucciones de [enviar mensajes de correo no deseado, mensajes seguros y suplantación de identidad a Microsoft para su análisis](https://docs.microsoft.com/microsoft-365/security/office-365-security/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis).</span><span class="sxs-lookup"><span data-stu-id="69875-172">You can report phishing message that contain ransomware by following the instructions in [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](https://docs.microsoft.com/microsoft-365/security/office-365-security/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis).</span></span>

## <a name="see-also"></a><span data-ttu-id="69875-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="69875-173">See also</span></span>

- [<span data-ttu-id="69875-174">Ransomware</span><span class="sxs-lookup"><span data-stu-id="69875-174">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="69875-175">Respuesta por ransomware: ¿pagar o no pagar?</span><span class="sxs-lookup"><span data-stu-id="69875-175">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="69875-176">Norsk de la anhidro responde al ataque de ransomware con transparencia</span><span class="sxs-lookup"><span data-stu-id="69875-176">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="69875-177">Detección de ransomware y recuperación de los archivos en OneDrive</span><span class="sxs-lookup"><span data-stu-id="69875-177">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.office.com/article/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="69875-178">Informe de inteligencia en seguridad de Microsoft</span><span class="sxs-lookup"><span data-stu-id="69875-178">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="69875-179">Habilitar o deshabilitar macros en archivos de Office</span><span class="sxs-lookup"><span data-stu-id="69875-179">Enable or disable macros in Office files</span></span>](https://support.office.com/article/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="69875-180">Configuración recomendada para EOP y la seguridad de ATP de Office 365</span><span class="sxs-lookup"><span data-stu-id="69875-180">Recommended settings for EOP and Office 365 ATP security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [<span data-ttu-id="69875-181">Una actualización que merece la pena: la seguridad de next-gen en Windows 10 prueba resistencia contra brotes de ransomware en 2017</span><span class="sxs-lookup"><span data-stu-id="69875-181">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="69875-182">No hay mas samas: ¿Cuál es el contenido del operando de un modus de ransomware?</span><span class="sxs-lookup"><span data-stu-id="69875-182">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="69875-183">Malware de bloqueo, suerte para evitarlo</span><span class="sxs-lookup"><span data-stu-id="69875-183">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="69875-184">MSRT julio de 2016: ransomware CERBER</span><span class="sxs-lookup"><span data-stu-id="69875-184">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="69875-185">Los tres cabezales del Cerberus-like CERBER ransomware</span><span class="sxs-lookup"><span data-stu-id="69875-185">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="69875-186">Troldesh ransomware afectado por el código de da Vinci</span><span class="sxs-lookup"><span data-stu-id="69875-186">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
