---
title: Cómo EOP valida la dirección De para evitar la suplantación de identidad
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
description: Los administradores pueden obtener información sobre los tipos de direcciones de correo electrónico aceptadas o rechazadas por Exchange Online Protection (EOP) y Outlook.com para ayudar a evitar la suplantación de identidad.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e7c2cbec49082fbded857dde13f73516fd3e0fd5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167520"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>Cómo EOP valida la dirección De para evitar la suplantación de identidad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Los ataques de suplantación de identidad son una amenaza constante para cualquier organización de correo electrónico. Además de usar direcciones de correo electrónico de remitente suplantadas [(falsificadas),](anti-spoofing-protection.md)los atacantes suelen usar valores en la dirección De que infringen los estándares de Internet. Para ayudar a evitar este tipo de suplantación de identidad, Exchange Online Protection (EOP) y Outlook.com ahora requieren que los mensajes entrantes incluyan una dirección De compatible con RFC, como se describe en este artículo. Esta aplicación se habilitó en noviembre de 2017.

**Notas**:

- Si recibe periódicamente correo electrónico de organizaciones que tienen direcciones De con formato no conforme a lo descrito en este artículo, anime a estas organizaciones a actualizar sus servidores de correo electrónico para que cumplan con los estándares de seguridad modernos.

- El campo Remitente relacionado (usado por Enviar en nombre de y las listas de distribución de correo) no se ve afectado por estos requisitos. Para obtener más información, consulte la siguiente entrada de blog: ¿Qué queremos decir cuando nos referimos al ["remitente" de un correo electrónico?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).

## <a name="an-overview-of-email-message-standards"></a>Información general sobre los estándares de mensajes de correo electrónico

Un mensaje de correo electrónico SMTP estándar está compuesto por el *sobre del mensaje* y el contenido del mensaje. El sobre del mensaje contiene información necesaria para transmitir y entregar el mensaje entre servidores SMTP. El contenido del mensaje contiene el cuerpo del mensaje y campos de encabezado de mensaje, que se denominan de forma colectiva *encabezado del mensaje*. El sobre del mensaje se describe en [RFC 5321](https://tools.ietf.org/html/rfc5321)y el encabezado del mensaje se describe en [RFC 5322](https://tools.ietf.org/html/rfc5322). Los destinatarios nunca ven el sobre del mensaje real porque lo genera el proceso de transmisión de mensajes y, en realidad, no forma parte del mensaje.

- La dirección (también conocida como dirección MAIL FROM, remitente P1 o remitente del sobre) es la dirección de correo electrónico que se usa en la transmisión `5321.MailFrom` SMTP del mensaje.  Esta dirección de correo electrónico normalmente se registra en el campo de encabezado **Return-Path** en el encabezado del mensaje (aunque es posible que el remitente designe una dirección de correo electrónico de **return-path** diferente).

- La dirección de correo electrónico (también conocida como la dirección De o el remitente P2) es la dirección de correo electrónico del campo de encabezado De y es la dirección de correo electrónico del remitente que se muestra en los clientes de `5322.From` correo electrónico.  La dirección De es el tema central de los requisitos de este artículo.

La dirección De se define en detalle en varias RFC (por ejemplo, RFC 5322 secciones 3.2.3, 3.4 y 3.4.1, y [RFC 3696](https://tools.ietf.org/html/rfc3696)). Hay muchas variaciones en el direccionamiento y lo que se considera válido o no válido. Para que sea sencillo, se recomienda el siguiente formato y definiciones:

`From: "Display Name" <EmailAddress>`

- **Nombre para mostrar:** una frase opcional que describe al propietario de la dirección de correo electrónico.

  - Se recomienda escribir siempre el nombre para mostrar entre comillas dobles (") como se muestra. Si el nombre para mostrar  contiene una coma, debe escribir la cadena entre comillas dobles según RFC 5322.
  - Si la dirección De incluye un nombre para mostrar, el valor EmailAddress debe ir entre corchetes angulares (< >) como se muestra.
  - Microsoft recomienda encarecidamente que inserte un espacio entre el nombre para mostrar y la dirección de correo electrónico.

- **EmailAddress**: una dirección de correo electrónico tiene el `local-part@domain` formato:

  - **elemento local:** cadena que identifica el buzón asociado con la dirección. Este valor es único dentro del dominio. A menudo, se usa el nombre de usuario o GUID del propietario del buzón.
  - **dominio:** el nombre de dominio completo (FQDN) del servidor de correo electrónico que hospeda el buzón identificado por la parte local de la dirección de correo electrónico.

  Estas son algunas consideraciones adicionales para el valor EmailAddress:

  - Solo una dirección de correo electrónico.
  - Se recomienda no separar los corchetes angulares con espacios.
  - No incluya texto adicional después de la dirección de correo electrónico.

## <a name="examples-of-valid-and-invalid-from-addresses"></a>Ejemplos de direcciones From válidas e no válidas

Las siguientes direcciones de correo electrónico De son válidas:

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` (No se recomienda porque hay espacios entre los corchetes angulares y la dirección de correo electrónico).

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (No se recomienda porque el nombre para mostrar no está entre comillas dobles).

Las siguientes direcciones de correo electrónico de Origen no son válidas:

- **Dirección no de** origen: algunos mensajes automatizados no incluyen una dirección de origen. En el pasado, cuando Microsoft 365 o Outlook.com recibían un mensaje sin una dirección De, el servicio agregaba la siguiente dirección De: predeterminada para que el mensaje se entregara:

  `From: <>`

  Ahora, los mensajes con una dirección De en blanco ya no se aceptan.

- `From: Microsoft 365 sender@contoso.com` (El nombre para mostrar está presente, pero la dirección de correo electrónico no está entre corchetes angulares).

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Texto después de la dirección de correo electrónico).

- `From: Sender, Example <sender.example@contoso.com>` (El nombre para mostrar contiene una coma, pero no está entre comillas dobles).

- `From: "Microsoft 365 <sender@contoso.com>"` (El valor entero está incorrectamente entre comillas dobles).

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (El nombre para mostrar está presente, pero la dirección de correo electrónico no está entre corchetes angulares).

- `From: Microsoft 365<sender@contoso.com>` (No hay espacio entre el nombre para mostrar y el corchete angular izquierdo).

- `From: "Microsoft 365"<sender@contoso.com>` (No hay espacio entre la comilla doble de cierre y el corchete angular izquierdo).

## <a name="suppress-auto-replies-to-your-custom-domain"></a>Suprimir las respuestas automáticas a su dominio personalizado

No puede usar el valor para `From: <>` suprimir las respuestas automáticas. En su lugar, debe configurar un registro MX nulo para su dominio personalizado. Las respuestas automáticas (y todas las respuestas) se suprimen de forma natural porque no hay ninguna dirección publicada a la que el servidor de respuesta pueda enviar mensajes.

- Elija un dominio de correo electrónico que no pueda recibir correo electrónico. Por ejemplo, si el dominio principal es contoso.com, puede elegir noreply.contoso.com.

- El registro MX nulo para este dominio consta de un único punto.

Por ejemplo:

```text
noreply.contoso.com IN MX .
```

Para obtener más información acerca de la configuración de registros MX, vea Crear registros DNS en cualquier proveedor de [hospedaje DNS para Microsoft 365.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)

Para obtener más información acerca de la publicación de un MX nulo, vea [RFC 7505](https://tools.ietf.org/html/rfc7505).

## <a name="override-from-address-enforcement"></a>Invalidar la aplicación de direcciones de origen

Para omitir los requisitos de dirección De para el correo electrónico entrante, puede usar la lista de direcciones IP permitidos (filtrado de conexiones) o reglas de flujo de correo (también conocidas como reglas de transporte) como se describe en Crear listas de remitentes seguros en [Microsoft 365](create-safe-sender-lists-in-office-365.md).

No puede invalidar los requisitos de dirección De para el correo electrónico saliente que envíe desde Microsoft 365. Además, Outlook.com no permitirá invalidaciones de ningún tipo, incluso a través de la compatibilidad.

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Otras formas de evitar y proteger contra los ciberdelincuencias en Microsoft 365

Para obtener más información sobre cómo puede reforzar su organización contra la suplantación de identidad, el correo no deseado, las infracciones de datos y otras amenazas, vea las 10 formas principales de proteger los planes de [Microsoft 365](../../admin/security-and-compliance/secure-your-business-data.md)para empresas.
