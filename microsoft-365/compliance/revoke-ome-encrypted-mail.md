---
title: Revocar el correo electrónico cifrado por cifrado de mensajes avanzado
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Como administrador y como remitente de mensajes, puede revocar ciertos correos electrónicos cifrados con cifrado avanzado de mensajes de Office 365.
ms.openlocfilehash: 340a9e73dba50e28223ee561db749a089c649df6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051722"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="60e38-103">Revocar el correo electrónico cifrado por cifrado de mensajes avanzado</span><span class="sxs-lookup"><span data-stu-id="60e38-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="60e38-104">La revocación de correo electrónico se ofrece como parte del cifrado avanzado de mensajes de Office 365.</span><span class="sxs-lookup"><span data-stu-id="60e38-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="60e38-105">El cifrado avanzado de mensajes de Office 365 se incluye en [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5 (precios de personal sin ánimo de lucro), Office 365 Enterprise E5 (precios de personal sin ánimo de lucro) y Office 365 Education A5.</span><span class="sxs-lookup"><span data-stu-id="60e38-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="60e38-106">Si su organización tiene una suscripción que no incluye cifrado de mensajes avanzado de Office 365, puede adquirirla con el complemento SKU de cumplimiento de Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (precios de personal sin ánimo de lucro) o el complemento SKU de cumplimiento avanzado de Office 365 para Microsoft 365 E3, Microsoft 365 E3 (precios de personal sin ánimo de lucro) o SKU de Office 365.</span><span class="sxs-lookup"><span data-stu-id="60e38-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="60e38-107">Este artículo forma parte de una serie más grande de artículos sobre cifrado de mensajes de [Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="60e38-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="60e38-108">Si un mensaje se cifra con cifrado de mensajes avanzado de Office 365 y es administrador de Microsoft 365 o es el remitente del mensaje, puede revocarlo en determinadas condiciones.</span><span class="sxs-lookup"><span data-stu-id="60e38-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="60e38-109">Los administradores revocan los mensajes con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60e38-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="60e38-110">Como remitente, revoca un mensaje que envió directamente desde Outlook en la web.</span><span class="sxs-lookup"><span data-stu-id="60e38-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="60e38-111">En este artículo se describen las circunstancias en las que es posible la revocación y cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="60e38-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="60e38-112">Correos electrónicos cifrados que puede revocar</span><span class="sxs-lookup"><span data-stu-id="60e38-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="60e38-113">Los administradores y los remitentes de mensajes pueden revocar los correos electrónicos cifrados si el destinatario recibió un correo electrónico cifrado basado en vínculos con marca.</span><span class="sxs-lookup"><span data-stu-id="60e38-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="60e38-114">Si el destinatario recibió una experiencia nativa en línea en un cliente de Outlook compatible, no puede revocar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="60e38-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="60e38-115">Si un destinatario recibe una experiencia basada en vínculos o una experiencia en línea depende del tipo de identidad del destinatario: los destinatarios de office 365 y cuenta microsoft (por ejemplo, usuarios de outlook.com) obtienen una experiencia en línea en clientes de Outlook compatibles.</span><span class="sxs-lookup"><span data-stu-id="60e38-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="60e38-116">Todos los demás tipos de destinatarios, como los destinatarios de Gmail y Yahoo, obtienen una experiencia basada en vínculos.</span><span class="sxs-lookup"><span data-stu-id="60e38-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="60e38-117">Los administradores y remitentes de mensajes pueden revocar los mensajes cifrados mediante el cifrado aplicado directamente desde Outlook en la web.</span><span class="sxs-lookup"><span data-stu-id="60e38-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="60e38-118">Por ejemplo, los mensajes cifrados con la opción Cifrar solo.</span><span class="sxs-lookup"><span data-stu-id="60e38-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Captura de pantalla que muestra la opción Cifrar solo en Outlook en la web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="60e38-120">Experiencia de destinatarios para correos electrónicos cifrados revocados</span><span class="sxs-lookup"><span data-stu-id="60e38-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="60e38-121">Una vez revocado un correo electrónico, el destinatario recibe un error al obtener acceso al correo electrónico cifrado a través del portal de cifrado de mensajes de Office 365: "El remitente ha revocado el mensaje".</span><span class="sxs-lookup"><span data-stu-id="60e38-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![Captura de pantalla que muestra un correo electrónico cifrado revocado.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="60e38-123">Cómo revocar un mensaje cifrado que envió</span><span class="sxs-lookup"><span data-stu-id="60e38-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="60e38-124">Puede revocar un correo que envió a un único destinatario que usa una cuenta social como gmail.com o yahoo.com.</span><span class="sxs-lookup"><span data-stu-id="60e38-124">You can revoke a mail that you sent to a single recipient that uses a social account such as gmail.com or yahoo.com.</span></span> <span data-ttu-id="60e38-125">En otras palabras, puede revocar un correo electrónico enviado a un único destinatario que recibió la experiencia basada en vínculos.</span><span class="sxs-lookup"><span data-stu-id="60e38-125">In other words, you can revoke an email sent to a single recipient that received the link-based experience.</span></span>

<span data-ttu-id="60e38-126">No puede revocar un correo que envió a un destinatario que usa una cuenta laboral o educativa de Office 365 o Microsoft 365 o un usuario que usa una cuenta de Microsoft, por ejemplo, una cuenta outlook.com.</span><span class="sxs-lookup"><span data-stu-id="60e38-126">You cannot revoke a mail that you sent to a recipient that uses a work or school account from Office 365 or Microsoft 365 or a user that uses a Microsoft account, for example, an outlook.com account.</span></span> 

<span data-ttu-id="60e38-127">Para revocar un mensaje cifrado que envió, siga estos pasos</span><span class="sxs-lookup"><span data-stu-id="60e38-127">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="60e38-128">En Outlook en la web, en la **carpeta Enviado,** busque el mensaje que desea revocar.</span><span class="sxs-lookup"><span data-stu-id="60e38-128">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="60e38-129">Si el correo es revocable, verá el vínculo "Quitar acceso externo" en la parte superior del mensaje.</span><span class="sxs-lookup"><span data-stu-id="60e38-129">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Captura de pantalla que muestra el correo cifrado que desea revocar en Outlook en la web.":::

2. <span data-ttu-id="60e38-131">Haga **clic en Quitar acceso externo** para revocar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="60e38-131">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="60e38-132">El mensaje muestra que su estado se revoca.</span><span class="sxs-lookup"><span data-stu-id="60e38-132">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Captura de pantalla que muestra un mensaje cifrado revocado en Outlook en la web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="60e38-134">Cómo revocar un mensaje cifrado como administrador</span><span class="sxs-lookup"><span data-stu-id="60e38-134">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="60e38-135">Los administradores de Microsoft 365 siguen estos pasos generales para revocar un correo electrónico cifrado elegible:</span><span class="sxs-lookup"><span data-stu-id="60e38-135">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="60e38-136">Obtener el identificador de mensaje del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="60e38-136">Get the Message ID of the email.</span></span>
- <span data-ttu-id="60e38-137">Compruebe que puede revocar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="60e38-137">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="60e38-138">Revocar el correo.</span><span class="sxs-lookup"><span data-stu-id="60e38-138">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="60e38-139">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="60e38-139">Step 1.</span></span> <span data-ttu-id="60e38-140">Obtener el identificador de mensaje del correo electrónico</span><span class="sxs-lookup"><span data-stu-id="60e38-140">Obtain the Message ID of the email</span></span>

<span data-ttu-id="60e38-141">Antes de poder revocar un correo cifrado, recopilo el identificador de mensaje del correo.</span><span class="sxs-lookup"><span data-stu-id="60e38-141">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="60e38-142">MessageId suele tener el formato:</span><span class="sxs-lookup"><span data-stu-id="60e38-142">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="60e38-143">Hay varias maneras de buscar el identificador de mensaje del correo electrónico que desea revocar.</span><span class="sxs-lookup"><span data-stu-id="60e38-143">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="60e38-144">En esta sección se describen un par de opciones, pero puede usar cualquier método que proporciona el identificador.</span><span class="sxs-lookup"><span data-stu-id="60e38-144">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="60e38-145">Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante el seguimiento de mensajes en el Centro de &amp; cumplimiento de seguridad</span><span class="sxs-lookup"><span data-stu-id="60e38-145">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="60e38-146">Busque el correo electrónico por remitente o destinatario mediante Nuevo seguimiento de mensajes en el Centro de [seguridad & cumplimiento](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="60e38-146">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="60e38-147">Una vez que haya localizado el correo electrónico, selecciónelo para que se active el panel **Detalles del seguimiento de** mensajes.</span><span class="sxs-lookup"><span data-stu-id="60e38-147">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="60e38-148">Expanda **Más información para** buscar el identificador de mensaje.</span><span class="sxs-lookup"><span data-stu-id="60e38-148">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="60e38-149">Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante informes de cifrado de mensajes de Office en el Centro de &amp; cumplimiento de seguridad</span><span class="sxs-lookup"><span data-stu-id="60e38-149">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="60e38-150">En el Centro de &amp; cumplimiento de seguridad, vaya al informe **cifrado de mensajes**.</span><span class="sxs-lookup"><span data-stu-id="60e38-150">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="60e38-151">Para obtener información sobre este informe, vea Ver informes de [seguridad de correo electrónico en el Centro de cumplimiento de &amp; seguridad](../security/defender-365-security/view-email-security-reports.md).</span><span class="sxs-lookup"><span data-stu-id="60e38-151">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/defender-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="60e38-152">Elija la **tabla Ver detalles** e identifique el mensaje que desea revocar.</span><span class="sxs-lookup"><span data-stu-id="60e38-152">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="60e38-153">Haga doble clic en el mensaje para ver los detalles que incluyen el identificador de mensaje.</span><span class="sxs-lookup"><span data-stu-id="60e38-153">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="60e38-154">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="60e38-154">Step 2.</span></span> <span data-ttu-id="60e38-155">Comprobar que el correo es revocable</span><span class="sxs-lookup"><span data-stu-id="60e38-155">Verify that the mail is revocable</span></span>

<span data-ttu-id="60e38-156">Para comprobar si puede revocar un mensaje, compruebe si el campo Estado  de revocación está visible en el informe cifrado, en la tabla Detalles del Centro de &amp; cumplimiento de seguridad.</span><span class="sxs-lookup"><span data-stu-id="60e38-156">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="60e38-157">Para comprobar si puede revocar un mensaje de correo electrónico determinado mediante Windows PowerShell, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="60e38-157">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="60e38-158">Con una cuenta laboral o educativa que tenga permisos de administrador global en su organización, inicie una sesión de Windows PowerShell y conéctese a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="60e38-158">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="60e38-159">Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="60e38-159">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="60e38-160">Ejecute el cmdlet Get-OMEMessageStatus de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="60e38-160">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="60e38-161">Este comando devuelve el asunto del mensaje y si el mensaje es revocable.</span><span class="sxs-lookup"><span data-stu-id="60e38-161">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="60e38-162">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="60e38-162">For example,</span></span>

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="60e38-163">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="60e38-163">Step 3.</span></span> <span data-ttu-id="60e38-164">Revocar el correo</span><span class="sxs-lookup"><span data-stu-id="60e38-164">Revoke the mail</span></span>

<span data-ttu-id="60e38-165">Una vez que conozca el identificador de mensaje del correo electrónico que desea revocar y haya comprobado que el mensaje es revocable, puede revocar el correo electrónico mediante el Centro de cumplimiento de seguridad &amp; o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60e38-165">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="60e38-166">Para revocar el mensaje mediante el Centro de &amp; cumplimiento de seguridad</span><span class="sxs-lookup"><span data-stu-id="60e38-166">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="60e38-167">Con una cuenta laboral o educativa que tenga permisos de administrador global en su organización, conéctese al Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="60e38-167">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="60e38-168">En el **informe Cifrado**, en la **tabla Detalles** del mensaje, elija Revocar **mensaje**.</span><span class="sxs-lookup"><span data-stu-id="60e38-168">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="60e38-169">Para revocar un correo electrónico mediante Windows PowerShell, use el cmdlet Set-OMEMessageRevocation.</span><span class="sxs-lookup"><span data-stu-id="60e38-169">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="60e38-170">Con una cuenta laboral o educativa que tenga permisos de administrador global en su organización, Conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="60e38-170">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="60e38-171">Ejecute el cmdlet Set-OMEMessageRevocation de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="60e38-171">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="60e38-172">Para comprobar si el correo electrónico se revocó, ejecute el cmdlet Get-OMEMessageStatus de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="60e38-172">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="60e38-173">Si la revocación se ha realizado correctamente, el cmdlet devuelve el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="60e38-173">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="60e38-174">Más información sobre el cifrado de mensajes avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="60e38-174">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="60e38-175">Cifrado avanzado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="60e38-175">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="60e38-176">Cifrado de mensajes avanzado de Office 365: expiración de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="60e38-176">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="60e38-177">Descripción del servicio de cumplimiento y directiva de mensajes</span><span class="sxs-lookup"><span data-stu-id="60e38-177">Message policy and compliance service description</span></span>](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)