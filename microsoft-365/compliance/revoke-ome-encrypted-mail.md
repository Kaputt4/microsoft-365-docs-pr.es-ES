---
title: Revocar correo electrónico cifrado por el cifrado de mensajes avanzado
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
description: Como administrador y como remitente del mensaje, puede revocar determinados mensajes de correo electrónico cifrados con el cifrado de mensajes avanzado de Office 365.
ms.openlocfilehash: 79ab3ef801d4d19317cbf1416d858de74d9f1393
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868964"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="dd880-103">Revocar correo electrónico cifrado por el cifrado de mensajes avanzado</span><span class="sxs-lookup"><span data-stu-id="dd880-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="dd880-104">La revocación de correo electrónico se ofrece como parte de un cifrado de mensajes avanzado de Office 365.</span><span class="sxs-lookup"><span data-stu-id="dd880-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="dd880-105">Office 365 Advanced Message Encryption se incluye en [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (precio de personal sin ánimo de lucro), Office 365 Enterprise E5 (precio de personal sin ánimo de lucro) y Office 365 Education A5.</span><span class="sxs-lookup"><span data-stu-id="dd880-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="dd880-106">Si su organización tiene una suscripción que no incluye el cifrado avanzado de mensajes de Office 365, puede adquirirlo con el complemento de SKU de cumplimiento de Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (precios para trabajadores sin ánimo de lucro), o el complemento de SKU de Office 365 Advanced Compliance para Microsoft 365 E3, Microsoft 365 E3 (no lucrativa personal) u Office 365 SKU.</span><span class="sxs-lookup"><span data-stu-id="dd880-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="dd880-107">Este artículo forma parte de una amplia serie de artículos sobre el [cifrado de mensajes de Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="dd880-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="dd880-108">Si un mensaje se cifró mediante el cifrado de mensajes avanzado de Office 365 y es administrador de Microsoft 365 o usted es el remitente del mensaje, puede revocar el mensaje en determinadas condiciones.</span><span class="sxs-lookup"><span data-stu-id="dd880-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="dd880-109">Los administradores revocan los mensajes con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd880-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="dd880-110">Como remitente, revoca un mensaje que envió directamente desde Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="dd880-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="dd880-111">En este artículo se describen las circunstancias en las que es posible la revocación y cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="dd880-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="dd880-112">Mensajes de correo electrónico cifrados que puede revocar</span><span class="sxs-lookup"><span data-stu-id="dd880-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="dd880-113">Los administradores y los remitentes de mensajes pueden revocar correos electrónicos cifrados si el destinatario recibe un correo electrónico cifrado basado en vínculos y con marcas.</span><span class="sxs-lookup"><span data-stu-id="dd880-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="dd880-114">Si el destinatario recibe una experiencia en línea nativa en un cliente de Outlook compatible, no podrá revocar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="dd880-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="dd880-115">El hecho de que un destinatario reciba una experiencia basada en vínculos o una experiencia en línea depende del tipo de identidad del destinatario: Office 365 y los destinatarios de la cuenta de Microsoft (por ejemplo, usuarios outlook.com) obtienen una experiencia en línea en clientes de Outlook compatibles.</span><span class="sxs-lookup"><span data-stu-id="dd880-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="dd880-116">Todos los demás tipos de destinatarios, como los destinatarios de gmail y Yahoo, obtienen una experiencia basada en vínculos.</span><span class="sxs-lookup"><span data-stu-id="dd880-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="dd880-117">Los administradores y los remitentes de mensajes pueden revocar mensajes cifrados mediante el cifrado que se aplican directamente desde Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="dd880-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="dd880-118">Por ejemplo, los mensajes cifrados con la opción solo cifrar.</span><span class="sxs-lookup"><span data-stu-id="dd880-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Captura de pantalla que muestra la opción solo cifrar en Outlook en la Web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="dd880-120">Experiencia del destinatario para correos electrónicos cifrados revocados</span><span class="sxs-lookup"><span data-stu-id="dd880-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="dd880-121">Una vez que se ha revocado un correo electrónico, el destinatario recibe un error cuando accede al correo electrónico cifrado a través del portal de cifrado de mensajes de Office 365: "el remitente ha revocado el mensaje".</span><span class="sxs-lookup"><span data-stu-id="dd880-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![Captura de pantalla que muestra un correo electrónico cifrado revocado.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="dd880-123">Cómo revocar un mensaje cifrado que envió</span><span class="sxs-lookup"><span data-stu-id="dd880-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="dd880-124">Para revocar un mensaje cifrado que envió, siga estos pasos</span><span class="sxs-lookup"><span data-stu-id="dd880-124">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="dd880-125">En Outlook en la web, en la carpeta **enviados** , busque el mensaje que desea revocar.</span><span class="sxs-lookup"><span data-stu-id="dd880-125">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="dd880-126">Si el correo es revocable, verá el vínculo "Quitar acceso externo" en la parte superior del mensaje.</span><span class="sxs-lookup"><span data-stu-id="dd880-126">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Captura de pantalla que muestra el correo cifrado que desea revocar en Outlook en la Web.":::

2. <span data-ttu-id="dd880-128">Haga clic en **Quitar acceso externo** para revocar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="dd880-128">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="dd880-129">El mensaje muestra que su estado es revocado.</span><span class="sxs-lookup"><span data-stu-id="dd880-129">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Captura de pantalla que muestra el mensaje cifrado revocado en Outlook en la Web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="dd880-131">Cómo revocar un mensaje cifrado como administrador</span><span class="sxs-lookup"><span data-stu-id="dd880-131">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="dd880-132">Los administradores de Microsoft 365 siguen estos pasos generales para revocar un correo electrónico cifrado apto:</span><span class="sxs-lookup"><span data-stu-id="dd880-132">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="dd880-133">Obtenga el identificador de mensaje del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="dd880-133">Get the Message ID of the email.</span></span>
- <span data-ttu-id="dd880-134">Compruebe que puede revocar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="dd880-134">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="dd880-135">Revocar el correo.</span><span class="sxs-lookup"><span data-stu-id="dd880-135">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="dd880-136">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="dd880-136">Step 1.</span></span> <span data-ttu-id="dd880-137">Obtener el identificador del mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="dd880-137">Obtain the Message ID of the email</span></span>

<span data-ttu-id="dd880-138">Para poder revocar un correo cifrado, reúna el identificador de mensaje del correo.</span><span class="sxs-lookup"><span data-stu-id="dd880-138">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="dd880-139">El MessageId suele tener el formato:</span><span class="sxs-lookup"><span data-stu-id="dd880-139">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="dd880-140">Hay varias formas de buscar el identificador de mensaje del correo electrónico que desea revocar.</span><span class="sxs-lookup"><span data-stu-id="dd880-140">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="dd880-141">En esta sección se describen un par de opciones, pero puede usar cualquier método que proporcione el ID.</span><span class="sxs-lookup"><span data-stu-id="dd880-141">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="dd880-142">Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante el seguimiento de mensajes en el centro de seguridad y &amp; cumplimiento</span><span class="sxs-lookup"><span data-stu-id="dd880-142">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="dd880-143">Busque el correo electrónico por remitente o destinatario mediante el [seguimiento de mensajes nuevos en el centro de seguridad & cumplimiento](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="dd880-143">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="dd880-144">Una vez que haya encontrado el correo electrónico, selecciónelo para que aparezca el panel de **detalles de seguimiento de mensajes** .</span><span class="sxs-lookup"><span data-stu-id="dd880-144">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="dd880-145">Expanda **más información** para buscar el identificador de mensaje.</span><span class="sxs-lookup"><span data-stu-id="dd880-145">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="dd880-146">Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante los informes de cifrado de mensajes de Office en el centro de seguridad y &amp; cumplimiento</span><span class="sxs-lookup"><span data-stu-id="dd880-146">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="dd880-147">En el centro de seguridad &amp; y cumplimiento, navegue hasta el **Informe de cifrado de mensajes**.</span><span class="sxs-lookup"><span data-stu-id="dd880-147">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="dd880-148">Para obtener información sobre este informe, consulte [ver informes de seguridad de correo electrónico en el centro de seguridad y &amp; cumplimiento](../security/office-365-security/view-email-security-reports.md).</span><span class="sxs-lookup"><span data-stu-id="dd880-148">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="dd880-149">Elija la tabla **Ver detalles** e identifique el mensaje que desea revocar.</span><span class="sxs-lookup"><span data-stu-id="dd880-149">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="dd880-150">Haga doble clic en el mensaje para ver los detalles que incluyen el identificador del mensaje.</span><span class="sxs-lookup"><span data-stu-id="dd880-150">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="dd880-151">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="dd880-151">Step 2.</span></span> <span data-ttu-id="dd880-152">Comprobar que el correo es revocable</span><span class="sxs-lookup"><span data-stu-id="dd880-152">Verify that the mail is revocable</span></span>

<span data-ttu-id="dd880-153">Para comprobar si puede revocar un mensaje, compruebe si el campo Estado de revocación está visible en el informe de cifrado, en la tabla de **detalles** del centro de seguridad y &amp; cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="dd880-153">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="dd880-154">Para comprobar si puede revocar un mensaje de correo electrónico determinado mediante Windows PowerShell, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="dd880-154">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="dd880-155">Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, inicie una sesión de Windows PowerShell y conéctese a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dd880-155">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="dd880-156">Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="dd880-156">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="dd880-157">Ejecute el cmdlet Get-OMEMessageStatus de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="dd880-157">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="dd880-158">Este comando devuelve el asunto del mensaje y si el mensaje es revocable.</span><span class="sxs-lookup"><span data-stu-id="dd880-158">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="dd880-159">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="dd880-159">For example,</span></span>

     ```text
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="dd880-160">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="dd880-160">Step 3.</span></span> <span data-ttu-id="dd880-161">Revocar el correo</span><span class="sxs-lookup"><span data-stu-id="dd880-161">Revoke the mail</span></span>

<span data-ttu-id="dd880-162">Una vez que conozca el identificador de mensaje del correo electrónico que desea revocar y haya comprobado que el mensaje es revocable, puede revocar el correo electrónico mediante el centro de seguridad y &amp; cumplimiento o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd880-162">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="dd880-163">Para revocar el mensaje mediante el centro de seguridad y &amp; cumplimiento</span><span class="sxs-lookup"><span data-stu-id="dd880-163">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="dd880-164">Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, conéctese al centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="dd880-164">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="dd880-165">En el **Informe de cifrado**, en la tabla de **detalles** del mensaje, elija **revocar mensaje**.</span><span class="sxs-lookup"><span data-stu-id="dd880-165">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="dd880-166">Para revocar un correo electrónico mediante Windows PowerShell, use el cmdlet Set-OMEMessageRevocation.</span><span class="sxs-lookup"><span data-stu-id="dd880-166">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="dd880-167">Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, [Conéctese a PowerShell de Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="dd880-167">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="dd880-168">Ejecute el cmdlet Set-OMEMessageRevocation de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="dd880-168">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="dd880-169">Para comprobar si el correo electrónico se ha revocado, ejecute el cmdlet Get-OMEMessageStatus de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="dd880-169">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="dd880-170">Si la revocación se ha realizado correctamente, el cmdlet devuelve el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="dd880-170">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="dd880-171">Más información sobre el cifrado de mensajes avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="dd880-171">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="dd880-172">Cifrado avanzado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="dd880-172">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="dd880-173">Office 365 Advanced Message Encryption-expiración del correo electrónico</span><span class="sxs-lookup"><span data-stu-id="dd880-173">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="dd880-174">Descripción de la Directiva de mensajes y el servicio de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="dd880-174">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
