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
ms.date: 02/28/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Como administrador, puede revocar determinados mensajes de correo electrónico cifrados con el cifrado de mensajes avanzado de Office 365.
ms.openlocfilehash: 271aa1b3644983907c341cf7f9ad6d526597ad59
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626496"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="5ed52-103">Revocar correo electrónico cifrado por el cifrado de mensajes avanzado</span><span class="sxs-lookup"><span data-stu-id="5ed52-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="5ed52-104">La revocación de correo electrónico se ofrece como parte de un cifrado de mensajes avanzado de Office 365.</span><span class="sxs-lookup"><span data-stu-id="5ed52-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="5ed52-105">Office 365 Advanced Message Encryption se incluye en [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (precio de personal sin ánimo de lucro), Office 365 Enterprise E5 (precio de personal sin ánimo de lucro) y Office 365 Education A5.</span><span class="sxs-lookup"><span data-stu-id="5ed52-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="5ed52-106">Si su organización tiene una suscripción que no incluye el cifrado avanzado de mensajes de Office 365, puede adquirirlo con el complemento de SKU de cumplimiento de Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (precios para trabajadores sin ánimo de lucro), o el complemento de SKU de Office 365 Advanced Compliance para Microsoft 365 E3, Microsoft 365 E3 (no lucrativa personal) u Office 365 SKU.</span><span class="sxs-lookup"><span data-stu-id="5ed52-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="5ed52-107">Este artículo forma parte de una amplia serie de artículos sobre el [cifrado de mensajes de Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="5ed52-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="5ed52-108">Si un mensaje se cifró mediante el cifrado de mensajes avanzado de Office 365 y es administrador de Microsoft 365, puede revocar el mensaje en determinadas condiciones.</span><span class="sxs-lookup"><span data-stu-id="5ed52-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="5ed52-109">En este artículo se describen las circunstancias en las que es posible la revocación y cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="5ed52-109">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="5ed52-110">Mensajes de correo electrónico cifrados que puede revocar</span><span class="sxs-lookup"><span data-stu-id="5ed52-110">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="5ed52-111">Puede revocar los correos electrónicos cifrados si el destinatario recibe un correo electrónico cifrado basado en vínculos con marcas.</span><span class="sxs-lookup"><span data-stu-id="5ed52-111">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="5ed52-112">Si el destinatario recibe una experiencia en línea nativa en un cliente de Outlook compatible, no podrá revocar esos.</span><span class="sxs-lookup"><span data-stu-id="5ed52-112">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke those.</span></span>

<span data-ttu-id="5ed52-113">El hecho de que un destinatario reciba una experiencia basada en vínculos o una experiencia en línea depende del tipo de identidad del destinatario: Office 365 y los destinatarios de la cuenta de Microsoft (por ejemplo, usuarios outlook.com) obtienen una experiencia en línea en clientes de Outlook compatibles.</span><span class="sxs-lookup"><span data-stu-id="5ed52-113">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="5ed52-114">Todos los demás tipos de destinatarios, como los destinatarios de gmail, obtienen una experiencia basada en vínculos.</span><span class="sxs-lookup"><span data-stu-id="5ed52-114">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="5ed52-115">Experiencia del destinatario para correos electrónicos cifrados revocados</span><span class="sxs-lookup"><span data-stu-id="5ed52-115">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="5ed52-116">Una vez que se ha revocado un correo electrónico, el destinatario recibe un error cuando accede al correo electrónico cifrado a través del portal de cifrado de mensajes de Office 365: "el remitente ha revocado el mensaje".</span><span class="sxs-lookup"><span data-stu-id="5ed52-116">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![Captura de pantalla que muestra un correo electrónico cifrado revocado.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="5ed52-118">Cómo revocar un correo electrónico cifrado</span><span class="sxs-lookup"><span data-stu-id="5ed52-118">How to revoke an encrypted email</span></span>

<span data-ttu-id="5ed52-119">Los administradores de Microsoft 365 siguen estos pasos generales para revocar un correo electrónico cifrado apto:</span><span class="sxs-lookup"><span data-stu-id="5ed52-119">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="5ed52-120">Obtenga el identificador de mensaje del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5ed52-120">Get the Message ID of the email.</span></span>
- <span data-ttu-id="5ed52-121">Compruebe que puede revocar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="5ed52-121">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="5ed52-122">Revocar el correo.</span><span class="sxs-lookup"><span data-stu-id="5ed52-122">Revoke the mail.</span></span>

<span data-ttu-id="5ed52-123">Siga leyendo para obtener instrucciones detalladas para cada paso del proceso de revocación.</span><span class="sxs-lookup"><span data-stu-id="5ed52-123">Keep reading for in-depth instructions for each step in the revocation process.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="5ed52-124">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="5ed52-124">Step 1.</span></span> <span data-ttu-id="5ed52-125">Obtener el identificador del mensaje de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="5ed52-125">Obtain the Message ID of the email</span></span>

<span data-ttu-id="5ed52-126">Para poder revocar un correo cifrado, reúna el identificador de mensaje del correo.</span><span class="sxs-lookup"><span data-stu-id="5ed52-126">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="5ed52-127">El MessageId suele tener el formato:</span><span class="sxs-lookup"><span data-stu-id="5ed52-127">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="5ed52-128">Hay varias formas de buscar el identificador de mensaje del correo electrónico que desea revocar.</span><span class="sxs-lookup"><span data-stu-id="5ed52-128">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="5ed52-129">En esta sección se describen un par de opciones, pero puede usar cualquier método que proporcione el ID.</span><span class="sxs-lookup"><span data-stu-id="5ed52-129">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="5ed52-130">Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante el seguimiento de mensajes en &amp; el centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="5ed52-130">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="5ed52-131">Busque el correo electrónico por remitente o destinatario mediante el [seguimiento de mensajes nuevos en el centro de seguridad & cumplimiento](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="5ed52-131">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="5ed52-132">Una vez que haya encontrado el correo electrónico, selecciónelo para que aparezca el panel de **detalles de seguimiento de mensajes** .</span><span class="sxs-lookup"><span data-stu-id="5ed52-132">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="5ed52-133">Expanda **más información** para buscar el identificador de mensaje.</span><span class="sxs-lookup"><span data-stu-id="5ed52-133">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="5ed52-134">Para identificar el identificador de mensaje del correo electrónico que desea revocar mediante los informes de cifrado de mensajes &amp; de Office en el centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="5ed52-134">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="5ed52-135">En el centro &amp; de seguridad y cumplimiento, navegue hasta el **Informe de cifrado de mensajes**.</span><span class="sxs-lookup"><span data-stu-id="5ed52-135">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="5ed52-136">Para obtener información sobre este informe, consulte [ver informes de seguridad de correo &amp; electrónico en el centro de seguridad y cumplimiento](../security/office-365-security/view-email-security-reports.md).</span><span class="sxs-lookup"><span data-stu-id="5ed52-136">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="5ed52-137">Elija la tabla **Ver detalles** e identifique el mensaje que desea revocar.</span><span class="sxs-lookup"><span data-stu-id="5ed52-137">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="5ed52-138">Haga doble clic en el mensaje para ver los detalles que incluyen el identificador del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5ed52-138">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="5ed52-139">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="5ed52-139">Step 2.</span></span> <span data-ttu-id="5ed52-140">Comprobar que el correo es revocable</span><span class="sxs-lookup"><span data-stu-id="5ed52-140">Verify that the mail is revocable</span></span>

<span data-ttu-id="5ed52-141">Para comprobar si puede revocar un mensaje, compruebe si el campo Estado de revocación está visible en el informe de cifrado **Details** , en la tabla de &amp; detalles del centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="5ed52-141">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="5ed52-142">Para comprobar si puede revocar un mensaje de correo electrónico determinado mediante Windows PowerShell, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5ed52-142">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="5ed52-143">Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, inicie una sesión de Windows PowerShell y conéctese a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5ed52-143">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="5ed52-144">Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="5ed52-144">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="5ed52-145">Ejecute el cmdlet Get-OMEMessageStatus de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="5ed52-145">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="5ed52-146">Este comando devuelve el asunto del mensaje y si el mensaje es revocable.</span><span class="sxs-lookup"><span data-stu-id="5ed52-146">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="5ed52-147">For example,</span><span class="sxs-lookup"><span data-stu-id="5ed52-147">For example,</span></span>

     ```text
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="5ed52-148">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="5ed52-148">Step 3.</span></span> <span data-ttu-id="5ed52-149">Revocar el correo</span><span class="sxs-lookup"><span data-stu-id="5ed52-149">Revoke the mail</span></span>

<span data-ttu-id="5ed52-150">Una vez que conozca el identificador de mensaje del correo electrónico que desea revocar y haya comprobado que el mensaje es revocable, puede revocar el correo electrónico mediante &amp; el centro de seguridad y cumplimiento o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ed52-150">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="5ed52-151">Para revocar el mensaje mediante el &amp; centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="5ed52-151">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="5ed52-152">Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, conéctese al centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="5ed52-152">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="5ed52-153">En el **Informe de cifrado**, en la tabla de **detalles** del mensaje, elija **revocar mensaje**.</span><span class="sxs-lookup"><span data-stu-id="5ed52-153">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="5ed52-154">Para revocar un correo electrónico mediante Windows PowerShell, use el cmdlet Set-OMEMessageRevocation.</span><span class="sxs-lookup"><span data-stu-id="5ed52-154">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="5ed52-155">Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, [Conéctese a PowerShell de Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="5ed52-155">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="5ed52-156">Ejecute el cmdlet Set-OMEMessageRevocation de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="5ed52-156">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="5ed52-157">Para comprobar si el correo electrónico se ha revocado, ejecute el cmdlet Get-OMEMessageStatus de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="5ed52-157">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="5ed52-158">Si la revocación se ha realizado correctamente, el cmdlet devuelve el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="5ed52-158">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="5ed52-159">Más información sobre el cifrado de mensajes avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="5ed52-159">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="5ed52-160">Cifrado avanzado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="5ed52-160">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="5ed52-161">Office 365 Advanced Message Encryption-expiración del correo electrónico</span><span class="sxs-lookup"><span data-stu-id="5ed52-161">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="5ed52-162">Descripción de la Directiva de mensajes y el servicio de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="5ed52-162">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
