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
ms.collection: m365-security
ms.localizationpriority: medium
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre las opciones disponibles y preferidas para permitir mensajes entrantes en Exchange Online Protection (EOP).
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 65520a890be1e7c8e529496b7fb78005139bde9d
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68645195"
---
# <a name="create-safe-sender-lists-in-eop"></a>Creación de listas de remitentes seguros en EOP

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Si es un cliente de Microsoft 365 con buzones en Exchange Online o un cliente independiente de Exchange Online Protection (EOP) sin Exchange Online buzones, EOP ofrece varias formas de garantizar que los usuarios recibirán correo electrónico de remitentes de confianza. Colectivamente, puede considerar estas opciones como _listas de remitentes seguros_.

Las listas de remitentes seguros disponibles se describen en la lista siguiente en orden de la más recomendada a la menos recomendada:

1. Permitir entradas para dominios y direcciones de correo electrónico (incluidos los remitentes suplantados) en la lista de permitidos o bloqueados de inquilinos.
2. Reglas de flujo de correo (también conocidas como reglas de transporte).
3. Remitentes seguros de Outlook (la lista Remitentes seguros que se almacena en cada buzón).
4. Lista de direcciones IP permitidas (filtrado de conexiones)
5. Listas de remitentes permitidos o listas de dominios permitidos (directivas contra correo no deseado)

El resto de este artículo contiene detalles sobre cada método.

> [!IMPORTANT]
> Los mensajes que se identifican como malware o suplantación de identidad de alta confianza siempre se ponen en cuarentena, independientemente de la opción de lista de remitentes seguros que use. Para obtener más información, consulte [Protección de forma predeterminada en Office 365](secure-by-default.md).
>
> Tenga cuidado de supervisar estrechamente _las_ excepciones que realice en el filtrado de correo no deseado mediante listas seguras de remitentes.
>
> Envíe siempre mensajes en las listas de remitentes seguros a Microsoft para su análisis. Para obtener instrucciones, consulte [Informe de un buen correo electrónico a Microsoft](admin-submission.md#report-good-email-to-microsoft). Si se determina que los mensajes o orígenes de mensajes son benignos, Microsoft puede permitir automáticamente los mensajes y no tendrá que mantener manualmente la entrada en listas de remitentes seguros.
>
> En lugar de permitir el correo electrónico, también tiene varias opciones para bloquear el correo electrónico de orígenes específicos mediante _listas de remitentes bloqueados_. Para más información, consulte [Crear listas de remitentes bloqueados en EOP](create-block-sender-lists-in-office-365.md).

## <a name="use-allow-entries-in-the-tenant-allowblock-list"></a>Uso de entradas allow en la lista de permitidos o bloqueados de inquilinos

Nuestra opción recomendada número uno para permitir el correo de remitentes o dominios es la lista de permitidos o bloqueados de inquilinos. Para obtener instrucciones, consulte [Permitir o bloquear el correo electrónico mediante la Lista de permitidos o bloqueados de inquilinos](allow-block-email-spoof.md).

Solo si no puede usar la lista de permitidos o bloqueados de inquilinos por algún motivo, considere la posibilidad de usar un método diferente para permitir remitentes.

## <a name="use-mail-flow-rules"></a>Uso de reglas de flujo de correo

> [!NOTE]
> No puede usar encabezados de mensaje ni reglas de flujo de correo para designar un remitente interno como remitente seguro. Los procedimientos de esta sección solo funcionan para remitentes externos.

Las reglas de flujo de correo en Exchange Online e independiente EOP usan condiciones y excepciones para identificar mensajes, y acciones para especificar lo que se debe hacer en esos mensajes. Para obtener más información, vea [Reglas de flujo de correo (reglas de transporte) en Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).

En el ejemplo siguiente se supone que necesita correo electrónico de contoso.com para omitir el filtrado de correo no deseado. Para ello, configure los siguientes valores:

1. **Condición**: **el dominio del remitente** \> **está** \> contoso.com.

2. Configure cualquiera de las siguientes opciones:

   - **Condición de regla de flujo** de **correo: un encabezado** \> **de mensaje incluye cualquiera de estas palabras** \> Nombre de **encabezado**: `Authentication-Results` \> **Valor de encabezado**: `dmarc=pass` o `dmarc=bestguesspass`.

     Esta condición comprueba el estado de autenticación de correo electrónico del dominio de correo electrónico de envío para asegurarse de que el dominio de envío no se está suplantando. Para obtener más información sobre la autenticación por correo electrónico, consulte [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md) y [DMARC](use-dmarc-to-validate-email.md).

   - **Lista de direcciones IP permitidas**: especifique la dirección IP de origen o el intervalo de direcciones en la directiva de filtro de conexión. Para obtener instrucciones, consulte [Configuración del filtrado de conexiones](configure-the-connection-filter-policy.md).

     Use esta configuración si el dominio de envío no usa la autenticación por correo electrónico. Sea lo más restrictivo posible cuando se trata de las direcciones IP de origen en la lista de direcciones IP permitidas. Se recomienda un intervalo de direcciones IP de /24 o menos (menos es mejor). No use intervalos de direcciones IP que pertenezcan a servicios de consumidor (por ejemplo, outlook.com) ni infraestructuras compartidas.

   > [!IMPORTANT]
   >
   > - Nunca configure reglas de flujo de correo con _solo_ el dominio remitente como condición para omitir el filtrado de correo no deseado. Si lo hace, aumentará _significativamente_ la probabilidad de que los atacantes puedan suplantar el dominio de envío (o suplantar la dirección de correo electrónico completa), omitir todo el filtrado de correo no deseado y omitir las comprobaciones de autenticación del remitente para que el mensaje llegue a la Bandeja de entrada del destinatario.
   >
   > - No use dominios de su propiedad (también conocidos como dominios aceptados) ni dominios populares (por ejemplo, microsoft.com) como condiciones en las reglas de flujo de correo. Esto se considera de alto riesgo porque crea oportunidades para que los atacantes envíen correo electrónico que, de lo contrario, se filtraría.
   >
   > - Si permite una dirección IP que está detrás de una puerta de enlace de traducción de direcciones de red (NAT), debe conocer los servidores que participan en el grupo nat para conocer el ámbito de la lista de direcciones IP permitidas. Las direcciones IP y los participantes de NAT pueden cambiar. Debe comprobar periódicamente las entradas de lista de direcciones IP permitidas como parte de los procedimientos de mantenimiento estándar.

3. **Condiciones opcionales**:

   - **El remitente** \> **es interno/externo** \> **Fuera de la organización**: esta condición es implícita, pero está bien usarla para tener en cuenta los servidores de correo electrónico locales que podrían no estar configurados correctamente.
   - **El asunto o el cuerpo** \> **asunto o cuerpo incluye cualquiera de estas palabras** \> \<keywords\>: si puede restringir aún más los mensajes por palabras clave o frases en la línea del asunto o el cuerpo del mensaje, puede usar esas palabras como condición.

4. **Acción**: configure ambas acciones en la regla:

   1. **Modificación de las propiedades** \> del mensaje **establecer el nivel de confianza de correo no deseado (SCL)** \> **Omita el filtrado de correo no deseado**.
   2. **Modificación de las propiedades** \> del mensaje **establecer un encabezado de mensaje**: **establezca el encabezado** \<CustomHeaderName\> del mensaje **en el valor** \<CustomHeaderValue\>.

      Por ejemplo, `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`. Si tiene más de un dominio en la regla, puede personalizar el texto del encabezado según corresponda.

      Cuando un mensaje omite el filtrado de correo no deseado debido a una regla de flujo de correo, el valor `SFV:SKN` se marca en el encabezado **X-Forefront-Antispam-Report** . Si el mensaje procede de un origen que se encuentra en la lista de direcciones IP permitidas, también se agrega el valor `IPV:CAL` . Estos valores pueden ayudarle a solucionar problemas.

      :::image type="content" source="../../media/1-AllowList-SkipFilteringFromContoso.png" alt-text="La configuración de la regla de flujo de correo en el EAC para omitir el filtrado de correo no deseado" lightbox="../../media/1-AllowList-SkipFilteringFromContoso.png":::

## <a name="use-outlook-safe-senders"></a>Uso de remitentes seguros de Outlook

> [!CAUTION]
> Este método crea un alto riesgo de que los atacantes entreguen correctamente el correo electrónico a la Bandeja de entrada que, de lo contrario, se filtraría; sin embargo, si se determina que un mensaje de una entrada de las listas de remitentes seguros o dominios seguros del usuario es malware o phishing de alta confianza, el mensaje se filtrará.

En lugar de una configuración organizativa, los usuarios o administradores pueden agregar las direcciones de correo electrónico del remitente a la lista Remitentes seguros del buzón. Para obtener instrucciones, consulte [Configuración del correo electrónico no deseado en Exchange Online buzones de Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

Este método no es deseable en la mayoría de las situaciones, ya que los remitentes omitirán partes de la pila de filtrado. Aunque confía en el remitente, el remitente puede seguir en peligro y enviar contenido malintencionado. Debe permitir que nuestros filtros comprueben cada mensaje y [, a continuación, informen de los falsos positivos o negativos a Microsoft](report-junk-email-messages-to-microsoft.md) si se ha producido un error. La omisión de la pila de filtrado también interfiere con la [purga automática de cero horas (ZAP).](zero-hour-auto-purge.md)

Por diseño y por mayor seguridad de Exchange Online buzones, solo se reconoce la configuración de correo no deseado para remitentes seguros, remitentes bloqueados y dominios bloqueados. Se omite la configuración de la lista de correo electrónico seguro.

**Nota**: En Exchange Online, las entradas de dominio de la lista Remitentes seguros de Outlook o el parámetro TrustedSendersAndDomains no se reconocen, por lo que solo se usan direcciones de correo electrónico.

Cuando los mensajes omiten el filtrado de correo no deseado debido a la lista de remitentes seguros de un usuario, el campo de encabezado **X-Forefront-Antispam-Report** contendrá el valor `SFV:SFE`, que indica que se omitió el filtrado de correo no deseado, suplantación de identidad y suplantación de identidad (phishing).

## <a name="use-the-ip-allow-list"></a>Uso de la lista de direcciones IP permitidas

> [!CAUTION]
> Sin comprobación adicional, como reglas de flujo de correo, el correo electrónico de los orígenes de la lista de direcciones IP permitidas omite las comprobaciones de filtrado de correo no deseado y autenticación del remitente (SPF, DKIM, DMARC). Este resultado crea un alto riesgo de que los atacantes entreguen correctamente el correo electrónico a la Bandeja de entrada que, de lo contrario, se filtraría; sin embargo, si se determina que un mensaje de una entrada de la lista de direcciones IP permitidas es malware o phishing de alta confianza, se filtrará el mensaje.

La siguiente mejor opción es agregar el servidor de correo electrónico de origen o los servidores a la lista de direcciones IP permitidas en la directiva de filtro de conexión. Para obtener más información, vea [Configurar el filtrado de conexiones en EOP](configure-the-connection-filter-policy.md).

**Notas**:

- Es importante que mantenga el número de direcciones IP permitidas al mínimo, por lo que evite usar intervalos de direcciones IP completos siempre que sea posible.
- No use intervalos de direcciones IP que pertenezcan a servicios de consumidor (por ejemplo, outlook.com) ni infraestructuras compartidas.
- Revise periódicamente las entradas de la lista de direcciones IP permitidas y quite las entradas que ya no necesite.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>Uso de listas de remitentes permitidas o listas de dominio permitidas

> [!CAUTION]
>
> Este método crea un alto riesgo de que los atacantes entreguen correctamente el correo electrónico a la Bandeja de entrada que, de lo contrario, se filtraría; sin embargo, si se determina que un mensaje de una entrada en las listas de remitentes permitidos o dominios permitidos es malware o phishing de alta confianza, el mensaje se filtrará.
>
> No use dominios de su propiedad (también conocidos como dominios aceptados) ni dominios populares (por ejemplo, microsoft.com) en listas de dominios permitidos.

La opción menos deseable es usar la lista de remitentes permitidos o la lista de dominios permitidos en las directivas contra correo no deseado. Debe evitar esta opción _si es posible_ porque los remitentes omiten todo el correo no deseado, la suplantación de identidad ( protección contra suplantación de identidad (excepto la suplantación de identidad de alta confianza) y la autenticación del remitente (SPF, DKIM, DMARC). Este método es más adecuado solo para las pruebas temporales. Los pasos detallados se pueden encontrar en [el tema Configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md) .

El límite máximo para estas listas es de aproximadamente 1000 entradas; aunque solo podrá escribir 30 entradas en el portal. Debe usar PowerShell para agregar más de 30 entradas.

## <a name="considerations-for-bulk-email"></a>Consideraciones para el correo electrónico masivo

Un mensaje de correo electrónico SMTP estándar está compuesto por el _sobre del mensaje_ y el contenido del mensaje. El sobre del mensaje contiene información necesaria para transmitir y entregar el mensaje entre servidores SMTP. El contenido del mensaje contiene el cuerpo del mensaje y campos de encabezado de mensaje, que se denominan de forma colectiva _encabezado del mensaje_. El sobre del mensaje se describe en RFC 5321 y el encabezado del mensaje se describe en RFC 5322. Los destinatarios nunca ven el sobre del mensaje real porque lo genera el proceso de transmisión de mensajes y en realidad no forma parte del mensaje.

- La `5321.MailFrom` dirección (también conocida como dirección **MAIL FROM** , remitente P1 o remitente de sobre) es la dirección de correo electrónico que se usa en la transmisión SMTP del mensaje. Esta dirección de correo electrónico se registra normalmente en el campo de encabezado **Return-Path** del encabezado del mensaje (aunque es posible que el remitente designe una dirección de correo electrónico **return-path** diferente). Si el mensaje no se puede entregar, es el destinatario del informe de no entrega (también conocido como NDR o mensaje de devolución).
- `5322.From` (también conocido como remitente **De** dirección o P2) es la dirección de correo electrónico en el campo **De** encabezado y es la dirección de correo electrónico del remitente que se muestra en los clientes de correo electrónico.

Con frecuencia, las `5321.MailFrom` direcciones y `5322.From` son las mismas (comunicación de persona a persona). Sin embargo, cuando se envía correo electrónico en nombre de otra persona, las direcciones pueden ser diferentes. Esto sucede con mayor frecuencia para los mensajes de correo electrónico masivos.

Por ejemplo, supongamos que Blue Yonder Airlines ha contratado a Margie's Travel para enviar mensajes de correo electrónico publicitarios. El mensaje que recibe en la Bandeja de entrada tiene las siguientes propiedades:

- La `5321.MailFrom` dirección es blueyonder.airlines@margiestravel.com.
- La `5322.From` dirección es blueyonder@news.blueyonderairlines.com, que es lo que verá en Outlook.

Las listas de remitentes seguros y las listas de dominios seguros en las directivas contra correo no deseado en EOP inspeccionan solo las `5322.From` direcciones. Este comportamiento es similar a los remitentes seguros de Outlook que usan la `5322.From` dirección.

Para evitar que se filtre este mensaje, puede realizar los pasos siguientes:

- Agregue blueyonder@news.blueyonderairlines.com (la `5322.From` dirección) como remitente seguro de Outlook.
- [Use una regla de flujo de correo](#use-mail-flow-rules) con una condición que busque mensajes de blueyonder@news.blueyonderairlines.com (la `5322.From` dirección), blueyonder.airlines@margiestravel.com (la `5321.MailFrom` dirección) o ambos.
