---
title: Cómo EOP valida la dirección From para evitar la suplantación de identidad
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre los tipos de direcciones de correo electrónico aceptadas o rechazadas por Exchange Online Protection (EOP) y Outlook.com ayudar a evitar el phishing.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71da944c02137024adda48434c5214695c54a817
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910683"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="3cd44-103">Cómo EOP valida la dirección From para evitar la suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="3cd44-103">How EOP validates the From address to prevent phishing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3cd44-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="3cd44-104">**Applies to**</span></span>
- [<span data-ttu-id="3cd44-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3cd44-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3cd44-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="3cd44-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="3cd44-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3cd44-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="3cd44-108">Los ataques de suplantación de identidad son una amenaza constante para cualquier organización de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3cd44-108">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="3cd44-109">Además de usar direcciones de correo electrónico de remitente suplantadas [(falsificadas),](anti-spoofing-protection.md)los atacantes suelen usar valores en la dirección From que infringen los estándares de Internet.</span><span class="sxs-lookup"><span data-stu-id="3cd44-109">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="3cd44-110">Para ayudar a evitar este tipo de phishing, Exchange Online Protection (EOP) y Outlook.com ahora requieren que los mensajes entrantes incluyan una dirección From compatible con RFC, como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="3cd44-110">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this article.</span></span> <span data-ttu-id="3cd44-111">Esta aplicación se ha habilitado en noviembre de 2017.</span><span class="sxs-lookup"><span data-stu-id="3cd44-111">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="3cd44-112">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="3cd44-112">**Notes**:</span></span>

- <span data-ttu-id="3cd44-113">Si recibe periódicamente correo electrónico de organizaciones con direcciones From malformadas, como se describe en este artículo, anime a estas organizaciones a actualizar sus servidores de correo electrónico para que cumplan con los estándares de seguridad modernos.</span><span class="sxs-lookup"><span data-stu-id="3cd44-113">If you regularly receive email from organizations that have malformed From addresses as described in this article, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="3cd44-114">El campo Remitente relacionado (usado por Enviar en nombre y listas de correo) no se ve afectado por estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="3cd44-114">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="3cd44-115">Para obtener más información, vea la siguiente entrada de blog: ¿Qué queremos decir cuando nos referimos al ["remitente" de un correo electrónico?](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email).</span><span class="sxs-lookup"><span data-stu-id="3cd44-115">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="3cd44-116">Información general sobre los estándares de mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="3cd44-116">An overview of email message standards</span></span>

<span data-ttu-id="3cd44-117">Un mensaje de correo electrónico SMTP estándar está compuesto por el *sobre del mensaje* y el contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="3cd44-117">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="3cd44-118">El sobre del mensaje contiene información necesaria para transmitir y entregar el mensaje entre servidores SMTP.</span><span class="sxs-lookup"><span data-stu-id="3cd44-118">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="3cd44-119">El contenido del mensaje contiene el cuerpo del mensaje y campos de encabezado de mensaje, que se denominan de forma colectiva *encabezado del mensaje*.</span><span class="sxs-lookup"><span data-stu-id="3cd44-119">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="3cd44-120">El sobre del mensaje se describe [en RFC 5321](https://tools.ietf.org/html/rfc5321)y el encabezado del mensaje se describe en [RFC 5322](https://tools.ietf.org/html/rfc5322).</span><span class="sxs-lookup"><span data-stu-id="3cd44-120">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="3cd44-121">Los destinatarios nunca ven el sobre de mensaje real porque lo genera el proceso de transmisión de mensajes y no forma parte del mensaje.</span><span class="sxs-lookup"><span data-stu-id="3cd44-121">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="3cd44-122">La dirección (también conocida como dirección `5321.MailFrom` **MAIL FROM,** remitente P1 o remitente de sobre) es la dirección de correo electrónico que se usa en la transmisión SMTP del mensaje.</span><span class="sxs-lookup"><span data-stu-id="3cd44-122">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="3cd44-123">Esta dirección de correo electrónico normalmente se registra en el campo de encabezado **Return-Path** en el encabezado del mensaje (aunque es posible que el remitente designe una dirección de correo electrónico **return-path** diferente).</span><span class="sxs-lookup"><span data-stu-id="3cd44-123">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="3cd44-124">El (también conocido como la dirección De o el remitente P2) es la dirección de correo electrónico en el campo De encabezado y es la dirección de correo electrónico del remitente que se muestra en los clientes `5322.From` de correo electrónico. </span><span class="sxs-lookup"><span data-stu-id="3cd44-124">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="3cd44-125">La dirección De es el foco de los requisitos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="3cd44-125">The From address is the focus of the requirements in this article.</span></span>

<span data-ttu-id="3cd44-126">La dirección De se define detalladamente en varias RFC (por ejemplo, rfc 5322 secciones 3.2.3, 3.4 y 3.4.1 y [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span><span class="sxs-lookup"><span data-stu-id="3cd44-126">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="3cd44-127">Hay muchas variaciones en el direccionamiento y lo que se considera válido o no válido.</span><span class="sxs-lookup"><span data-stu-id="3cd44-127">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="3cd44-128">Para que sea sencillo, recomendamos el siguiente formato y definiciones:</span><span class="sxs-lookup"><span data-stu-id="3cd44-128">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="3cd44-129">**Nombre para** mostrar: una frase opcional que describe al propietario de la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3cd44-129">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="3cd44-130">Se recomienda incluir siempre el nombre para mostrar entre comillas dobles (") como se muestra.</span><span class="sxs-lookup"><span data-stu-id="3cd44-130">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="3cd44-131">Si el nombre para mostrar contiene una coma, debe escribir _la_ cadena entre comillas dobles por RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="3cd44-131">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="3cd44-132">Si la dirección De incluye un nombre para mostrar, el valor EmailAddress debe incluirse entre corchetes angulares (< >) como se muestra.</span><span class="sxs-lookup"><span data-stu-id="3cd44-132">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="3cd44-133">Microsoft recomienda encarecidamente insertar un espacio entre el nombre para mostrar y la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3cd44-133">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="3cd44-134">**EmailAddress:** una dirección de correo electrónico usa el formato `local-part@domain` :</span><span class="sxs-lookup"><span data-stu-id="3cd44-134">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="3cd44-135">**local-part:** cadena que identifica el buzón asociado a la dirección.</span><span class="sxs-lookup"><span data-stu-id="3cd44-135">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="3cd44-136">Este valor es único dentro del dominio.</span><span class="sxs-lookup"><span data-stu-id="3cd44-136">This value is unique within the domain.</span></span> <span data-ttu-id="3cd44-137">A menudo, se usa el nombre de usuario o GUID del propietario del buzón.</span><span class="sxs-lookup"><span data-stu-id="3cd44-137">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="3cd44-138">**dominio:** el nombre de dominio completo (FQDN) del servidor de correo electrónico que hospeda el buzón identificado por la parte local de la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3cd44-138">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="3cd44-139">Estas son algunas consideraciones adicionales para el valor EmailAddress:</span><span class="sxs-lookup"><span data-stu-id="3cd44-139">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="3cd44-140">Solo una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3cd44-140">Only one email address.</span></span>
  - <span data-ttu-id="3cd44-141">Se recomienda no separar los corchetes angulares con espacios.</span><span class="sxs-lookup"><span data-stu-id="3cd44-141">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="3cd44-142">No incluya texto adicional después de la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3cd44-142">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="3cd44-143">Ejemplos de direcciones From válidas y no válidas</span><span class="sxs-lookup"><span data-stu-id="3cd44-143">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="3cd44-144">Las siguientes direcciones de correo electrónico De son válidas:</span><span class="sxs-lookup"><span data-stu-id="3cd44-144">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="3cd44-145">`From: < sender@contoso.com >` (No se recomienda porque hay espacios entre los corchetes angulares y la dirección de correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="3cd44-145">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="3cd44-146">`From: Microsoft 365 <sender@contoso.com>` (No se recomienda porque el nombre para mostrar no está entre comillas dobles).</span><span class="sxs-lookup"><span data-stu-id="3cd44-146">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="3cd44-147">Las siguientes direcciones de correo electrónico De no son válidas:</span><span class="sxs-lookup"><span data-stu-id="3cd44-147">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="3cd44-148">**No Dirección de origen:** algunos mensajes automatizados no incluyen una dirección De.</span><span class="sxs-lookup"><span data-stu-id="3cd44-148">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="3cd44-149">En el pasado, cuando Microsoft 365 o Outlook.com recibió un mensaje sin una dirección From, el servicio agregó la siguiente dirección predeterminada From: para que el mensaje sea entregable:</span><span class="sxs-lookup"><span data-stu-id="3cd44-149">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="3cd44-150">Ahora, los mensajes con una dirección De en blanco ya no se aceptan.</span><span class="sxs-lookup"><span data-stu-id="3cd44-150">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="3cd44-151">`From: Microsoft 365 sender@contoso.com` (El nombre para mostrar está presente, pero la dirección de correo electrónico no está entre corchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="3cd44-151">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="3cd44-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Texto después de la dirección de correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="3cd44-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="3cd44-153">`From: Sender, Example <sender.example@contoso.com>` (El nombre para mostrar contiene una coma, pero no está entre comillas dobles).</span><span class="sxs-lookup"><span data-stu-id="3cd44-153">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="3cd44-154">`From: "Microsoft 365 <sender@contoso.com>"` (El valor completo está incorrectamente entre comillas dobles).</span><span class="sxs-lookup"><span data-stu-id="3cd44-154">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="3cd44-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (El nombre para mostrar está presente, pero la dirección de correo electrónico no está entre corchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="3cd44-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="3cd44-156">`From: Microsoft 365<sender@contoso.com>` (Sin espacio entre el nombre para mostrar y el corchete angular izquierdo).</span><span class="sxs-lookup"><span data-stu-id="3cd44-156">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="3cd44-157">`From: "Microsoft 365"<sender@contoso.com>` (Sin espacio entre la comilla doble de cierre y el corchete angular izquierdo).</span><span class="sxs-lookup"><span data-stu-id="3cd44-157">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="3cd44-158">Suprimir las respuestas automáticas al dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="3cd44-158">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="3cd44-159">No puede usar el valor para `From: <>` suprimir las respuestas automáticas.</span><span class="sxs-lookup"><span data-stu-id="3cd44-159">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="3cd44-160">En su lugar, debe configurar un registro MX nulo para su dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="3cd44-160">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="3cd44-161">Las respuestas automáticas (y todas las respuestas) se suprimen de forma natural porque no hay ninguna dirección publicada a la que el servidor que responde pueda enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="3cd44-161">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="3cd44-162">Elija un dominio de correo electrónico que no pueda recibir correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3cd44-162">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="3cd44-163">Por ejemplo, si el dominio principal está contoso.com, puede elegir noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3cd44-163">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="3cd44-164">El registro MX nulo para este dominio consta de un solo punto.</span><span class="sxs-lookup"><span data-stu-id="3cd44-164">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="3cd44-165">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3cd44-165">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="3cd44-166">Para obtener más información acerca de la configuración de registros MX, vea [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="3cd44-166">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="3cd44-167">Para obtener más información acerca de la publicación de un MX nulo, [vea RFC 7505](https://tools.ietf.org/html/rfc7505).</span><span class="sxs-lookup"><span data-stu-id="3cd44-167">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="3cd44-168">Invalidación de la aplicación de direcciones</span><span class="sxs-lookup"><span data-stu-id="3cd44-168">Override From address enforcement</span></span>

<span data-ttu-id="3cd44-169">Para omitir los requisitos de direcciones de origen para el correo electrónico entrante, puede usar la lista de direcciones IP permitidos (filtrado de conexiones) o las reglas de flujo de correo (también conocidas como reglas de transporte) como se describe en Crear listas de remitentes seguros en [Microsoft 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="3cd44-169">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="3cd44-170">No puede invalidar los requisitos de dirección De para el correo electrónico saliente que envíe desde Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cd44-170">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="3cd44-171">Además, Outlook.com no permitirá invalidaciones de ningún tipo, incluso a través de la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="3cd44-171">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="3cd44-172">Otras formas de evitar y proteger contra los delitos cibernéticos en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3cd44-172">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="3cd44-173">Para obtener más información sobre cómo reforzar la organización contra el phishing, el correo no deseado, las vulneraciones de datos y otras amenazas, vea [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span><span class="sxs-lookup"><span data-stu-id="3cd44-173">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>