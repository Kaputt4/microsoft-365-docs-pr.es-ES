---
title: 'Paso 6: Configurar el cifrado de correo electrónico'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Comprenda y configure la administración del acceso con privilegios para Office 365
ms.openlocfilehash: 252a5f76197deb1034d200553308a281ef079957
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600927"
---
# <a name="step-6-configure-email-encryption"></a><span data-ttu-id="c4fcd-103">Paso 6: Configurar el cifrado de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="c4fcd-103">Step 6: Configure email encryption</span></span>

<span data-ttu-id="c4fcd-104">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="c4fcd-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: Protección de la información](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="c4fcd-106">Hay tres tipos de cifrado de correo electrónico en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-106">There are three types of email encryption in Microsoft 365.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="c4fcd-107">Cifrado de mensajes de Office (OME)</span><span class="sxs-lookup"><span data-stu-id="c4fcd-107">Office Message Encryption (OME)</span></span> | <span data-ttu-id="c4fcd-108">Cifrado para el correo electrónico de Exchange Online enviado fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-108">Encryption for Exchange Online email sent outside your organization.</span></span> |
| <span data-ttu-id="c4fcd-109">Information Rights Management (IRM)</span><span class="sxs-lookup"><span data-stu-id="c4fcd-109">Information Rights Management (IRM)</span></span> | <span data-ttu-id="c4fcd-110">Cifrado y permisos que viajan con el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-110">Encryption and permissions that travel with the email.</span></span> |
| <span data-ttu-id="c4fcd-111">Extensiones seguras multipropósito al correo de Internet (S/MIME)</span><span class="sxs-lookup"><span data-stu-id="c4fcd-111">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span> | <span data-ttu-id="c4fcd-112">Protección de correo electrónico con cifrado y firmas digitales.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-112">Email protection with encryption and digital signatures.</span></span> |
|||

## <a name="office-365-message-encryption"></a><span data-ttu-id="c4fcd-113">Cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="c4fcd-113">Office 365 Message Encryption</span></span>

<span data-ttu-id="c4fcd-114">Con OME, su organización puede enviar y recibir mensajes de correo electrónico cifrados entre usuarios de dentro y fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-114">With OME, your organization can send and receive encrypted email messages between people inside and outside your organization.</span></span> <span data-ttu-id="c4fcd-115">OME funciona con Outlook.com, Yahoo!, gmail y otros servicios de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-115">OME works with Outlook.com, Yahoo!, Gmail, and other email services.</span></span> <span data-ttu-id="c4fcd-116">El cifrado de mensajes de correo electrónico ayuda a garantizar que solo los destinatarios deseados puedan ver el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-116">Email message encryption helps ensure that only intended recipients can view the message.</span></span>

![Cifrado de OME mensajes de correo electrónico](./media/infoprotect-email-encryption/ome-encryption.png)

<span data-ttu-id="c4fcd-118">Configure las reglas de transporte que definen las condiciones para el cifrado.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-118">You set up transport rules that define the conditions for encryption.</span></span> <span data-ttu-id="c4fcd-119">Cuando un usuario envía un mensaje que coincide con una regla, se aplica automáticamente el cifrado.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-119">When a user sends a message that matches a rule, encryption is applied automatically.</span></span>

<span data-ttu-id="c4fcd-120">Para ver los mensajes cifrados, los destinatarios pueden obtener un código de acceso de un solo uso, iniciar sesión con una cuenta de Microsoft o iniciar sesión con una cuenta profesional o educativa asociada con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-120">To view encrypted messages, recipients can either get a one-time passcode, sign in with a Microsoft account, or sign in with a work or school account associated with Microsoft 365.</span></span> <span data-ttu-id="c4fcd-121">Los destinatarios también pueden enviar respuestas cifradas.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-121">Recipients can also send encrypted replies.</span></span> <span data-ttu-id="c4fcd-122">No necesitan su propia suscripción a Microsoft 365 para ver mensajes cifrados ni enviar respuestas cifradas.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-122">They don't need their own Microsoft 365 subscription to view encrypted messages or send encrypted replies.</span></span>

<span data-ttu-id="c4fcd-123">Para obtener más información, consulte [Cifrado en Office 365](https://docs.microsoft.com/Office365/SecurityCompliance/ome).</span><span class="sxs-lookup"><span data-stu-id="c4fcd-123">For more information, see [Office 365 Message Encryption](https://docs.microsoft.com/Office365/SecurityCompliance/ome).</span></span>

## <a name="irm"></a><span data-ttu-id="c4fcd-124">IRM</span><span class="sxs-lookup"><span data-stu-id="c4fcd-124">IRM</span></span>

<span data-ttu-id="c4fcd-125">IRM en Microsoft 365 le ayuda a proteger su información con cifrado adicional y al aplicar una directiva inteligente que especifica quién tiene acceso a lo que puede hacer.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-125">IRM in Microsoft 365 helps you secure your information with additional encryption and by applying an intelligent policy that specifies who has access what they can do.</span></span> <span data-ttu-id="c4fcd-126">Para los mensajes de correo electrónico, puede usar IRM para cifrado y aplicar restricciones de uso.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-126">For email messages, you can use IRM for encryption and to apply usage restrictions.</span></span> <span data-ttu-id="c4fcd-127">Por ejemplo, puede especificar que algunos destinatarios tengan todas las capacidades para administrar el correo electrónico y otros no puedan imprimir o reenviar el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-127">For example, you can specify that some recipients have all abilities to manage the email and some do not have the ability to print or forward the email.</span></span> 

<span data-ttu-id="c4fcd-128">Las directivas de IRM se configuran en Microsoft 365 y se pueden aplicar a documentos en SharePoint Online y mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-128">IRM policies are configured within Microsoft 365 and can apply to documents in SharePoint Online and email messages.</span></span> <span data-ttu-id="c4fcd-129">Un correo electrónico protegido con IRM incluye la configuración de directiva aplicada y se desplaza con ella.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-129">An IRM-protected email includes the applied policy settings applied and travel with it.</span></span> 

![Protección de los mensajes de correo electrónico con IRM](./media/infoprotect-email-encryption/irm-protection.png)

<span data-ttu-id="c4fcd-131">Cuando el destinatario abre el correo electrónico con la Directiva incluida, la configuración de la Directiva se usa para descifrar el mensaje y determinar lo que el destinatario puede hacer con él.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-131">When the recipient opens the email with the included policy, the policy settings are used to decrypt the message and determine what the recipient can do with it.</span></span> 

<span data-ttu-id="c4fcd-132">Para obtener más información, consulte [Information Rights Management en Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="c4fcd-132">For more information, see [Information Rights Management in Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).</span></span>

## <a name="smime"></a><span data-ttu-id="c4fcd-133">S/MIME</span><span class="sxs-lookup"><span data-stu-id="c4fcd-133">S/MIME</span></span>

<span data-ttu-id="c4fcd-134">S/MIME es una solución de protección basada en correo electrónico basada en certificados digitales que permite cifrar y firmar digitalmente un mensaje.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-134">S/MIME is a digital certificate-based email-based protection solution that allows you to both encrypt and digitally sign a message.</span></span> <span data-ttu-id="c4fcd-135">El cifrado de mensajes ayuda a garantizar que solo el destinatario pueda abrir y leer el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-135">The message encryption helps ensure that only the intended recipient can open and read the message.</span></span> <span data-ttu-id="c4fcd-136">Una firma digital ayuda al destinatario a validar la identidad del remitente y a determinar que sólo el remitente lo haya enviado.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-136">A digital signature helps the recipient validate the identity of the sender and determine that only the sender could have sent it.</span></span>

![Protección S/MIME de los mensajes de correo electrónico](./media/infoprotect-email-encryption/smime-protection.png)

<span data-ttu-id="c4fcd-138">S/MIME puede usarse para el correo electrónico a otros buzones de la suscripción de Microsoft 365 o a usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-138">S/MIME can be used for email to other mailboxes in your Microsoft 365 subscription or to external users.</span></span>
<span data-ttu-id="c4fcd-139">Tanto el cifrado de mensajes como las firmas digitales se hacen posible mediante el uso de certificados digitales que contienen las claves públicas y privadas para cifrar o descifrar mensajes, y para crear y comprobar firmas digitales.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-139">Both message encryption and digital signatures are made possible through the use of digital certificates that contain the public and private keys for encrypting or decrypting messages and creating and verifying digital signatures.</span></span>
<span data-ttu-id="c4fcd-140">Para usar S/MIME, debe tener las claves públicas para cada destinatario.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-140">To use S/MIME, you must have the public keys for each recipient.</span></span> <span data-ttu-id="c4fcd-141">Los destinatarios mantienen sus propias claves privadas, que deben permanecer seguras.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-141">Recipients maintain their own private keys, which must remain secure.</span></span> <span data-ttu-id="c4fcd-142">Si la clave privada está comprometida, debe obtener un nuevo certificado digital y redistribuir las claves públicas a todos los remitentes potenciales.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-142">If your private key is compromised, you need to get a new digital certificate and redistribute public keys to all potential senders.</span></span>

<span data-ttu-id="c4fcd-143">Para obtener más información, vea [S/MIME para la firma y el cifrado de mensajes](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).</span><span class="sxs-lookup"><span data-stu-id="c4fcd-143">For more information, see [S/MIME for message signing and encryption](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).</span></span>


<span data-ttu-id="c4fcd-144">Como punto de control provisional, vea los [criterios de salida](infoprotect-exit-criteria.md#crit-infoprotect-step6) correspondientes a este paso.</span><span class="sxs-lookup"><span data-stu-id="c4fcd-144">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step6) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="c4fcd-145">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="c4fcd-145">Next step</span></span>

|||
|:-------|:-----|
|![Paso 7](./media/stepnumbers/Step7.png)|[<span data-ttu-id="c4fcd-147">Configurar Privileged Access Management para Office 365</span><span class="sxs-lookup"><span data-stu-id="c4fcd-147">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
