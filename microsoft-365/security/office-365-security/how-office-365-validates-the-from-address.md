---
title: Cómo Microsoft 365 valida la dirección from para evitar la suplantación de identidad
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Borrar los requisitos de las direcciones de correo electrónico de los mensajes entrantes en Microsoft 365. A partir del 2017 de noviembre, el servicio requiere ahora compatibilidad con RFC desde direcciones para ayudar a evitar la suplantación de identidad.
ms.openlocfilehash: 876ede087b37c381b9e9b557268057122e0987c0
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633983"
---
# <a name="how-microsoft-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="a1d65-104">Cómo Microsoft 365 valida la dirección from para evitar la suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="a1d65-104">How Microsoft 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="a1d65-105">Las cuentas de correo electrónico de Microsoft 365 reciben un número cada vez mayor de ataques de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="a1d65-105">Microsoft 365 email accounts receive an increasingly large number of phishing attacks.</span></span> <span data-ttu-id="a1d65-106">Además de usar [las direcciones de correo electrónico de remitente falsificado (falso)](anti-spoofing-protection.md), los atacantes suelen usar valores en la dirección from que infringen los estándares de Internet.</span><span class="sxs-lookup"><span data-stu-id="a1d65-106">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="a1d65-107">Para ayudar a evitar este tipo de suplantación de identidad (phishing), Microsoft 365 y Outlook.com ahora requieren que los mensajes entrantes incluyan una dirección de RFC conforme a lo descrito en este tema.</span><span class="sxs-lookup"><span data-stu-id="a1d65-107">To help prevent this type of phishing, Microsoft 365 and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this topic.</span></span> <span data-ttu-id="a1d65-108">Esta aplicación se habilitó en noviembre de 2017.</span><span class="sxs-lookup"><span data-stu-id="a1d65-108">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="a1d65-109">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="a1d65-109">**Notes**:</span></span>

- <span data-ttu-id="a1d65-110">Si recibe regularmente correo electrónico de organizaciones que tienen direcciones de formato incorrecto como se describe en este tema, Anime a estas organizaciones a que actualicen sus servidores de correo electrónico para cumplir con los estándares de seguridad modernos.</span><span class="sxs-lookup"><span data-stu-id="a1d65-110">If you regularly receive email from organizations that have malformed From addresses as described in this topic, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="a1d65-111">El campo de remitente relacionado (usado por el envío en nombre y las listas de correo) no se ve afectado por estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="a1d65-111">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="a1d65-112">Para obtener más información, vea la siguiente entrada de blog: [¿qué queremos decir cuando hacemos referencia al "remitente" de un correo electrónico?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span><span class="sxs-lookup"><span data-stu-id="a1d65-112">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="a1d65-113">Información general sobre los estándares de mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="a1d65-113">An overview of email message standards</span></span>

<span data-ttu-id="a1d65-114">Un mensaje de correo electrónico SMTP estándar está compuesto por el *sobre del mensaje* y el contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a1d65-114">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="a1d65-115">El sobre del mensaje contiene información necesaria para transmitir y entregar el mensaje entre servidores SMTP.</span><span class="sxs-lookup"><span data-stu-id="a1d65-115">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="a1d65-116">El contenido del mensaje contiene el cuerpo del mensaje y campos de encabezado de mensaje, que se denominan de forma colectiva *encabezado del mensaje*.</span><span class="sxs-lookup"><span data-stu-id="a1d65-116">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="a1d65-117">El sobre del mensaje se describe en [rfc 5321](https://tools.ietf.org/html/rfc5321)y el encabezado del mensaje se describe en [RFC 5322](https://tools.ietf.org/html/rfc5322).</span><span class="sxs-lookup"><span data-stu-id="a1d65-117">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="a1d65-118">Los destinatarios nunca ven el sobre del mensaje real porque lo genera el proceso de transmisión del mensaje y, en realidad, no forma parte del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a1d65-118">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="a1d65-119">La `5321.MailFrom` dirección (también conocida como **correo de** la dirección de, P1 Sender o Envelope Sender) es la dirección de correo electrónico que se usa en la transmisión SMTP del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a1d65-119">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="a1d65-120">Esta dirección de correo electrónico suele registrarse en el campo de encabezado **Return-Path** del encabezado del mensaje (aunque es posible que el remitente designe otra dirección **de correo electrónico de ruta de regreso** ).</span><span class="sxs-lookup"><span data-stu-id="a1d65-120">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="a1d65-121">El `5322.From` (también conocido como dirección de de o remitente P2) es la dirección de correo electrónico que aparece en el campo **de encabezado de** y es la dirección de correo electrónico del remitente que se muestra en los clientes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a1d65-121">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="a1d65-122">La dirección de es el centro de los requisitos de este tema.</span><span class="sxs-lookup"><span data-stu-id="a1d65-122">The From address is the focus of the requirements in this topic.</span></span>

<span data-ttu-id="a1d65-123">La dirección de se define en detalle en varias RFC (por ejemplo, las secciones RFC 5322 3.2.3, 3,4, 3.4.1 y [rfc 3696](https://tools.ietf.org/html/rfc3696)).</span><span class="sxs-lookup"><span data-stu-id="a1d65-123">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="a1d65-124">Hay muchas variaciones en el direccionamiento y lo que se considera válido o no válido.</span><span class="sxs-lookup"><span data-stu-id="a1d65-124">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="a1d65-125">Para simplificarlo, le recomendamos el siguiente formato y las siguientes definiciones:</span><span class="sxs-lookup"><span data-stu-id="a1d65-125">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="a1d65-126">**Nombre para mostrar**: frase opcional que describe el propietario de la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a1d65-126">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="a1d65-127">Se recomienda incluir siempre el nombre para mostrar entre comillas dobles ("), tal y como se muestra.</span><span class="sxs-lookup"><span data-stu-id="a1d65-127">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="a1d65-128">Si el nombre para mostrar contiene una coma, _debe_ escribir la cadena entre comillas dobles según RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="a1d65-128">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="a1d65-129">Si la dirección de incluye un nombre para mostrar, el valor EmailAddress debe estar entre corchetes angulares (< >), tal como se muestra.</span><span class="sxs-lookup"><span data-stu-id="a1d65-129">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="a1d65-130">Microsoft recomienda encarecidamente que inserte un espacio entre el nombre para mostrar y la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a1d65-130">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="a1d65-131">**EmailAddress**: una dirección de correo electrónico usa `local-part@domain`el formato:</span><span class="sxs-lookup"><span data-stu-id="a1d65-131">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="a1d65-132">**local-Part**: cadena que identifica el buzón asociado con la dirección.</span><span class="sxs-lookup"><span data-stu-id="a1d65-132">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="a1d65-133">Este valor es único dentro del dominio.</span><span class="sxs-lookup"><span data-stu-id="a1d65-133">This value is unique within the domain.</span></span> <span data-ttu-id="a1d65-134">A menudo se usa el nombre de usuario o GUID del propietario del buzón.</span><span class="sxs-lookup"><span data-stu-id="a1d65-134">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="a1d65-135">**dominio**: el nombre de dominio completo (FQDN) del servidor de correo electrónico que hospeda el buzón identificado por la parte local de la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a1d65-135">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="a1d65-136">Estas son algunas consideraciones adicionales para el valor EmailAddress:</span><span class="sxs-lookup"><span data-stu-id="a1d65-136">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="a1d65-137">Solo una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a1d65-137">Only one email address.</span></span>
  - <span data-ttu-id="a1d65-138">Le recomendamos que no separe los corchetes angulares con espacios.</span><span class="sxs-lookup"><span data-stu-id="a1d65-138">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="a1d65-139">No incluya texto adicional después de la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a1d65-139">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="a1d65-140">Ejemplos de direcciones válidas y no válidas</span><span class="sxs-lookup"><span data-stu-id="a1d65-140">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="a1d65-141">Las siguientes direcciones de correo electrónico son válidas:</span><span class="sxs-lookup"><span data-stu-id="a1d65-141">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="a1d65-142">`From: < sender@contoso.com >`(No se recomienda porque hay espacios entre los corchetes angulares y la dirección de correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="a1d65-142">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="a1d65-143">`From: Microsoft 365 <sender@contoso.com>`(No se recomienda porque el nombre para mostrar no está incluido entre comillas dobles).</span><span class="sxs-lookup"><span data-stu-id="a1d65-143">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="a1d65-144">Las siguientes direcciones de correo electrónico no son válidas:</span><span class="sxs-lookup"><span data-stu-id="a1d65-144">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="a1d65-145">**No desde dirección**: algunos mensajes automatizados no incluyen una dirección de de.</span><span class="sxs-lookup"><span data-stu-id="a1d65-145">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="a1d65-146">En el pasado, cuando Microsoft 365 o Outlook.com recibía un mensaje sin una dirección de desde, el servicio agregaba el siguiente valor predeterminado de: Address para que el mensaje se pudiera entregar:</span><span class="sxs-lookup"><span data-stu-id="a1d65-146">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="a1d65-147">Ahora, ya no se aceptan los mensajes con una dirección desde en blanco.</span><span class="sxs-lookup"><span data-stu-id="a1d65-147">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="a1d65-148">`From: Microsoft 365 sender@contoso.com`(El nombre para mostrar está presente, pero la dirección de correo electrónico no se incluye entre corchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="a1d65-148">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="a1d65-149">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)`(Texto después de la dirección de correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="a1d65-149">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="a1d65-150">`From: Sender, Example <sender.example@contoso.com>`(El nombre para mostrar contiene una coma, pero no se incluye entre comillas dobles).</span><span class="sxs-lookup"><span data-stu-id="a1d65-150">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="a1d65-151">`From: "Microsoft 365 <sender@contoso.com>"`(El valor completo se incluye incorrectamente entre comillas dobles).</span><span class="sxs-lookup"><span data-stu-id="a1d65-151">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="a1d65-152">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com`(El nombre para mostrar está presente, pero la dirección de correo electrónico no se incluye entre corchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="a1d65-152">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="a1d65-153">`From: Microsoft 365<sender@contoso.com>`(Sin espacio entre el nombre para mostrar y el corchete angular de apertura).</span><span class="sxs-lookup"><span data-stu-id="a1d65-153">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="a1d65-154">`From: "Microsoft 365"<sender@contoso.com>`(Sin espacio entre el signo de comillas tipográficas y el corchete angular de cierre).</span><span class="sxs-lookup"><span data-stu-id="a1d65-154">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="a1d65-155">Suprimir las respuestas automáticas a su dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="a1d65-155">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="a1d65-156">No puede usar el valor `From: <>` para suprimir las respuestas automáticas.</span><span class="sxs-lookup"><span data-stu-id="a1d65-156">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="a1d65-157">En su lugar, debe configurar un registro MX nulo para el dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="a1d65-157">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="a1d65-158">Las respuestas automáticas (y todas las respuestas) se suprimen naturalmente porque no hay ninguna dirección publicada a la que el servidor de respuesta pueda enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="a1d65-158">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="a1d65-159">Elija un dominio de correo electrónico que no pueda recibir correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a1d65-159">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="a1d65-160">Por ejemplo, si su dominio principal es contoso.com, puede elegir noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a1d65-160">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="a1d65-161">El registro MX nulo para este dominio consta de un único período.</span><span class="sxs-lookup"><span data-stu-id="a1d65-161">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="a1d65-162">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a1d65-162">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="a1d65-163">Para obtener más información acerca de la configuración de registros MX, vea [crear registros DNS en cualquier proveedor de hospedaje DNS para Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="a1d65-163">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="a1d65-164">Para obtener más información acerca de la publicación de un MX nulo, consulte [RFC 7505](https://tools.ietf.org/html/rfc7505).</span><span class="sxs-lookup"><span data-stu-id="a1d65-164">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="a1d65-165">Invalidar de la aplicación de direcciones</span><span class="sxs-lookup"><span data-stu-id="a1d65-165">Override From address enforcement</span></span>

<span data-ttu-id="a1d65-166">Para omitir los requisitos de dirección de de para el correo electrónico entrante, puede usar la lista de direcciones IP permitidas (filtrado de la conexión) o las reglas de flujo de correo (también conocidas como reglas de transporte), como se describe en [crear listas de remitentes seguros en Microsoft 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="a1d65-166">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="a1d65-167">No puede invalidar los requisitos de dirección de de dirección para el correo electrónico saliente que envíe desde Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a1d65-167">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="a1d65-168">Además, Outlook.com no permitirá invalidaciones de ningún tipo, incluso a través del soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="a1d65-168">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="a1d65-169">Otras formas de evitar y proteger contra cybercrimes en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a1d65-169">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="a1d65-170">Para obtener más información sobre cómo reforzar la organización contra el phishing, el correo no deseado, las infracciones de datos y otras amenazas, vea las [diez formas principales de proteger los planes de Microsoft 365 para empresas](../../admin/security-and-compliance/secure-your-business-data.md).</span><span class="sxs-lookup"><span data-stu-id="a1d65-170">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>