---
title: Servicios para no clientes que envían correo a Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: Para ayudar a mantener la confianza del usuario en el uso del correo electrónico, Microsoft ha puesto en marcha distintas políticas y tecnologías para ayudar a proteger a nuestros usuarios.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3213cae1b04b3f1a1b861e8f2cfc698576013546
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207370"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a><span data-ttu-id="2f80f-103">Servicios para no clientes que envían correo a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2f80f-103">Services for non-customers sending mail to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2f80f-104">El abuso de correo electrónico, correo electrónico no deseado y correos electrónicos fraudulentos (phishing) siguen sobrecargando todo el ecosistema de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2f80f-104">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem.</span></span> <span data-ttu-id="2f80f-105">Para ayudar a mantener la confianza de los usuarios en el uso del correo electrónico, Microsoft ha puesto en marcha varias directivas y tecnologías para ayudar a proteger a nuestros usuarios.</span><span class="sxs-lookup"><span data-stu-id="2f80f-105">To help maintain user trust in the use of email, Microsoft has put various policies and technologies in place to help protect our users.</span></span> <span data-ttu-id="2f80f-106">Sin embargo, Microsoft entiende que el correo electrónico legítimo no debería verse afectado negativamente.</span><span class="sxs-lookup"><span data-stu-id="2f80f-106">However, Microsoft understands that legitimate email should not be negatively affected.</span></span> <span data-ttu-id="2f80f-107">Por lo tanto, hemos establecido un conjunto de servicios para ayudar a los remitentes a mejorar su capacidad para entregar correo electrónico a los usuarios de Microsoft 365 mediante la administración proactiva de su reputación de envío.</span><span class="sxs-lookup"><span data-stu-id="2f80f-107">Therefore, we have established a suite of services to help senders improve their ability to deliver email to Microsoft 365 users by proactively managing their sending reputation.</span></span>

<span data-ttu-id="2f80f-108">Esta introducción proporciona información sobre las ventajas que proporcionamos a su organización incluso si no es cliente.</span><span class="sxs-lookup"><span data-stu-id="2f80f-108">This overview provides information about benefits we provide to your organization even if you aren't a customer.</span></span>

## <a name="sender-solutions"></a><span data-ttu-id="2f80f-109">Soluciones de remitente</span><span class="sxs-lookup"><span data-stu-id="2f80f-109">Sender solutions</span></span>

****

|<span data-ttu-id="2f80f-110">Servicio</span><span class="sxs-lookup"><span data-stu-id="2f80f-110">Service</span></span>|<span data-ttu-id="2f80f-111">Ventajas</span><span class="sxs-lookup"><span data-stu-id="2f80f-111">Benefits</span></span>|
|---|---|
|<span data-ttu-id="2f80f-112">En este contenido de la Ayuda en línea</span><span class="sxs-lookup"><span data-stu-id="2f80f-112">This online help content</span></span>|<span data-ttu-id="2f80f-113">se ofrece:</span><span class="sxs-lookup"><span data-stu-id="2f80f-113">Provides:</span></span> <ul><li><span data-ttu-id="2f80f-114">Un punto de partida para cualquier pregunta relacionada con la entrega de comunicaciones a los usuarios de EOP.</span><span class="sxs-lookup"><span data-stu-id="2f80f-114">A starting point for any questions related to delivering communications to EOP users.</span></span></li><li><span data-ttu-id="2f80f-115">Incluye una guía en línea sencilla con nuestras directivas y requisitos.</span><span class="sxs-lookup"><span data-stu-id="2f80f-115">Includes a simple online guide with our policies and requirements.</span></span></li><li><span data-ttu-id="2f80f-116">Información general sobre los filtros de correo no deseado y las tecnologías de autenticación empleadas por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2f80f-116">An overview of the junk email filters and authentication technologies employed by Microsoft.</span></span></li><ul>|
|[<span data-ttu-id="2f80f-117">Soporte técnico de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2f80f-117">Microsoft support</span></span>](#microsoft-support)|<span data-ttu-id="2f80f-118">Proporciona soporte de autoayuda y escalamiento para problemas de entrega.</span><span class="sxs-lookup"><span data-stu-id="2f80f-118">Provides self-help and escalation support for delivery issues.</span></span>|
|[<span data-ttu-id="2f80f-119">Portal de lista ip contra correo no deseado</span><span class="sxs-lookup"><span data-stu-id="2f80f-119">Anti-Spam IP Delist Portal</span></span>](#anti-spam-ip-delist-portal)|<span data-ttu-id="2f80f-p102">Una herramienta para enviar solicitudes de eliminación de IP de la lista. Antes de enviar esta solicitud, es responsabilidad del remitente asegurarse de que cualquier otro mensaje procedente de la dirección IP en cuestión no es abusivo ni malintencionado.</span><span class="sxs-lookup"><span data-stu-id="2f80f-p102">A tool to submit IP delist request. Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>|
|[<span data-ttu-id="2f80f-122">Notificación de abusos y spam relativos a correos electrónicos no deseados procedentes de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2f80f-122">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|<span data-ttu-id="2f80f-123">Evita que el correo no deseado y otro correo no deseado se envíen desde Exchange Online y abarrote Internet y el sistema de correo.</span><span class="sxs-lookup"><span data-stu-id="2f80f-123">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the internet and your mail system.</span></span>|
|

## <a name="microsoft-support"></a><span data-ttu-id="2f80f-124">Soporte técnico de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2f80f-124">Microsoft support</span></span>

<span data-ttu-id="2f80f-125">Microsoft ofrece varias opciones de soporte técnico para personas con problemas para enviar correo a destinatarios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2f80f-125">Microsoft offers several support options for people having trouble sending mail to Microsoft 365 recipients.</span></span> <span data-ttu-id="2f80f-126">Le recomendamos que haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2f80f-126">We recommend that you:</span></span>

- <span data-ttu-id="2f80f-127">Siga las instrucciones de cualquier informe de no entrega que reciba.</span><span class="sxs-lookup"><span data-stu-id="2f80f-127">Follow the instructions in any non-delivery report you receive.</span></span>

- <span data-ttu-id="2f80f-128">Consulte los problemas más comunes que los no clientes encuentran en [Correo de solución de problemas enviado a Office 365](troubleshooting-mail-sent-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="2f80f-128">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>

- <span data-ttu-id="2f80f-129">Use el portal de deslist de [Microsoft 365](https://sender.office.com) para enviar una solicitud para que se quite la IP de la lista del remitente bloqueado.</span><span class="sxs-lookup"><span data-stu-id="2f80f-129">Use the [Microsoft 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span>

- <span data-ttu-id="2f80f-130">Lea los [foros de la comunidad de Microsoft](https://community.office365.com/f/).</span><span class="sxs-lookup"><span data-stu-id="2f80f-130">Read the [Microsoft community forums](https://community.office365.com/f/).</span></span>

- <span data-ttu-id="2f80f-131">Póngase en contacto con el cliente que está intentando enviar por correo electrónico con otro método y pídale que se puso en contacto con el Soporte técnico de Microsoft y abra un vale de soporte técnico en su nombre.</span><span class="sxs-lookup"><span data-stu-id="2f80f-131">Contact the customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf.</span></span> <span data-ttu-id="2f80f-132">En algunos casos, por motivos legales, el Soporte técnico de Microsoft debe ponerse directamente en contacto con el remitente que posee el espacio de IP que está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="2f80f-132">In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked.</span></span> <span data-ttu-id="2f80f-133">Sin embargo, normalmente los no clientes no pueden abrir incidencias de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="2f80f-133">However, non-customers typically can't open support tickets.</span></span>

  <span data-ttu-id="2f80f-134">Para obtener más información acerca del Soporte técnico de Microsoft para Office 365, consulte [Soporte técnico](/office365/servicedescriptions/office-365-platform-service-description/support).</span><span class="sxs-lookup"><span data-stu-id="2f80f-134">For more information about Microsoft Technical support for Office 365, see [Support](/office365/servicedescriptions/office-365-platform-service-description/support).</span></span>

## <a name="anti-spam-ip-delist-portal"></a><span data-ttu-id="2f80f-135">Portal de lista ip contra correo no deseado</span><span class="sxs-lookup"><span data-stu-id="2f80f-135">Anti-Spam IP Delist Portal</span></span>

<span data-ttu-id="2f80f-136">Este es un portal de autoservicio que puede usar para quitarse de la lista de remitentes bloqueados de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2f80f-136">This is a self-service portal you can use to remove yourself from the Microsoft 365 blocked senders list.</span></span> <span data-ttu-id="2f80f-137">Use este portal si recibe un mensaje de error cuando intente enviar un correo electrónico a un destinatario cuya dirección de correo electrónico se encuentra en Microsoft 365 y no cree que deba estarlo.</span><span class="sxs-lookup"><span data-stu-id="2f80f-137">Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365 and you don't think you should be.</span></span> <span data-ttu-id="2f80f-138">Para más información, consulte [Usar el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="2f80f-138">For more information, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="2f80f-139">Notificación de abusos y spam relativos a correos electrónicos no deseados procedentes de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2f80f-139">Abuse and spam reporting for junk email originating from Exchange Online</span></span>

<span data-ttu-id="2f80f-140">A veces, Microsoft365 es usado por terceros para enviar correo electrónico no deseado, en violación de nuestros términos de uso y directiva.</span><span class="sxs-lookup"><span data-stu-id="2f80f-140">Sometimes Microsoft365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="2f80f-141">Si recibe correo electrónico no deseado de Office 365, puede notificar estos mensajes a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2f80f-141">If you receive any junk email from Office 365, you can report these messages to Microsoft.</span></span> <span data-ttu-id="2f80f-142">Para obtener instrucciones, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="2f80f-142">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>