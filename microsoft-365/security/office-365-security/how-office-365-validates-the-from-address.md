---
title: Cómo EOP valida la dirección from para evitar la suplantación de identidad
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre los tipos de direcciones de correo electrónico que aceptan o rechazan Exchange Online Protection (EOP) y Outlook.com para ayudar a evitar la suplantación de identidad (phishing).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 25fbca8fa5d264a212ac25e2035bffde0819383d
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659659"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>Cómo EOP valida la dirección from para evitar la suplantación de identidad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Los ataques de suplantación de identidad son una amenaza constante para cualquier organización de correo electrónico. Además de usar [las direcciones de correo electrónico de remitente falsificado (falso)](anti-spoofing-protection.md), los atacantes suelen usar valores en la dirección from que infringen los estándares de Internet. Para ayudar a evitar este tipo de suplantación de identidad (phishing), Exchange Online Protection (EOP) y Outlook.com ahora requieren que los mensajes entrantes incluyan una dirección de RFC conforme a lo descrito en este artículo. Esta aplicación se habilitó en noviembre de 2017.

**Notas**:

- Si recibe regularmente correo electrónico de organizaciones que tienen direcciones de formato incorrecto como se describe en este artículo, Anime a estas organizaciones a que actualicen sus servidores de correo electrónico para cumplir con los estándares de seguridad modernos.

- El campo de remitente relacionado (usado por el envío en nombre y las listas de correo) no se ve afectado por estos requisitos. Para obtener más información, vea la siguiente entrada de blog: [¿qué queremos decir cuando hacemos referencia al "remitente" de un correo electrónico?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).

## <a name="an-overview-of-email-message-standards"></a>Información general sobre los estándares de mensajes de correo electrónico

Un mensaje de correo electrónico SMTP estándar está compuesto por el *sobre del mensaje* y el contenido del mensaje. El sobre del mensaje contiene información necesaria para transmitir y entregar el mensaje entre servidores SMTP. El contenido del mensaje contiene el cuerpo del mensaje y campos de encabezado de mensaje, que se denominan de forma colectiva *encabezado del mensaje*. El sobre del mensaje se describe en [rfc 5321](https://tools.ietf.org/html/rfc5321)y el encabezado del mensaje se describe en [RFC 5322](https://tools.ietf.org/html/rfc5322). Los destinatarios nunca ven el sobre del mensaje real porque lo genera el proceso de transmisión del mensaje y, en realidad, no forma parte del mensaje.

- La `5321.MailFrom` dirección (también conocida como **correo de** la dirección de, P1 Sender o Envelope Sender) es la dirección de correo electrónico que se usa en la transmisión SMTP del mensaje. Esta dirección de correo electrónico suele registrarse en el campo de encabezado **Return-Path** del encabezado del mensaje (aunque es posible que el remitente designe otra dirección **de correo electrónico de ruta de regreso** ).

- El `5322.From` (también conocido como dirección de de o remitente P2) es la dirección de correo electrónico que aparece en el campo **de encabezado de** y es la dirección de correo electrónico del remitente que se muestra en los clientes de correo electrónico. La dirección de es la que se centra en los requisitos de este artículo.

La dirección de se define en detalle en varias RFC (por ejemplo, las secciones RFC 5322 3.2.3, 3,4, 3.4.1 y [rfc 3696](https://tools.ietf.org/html/rfc3696)). Hay muchas variaciones en el direccionamiento y lo que se considera válido o no válido. Para simplificarlo, le recomendamos el siguiente formato y las siguientes definiciones:

`From: "Display Name" <EmailAddress>`

- **Nombre para mostrar**: frase opcional que describe el propietario de la dirección de correo electrónico.

  - Se recomienda incluir siempre el nombre para mostrar entre comillas dobles ("), tal y como se muestra. Si el nombre para mostrar contiene una coma, _debe_ escribir la cadena entre comillas dobles según RFC 5322.
  - Si la dirección de incluye un nombre para mostrar, el valor EmailAddress debe estar entre corchetes angulares (< >), tal como se muestra.
  - Microsoft recomienda encarecidamente que inserte un espacio entre el nombre para mostrar y la dirección de correo electrónico.

- **EmailAddress**: una dirección de correo electrónico usa el formato `local-part@domain` :

  - **local-Part**: cadena que identifica el buzón asociado con la dirección. Este valor es único dentro del dominio. A menudo se usa el nombre de usuario o GUID del propietario del buzón.
  - **dominio**: el nombre de dominio completo (FQDN) del servidor de correo electrónico que hospeda el buzón identificado por la parte local de la dirección de correo electrónico.

  Estas son algunas consideraciones adicionales para el valor EmailAddress:

  - Solo una dirección de correo electrónico.
  - Le recomendamos que no separe los corchetes angulares con espacios.
  - No incluya texto adicional después de la dirección de correo electrónico.

## <a name="examples-of-valid-and-invalid-from-addresses"></a>Ejemplos de direcciones válidas y no válidas

Las siguientes direcciones de correo electrónico son válidas:

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` (No se recomienda porque hay espacios entre los corchetes angulares y la dirección de correo electrónico).

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (No se recomienda porque el nombre para mostrar no está incluido entre comillas dobles).

Las siguientes direcciones de correo electrónico no son válidas:

- **No desde dirección**: algunos mensajes automatizados no incluyen una dirección de de. En el pasado, cuando Microsoft 365 o Outlook.com recibía un mensaje sin una dirección de desde, el servicio agregaba el siguiente valor predeterminado de: Address para que el mensaje se pudiera entregar:

  `From: <>`

  Ahora, ya no se aceptan los mensajes con una dirección desde en blanco.

- `From: Microsoft 365 sender@contoso.com` (El nombre para mostrar está presente, pero la dirección de correo electrónico no se incluye entre corchetes angulares).

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Texto después de la dirección de correo electrónico).

- `From: Sender, Example <sender.example@contoso.com>` (El nombre para mostrar contiene una coma, pero no se incluye entre comillas dobles).

- `From: "Microsoft 365 <sender@contoso.com>"` (El valor completo se incluye incorrectamente entre comillas dobles).

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (El nombre para mostrar está presente, pero la dirección de correo electrónico no se incluye entre corchetes angulares).

- `From: Microsoft 365<sender@contoso.com>` (Sin espacio entre el nombre para mostrar y el corchete angular de apertura).

- `From: "Microsoft 365"<sender@contoso.com>` (Sin espacio entre el signo de comillas tipográficas y el corchete angular de cierre).

## <a name="suppress-auto-replies-to-your-custom-domain"></a>Suprimir las respuestas automáticas a su dominio personalizado

No puede usar el valor `From: <>` para suprimir las respuestas automáticas. En su lugar, debe configurar un registro MX nulo para el dominio personalizado. Las respuestas automáticas (y todas las respuestas) se suprimen naturalmente porque no hay ninguna dirección publicada a la que el servidor de respuesta pueda enviar mensajes.

- Elija un dominio de correo electrónico que no pueda recibir correo electrónico. Por ejemplo, si su dominio principal es contoso.com, puede elegir noreply.contoso.com.

- El registro MX nulo para este dominio consta de un único período.

Por ejemplo:

```text
noreply.contoso.com IN MX .
```

Para obtener más información acerca de la configuración de registros MX, vea [crear registros DNS en cualquier proveedor de hospedaje DNS para Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

Para obtener más información acerca de la publicación de un MX nulo, consulte [RFC 7505](https://tools.ietf.org/html/rfc7505).

## <a name="override-from-address-enforcement"></a>Invalidar de la aplicación de direcciones

Para omitir los requisitos de dirección de de para el correo electrónico entrante, puede usar la lista de direcciones IP permitidas (filtrado de la conexión) o las reglas de flujo de correo (también conocidas como reglas de transporte), como se describe en [crear listas de remitentes seguros en Microsoft 365](create-safe-sender-lists-in-office-365.md).

No puede invalidar los requisitos de dirección de de dirección para el correo electrónico saliente que envíe desde Microsoft 365. Además, Outlook.com no permitirá invalidaciones de ningún tipo, incluso a través del soporte técnico.

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Otras formas de evitar y proteger contra cybercrimes en Microsoft 365

Para obtener más información sobre cómo reforzar la organización contra el phishing, el correo no deseado, las infracciones de datos y otras amenazas, vea las [diez formas principales de proteger los planes de Microsoft 365 para empresas](../../admin/security-and-compliance/secure-your-business-data.md).
