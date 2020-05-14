---
title: Remitente no verificado
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
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
ms.custom:
- seo-marvel-apr2020
description: En este artículo se le guiará en el cómo evitar que los mensajes de suplantación de identidad lleguen a su buzón de correo, Outlook.com y Outlook en la Web.
ms.openlocfilehash: 2172a9890d629dd840c3e2e2591d78546899d17e
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224884"
---
# <a name="unverified-sender"></a><span data-ttu-id="9759a-103">Remitente no verificado</span><span class="sxs-lookup"><span data-stu-id="9759a-103">Unverified Sender</span></span>

> [!NOTE]
> <span data-ttu-id="9759a-104">Estas actualizaciones se están implementando ahora y es posible que no estén disponibles para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9759a-104">These updates are rolling out now, and might not be available for all users.</span></span> <span data-ttu-id="9759a-105">Esta característica es compatible con los usuarios de Outlook.com y de escritorio de Outlook de empresa de Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9759a-105">This feature is supported for Enterprise Outlook.com and Enterprise Outlook Win32 desktop users.</span></span> <span data-ttu-id="9759a-106">Actualmente no está disponible para usuarios de Office 365 de consumo.</span><span class="sxs-lookup"><span data-stu-id="9759a-106">It is not currently available for consumer Office 365 users.</span></span>

<span data-ttu-id="9759a-107">Para evitar que los mensajes de suplantación de identidad lleguen a su buzón, Office 365 comprueba que los remitentes son quienes dicen que son y marcan los mensajes sospechosos como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="9759a-107">To prevent phishing messages from reaching your mailbox, Office 365 verifies that the senders are who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9759a-108">Cuando un mensaje se marca como una estafa de suplantación de identidad, Outlook muestra una advertencia en la parte superior de la página, pero los vínculos del mensaje todavía se pueden abrir.</span><span class="sxs-lookup"><span data-stu-id="9759a-108">When a message is marked as a phishing scam, Outlook displays a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="9759a-109">¿Cómo puedo identificar un mensaje sospechoso en mi bandeja de entrada?</span><span class="sxs-lookup"><span data-stu-id="9759a-109">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="9759a-110">Outlook muestra indicadores cuando no se puede identificar el remitente de un mensaje o su identidad es diferente de la que se ve en la dirección from.</span><span class="sxs-lookup"><span data-stu-id="9759a-110">Outlook shows indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="9759a-111">Ve un '? ' en la imagen del remitente</span><span class="sxs-lookup"><span data-stu-id="9759a-111">You see a '?' in the sender image</span></span>

<span data-ttu-id="9759a-112">Cuando Office 365 no puede comprobar la identidad del remitente mediante técnicas de autenticación de correo electrónico, se muestra un '? ' en la imagen del remitente.</span><span class="sxs-lookup"><span data-stu-id="9759a-112">When Office 365 can't verify the identity of the sender using email authentication techniques, a '?' is displayed in the sender image.</span></span>

![El mensaje no pasó la comprobación](../../media/message-did-not-pass-verification.jpg)

<span data-ttu-id="9759a-114">No todos los mensajes que no se autentican son malintencionados.</span><span class="sxs-lookup"><span data-stu-id="9759a-114">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="9759a-115">Sin embargo, debe tener cuidado al interactuar con los mensajes que no se autentican si no reconoce al remitente.</span><span class="sxs-lookup"><span data-stu-id="9759a-115">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="9759a-116">O bien, si reconoce a un remitente que normalmente no tiene un '? ' en la imagen del remitente, pero, de repente, lo empieza a ver, es posible que se trate de una firma en la que se está suplantando el remitente.</span><span class="sxs-lookup"><span data-stu-id="9759a-116">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="9759a-117">Cómo administrar qué mensajes reciben el tratamiento de remitentes no comprobados</span><span class="sxs-lookup"><span data-stu-id="9759a-117">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="9759a-118">Si es un cliente de Office 365, puede administrar esta característica a través del centro de seguridad & cumplimiento de Office 365.</span><span class="sxs-lookup"><span data-stu-id="9759a-118">If you are an Office 365 customer you can manage this feature through the Office 365 Security & Compliance Center.</span></span>

- <span data-ttu-id="9759a-119">En el centro de seguridad & cumplimiento, los administradores globales o de seguridad pueden activar o desactivar la característica mediante protección contra la suplantación de identidad (phishing) en la Directiva ANTIPHISH.</span><span class="sxs-lookup"><span data-stu-id="9759a-119">In the Security & Compliance Center, global or security administrators can turn the feature on or off, through anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="9759a-120">Además, puede usar el cmdlet **set-AntiPhishPolicy** en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9759a-120">Additionally, you can use the **Set-AntiPhishPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="9759a-121">Para obtener más información, consulte [protección contra la suplantación de identidad en Office 365](anti-phishing-protection.md) y [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy).</span><span class="sxs-lookup"><span data-stu-id="9759a-121">For details, see [Anti-phishing protection in Office 365](anti-phishing-protection.md) and [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy).</span></span>

    ![Edición de remitentes no autenticados en la interfaz gráfica.](../../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="9759a-123">Si un administrador ha identificado un falso positivo y un remitente no debe recibir el tratamiento de remitente no verificado, se puede llevar a cabo una de las siguientes acciones para agregar el remitente a la lista de permitidos de falsificación de inteligencia de identidad:</span><span class="sxs-lookup"><span data-stu-id="9759a-123">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment, one of the following actions can be taken to add the sender to the Spoof Intelligence spoof allow list:</span></span>

  - <span data-ttu-id="9759a-124">Agregue el par de dominios mediante el conocimiento de inteligencia de ti falso.</span><span class="sxs-lookup"><span data-stu-id="9759a-124">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="9759a-125">Para obtener más información, vea [Tutorial: suplantar la información sobre inteligencia empresarial](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="9759a-125">For details, see [Walkthrough: spoof intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

  - <span data-ttu-id="9759a-126">Agregue el par de dominios mediante el cmdlet **set-PhishFilterPolicy** en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9759a-126">Add the domain pair through the **Set-PhishFilterPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="9759a-127">Para obtener más información, consulte [set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) y [set up Office 365 ATP anti-phishing and anti-phishing Policies](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9759a-127">For details, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) and [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="9759a-128">Además, no se aplica el tratamiento de remitente no verificado si el mensaje se entregó a la bandeja de entrada a través de reglas de flujo de correo (también conocidas como reglas de transporte) o la lista de dominios seguros (directivas contra correo no deseado).</span><span class="sxs-lookup"><span data-stu-id="9759a-128">Additionally, we don't apply the unverified sender treatment if the message was delivered to the Inbox via mail flow rules (also known as transport rules) or the Safe Domain List (anti-spam policies).</span></span>

## <a name="how-to-manage-the-via-tag"></a><span data-ttu-id="9759a-129">Cómo administrar la etiqueta "mediante"</span><span class="sxs-lookup"><span data-stu-id="9759a-129">How to manage the 'via' tag</span></span> 

<span data-ttu-id="9759a-130">Si es un cliente de Office 365, puede administrar esta característica a través del centro de seguridad & cumplimiento de Office 365, del mismo modo que administra el tratamiento de remitentes no comprobados.</span><span class="sxs-lookup"><span data-stu-id="9759a-130">If you are an Office 365 customer you can manage this feature through the Office 365 Security & Compliance center, the same way that you manage the unverified sender treatment.</span></span> <span data-ttu-id="9759a-131">Si agrega el remitente a la lista de permitidos de imitación de inteligencia empresarial, no se aplicará el tratamiento "Via".</span><span class="sxs-lookup"><span data-stu-id="9759a-131">If you add the sender to the Spoof Intelligence spoof allow list, the 'via' treatment will not be applied.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="9759a-132">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="9759a-132">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-win32-desktop-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="9759a-133">¿Qué criterios Outlook.com y Outlook Win32 Desktop usan para agregar las propiedades "?" y "Via"?</span><span class="sxs-lookup"><span data-stu-id="9759a-133">What criteria does Outlook.com and Outlook Win32 desktop use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="9759a-134">Para el '? ' en la imagen del remitente: Outlook.com requiere que el mensaje pase la autenticación de SPF o DKIM y reciba una transferencia de dMarc o un paso de autenticación compuesto de la inteligencia de Office 365 suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="9759a-134">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication and receive either a dmarc pass, or a composite authentication pass from Office 365 Spoof Intelligence.</span></span> <span data-ttu-id="9759a-135">Para obtener más información, consulte [configurar SPF en Office 365 para evitar la suplantación de identidad (spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) ) y el [uso de DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="9759a-135">For details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="9759a-136">Para la etiqueta Via: Si el dominio de la dirección de es diferente del dominio de la firma DKIM o del correo SMTP de, Outlook.com muestra el dominio en uno de estos dos campos (prefiriendo la firma DKIM).</span><span class="sxs-lookup"><span data-stu-id="9759a-136">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="how-do-i-remove-the--without-utilizing-the-spoof-intelligence-spoof-allow-list"></a><span data-ttu-id="9759a-137">¿Cómo quito el '? ' sin usar la lista de permitidos de simulación de simulación de falsificación?</span><span class="sxs-lookup"><span data-stu-id="9759a-137">How do I remove the '?' without utilizing the Spoof Intelligence spoof allow list?</span></span>

<span data-ttu-id="9759a-138">Para el '? ' en la imagen del remitente: como remitente, debe autenticar el mensaje con SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="9759a-138">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="9759a-139">Para la etiqueta Via: como remitente, debe asegurarse de que el dominio de la firma DKIM o el correo SMTP de sea el mismo que o sea un subdominio de, el dominio de la dirección de remitente.</span><span class="sxs-lookup"><span data-stu-id="9759a-139">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="do-outlookcom-and-outlook-win32-desktop-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="9759a-140">¿Outlook.com y Outlook Win32 de escritorio muestran esto para cada mensaje que no supera la autenticación?</span><span class="sxs-lookup"><span data-stu-id="9759a-140">Do Outlook.com and Outlook Win32 desktop show this for every message that doesn't pass authentication?</span></span>

<span data-ttu-id="9759a-141">No necesariamente.</span><span class="sxs-lookup"><span data-stu-id="9759a-141">Not necessarily.</span></span> <span data-ttu-id="9759a-142">Office 365 puede tener otras propiedades dentro del mensaje para autenticar al remitente.</span><span class="sxs-lookup"><span data-stu-id="9759a-142">Office 365 may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9759a-143">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="9759a-143">Related topics</span></span>

[<span data-ttu-id="9759a-144">Ayuda para proteger su cuenta de correo electrónico de Outlook.com</span><span class="sxs-lookup"><span data-stu-id="9759a-144">Help protect your Outlook.com email account</span></span>](https://support.microsoft.com/en-us/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="9759a-145">Trabajar con suplantación de identidad (phishing) en Outlook.com</span><span class="sxs-lookup"><span data-stu-id="9759a-145">Deal with phishing or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="9759a-146">Filtrar correo no deseado y correo no deseado en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="9759a-146">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
