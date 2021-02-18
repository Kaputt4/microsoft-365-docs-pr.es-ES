---
title: Crear listas de remitentes seguros
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre las opciones disponibles y preferidas para permitir mensajes entrantes en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ddcd6240cfc80350920999f9fc1e8ea188834553
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289716"
---
# <a name="create-safe-sender-lists-in-eop"></a>Crear listas de remitentes seguros en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Si es un cliente de Microsoft 365 con buzones en Exchange Online o un cliente independiente de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP ofrece varias formas de garantizar que los usuarios recibirán correo electrónico de remitentes de confianza. Estas opciones incluyen reglas de flujo de correo de Exchange (también conocidas como reglas de transporte), remitentes seguros de Outlook, la lista de direcciones IP permitidas (filtrado de conexiones) y listas de remitentes permitidos o listas de dominios permitidos en directivas contra correo no deseado. Colectivamente, puede pensar en estas opciones como listas _de remitentes seguros._

Las listas de remitentes seguros disponibles se describen en la siguiente lista en orden de más recomendado a menos recomendado:

1. Reglas de flujo de correo
2. Remitentes seguros de Outlook
3. Lista de direcciones IP permitidos (filtrado de conexiones)
4. Listas de remitentes permitidos o listas de dominios permitidos (directivas contra correo no deseado)

Las reglas de flujo de correo permiten la mayor flexibilidad para garantizar que solo se permiten los mensajes correctos. Las listas de remitentes permitidos y dominios permitidos en las directivas contra correo no deseado no son tan seguras como la lista de direcciones IP permitidas, ya que el dominio de correo electrónico del remitente se suplanta fácilmente. Sin embargo, la lista de direcciones IP  permitidos también presenta un riesgo, ya que el correo electrónico de cualquier dominio que se envíe desde esa dirección IP omitirá el filtrado de correo no deseado.

> [!IMPORTANT]
>
> - Tenga cuidado de supervisar detenidamente *las excepciones* que realice en el filtrado de correo no deseado mediante listas de remitentes seguros.
>
> - Aunque puede usar listas de remitentes seguros para ayudar con falsos positivos (correo electrónico bueno marcado como mal), debe considerar el uso de listas de remitentes seguros como una solución temporal que debe evitarse si es posible. No se recomienda administrar falsos positivos mediante listas de remitentes seguros, ya que las excepciones al filtrado de correo no deseado pueden abrir la organización a la suplantación de identidad y a otros ataques. Si desea usar listas de remitentes seguros para administrar falsos positivos, debe estar atento y mantener el tema Informar de mensajes y archivos a [Microsoft](report-junk-email-messages-to-microsoft.md) a la vez.
>
> - Para permitir que un dominio envíe correo electrónico no autenticado (omitir la protección contra la suplantación de identidad) pero no omitir las comprobaciones contra correo no deseado y antimalware, puede agregarlo a la lista de remitentes seguros [AllowedToSpoof](walkthrough-spoof-intelligence-insight.md)
>
> - EOP y Outlook inspeccionan distintas propiedades del mensaje para determinar el remitente del mensaje. Para obtener más información, vea la sección [Consideraciones para el correo electrónico](#considerations-for-bulk-email) masivo más adelante en este artículo.

Por el contrario, también tiene varias opciones para bloquear el correo electrónico de orígenes específicos mediante listas _de remitentes bloqueados._ Para más información, consulte [Crear listas de remitentes bloqueados en EOP](create-block-sender-lists-in-office-365.md)

## <a name="recommended-use-mail-flow-rules"></a>(Recomendado) Usar reglas de flujo de correo

Las reglas de flujo de correo en Exchange Online y EOP independiente usan condiciones y excepciones para identificar mensajes y acciones para especificar qué se debe hacer con esos mensajes. Para obtener más información, vea [Reglas de flujo de correo (reglas de transporte) en Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).

En el siguiente ejemplo se supone que necesita correo electrónico de contoso.com para omitir el filtrado de correo no deseado. Para ello, configure las siguientes opciones:

1. **Condición:** **el dominio del** remitente \> **es** \> contoso.com.

2. Configure una de las siguientes opciones:

   - **Condición de regla de flujo de correo:** **un encabezado de** mensaje incluye cualquiera de estas palabras Nombre de encabezado : Valor de \>  \>  `Authentication-Results` \> **encabezado**: o `dmarc=pass` `dmarc=bestguesspass` .

     Esta condición comprueba el estado de autenticación de correo electrónico del dominio de correo electrónico de envío para asegurarse de que no se está suplantado el dominio de envío. Para obtener más información acerca de la autenticación de correo electrónico, [vea SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)y [DMARC](use-dmarc-to-validate-email.md).

   - **Lista de direcciones IP permitidos:** especifique la dirección IP de origen o el intervalo de direcciones en la directiva de filtro de conexión.

     Use esta configuración si el dominio de envío no usa la autenticación de correo electrónico. Sea lo más restrictivo posible cuando se trata de las direcciones IP de origen en la lista de direcciones IP permitidos. Se recomienda un intervalo de direcciones IP de /24 o menos (menos es mejor). No use intervalos de direcciones IP que pertenezcan a servicios de consumidor (por ejemplo, outlook.com) o infraestructuras compartidas.

   > [!IMPORTANT]
   >
   > - No configure nunca reglas de flujo de correo solo con *el* dominio del remitente como la condición para omitir el filtrado de correo no deseado. Si lo  hace, aumentará considerablemente la probabilidad de que los atacantes puedan suplantar el dominio remitente (o suplantar la dirección de correo electrónico completa), omitir todo el filtrado de correo no deseado y omitir las comprobaciones de autenticación del remitente para que el mensaje llegue a la Bandeja de entrada del destinatario.
   >
   > - No use dominios de su propiedad (también conocidos como dominios aceptados) o dominios populares (por ejemplo, microsoft.com) como condiciones en las reglas de flujo de correo. Si lo hace, se considera de alto riesgo porque crea oportunidades para que los atacantes envíen correo electrónico que, de lo contrario, se filtraría.
   >
   > - Si permite una dirección IP que está detrás de una puerta de enlace de traducción de direcciones de red (NAT), debe conocer los servidores que participan en el grupo nat para conocer el ámbito de la lista de direcciones IP permitidos. Las direcciones IP y los participantes nat pueden cambiar. Debe comprobar periódicamente las entradas de la lista de direcciones IP permitidos como parte de los procedimientos de mantenimiento estándar.

3. **Condiciones opcionales:**

   - **El remitente** \> **es interno/externo** \> **Fuera de la organización:** esta condición es implícita, pero está bien usarla para tener en cuenta los servidores de correo electrónico locales que podrían no estar configurados correctamente.

   - **El asunto o el cuerpo** \> **asunto o cuerpo incluye cualquiera de estas palabras** \> : si puede restringir aún más los mensajes por palabras clave o frases en la línea de asunto o en el cuerpo del mensaje, puede usar esas palabras \<keywords\> como condición.

4. **Acción:** configure ambas acciones en la regla:

   a. **Modificar las propiedades del mensaje** \> **establecer el nivel de confianza contra correo no deseado (SCL)** \> **Omitir el filtrado de correo no deseado.**

   b. **Modificar las propiedades del mensaje** \> **set a message header**: **Set the message header** to \<CustomHeaderName\> **the value** \<CustomHeaderValue\> .

      Por ejemplo, `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`. Si tiene más de un dominio en la regla, puede personalizar el texto del encabezado según corresponda.

      Cuando un mensaje omite el filtrado de correo no deseado debido a una regla de flujo de correo, el valor se marca en el encabezado `SFV:SKN` **X-Forefront-Antispam-Report.** Si el mensaje es de un origen que está en la lista de direcciones IP permitidos, también se `IPV:CAL` agrega el valor. Estos valores pueden ayudarle con la solución de problemas.

![Configuración de reglas de flujo de correo en el EAC para omitir el filtrado de correo no deseado.](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Usar remitentes seguros de Outlook

> [!CAUTION]
> Este método crea un alto riesgo de que los atacantes entreguen correctamente correo electrónico a la Bandeja de entrada que, de lo contrario, se filtraría; sin embargo, las listas de remitentes seguros o dominios seguros del usuario no impiden que se filtren mensajes de suplantación de identidad de confianza alta o malware.

En lugar de una configuración organizativa, los usuarios o administradores pueden agregar las direcciones de correo electrónico del remitente a la lista de remitentes seguros del buzón. Para obtener instrucciones, consulte [Configurar las opciones de correo no deseado en buzones de Exchange Online en Office 365.](configure-junk-email-settings-on-exo-mailboxes.md) Esto no es deseable en la mayoría de las situaciones, ya que los remitentes omitirán partes de la pila de filtrado. Aunque confíe en el remitente, el remitente aún puede verse comprometido y enviar contenido malintencionado. Es mejor que permita que nuestros filtros hagan lo necesario para comprobar cada mensaje y, a continuación, notificar los falsos positivos o negativos a [Microsoft](report-junk-email-messages-to-microsoft.md) si nuestros filtros no lo han hecho. Omitir la pila de filtrado también interfiere con [ZAP](zero-hour-auto-purge.md).

Cuando los mensajes omiten el filtrado de correo no deseado debido a la lista de remitentes seguros de un usuario, el campo de encabezado **X-Forefront-Antispam-Report** contendrá el valor , lo que indica que se omitió el filtrado de correo no deseado, suplantación de identidad y suplantación de `SFV:SFE` identidad.

## <a name="use-the-ip-allow-list"></a>Usar la lista de direcciones IP permitidos

Si no puede usar reglas de flujo de correo como se describió anteriormente, la siguiente mejor opción es agregar el servidor o servidores de correo electrónico de origen a la lista de direcciones IP permitidos en la directiva de filtro de conexión. Para obtener más información, vea [Configurar el filtrado de conexiones en EOP.](configure-the-connection-filter-policy.md)

**Notas**:

- Es importante que mantenga el número de direcciones IP permitidas al mínimo, así que evite usar intervalos de direcciones IP completos siempre que sea posible.

- No use intervalos de direcciones IP que pertenezcan a servicios de consumidor (por ejemplo, outlook.com) o infraestructuras compartidas.

- Revise periódicamente las entradas de la lista de direcciones IP permitidos y quite las entradas que ya no necesite.

> [!CAUTION]
> Sin comprobación adicional, como las reglas de flujo de correo, el correo electrónico procedente de orígenes de la lista de direcciones IP no deseados omite el filtrado de correo no deseado y las comprobaciones de autenticación de remitentes (SPF, DKIM, DMARC). Esto crea un alto riesgo de que los atacantes entreguen correctamente correo electrónico a la Bandeja de entrada que, de lo contrario, se filtraría; sin embargo, la lista de direcciones IP no impide que se filtren mensajes de suplantación de identidad de confianza alta o malware.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>Usar listas de remitentes permitidos o listas de dominios permitidos

La opción menos deseable es usar la lista de remitentes permitidos o la lista de dominios permitidos en las directivas contra correo no deseado. Debe evitar esta  opción si es posible porque los remitentes omiten toda la protección contra correo no deseado, suplantación de identidad y suplantación de identidad y autenticación de remitentes (SPF, DKIM, DMARC). Este método es más adecuado solo para las pruebas temporales. Encontrará los pasos detallados en el tema Configurar directivas contra correo no deseado [en EOP.](configure-your-spam-filter-policies.md)

El límite máximo para estas listas es de aproximadamente 1000 entradas; aunque solo podrá escribir 30 entradas en el portal. Debe usar PowerShell para agregar más de 30 entradas.

> [!CAUTION]
>
> - Este método crea un alto riesgo de que los atacantes entreguen correctamente correo electrónico a la Bandeja de entrada que, de lo contrario, se filtraría; sin embargo, los remitentes permitidos o las listas de dominios permitidos no impiden que se filtren los mensajes de suplantación de identidad de confianza alta o malware.
>
> - No use dominios de su propiedad (también conocidos como dominios aceptados) o dominios populares (por ejemplo, microsoft.com) en listas de dominios permitidos.

## <a name="considerations-for-bulk-email"></a>Consideraciones para el correo electrónico masivo

Un mensaje de correo electrónico SMTP estándar está compuesto por el *sobre del mensaje* y el contenido del mensaje. El sobre del mensaje contiene información necesaria para transmitir y entregar el mensaje entre servidores SMTP. El contenido del mensaje contiene el cuerpo del mensaje y campos de encabezado de mensaje, que se denominan de forma colectiva *encabezado del mensaje*. El sobre del mensaje se describe en RFC 5321 y el encabezado del mensaje se describe en RFC 5322. Los destinatarios nunca ven el sobre del mensaje real porque lo genera el proceso de transmisión de mensajes y, en realidad, no forma parte del mensaje.

- La dirección (también conocida como dirección MAIL FROM, remitente P1 o remitente del sobre) es la dirección de correo electrónico que se usa en la transmisión `5321.MailFrom` SMTP del mensaje.  Esta dirección de correo electrónico normalmente se registra en el campo de encabezado **Return-Path** en el encabezado del mensaje (aunque es posible que el remitente designe una dirección de correo electrónico de **return-path** diferente). Si el mensaje no se puede entregar, es el destinatario del informe de no entrega (también conocido como NDR o mensaje de de rebote).

- La dirección de correo electrónico (también conocida como la dirección De o el remitente P2) es la dirección de correo electrónico del campo de encabezado De y es la dirección de correo electrónico del remitente que se muestra en los clientes de `5322.From` correo electrónico.  

Con frecuencia, las direcciones y son las mismas (comunicación de persona `5321.MailFrom` `5322.From` a persona). Sin embargo, cuando el correo electrónico se envía en nombre de otra persona, las direcciones pueden ser diferentes. Esto sucede con más frecuencia para los mensajes de correo electrónico masivo.

Por ejemplo, supongamos que Blue Yonder Airlines ha contratado a Viajes Margie para enviar su publicidad por correo electrónico. El mensaje que recibe en la Bandeja de entrada tiene las siguientes propiedades:

- La `5321.MailFrom` dirección es blueyonder.airlines@margiestravel.com.

- La `5322.From` dirección es blueyonder@news.blueyonderairlines.com, que es lo que verá en Outlook.

Las listas de remitentes seguros y las listas de dominios seguros de las directivas contra correo no deseado de EOP inspeccionan solo las direcciones, lo que es similar a los remitentes seguros de `5322.From` Outlook que usan la `5322.From` dirección.

Para evitar que este mensaje se filtre, puede realizar los siguientes pasos:

- Agregue blueyonder@news.blueyonderairlines.com (la `5322.From` dirección) como remitente seguro de Outlook.

- [Use una regla de flujo de](#recommended-use-mail-flow-rules) correo con una condición que busca mensajes de blueyonder@news.blueyonderairlines.com (la `5322.From` dirección, blueyonder.airlines@margiestravel.com (el `5321.MailFrom` ) o ambos.

Para obtener más información, vea [Crear listas de remitentes seguros en EOP.](create-safe-sender-lists-in-office-365.md)
