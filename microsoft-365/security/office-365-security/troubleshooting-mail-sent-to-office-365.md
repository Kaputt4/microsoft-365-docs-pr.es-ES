---
title: Correo de solución de problemas enviado a Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: En este artículo se proporciona información para solucionar problemas con el envío de correo electrónico a los buzones de correo de Microsoft 365 & procedimientos recomendados para el envío masivo de correo a los clientes de Microsoft 365.
ms.openlocfilehash: 3504d7518073826f3979c3c837c58d4406886b41
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760487"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a><span data-ttu-id="9e95e-103">Correo de solución de problemas enviado a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e95e-103">Troubleshooting mail sent to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9e95e-104">En este artículo se proporciona información de solución de problemas para los remitentes que experimentan problemas al intentar enviar correo electrónico a las bandejas de correo de Microsoft 365 y los procedimientos recomendados para el envío masivo de correo a los clientes.</span><span class="sxs-lookup"><span data-stu-id="9e95e-104">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Microsoft 365 and best practices for bulk mailing to customers.</span></span>

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="9e95e-105">¿Está administrando la reputación de envío de dominios e IP?</span><span class="sxs-lookup"><span data-stu-id="9e95e-105">Are you managing your IP and domain's sending reputation?</span></span>

<span data-ttu-id="9e95e-106">Las tecnologías de filtrado de EOP están diseñadas para proporcionar protección contra correo no deseado para Microsoft 365, además de otros productos de Microsoft como Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="9e95e-106">EOP filtering technologies are designed to provide anti-spam protection for Microsoft 365 as well as other Microsoft products like Exchange Server.</span></span> <span data-ttu-id="9e95e-107">También aprovechamos SPF, DKIM y DMARC; tecnologías de autenticación de correo electrónico que ayudan a solucionar el problema de la suplantación de identidad y phishing al comprobar que el dominio que envía el correo electrónico está autorizado a hacerlo.</span><span class="sxs-lookup"><span data-stu-id="9e95e-107">We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so.</span></span> <span data-ttu-id="9e95e-108">El filtrado de EOP se ve influenciado por una serie de factores relacionados con la IP de envío, dominio, autenticación, precisión de lista, tasas de denuncia, contenido, etc.</span><span class="sxs-lookup"><span data-stu-id="9e95e-108">EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more.</span></span> <span data-ttu-id="9e95e-109">De estos factores, uno de los que más empeora la reputación del remitente y su capacidad para entregar correo electrónico es su tasa de denuncia de correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="9e95e-109">Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span>

## <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="9e95e-110">¿Está enviando correo electrónico desde direcciones IP nuevas?</span><span class="sxs-lookup"><span data-stu-id="9e95e-110">Are you sending email from new IP addresses?</span></span>

<span data-ttu-id="9e95e-p102">Las direcciones IP que no se hayan usado previamente para enviar correo electrónico por lo general no tienen ninguna reputación en nuestros sistemas. Como resultado, los correos electrónicos de IP nuevas es más probable que experimenten problemas de entrega. Una vez que la dirección IP tiene una reputación en la que no figura el envío de correo electrónico no deseado, EOP suele permitir un mejor proceso de entrega satisfactoria de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9e95e-p102">IP addresses not previously used to send email typically don't have any reputation built up in our systems. As a result, emails from new IPs are more likely to experience delivery issues. Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>

<span data-ttu-id="9e95e-p103">Las IP nuevas que se agregan a dominios que están autenticados en los registros de SPF existentes suelen disfrutar del beneficio añadido de heredar parte de la reputación del remitente del dominio. Si su dominio tiene una buena reputación de envío, las nuevas IP puede que disfruten de un tiempo más rápido de impulso. Normalmente una nueva IP se impulsa completamente en un par de semanas o antes según el volumen, la exactitud de la lista y las tasas de denuncia de correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="9e95e-p103">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation. If your domain has a good sending reputation new IPs may experience a faster ramp up time. A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>

## <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="9e95e-117">Confirme que su DNS está configurado correctamente</span><span class="sxs-lookup"><span data-stu-id="9e95e-117">Confirm that your DNS is set up correctly</span></span>

<span data-ttu-id="9e95e-118">Para obtener instrucciones acerca de cómo crear y mantener registros DNS, incluido el registro MX necesario para enrutar el correo, debe ponerse en contacto con su proveedor de hospedaje de DNS.</span><span class="sxs-lookup"><span data-stu-id="9e95e-118">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="9e95e-119">Asegúrese de que usted no se anuncia como una dirección IP no enrutable</span><span class="sxs-lookup"><span data-stu-id="9e95e-119">Ensure that you do not advertise yourself as a non-routable IP</span></span>

<span data-ttu-id="9e95e-p104">No podemos aceptar correo electrónico de los remitentes que no logran una búsqueda de DNS inverso. En algunos casos, los remitentes legítimos se anuncian incorrectamente como IP no enrutable de Internet cuando se intenta abrir una conexión a EOP. Las direcciones IP reservadas para una red privada (no enrutable) incluyen:</span><span class="sxs-lookup"><span data-stu-id="9e95e-p104">We may not accept email from senders who fail a reverse-DNS lookup. In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP. IP addresses that are reserved for private (non-routable) networking include:</span></span>

- <span data-ttu-id="9e95e-123">192.168.0.0/16 (o 192.168.0.0 - 192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="9e95e-123">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>
- <span data-ttu-id="9e95e-124">10.0.0.0/8 (o 10.0.0.0 - 10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="9e95e-124">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>
- <span data-ttu-id="9e95e-125">172.16.0.0/11 (o 172.16.0.0 - 172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="9e95e-125">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="9e95e-126">Ha recibido un informe de no entrega (NDR) al enviar un correo electrónico a un usuario en Office 365</span><span class="sxs-lookup"><span data-stu-id="9e95e-126">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>

<span data-ttu-id="9e95e-p105">Algunos problemas de entrega se deben a que Microsoft ha bloqueado la dirección IP del remitente o a que la cuenta de usuario se identifica como remitente prohibido debido a una actividad precedente de correo no deseado. Si cree que ha recibido el NDR por error, en primer lugar, siga las instrucciones del mensaje de NDR para resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="9e95e-p105">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity. If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span>

<span data-ttu-id="9e95e-129">Para obtener más información sobre el error que ha recibido, consulte la lista de códigos de error en [informes de no entrega de correo electrónico en Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="9e95e-129">For more information about the error you received, see the list of error codes in [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

 <span data-ttu-id="9e95e-130">Por ejemplo, si recibe el NDR siguiente, indica que Microsoft ha bloqueado la dirección IP de envío:</span><span class="sxs-lookup"><span data-stu-id="9e95e-130">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft:</span></span>

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

<span data-ttu-id="9e95e-131">Para solicitar la eliminación de esta lista, puede [usar el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="9e95e-131">To request removal from this list, you can [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a><span data-ttu-id="9e95e-132">Mi correo electrónico descargado en la carpeta de correo no deseado del destinatario</span><span class="sxs-lookup"><span data-stu-id="9e95e-132">My email landed in the recipient's Junk Email folder</span></span>

<span data-ttu-id="9e95e-133">Si EOP identificó incorrectamente un mensaje como correo no deseado, puede hablar con el destinatario para enviar este mensaje falso positivo al equipo de análisis de correo no deseado de Microsoft, que lo evaluará y analizará.</span><span class="sxs-lookup"><span data-stu-id="9e95e-133">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="9e95e-134">Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="9e95e-134">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="9e95e-135">El tráfico de mi dirección IP está limitado por EOP</span><span class="sxs-lookup"><span data-stu-id="9e95e-135">Traffic from my IP address is throttled by EOP</span></span>

<span data-ttu-id="9e95e-136">Si recibe un NDR de EOP que indica que EOP está limitando su dirección IP, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9e95e-136">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

<span data-ttu-id="9e95e-p107">Ha recibido el NDR porque se ha detectado actividad sospechosa procedente de la dirección IP en cuestión y se ha restringido temporalmente mientras se analiza el caso en profundidad. Si después del análisis, la dirección deja de ser sospechosa, la restricción se levantará en breve.</span><span class="sxs-lookup"><span data-stu-id="9e95e-p107">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated. If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a><span data-ttu-id="9e95e-139">No puedo recibir correo electrónico de remitentes en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e95e-139">I can't receive email from senders in Microsoft 365</span></span>

 <span data-ttu-id="9e95e-140">Para recibir mensajes de nuestros usuarios, asegúrese de que la red permite conexiones desde las direcciones IP que EOP usa en nuestros centros de datos.</span><span class="sxs-lookup"><span data-stu-id="9e95e-140">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="9e95e-141">Para obtener más información, consulte [Exchange Online Protection IP addresses](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="9e95e-141">For more information, see [Exchange Online Protection IP addresses](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span></span>

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a><span data-ttu-id="9e95e-142">Procedimientos recomendados para el correo electrónico masivo a los usuarios de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e95e-142">Best practices for bulk emailing to Microsoft 365 users</span></span>

<span data-ttu-id="9e95e-143">Si suele llevar a cabo campañas de correo electrónico masivo a los usuarios de Microsoft 365 y desea asegurarse de que los mensajes llegan de manera oportuna y segura, siga las sugerencias de esta sección.</span><span class="sxs-lookup"><span data-stu-id="9e95e-143">If you often conduct bulk email campaigns to Microsoft 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="9e95e-144">Asegurarse de que el nombre from refleja quién envía el mensaje</span><span class="sxs-lookup"><span data-stu-id="9e95e-144">Ensure that the From name reflects who is sending the message</span></span>

<span data-ttu-id="9e95e-p109">El Asunto debe ser un breve resumen del contenido del mensaje y el cuerpo del mensaje debe indicar clara y sucintamente de qué trata la oferta, servicio o producto. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9e95e-p109">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about. For example:</span></span>

<span data-ttu-id="9e95e-147">Correcto:</span><span class="sxs-lookup"><span data-stu-id="9e95e-147">Correct:</span></span>

> <span data-ttu-id="9e95e-148">De: marketing@shoppershandbag.com</span><span class="sxs-lookup"><span data-stu-id="9e95e-148">From: marketing@shoppershandbag.com</span></span> <br> <span data-ttu-id="9e95e-149">Asunto: ¡ Catálogo actualizado para la temporada de Navidad!</span><span class="sxs-lookup"><span data-stu-id="9e95e-149">Subject: Updated catalog for the Christmas season!</span></span>

<span data-ttu-id="9e95e-150">Incorrecto:</span><span class="sxs-lookup"><span data-stu-id="9e95e-150">Incorrect:</span></span>

> <span data-ttu-id="9e95e-151">De: someone@outlook.com</span><span class="sxs-lookup"><span data-stu-id="9e95e-151">From: someone@outlook.com</span></span> <br> <span data-ttu-id="9e95e-152">Asunto: Catálogos</span><span class="sxs-lookup"><span data-stu-id="9e95e-152">Subject: Catalogs</span></span>

<span data-ttu-id="9e95e-153">Cuanto más fácil sea que las personas sepan quién es usted y lo que hace, menos problemas tendrá para entregar correctamente sus mensajes a través de la mayoría de los filtros de correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="9e95e-153">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="9e95e-154">Incluir siempre una opción de cancelación de suscripción en mensajes de correo electrónico de campaña</span><span class="sxs-lookup"><span data-stu-id="9e95e-154">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="9e95e-p110">Los correos electrónicos de marketing, especialmente los boletines, siempre deben incluir una manera de cancelar la suscripción de futuros correos. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9e95e-p110">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails. For example:</span></span>

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

<span data-ttu-id="9e95e-p111">Algunos remitentes incluyen esta opción requiriendo a los destinatarios enviar un correo electrónico a un alias determinado con "Cancelar suscripción" en el asunto. Es preferible decantarse por el ejemplo de un solo clic anterior. Si decide que los destinatarios tengan que enviar un correo, asegúrese de que cuando hagan clic en el vínculo, todos los campos obligatorios estén cumplimentados previamente.</span><span class="sxs-lookup"><span data-stu-id="9e95e-p111">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject. This is not preferable to the one-click example above. If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="9e95e-160">Use la opción de doble verificación para registros de correo electrónico de marketing o boletines</span><span class="sxs-lookup"><span data-stu-id="9e95e-160">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="9e95e-p112">Se aconseja optar por esta práctica recomendada si su empresa requiere o anima a los usuarios a registrar su información de contacto para poder acceder a sus productos o servicios. Algunas empresas siguen la práctica de suscribir automáticamente a sus usuarios a mensajes de correo electrónico de marketing o boletines durante el proceso de registro, pero esto se considera un procedimiento cuestionable de marketing en el mundo del filtrado del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9e95e-p112">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services. Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>

<span data-ttu-id="9e95e-163">Durante el proceso de registro, si la casilla de verificación "Sí, por favor, envíame el boletín" o "Sí, envíenme ofertas especiales" está seleccionada por defecto, los usuarios que no presten atención pueden suscribirse involuntariamente a correo electrónico de marketing o boletines de noticias que no quieren recibir.</span><span class="sxs-lookup"><span data-stu-id="9e95e-163">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>

 <span data-ttu-id="9e95e-p113">Se recomienda en su lugar la opción de doble verificación, lo que significa que la casilla de verificación no está seleccionada de forma predeterminada para correos electrónicos de marketing o boletines. Además, una vez que se ha enviado el formulario de registro, se envía al usuario un correo electrónico de verificación con una dirección URL que le permite confirmar su decisión de recibir correos electrónicos de marketing.</span><span class="sxs-lookup"><span data-stu-id="9e95e-p113">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default. Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span>

 <span data-ttu-id="9e95e-166">Esto ayuda a garantizar que solo aquellos usuarios que quieren recibir correo electrónico de marketing se registraron para mensajes de correo electrónico, lo que libera a la empresa de envío de ser acusada de hacer uso de cualquier práctica de marketing de correo electrónico cuestionable.</span><span class="sxs-lookup"><span data-stu-id="9e95e-166">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span>

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="9e95e-167">Asegúrese de que el contenido del mensaje de correo electrónico sea transparente y rastreable.</span><span class="sxs-lookup"><span data-stu-id="9e95e-167">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="9e95e-p114">Igual de importante que la forma en que se envían los mensajes de correo electrónico es su contenido. Al crear contenido de correo electrónico, siga las siguientes prácticas recomendadas para asegurarse de que los servicios de filtrado del correo electrónico no marcarán sus correos electrónicos:</span><span class="sxs-lookup"><span data-stu-id="9e95e-p114">Just as important as the way the emails are sent is the content they contain. When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>

- <span data-ttu-id="9e95e-170">Cuando el mensaje de correo requiera que los destinatarios agreguen al remitente a la libreta de direcciones, debe especificarse claramente que dicha acción no es una garantía de entrega.</span><span class="sxs-lookup"><span data-stu-id="9e95e-170">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>

- <span data-ttu-id="9e95e-p115">Los redireccionamientos que se incluyen en el cuerpo del mensaje deben ser similares y coherentes, y no múltiples ni variados. Un redireccionamiento en este contexto es cualquier cosa que apunta fuera del mensaje, como vínculos y documentos. Si tiene mucha publicidad o vínculos de cancelación de suscripción o de actualización de perfiles, todo debe apuntar al mismo dominio. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9e95e-p115">Redirects included in the body of the message should be similar and consistent, and not multiple and varied. A redirect in this context is anything that points away from the message, such as links and documents. If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain. For example:</span></span>

  <span data-ttu-id="9e95e-175">Correcto (todos los dominios son los mismos):</span><span class="sxs-lookup"><span data-stu-id="9e95e-175">Correct (all domains are the same):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  <span data-ttu-id="9e95e-176">Incorrecto (todos los dominios son diferentes):</span><span class="sxs-lookup"><span data-stu-id="9e95e-176">Incorrect (all domains are different):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- <span data-ttu-id="9e95e-177">Evite contenidos con imágenes o datos adjuntos pesados, o mensajes que estén únicamente compuestos por una imagen.</span><span class="sxs-lookup"><span data-stu-id="9e95e-177">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>

- <span data-ttu-id="9e95e-178">Su configuración de P3P o de privacidad pública debe especificar claramente la presencia de píxeles de seguimiento (errores o señalizaciones web).</span><span class="sxs-lookup"><span data-stu-id="9e95e-178">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>

### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="9e95e-179">Quitar alias de correo electrónico incorrectos de sus bases de datos</span><span class="sxs-lookup"><span data-stu-id="9e95e-179">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="9e95e-p116">Los alias de correo electrónico de la base de datos que generan devoluciones son innecesarios y exponen a sus correos electrónicos salientes al riesgo de ser objeto de un mayor escrutinio por parte de los servicios de filtrado del correo electrónico. Asegúrese de que la base de datos de su correo electrónico está actualizada.</span><span class="sxs-lookup"><span data-stu-id="9e95e-p116">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services. Ensure that your email database is up-to-date.</span></span>
