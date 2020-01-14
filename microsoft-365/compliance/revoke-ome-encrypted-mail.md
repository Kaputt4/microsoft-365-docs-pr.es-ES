---
title: Revocar el correo electrónico cifrado por el cifrado avanzado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/8/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Como administrador de Office 365, puede revocar determinados mensajes de correo electrónico cifrados con el cifrado avanzado de mensajes de Office 365.
ms.openlocfilehash: d3d449c969b2fa5d21042779ebad11e3807d1d3e
ms.sourcegitcommit: 39bd4be7e8846770f060b5dd7d895fc8040b18f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "41112524"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="b9683-103">Revocar el correo electrónico cifrado por el cifrado avanzado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="b9683-103">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="b9683-104">La revocación de correo electrónico se ofrece como parte de un cifrado de mensajes avanzado de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9683-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="b9683-105">Office 365 Advanced Message Encryption se incluye en [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (precio de personal sin ánimo de lucro), Office 365 Enterprise E5 (precio de personal sin ánimo de lucro) y Office 365 Education A5.</span><span class="sxs-lookup"><span data-stu-id="b9683-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="b9683-106">Si su organización tiene una suscripción que no incluye el cifrado avanzado de mensajes de Office 365, puede adquirirlo con el complemento de SKU de cumplimiento de Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (precio del personal sin ánimo de lucro) o el Office 365 Advanced Complemento de SKU de cumplimiento para Microsoft 365 E3, Microsoft 365 E3 (precio del personal sin ánimo de lucro) o SKU de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9683-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="b9683-107">Este artículo forma parte de una amplia serie de artículos sobre el [cifrado de mensajes de Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="b9683-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="b9683-108">Si un mensaje se cifró mediante el cifrado de mensajes avanzado de Office 365 y usted es administrador de Office 365, puede revocar el mensaje en determinadas circunstancias.</span><span class="sxs-lookup"><span data-stu-id="b9683-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are an Office 365 admin, you can do revoke the message under certain conditions.</span></span> <span data-ttu-id="b9683-109">En este artículo se describen las circunstancias en las que es posible la revocación y cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="b9683-109">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="b9683-110">Mensajes de correo electrónico cifrados que puede revocar</span><span class="sxs-lookup"><span data-stu-id="b9683-110">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="b9683-111">Puede revocar los correos electrónicos cifrados si el destinatario recibe un correo electrónico cifrado basado en vínculos con marcas.</span><span class="sxs-lookup"><span data-stu-id="b9683-111">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="b9683-112">Si el destinatario recibe una experiencia en línea nativa en un cliente de Outlook compatible, dichos mensajes no se pueden revocar.</span><span class="sxs-lookup"><span data-stu-id="b9683-112">If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="b9683-113">El hecho de que un destinatario reciba una experiencia basada en vínculos o una experiencia en línea depende del tipo de identidad del destinatario: Office 365 y los destinatarios de la cuenta de Microsoft (por ejemplo, usuarios outlook.com) obtienen una experiencia en línea en clientes de Outlook compatibles.</span><span class="sxs-lookup"><span data-stu-id="b9683-113">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="b9683-114">Todos los demás tipos de destinatarios, como los destinatarios de gmail, obtienen una experiencia basada en vínculos.</span><span class="sxs-lookup"><span data-stu-id="b9683-114">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="b9683-115">Experiencia del destinatario para correos electrónicos cifrados revocados</span><span class="sxs-lookup"><span data-stu-id="b9683-115">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="b9683-116">Una vez que se ha revocado un correo electrónico, el destinatario recibe un error cuando accede al correo electrónico cifrado a través del portal de cifrado de mensajes de Office 365: "el remitente ha revocado el mensaje".</span><span class="sxs-lookup"><span data-stu-id="b9683-116">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![Captura de pantalla que muestra un correo electrónico cifrado revocado.](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="b9683-118">Cómo revocar un correo electrónico cifrado</span><span class="sxs-lookup"><span data-stu-id="b9683-118">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="b9683-119">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="b9683-119">Step 1.</span></span> <span data-ttu-id="b9683-120">Obtener el identificador del mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="b9683-120">Obtain the Message ID of the email</span></span>

<span data-ttu-id="b9683-121">Para poder revocar un correo cifrado, debe recopilar el identificador de mensaje del correo.</span><span class="sxs-lookup"><span data-stu-id="b9683-121">Before you can revoke an encrypted mail you gather the Message ID of the mail.</span></span> <span data-ttu-id="b9683-122">El MessageId suele tener el formato:</span><span class="sxs-lookup"><span data-stu-id="b9683-122">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="b9683-123">Hay varias formas de buscar el identificador de mensaje del correo electrónico que desea revocar.</span><span class="sxs-lookup"><span data-stu-id="b9683-123">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="b9683-124">En esta sección se describen un par de opciones, pero puede usar cualquier método que proporcione el ID.</span><span class="sxs-lookup"><span data-stu-id="b9683-124">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="b9683-125">Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante el seguimiento de mensajes en &amp; el centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b9683-125">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="b9683-126">Busque el correo electrónico por remitente o destinatario mediante el [seguimiento de mensajes nuevo en el centro de seguridad & cumplimiento de Office 365](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="b9683-126">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="b9683-127">Una vez que haya encontrado el correo electrónico, selecciónelo para que aparezca el panel de **detalles de seguimiento de mensajes** .</span><span class="sxs-lookup"><span data-stu-id="b9683-127">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="b9683-128">Expanda **más información** para buscar el identificador de mensaje.</span><span class="sxs-lookup"><span data-stu-id="b9683-128">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="b9683-129">Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante los informes de cifrado de mensajes &amp; de Office en el centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b9683-129">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="b9683-130">En el centro &amp; de seguridad y cumplimiento, navegue hasta el **Informe de cifrado de mensajes**.</span><span class="sxs-lookup"><span data-stu-id="b9683-130">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="b9683-131">Para obtener información sobre este informe, consulte [ver informes de seguridad de correo &amp; electrónico en el centro de seguridad y cumplimiento](../security/office-365-security/view-email-security-reports.md).</span><span class="sxs-lookup"><span data-stu-id="b9683-131">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="b9683-132">Elija la tabla **Ver detalles** e identifique el mensaje que desea revocar.</span><span class="sxs-lookup"><span data-stu-id="b9683-132">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="b9683-133">Haga doble clic en el mensaje para ver los detalles que incluyen el identificador del mensaje.</span><span class="sxs-lookup"><span data-stu-id="b9683-133">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="b9683-134">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="b9683-134">Step 2.</span></span> <span data-ttu-id="b9683-135">Comprobar que el correo es revocable</span><span class="sxs-lookup"><span data-stu-id="b9683-135">Verify that the mail is revocable</span></span>

<span data-ttu-id="b9683-136">Para comprobar si puede revocar un mensaje, compruebe si el campo Estado de revocación está visible en el informe de cifrado \*\*\*\* , en la tabla de &amp; detalles del centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b9683-136">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="b9683-137">Para comprobar si puede revocar un mensaje de correo electrónico determinado mediante Windows PowerShell, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b9683-137">To verify whether you can revoke a particular email message by using Windows Powershell, complete these steps.</span></span>

1. <span data-ttu-id="b9683-138">Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie una sesión de Windows PowerShell y conéctese a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b9683-138">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="b9683-139">Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="b9683-139">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="b9683-140">Ejecute el cmdlet Get-OMEMessageStatus de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b9683-140">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="b9683-141">Esto devuelve el asunto del mensaje y si el mensaje es revocable.</span><span class="sxs-lookup"><span data-stu-id="b9683-141">This returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="b9683-142">For example,</span><span class="sxs-lookup"><span data-stu-id="b9683-142">For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="b9683-143">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="b9683-143">Step 3.</span></span> <span data-ttu-id="b9683-144">Revocar el correo</span><span class="sxs-lookup"><span data-stu-id="b9683-144">Revoke the mail</span></span>

<span data-ttu-id="b9683-145">Una vez que conozca el identificador de mensaje del correo electrónico que desea revocar y haya comprobado que el mensaje es revocable, puede revocar el correo electrónico mediante &amp; el centro de seguridad y cumplimiento o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9683-145">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows Powershell.</span></span>

<span data-ttu-id="b9683-146">Para revocar el mensaje mediante el &amp; centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b9683-146">To revoke the message using the Security &amp; Compliance Center</span></span>

<span data-ttu-id="b9683-147">Para revocar el correo electrónico en &amp; el centro de seguridad y cumplimiento, en el informe de cifrado, en la tabla de **detalles** del mensaje, elija **revocar mensaje**.</span><span class="sxs-lookup"><span data-stu-id="b9683-147">To revoke the email in the Security &amp; Compliance Center, in the Encryption report, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="b9683-148">Puede revocar un correo electrónico mediante Windows PowerShell con el cmdlet Set-OMEMessageRevocation.</span><span class="sxs-lookup"><span data-stu-id="b9683-148">You can revoke an email by using Windows Powershell by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="b9683-149">[Conexión a PowerShell de Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="b9683-149">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="b9683-150">Ejecute el cmdlet Set-OMEMessageRevocation de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b9683-150">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="b9683-151">Para comprobar si el correo electrónico se ha revocado, ejecute el cmdlet Get-OMEMessageStatus de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b9683-151">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="b9683-152">Si la revocación se ha realizado correctamente, el cmdlet devuelve el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b9683-152">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="b9683-153">Más información sobre el cifrado de mensajes avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="b9683-153">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="b9683-154">Cifrado avanzado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="b9683-154">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="b9683-155">Office 365 Advanced Message Encryption-expiración del correo electrónico</span><span class="sxs-lookup"><span data-stu-id="b9683-155">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="b9683-156">Descripción de la Directiva de mensajes y el servicio de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b9683-156">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
