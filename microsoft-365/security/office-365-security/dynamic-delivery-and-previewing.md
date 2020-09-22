---
title: Entrega dinámica y vista previa con datos adjuntos seguros de ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 04/19/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: Cuando configure las directivas de datos adjuntos seguros de ATP, elija Entrega dinámica para evitar retrasos en los mensajes y permitir que los usuarios puedan obtener una vista previa de los datos adjuntos mientras se examinan.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c0b19317babbd433ba0914ca2385cf6c9b40d89b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203040"
---
# <a name="dynamic-delivery-and-previewing-with-atp-safe-attachments"></a><span data-ttu-id="31c11-103">Entrega dinámica y vista previa con datos adjuntos seguros de ATP</span><span class="sxs-lookup"><span data-stu-id="31c11-103">Dynamic Delivery and previewing with ATP Safe Attachments</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-dynamic-delivery"></a><span data-ttu-id="31c11-104">Características básicas de la entrega dinámica</span><span class="sxs-lookup"><span data-stu-id="31c11-104">Basic features of Dynamic Delivery</span></span>

<span data-ttu-id="31c11-105">La entrega dinámica es una opción que se puede seleccionar para [Datos adjuntos seguros de ATP](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="31c11-105">Dynamic Delivery is an option that can be selected for [ATP Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="31c11-106">Lea este artículo para obtener información sobre la entrega dinámica y las funciones de vista previa de datos adjuntos en [Datos adjuntos seguros de ATP en Office 365](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="31c11-106">Read this article to learn about Dynamic Delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="31c11-107">Cuando se [configuran directivas de Datos adjuntos seguros de ATP ](set-up-atp-safe-attachments-policies.md) para su organización, hay varias opciones sobre cómo se manejan los datos adjuntos de correo.</span><span class="sxs-lookup"><span data-stu-id="31c11-107">When [ATP Safe Attachments policies are set up](set-up-atp-safe-attachments-policies.md) for your organization, there are several options for how email attachments are handled.</span></span> <span data-ttu-id="31c11-108">Estas incluyen **Bloquear**, **Reemplazar** y **Entrega dinámica**.</span><span class="sxs-lookup"><span data-stu-id="31c11-108">These include **Block**, **Replace**, and **Dynamic Delivery**.</span></span> <span data-ttu-id="31c11-109">Dependiendo de cómo estén configuradas las directivas de datos adjuntos seguros de ATP, los destinatarios del correo podrían experimentar un retraso mínimo en la entrega del correo mientras se analizan sus datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="31c11-109">Depending on how ATP Safe Attachments policies are configured, email recipients might experience a minor delay in email delivery while their attachments are scanned.</span></span> <span data-ttu-id="31c11-110">Para evitar retrasos en los mensajes, elija **Entrega dinámica**.</span><span class="sxs-lookup"><span data-stu-id="31c11-110">To avoid message delays, choose **Dynamic Delivery**.</span></span>

## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="31c11-111">Cómo funciona la Entrega dinámica</span><span class="sxs-lookup"><span data-stu-id="31c11-111">How Dynamic Delivery works</span></span>

<span data-ttu-id="31c11-112">La Entrega dinámica elimina los retrasos del correo electrónico enviando el cuerpo de un mensaje de correo al destinatario con un marcador de posición para cada dato adjunto.</span><span class="sxs-lookup"><span data-stu-id="31c11-112">Dynamic Delivery eliminates email delays by sending the body of an email message through to the recipient with a placeholder for each email attachment.</span></span> <span data-ttu-id="31c11-113">El marcador de posición permanece hasta que [Datos adjuntos seguros de ATP](atp-safe-attachments.md) analiza la copia de los datos y determina que son seguros.</span><span class="sxs-lookup"><span data-stu-id="31c11-113">The placeholder remains until a copy of the attachment is scanned and determined to be safe by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>

- <span data-ttu-id="31c11-114">A medida que se comprueba cada dato adjunto, pasará a estar disponible para abrir o descargar.</span><span class="sxs-lookup"><span data-stu-id="31c11-114">As each attachment is cleared, it is available to open or download.</span></span>

- <span data-ttu-id="31c11-115">Si los datos adjuntos se determinan como malintencionados, se envían a cuarentena, donde alguien del equipo de seguridad de su organización (como un administrador global o un administrador de seguridad) puede [administrar los mensajes en cuarentena en Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="31c11-115">If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as a global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="31c11-116">La mayoría de los documentos PDF y de Office se pueden ver en la vista previa en modo seguro mientras se realiza el análisis de ATP.</span><span class="sxs-lookup"><span data-stu-id="31c11-116">Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway.</span></span> <span data-ttu-id="31c11-117">Si un dato adjunto no es compatibles con la vista previa de Entrega dinámica, los destinatarios del correo ven un marcador de posición de datos adjuntos hasta que se complete el análisis de Datos adjuntos seguros de ATP.</span><span class="sxs-lookup"><span data-stu-id="31c11-117">If an attachment is not compatible with the Dynamic Delivery previewer, email recipients see an attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>

> [!TIP]
> <span data-ttu-id="31c11-118">Si está usando un dispositivo móvil y los PDF no se representan en primer lugar en el previsualizador de entrega dinámica, intente iniciar sesión con el explorador móvil.</span><span class="sxs-lookup"><span data-stu-id="31c11-118">If you're using a mobile device, and PDFs are not rendering in Dynamic Delivery previewer at first, try signing in using your mobile browser.</span></span>

<span data-ttu-id="31c11-119">Con la Entrega dinámica, los usuarios pueden leer y responder a sus mensajes de correo inmediatamente, mientras se analizan los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="31c11-119">With Dynamic Delivery, people can read and respond to their email messages right away, while their attachments are being analyzed.</span></span>

<span data-ttu-id="31c11-120">ATP el análisis de datos adjuntos seguros se realiza en la misma región en la que residen los datos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31c11-120">ATP Safe Attachments scanning takes place in the same region where your Microsoft 365 data resides.</span></span> <span data-ttu-id="31c11-121">Para más información sobre la geografía de centros de datos, consulte [¿Dónde se encuentran los datos?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="31c11-121">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span>

## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="31c11-122">¿Qué ocurre cuando alguien reenvía un correo electrónico que contiene datos adjuntos?</span><span class="sxs-lookup"><span data-stu-id="31c11-122">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="31c11-123">Supongamos que una organización usa la Entrega dinámica para su [directiva de Datos adjuntos seguros de ATP](set-up-atp-safe-attachments-policies.md) y alguien recibe un correo que contiene datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="31c11-123">Suppose that an organization is using Dynamic Delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment.</span></span> <span data-ttu-id="31c11-124">Ahora suponga que la persona reenvía el mensaje de correo a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="31c11-124">Now suppose that person forwards the email message to someone else.</span></span> <span data-ttu-id="31c11-125">¿Qué ocurre?</span><span class="sxs-lookup"><span data-stu-id="31c11-125">What happens?</span></span> <span data-ttu-id="31c11-126">Depende de si los destinatarios adicionales están incluidos en las directivas de Datos adjuntos seguros de ATP.</span><span class="sxs-lookup"><span data-stu-id="31c11-126">It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>

- <span data-ttu-id="31c11-127">Si un destinatario está cubierto por una directiva de Datos adjuntos seguros de ATP con la opción de Entrega dinámica, el destinatario ve el marcador de posición, con la capacidad de tener una vista previa de los archivos compatibles.</span><span class="sxs-lookup"><span data-stu-id="31c11-127">If a recipient is covered by an ATP Safe Attachments policy using the Dynamic Delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>

- <span data-ttu-id="31c11-128">Si un destinatario no se encuentra incluido en la directiva de Datos adjuntos seguros de ATP, el correo y los datos adjuntos se enviarán sin análisis de Datos adjuntos seguros de ATP ni marcadores de posición de datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="31c11-128">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without any ATP Safe Attachments scanning or attachment placeholders.</span></span>

## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="31c11-129">¿Qué se necesita para que funcione la Entrega dinámica?</span><span class="sxs-lookup"><span data-stu-id="31c11-129">What's required for Dynamic Delivery to work?</span></span>

- <span data-ttu-id="31c11-130">La organización debe tener la [Protección contra amenazas avanzada de Office 365](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="31c11-130">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>

- <span data-ttu-id="31c11-131">Se deben definir directivas para Datos adjuntos seguros de ATP con la opción de Entrega dinámica (consulte [Configurar directivas de Datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md))</span><span class="sxs-lookup"><span data-stu-id="31c11-131">Policies must be defined for ATP Safe Attachments using the Dynamic Delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>

- <span data-ttu-id="31c11-132">El correo de la organización debe estar alojado en Office 365.</span><span class="sxs-lookup"><span data-stu-id="31c11-132">Your organization's email must be hosted in Office 365.</span></span> <span data-ttu-id="31c11-133">Aunque [se puede usar la Protección contra amenazas avanzada de Office 365 con cualquier agente de transferencia de correo SMTP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (como Exchange Server), la opción de Entrega dinámica para Datos adjuntos seguros de ATP requiere que el correo electrónico de su organización esté alojado en Office 365.</span><span class="sxs-lookup"><span data-stu-id="31c11-133">Although [Office 365 Advanced Threat Protection can be used with any SMTP mail transfer agent](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (such as Exchange Server), the Dynamic Delivery option for ATP Safe Attachments requires that your organization's email be hosted in Office 365.</span></span> <span data-ttu-id="31c11-134">Si su correo electrónico no se hospeda en Office 365, elija otra [opción de directiva de Datos adjuntos seguros de ATP](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), como **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="31c11-134">If your email is not hosted in Office 365, choose a different [ATP Safe Attachments policy option](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), such as **Block**.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="31c11-135">Consideraciones adicionales</span><span class="sxs-lookup"><span data-stu-id="31c11-135">Additional considerations</span></span>

<span data-ttu-id="31c11-136">Hay algunos escenarios en los que los datos adjuntos seguros (incluida la entrega dinámica) no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="31c11-136">There are certain scenarios in which Safe Attachments (including Dynamic Delivery is not supported).</span></span> <span data-ttu-id="31c11-137">Entre ellos se incluyen:</span><span class="sxs-lookup"><span data-stu-id="31c11-137">These include:</span></span>

- <span data-ttu-id="31c11-138">Mensajes de correo electrónico que están en carpetas públicas.</span><span class="sxs-lookup"><span data-stu-id="31c11-138">Email messages that are in public folders.</span></span>

- <span data-ttu-id="31c11-139">Mensajes de correo electrónico que se redirigen del y después al buzón del usuario mediante reglas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="31c11-139">Email messages that are routed out of and then back into the user's mailbox using custom rules.</span></span>

- <span data-ttu-id="31c11-140">Mensajes de correo electrónico que se mueven (de forma automática o manual) del buzón de correo hospedado y a otras ubicaciones, incluidas las carpetas de archivo.</span><span class="sxs-lookup"><span data-stu-id="31c11-140">Email messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders.</span></span>

- <span data-ttu-id="31c11-141">Mensajes de correo electrónico que se eliminan.</span><span class="sxs-lookup"><span data-stu-id="31c11-141">Email messages that are deleted.</span></span>

- <span data-ttu-id="31c11-142">Carpeta de búsqueda del buzón de un usuario que se encuentra en estado de error.</span><span class="sxs-lookup"><span data-stu-id="31c11-142">A user's mailbox search folder that is in an error state.</span></span>

- <span data-ttu-id="31c11-143">Entornos en los que un administrador de Exchange Online ha habilitado Exclaimer.</span><span class="sxs-lookup"><span data-stu-id="31c11-143">Environments in which an Exchange Online admin has enabled Exclaimer.</span></span> <span data-ttu-id="31c11-144">Para resolver esto, consulte [los mensajes con datos adjuntos no se entregan cuando se usan la entrega y Exclaim dinámico de ATP](https://support.microsoft.com/help/4014438).</span><span class="sxs-lookup"><span data-stu-id="31c11-144">To resolve this, see [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438).</span></span>

- <span data-ttu-id="31c11-145">Mensajes cifrados con [extensiones seguras multipropósito al correo de Internet (S/MIME)](s-mime-for-message-signing-and-encryption.md)).</span><span class="sxs-lookup"><span data-stu-id="31c11-145">Messages encrypted with [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md)).</span></span>

- <span data-ttu-id="31c11-146">En los casos en los que no se admita la entrega dinámica, los datos adjuntos seguros no examinarán los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="31c11-146">In cases where Dynamic Delivery is not supported, Safe Attachments will not scan email messages.</span></span> <span data-ttu-id="31c11-147">Sin embargo, se comprobará la entrega de mensajes de correo con datos adjuntos que contengan direcciones URL, dependiendo de cómo estén configuradas las [directivas de Vínculos seguros de ATP](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="31c11-147">However, delivering email messages with attachments that contain URLs will be checked, depending on how your [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured.</span></span> <span data-ttu-id="31c11-148">En estos casos, se comprueban las direcciones URL de los mensajes de correo y los archivos de Office.</span><span class="sxs-lookup"><span data-stu-id="31c11-148">In these cases, URLs in email messages and Office files are checked.</span></span>
