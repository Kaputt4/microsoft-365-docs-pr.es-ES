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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- m365-security
ms.custom:
- seo-marvel-apr2020
description: En este artículo se proporciona información para solucionar problemas relacionados con el envío de correo electrónico a bandejas de entrada en Microsoft 365 & procedimientos recomendados para el envío masivo de correo a clientes de Microsoft 365.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 7e9410da7ddf8fc8d125d97601a7bc57db50583a
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68075062"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a>Correo de solución de problemas enviado a Microsoft 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

En este artículo se proporciona información de solución de problemas para los remitentes que experimentan problemas al intentar enviar correo electrónico a bandejas de entrada en Microsoft 365 y procedimientos recomendados para el envío masivo de correo a los clientes.

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>¿Está administrando la reputación de envío de dominios e IP?

Las tecnologías de filtrado de EOP están diseñadas para proporcionar protección contra correo no deseado para Microsoft 365 y otros productos de Microsoft, como Exchange Server. También usamos SPF, DKIM y DMARC; tecnologías de autenticación por correo electrónico que ayudan a solucionar el problema de suplantación de identidad y suplantación de identidad mediante la comprobación de que el dominio que envía el correo electrónico está autorizado para hacerlo. El filtrado de EOP está influenciado por muchos factores relacionados con la dirección IP de envío, el dominio, la autenticación, la precisión de la lista, las tasas de quejas, el contenido y mucho más. De estos factores, uno de los que más empeora la reputación del remitente y su capacidad para entregar correo electrónico es su tasa de denuncia de correo electrónico no deseado.

## <a name="are-you-sending-email-from-new-ip-addresses"></a>¿Está enviando correo electrónico desde direcciones IP nuevas?

IP addresses not previously used to send email typically don't have any reputation built up in our systems. As a result, emails from new IPs are more likely to experience delivery issues. Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.

New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation. If your domain has a good sending reputation new IPs may experience a faster ramp up time. A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.

## <a name="confirm-that-your-dns-is-set-up-correctly"></a>Confirme que su DNS está configurado correctamente

Para obtener instrucciones acerca de cómo crear y mantener registros DNS, incluido el registro MX necesario para enrutar el correo, debe ponerse en contacto con su proveedor de hospedaje de DNS.

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>Asegúrese de que usted no se anuncia como una dirección IP no enrutable

We may not accept email from senders who fail a reverse-DNS lookup. In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP. IP addresses that are reserved for private (non-routable) networking include:

- 192.168.0.0/16 (o 192.168.0.0 - 192.168.255.255)
- 10.0.0.0/8 (o 10.0.0.0 - 10.255.255.255)
- 172.16.0.0/11 (o 172.16.0.0 - 172.31.255.255)

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>Ha recibido un informe de no entrega (NDR) al enviar un correo electrónico a un usuario en Office 365

Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity. If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.

Para obtener más información sobre el error que ha recibido, consulte la lista de códigos de error en [Email informes de no entrega en Exchange Online](/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).

 Por ejemplo, si recibe el siguiente NDR, indica que Microsoft bloqueó la dirección IP de envío:

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

Para solicitar la eliminación de esta lista, puede [usar el portal de deslist para quitarse de la lista de remitentes bloqueados](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a>Mi correo electrónico aterrizó en la carpeta de Email no deseado del destinatario.

Si EOP identificó incorrectamente un mensaje como correo no deseado, puede hablar con el destinatario para enviar este mensaje falso positivo al equipo de análisis de correo no deseado de Microsoft, que lo evaluará y analizará. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>El tráfico de mi dirección IP está limitado por EOP

Si recibe un NDR de EOP que indica que EOP está limitando su dirección IP, por ejemplo:

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated. If the suspicion is cleared through evaluation, this restriction will be lifted shortly.

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a>No puedo recibir correo electrónico de remitentes en Microsoft 365

 Para recibir mensajes de nuestros usuarios, asegúrese de que la red permite conexiones desde las direcciones IP que EOP usa en nuestros centros de datos. Para obtener más información, consulte [Exchange Online Protection direcciones IP](../../enterprise/urls-and-ip-address-ranges.md).

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a>Procedimientos recomendados para enviar correo electrónico masivo a usuarios de Microsoft 365

Si a menudo realiza campañas de correo electrónico masivas a los usuarios de Microsoft 365 y desea asegurarse de que los correos electrónicos llegan de forma segura y oportuna, siga las sugerencias de esta sección.

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>Asegúrese de que el nombre De refleja quién envía el mensaje.

The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about. For example:

Correcto:

> Desde: marketing@shoppershandbag.com <br> Asunto: ¡Se ha actualizado el catálogo para la temporada navideña!

Incorrecto:

> Desde: someone@outlook.com <br> Asunto: Catálogos

Cuanto más fácil sea que las personas sepan quién es usted y lo que hace, menos problemas tendrá para entregar correctamente sus mensajes a través de la mayoría de los filtros de correo electrónico no deseado.

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>Incluir siempre una opción de cancelación de suscripción en mensajes de correo electrónico de campaña

Los correos electrónicos de marketing, especialmente los boletines, siempre deben incluir una manera de cancelar la suscripción de futuros correos. Por ejemplo:

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject. This is not preferable to the one-click example above. If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>Use la opción de doble verificación para registros de correo electrónico de marketing o boletines

This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services. Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.

Durante el proceso de registro, si la casilla de verificación "Sí, por favor, envíame el boletín" o "Sí, envíenme ofertas especiales" está seleccionada por defecto, los usuarios que no presten atención pueden suscribirse involuntariamente a correo electrónico de marketing o boletines de noticias que no quieren recibir.

 Microsoft recomienda la opción de participación doble en su lugar, lo que significa que la casilla de correos electrónicos de marketing o boletines de noticias está desactivada de forma predeterminada. Además, una vez que se ha enviado el formulario de registro, se envía al usuario un correo electrónico de verificación con una dirección URL que le permite confirmar su decisión de recibir correos electrónicos de marketing.

 Esto ayuda a garantizar que solo aquellos usuarios que quieren recibir correo electrónico de marketing se registraron para mensajes de correo electrónico, lo que libera a la empresa de envío de ser acusada de hacer uso de cualquier práctica de marketing de correo electrónico cuestionable.

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>Asegúrese de que el contenido del mensaje de correo electrónico sea transparente y rastreable.

Just as important as the way the emails are sent is the content they contain. When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:

- Cuando el mensaje de correo requiera que los destinatarios agreguen al remitente a la libreta de direcciones, debe especificarse claramente que dicha acción no es una garantía de entrega.

- Redirects included in the body of the message should be similar and consistent, and not multiple and varied. A redirect in this context is anything that points away from the message, such as links and documents. If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain. For example:

  Correcto (todos los dominios son iguales):

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  Incorrecto (todos los dominios son diferentes):

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- Evite contenidos con imágenes o datos adjuntos pesados, o mensajes que estén únicamente compuestos por una imagen.

- Su configuración de P3P o de privacidad pública debe especificar claramente la presencia de píxeles de seguimiento (errores o señalizaciones web).

### <a name="remove-incorrect-email-aliases-from-your-databases"></a>Quitar alias de correo electrónico incorrectos de sus bases de datos

Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services. Ensure that your email database is up-to-date.
