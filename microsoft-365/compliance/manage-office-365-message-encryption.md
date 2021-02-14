---
title: Administrar el Cifrado de mensajes de Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Una vez que haya terminado de configurar el cifrado de mensajes de Office 365 (OME), aprenda a personalizar la implementación de varias maneras.
ms.openlocfilehash: 83fa620852ea9b2e0cd50d50b6715742658b7239
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815437"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="78375-103">Administrar el Cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="78375-103">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="78375-104">Una vez que haya terminado de configurar el Cifrado de mensajes de Office 365 (OME), puede personalizar la configuración de la implementación de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="78375-104">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="78375-105">Por ejemplo, puede configurar si desea habilitar códigos  de paso de un solo uso, mostrar el botón Cifrar en Outlook en la Web y mucho más.</span><span class="sxs-lookup"><span data-stu-id="78375-105">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="78375-106">Las tareas de este artículo describen cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="78375-106">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="78375-107">Administrar si los destinatarios de cuentas de Google, Yahoo y Microsoft pueden usar estas cuentas para iniciar sesión en el portal de cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="78375-107">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="78375-108">Al configurar las nuevas capacidades de cifrado de mensajes de Office 365, los usuarios de su organización pueden enviar mensajes a destinatarios que están fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="78375-108">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your organization.</span></span> <span data-ttu-id="78375-109">Si el destinatario usa un id. *social* como una cuenta de Google, una cuenta de Yahoo o una cuenta de Microsoft, el destinatario puede iniciar sesión en el portal de OME con un id. social.</span><span class="sxs-lookup"><span data-stu-id="78375-109">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="78375-110">Si lo desea, puede elegir no permitir que los destinatarios usen los IDs sociales para iniciar sesión en el portal de OME.</span><span class="sxs-lookup"><span data-stu-id="78375-110">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="78375-111">Para administrar si los destinatarios pueden usar los IDs sociales para iniciar sesión en el portal de OME</span><span class="sxs-lookup"><span data-stu-id="78375-111">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="78375-112">[Conéctese a Exchange Online con PowerShell remoto.](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="78375-112">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="78375-113">Ejecute el cmdlet Set-OMEConfiguration con el parámetro SocialIdSignIn de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="78375-113">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="78375-114">Por ejemplo, para deshabilitar los IDs sociales:</span><span class="sxs-lookup"><span data-stu-id="78375-114">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="78375-115">Para habilitar los IDs sociales:</span><span class="sxs-lookup"><span data-stu-id="78375-115">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="78375-116">Administrar el uso de códigos de paso de un solo uso para el portal de cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="78375-116">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="78375-117">Si el destinatario de un mensaje cifrado por OME no usa Outlook, independientemente de la cuenta usada por el destinatario, el destinatario recibe un vínculo de vista web de tiempo limitado que le permite leer el mensaje.</span><span class="sxs-lookup"><span data-stu-id="78375-117">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="78375-118">Este vínculo incluye un código de paso único.</span><span class="sxs-lookup"><span data-stu-id="78375-118">This link includes a one-time pass code.</span></span> <span data-ttu-id="78375-119">Como administrador, puede decidir si los destinatarios pueden usar códigos de paso de un solo uso para iniciar sesión en el portal de OME.</span><span class="sxs-lookup"><span data-stu-id="78375-119">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="78375-120">Para administrar si OME genera códigos de paso de un solo paso</span><span class="sxs-lookup"><span data-stu-id="78375-120">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="78375-121">Use una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización e inicie una sesión de Windows PowerShell y conéctese a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="78375-121">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="78375-122">Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="78375-122">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="78375-123">Ejecute el cmdlet Set-OMEConfiguration con el parámetro OTPEnabled:</span><span class="sxs-lookup"><span data-stu-id="78375-123">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="78375-124">Por ejemplo, para deshabilitar los códigos de paso de un solo uso:</span><span class="sxs-lookup"><span data-stu-id="78375-124">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="78375-125">Para habilitar códigos de paso de un solo uso:</span><span class="sxs-lookup"><span data-stu-id="78375-125">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="78375-126">Administrar la visualización del botón Cifrar en Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="78375-126">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="78375-127">Como administrador, puede administrar si desea mostrar este botón a los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="78375-127">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="78375-128">Para administrar si el botón Cifrar aparece en Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="78375-128">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="78375-129">Use una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización e inicie una sesión de Windows PowerShell y conéctese a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="78375-129">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="78375-130">Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="78375-130">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="78375-131">Ejecute el cmdlet Set-IRMConfiguration con el parámetro -SimplifiedClientAccessEnabled:</span><span class="sxs-lookup"><span data-stu-id="78375-131">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="78375-132">Por ejemplo, para deshabilitar el **botón Cifrar:**</span><span class="sxs-lookup"><span data-stu-id="78375-132">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="78375-133">Para habilitar el **botón** Cifrar:</span><span class="sxs-lookup"><span data-stu-id="78375-133">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="78375-134">Habilitar el descifrado del lado del servicio de los mensajes de correo electrónico para los usuarios de la aplicación de correo de iOS</span><span class="sxs-lookup"><span data-stu-id="78375-134">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="78375-135">La aplicación de correo de iOS no puede descifrar mensajes protegidos con el cifrado de mensajes de Office 365.</span><span class="sxs-lookup"><span data-stu-id="78375-135">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="78375-136">Como administrador de Microsoft 365, puede aplicar el descifrado del lado del servicio para los mensajes entregados a la aplicación de correo de iOS.</span><span class="sxs-lookup"><span data-stu-id="78375-136">As a Microsoft 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="78375-137">Cuando decide usar el descifrado del lado del servicio, el servicio envía una copia descifrada del mensaje al dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="78375-137">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="78375-138">El dispositivo cliente almacena una copia descifrada del mensaje.</span><span class="sxs-lookup"><span data-stu-id="78375-138">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="78375-139">El mensaje también conserva información sobre los derechos de uso aunque la aplicación de correo de iOS no aplique derechos de uso del lado cliente al usuario.</span><span class="sxs-lookup"><span data-stu-id="78375-139">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="78375-140">El usuario puede copiar o imprimir el mensaje incluso si originalmente no tenía los derechos para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="78375-140">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="78375-141">Sin embargo, si el usuario intenta completar una acción que requiere el servidor de correo de Microsoft 365, como reenviar el mensaje, el servidor no permitirá la acción si el usuario no tenía originalmente el derecho de uso para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="78375-141">However, if the user attempts to complete an action that requires the Microsoft 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="78375-142">Sin embargo, los usuarios finales pueden evitar la restricción de uso "No reenviar" reenviando el mensaje desde una cuenta diferente dentro de la aplicación de correo de iOS.</span><span class="sxs-lookup"><span data-stu-id="78375-142">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="78375-143">Independientemente de si configura el descifrado del lado del servicio de correo, los datos adjuntos del correo cifrado y protegidos con derechos no se pueden ver en la aplicación de correo de iOS.</span><span class="sxs-lookup"><span data-stu-id="78375-143">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="78375-144">Si decide no permitir que los mensajes descifrados se envíen a los usuarios de la aplicación de correo de iOS, los usuarios recibirán un mensaje que indica que no tienen los derechos para ver el mensaje.</span><span class="sxs-lookup"><span data-stu-id="78375-144">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="78375-145">De forma predeterminada, el descifrado del lado del servicio de los mensajes de correo electrónico no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="78375-145">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="78375-146">Para obtener más información y ver una vista de la experiencia del cliente, vea Ver mensajes cifrados en [su iPhone o iPad.](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)</span><span class="sxs-lookup"><span data-stu-id="78375-146">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="78375-147">Para administrar si los usuarios de la aplicación de correo de iOS pueden ver los mensajes protegidos por el cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="78375-147">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="78375-148">Use una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización e inicie una sesión de Windows PowerShell y conéctese a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="78375-148">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="78375-149">Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="78375-149">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="78375-150">Ejecute el cmdlet Set-ActiveSyncOrganizations cmdlet con el parámetro AllowRMSSupportForUnenlightenedApps:</span><span class="sxs-lookup"><span data-stu-id="78375-150">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="78375-151">Por ejemplo, para configurar el servicio para descifrar mensajes antes de que se envíen a aplicaciones no disponibles como la aplicación de correo de iOS:</span><span class="sxs-lookup"><span data-stu-id="78375-151">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="78375-152">O bien, para configurar el servicio para que no envíe mensajes descifrados a aplicaciones no disponibles:</span><span class="sxs-lookup"><span data-stu-id="78375-152">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> <span data-ttu-id="78375-153">Las directivas de buzón individuales (OWA/ActiveSync) invalidan esta configuración (es decir, si -IRMEnabled se establece en False dentro de la directiva de buzón de OWA correspondiente o en la directiva de buzón de ActiveSync, estas configuraciones no se aplicarían).</span><span class="sxs-lookup"><span data-stu-id="78375-153">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="78375-154">Habilitar el descifrado del lado del servicio de datos adjuntos de correo electrónico para clientes de correo del explorador web</span><span class="sxs-lookup"><span data-stu-id="78375-154">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="78375-155">Normalmente, al usar el cifrado de mensajes de Office 365, los datos adjuntos se cifran automáticamente.</span><span class="sxs-lookup"><span data-stu-id="78375-155">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="78375-156">Como administrador, puede aplicar el descifrado del lado del servicio para los datos adjuntos de correo electrónico que los usuarios descargan desde un explorador web.</span><span class="sxs-lookup"><span data-stu-id="78375-156">As an administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="78375-157">Al usar el descifrado del lado del servicio, el servicio envía una copia descifrada del archivo al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="78375-157">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="78375-158">El mensaje aún está cifrado.</span><span class="sxs-lookup"><span data-stu-id="78375-158">The message is still encrypted.</span></span> <span data-ttu-id="78375-159">Los datos adjuntos de correo electrónico también mantienen información sobre los derechos de uso aunque el explorador no aplique derechos de uso del lado cliente al usuario.</span><span class="sxs-lookup"><span data-stu-id="78375-159">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="78375-160">El usuario puede copiar o imprimir los datos adjuntos del correo electrónico incluso si originalmente no tenía los derechos para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="78375-160">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="78375-161">Sin embargo, si el usuario intenta completar una acción que requiere el servidor de correo de Microsoft 365, como reenviar los datos adjuntos, el servidor no permitirá la acción si el usuario no tenía originalmente el derecho de uso para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="78375-161">However, if the user tries to complete an action that requires the Microsoft 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="78375-162">Independientemente de si configura el descifrado del lado del servicio de los datos adjuntos, los usuarios no pueden ver ningún archivo adjunto al correo cifrado y protegido con derechos en la aplicación de correo de iOS.</span><span class="sxs-lookup"><span data-stu-id="78375-162">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="78375-163">Si decide no permitir datos adjuntos de correo electrónico descifrados, que es el valor predeterminado, los usuarios reciben un mensaje que indica que no tienen los derechos para ver los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="78375-163">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="78375-164">Para obtener más información acerca de cómo Microsoft 365 implementa el cifrado para correos electrónicos y datos adjuntos de correo electrónico con la opción Encrypt-Only, vea la opción Cifrar solo para mensajes de [correo electrónico.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="78375-164">For more information about how Microsoft 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="78375-165">Para administrar si los datos adjuntos de correo electrónico se descifran al descargarlos desde un explorador web</span><span class="sxs-lookup"><span data-stu-id="78375-165">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="78375-166">Use una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización e inicie una sesión de Windows PowerShell y conéctese a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="78375-166">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="78375-167">Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="78375-167">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="78375-168">Ejecute el cmdlet Set-IRMConfiguration cmdlet con el parámetro DecryptAttachmentForEncryptOnly:</span><span class="sxs-lookup"><span data-stu-id="78375-168">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentForEncryptOnly parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   <span data-ttu-id="78375-169">Por ejemplo, para configurar el servicio para descifrar datos adjuntos de correo electrónico cuando un usuario los descarga desde un explorador web:</span><span class="sxs-lookup"><span data-stu-id="78375-169">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   <span data-ttu-id="78375-170">Para configurar el servicio de forma que deje los datos adjuntos de correo electrónico cifrados tal como están al descargarlos:</span><span class="sxs-lookup"><span data-stu-id="78375-170">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a><span data-ttu-id="78375-171">Asegurarse de que todos los destinatarios externos usan el Portal de OME para leer correo cifrado</span><span class="sxs-lookup"><span data-stu-id="78375-171">Ensure all external recipients use the OME Portal to read encrypted mail</span></span>

<span data-ttu-id="78375-172">Puede usar plantillas de personalización de marca personalizadas para obligar a los destinatarios a recibir un correo contenedor que les dirija a leer correo electrónico cifrado en el Portal de OME en lugar de usar Outlook o Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="78375-172">You can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="78375-173">Es posible que desee hacerlo si desea un mayor control sobre cómo usan los destinatarios el correo que reciben.</span><span class="sxs-lookup"><span data-stu-id="78375-173">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="78375-174">Por ejemplo, si los destinatarios externos ven el correo electrónico en el portal web, puede establecer una fecha de expiración para el correo electrónico y puede revocar el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="78375-174">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="78375-175">Estas características solo se admiten a través del Portal de OME.</span><span class="sxs-lookup"><span data-stu-id="78375-175">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="78375-176">Puede usar las opciones Cifrar y No reenviar al crear las reglas de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="78375-176">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a><span data-ttu-id="78375-177">Usar una plantilla personalizada para forzar a todos los destinatarios externos a usar el Portal de OME y para el correo electrónico cifrado</span><span class="sxs-lookup"><span data-stu-id="78375-177">Use a custom template to force all external recipients to use the OME Portal and for encrypted email</span></span>

1. <span data-ttu-id="78375-178">Use una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización e inicie una sesión de Windows PowerShell y conéctese a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="78375-178">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="78375-179">Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="78375-179">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="78375-180">Ejecute el cmdlet New-TransportRule:</span><span class="sxs-lookup"><span data-stu-id="78375-180">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="78375-181">donde:</span><span class="sxs-lookup"><span data-stu-id="78375-181">where:</span></span>

   - <span data-ttu-id="78375-182">`mail flow rule name` es el nombre que desea usar para la nueva regla de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="78375-182">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="78375-183">`option name` es uno `Encrypt` o `Do Not Forward` .</span><span class="sxs-lookup"><span data-stu-id="78375-183">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="78375-184">`template name` es el nombre que le ha dado a la plantilla de personalización de marca personalizada, por `OME Configuration` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="78375-184">`template name` is the name you gave the custom branding template, for example `OME Configuration`.</span></span>

   <span data-ttu-id="78375-185">Para cifrar todo el correo electrónico externo con la plantilla "Configuración de OME" y aplicar la Encrypt-Only siguiente:</span><span class="sxs-lookup"><span data-stu-id="78375-185">To encrypt all external email with the "OME Configuration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   <span data-ttu-id="78375-186">Para cifrar todo el correo electrónico externo con la plantilla "Configuración de OME" y aplicar la opción No reenviar:</span><span class="sxs-lookup"><span data-stu-id="78375-186">To encrypt all external email with the "OME Configuration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="78375-187">Personalizar la apariencia de los mensajes de correo electrónico y el portal de OME</span><span class="sxs-lookup"><span data-stu-id="78375-187">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="78375-188">Para obtener información detallada sobre cómo personalizar OME para su organización, vea Agregar la marca de su organización [a los mensajes cifrados.](add-your-organization-brand-to-encrypted-messages.md)</span><span class="sxs-lookup"><span data-stu-id="78375-188">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="78375-189">Deshabilitar las nuevas funcionalidades para OME</span><span class="sxs-lookup"><span data-stu-id="78375-189">Disable the new capabilities for OME</span></span>

<span data-ttu-id="78375-190">Esperamos que no se haga, pero si es necesario, deshabilitar las nuevas funcionalidades para OME es muy sencillo.</span><span class="sxs-lookup"><span data-stu-id="78375-190">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="78375-191">En primer lugar, deberá quitar todas las reglas de flujo de correo que haya creado que usen las nuevas funcionalidades de OME.</span><span class="sxs-lookup"><span data-stu-id="78375-191">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="78375-192">Para obtener información acerca de cómo quitar reglas de flujo de correo, vea [Administrar reglas de flujo de correo.](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="78375-192">For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span></span> <span data-ttu-id="78375-193">A continuación, siga estos pasos en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78375-193">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="78375-194">Para deshabilitar las nuevas funcionalidades para OME</span><span class="sxs-lookup"><span data-stu-id="78375-194">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="78375-195">Con una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, inicie una sesión de Windows PowerShell y conéctese a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="78375-195">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="78375-196">Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="78375-196">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="78375-197">Si habilitó el **botón** Cifrar en Outlook en la Web, deshabilitelo ejecutando el cmdlet Set-IRMConfiguration con el parámetro SimplifiedClientAccessEnabled.</span><span class="sxs-lookup"><span data-stu-id="78375-197">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="78375-198">De lo contrario, omita este paso.</span><span class="sxs-lookup"><span data-stu-id="78375-198">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="78375-199">Deshabilite las nuevas funcionalidades para OME ejecutando el cmdlet Set-IRMConfiguration con el parámetro AzureRMSLicensingEnabled establecido en false:</span><span class="sxs-lookup"><span data-stu-id="78375-199">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
