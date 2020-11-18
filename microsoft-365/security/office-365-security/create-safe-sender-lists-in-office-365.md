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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre las opciones preferidas y disponibles para permitir los mensajes entrantes en Exchange Online Protection (EOP).
ms.openlocfilehash: 6d862f0ed6d6bbea56cb2bb79fee69a044e4fede
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130798"
---
# <a name="create-safe-sender-lists-in-eop"></a>Crear listas de remitentes seguros en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Si es un cliente de Microsoft 365 con buzones en Exchange online o un cliente independiente de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP ofrece varias formas de garantizar que los usuarios recibirán correo electrónico de remitentes de confianza. Estas opciones incluyen reglas de flujo de correo de Exchange (también conocidas como reglas de transporte), remitentes seguros de Outlook, la lista de direcciones IP permitidas (filtrado de conexiones) y listas de remitentes permitidos o listas de dominios permitidos en las directivas contra correo no deseado. De forma colectiva, puede considerar estas opciones como _listas de remitentes seguros_.

Las listas de remitentes seguros disponibles se describen en la siguiente lista, en orden de más recomendada a mínima recomendada:

1. Reglas de flujo de correo
2. Remitentes seguros de Outlook
3. Lista de direcciones IP permitidas (filtrado de la conexión)
4. Listas de remitentes permitidos o listas de dominios permitidos (directivas contra correo no deseado)

Las reglas de flujo de correo permiten la máxima flexibilidad para asegurarse de que solo se permiten los mensajes correctos. Los remitentes permitidos y las listas de dominios permitidos en las directivas contra correo no deseado no son tan seguros como la lista de direcciones IP permitidas, ya que el dominio de correo electrónico del remitente se falsifica fácilmente. Pero la lista de direcciones IP permitidas también presenta un riesgo, ya que el correo de _cualquier_ dominio que se envíe desde esa dirección IP omitirá el filtrado de correo no deseado.

> [!IMPORTANT]
>
> - Tenga cuidado al supervisar de cerca *las* excepciones que se produzcan en el filtrado de correo no deseado mediante listas de remitentes seguros.
>
> - Aunque puede usar listas de remitentes seguros para ayudar con falsos positivos (correo electrónico bueno marcado como correo no deseado), debe considerar el uso de listas de remitentes seguros como una solución temporal que debería evitarse si es posible. No se recomienda administrar los falsos positivos mediante listas de remitentes seguros, ya que las excepciones al filtrado de correo no deseado pueden abrir la organización a través de suplantación de identidad y otros ataques. Si insiste en usar listas de remitentes seguros para administrar falsos positivos, debe estar atento y mantener los [mensajes y archivos del informe](report-junk-email-messages-to-microsoft.md) de temas de Microsoft en la lista.
>
> - Para permitir a un dominio enviar correo electrónico no autenticado (evitar la protección contra la suplantación de identidad) pero no omitir las comprobaciones contra correo no deseado y antimalware, puede agregarlo a la [lista de remitentes seguros de AllowedToSpoof](walkthrough-spoof-intelligence-insight.md)
>
> - EOP y Outlook inspeccionar distintas propiedades del mensaje para determinar el remitente del mensaje. Para obtener más información, vea la sección [consideraciones para el correo electrónico masivo](#considerations-for-bulk-email) más adelante en este tema.

Por el contrario, también tiene varias opciones para bloquear el correo electrónico de fuentes específicas usando _listas de remitentes bloqueados_. Para más información, consulte [Crear listas de remitentes bloqueados en EOP](create-block-sender-lists-in-office-365.md)

## <a name="recommended-use-mail-flow-rules"></a>Recomenda Usar reglas de flujo de correo

Las reglas de flujo de correo de Exchange Online y EOP independiente usan condiciones y excepciones para identificar mensajes, así como acciones para especificar lo que se debe hacer a esos mensajes. Para obtener más información, vea [reglas de flujo de correo (reglas de transporte) en Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).

En el siguiente ejemplo se supone que necesita correo electrónico de contoso.com para omitir el filtrado de correo no deseado. Para ello, configure las siguientes opciones:

1. **Condición**: **el dominio del remitente** \> **es** \> contoso.com.

2. Configure cualquiera de las siguientes opciones:

   - **Condición de regla de flujo de correo**: **un encabezado** \> **de mensaje incluye cualquiera de estas palabras** \> **encabezado nombre**: `Authentication-Results` \> **valor de encabezado**: `dmarc=pass` o `dmarc=bestguesspass` .

     Esta condición comprueba el estado de autenticación de correo electrónico del dominio de envío de correo electrónico para asegurarse de que el dominio de envío no se está falsificando. Para obtener más información acerca de la autenticación de correo electrónico, consulte [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)y [DMARC](use-dmarc-to-validate-email.md).

   - Lista de direcciones IP **permitidas**: especifique la dirección IP o el intervalo de direcciones de origen en la Directiva de filtro de conexión.
  
     Use esta configuración si el dominio de envío no usa la autenticación de correo electrónico. Sea lo más restrictivo posible cuando se trata de las direcciones IP de origen en la lista de direcciones IP permitidas. Se recomienda un intervalo de direcciones IP de/24 o menos (menos es mejor). No use intervalos de direcciones IP que pertenezcan a servicios de consumidor (por ejemplo, outlook.com) o infraestructuras compartidas.

   > [!IMPORTANT]
   >
   > - No configure nunca reglas de flujo de correo *solo* con el dominio del remitente como la condición para omitir el filtrado de correo no deseado. Al hacerlo, aumentará *significativamente* la probabilidad de que los intrusos puedan suplantar el dominio remitente (o suplantar la dirección de correo electrónico completa), omitir el filtrado de correo no deseado y omitir las comprobaciones de autenticación de remitente para que el mensaje llegue a la bandeja de entrada del destinatario.
   >
   > - No use dominios de su propiedad (también conocidos como dominios aceptados) o dominios populares (por ejemplo, microsoft.com) como condiciones en las reglas de flujo de correo. Al hacerlo, se considera un riesgo alto porque crea oportunidades para que los atacantes envíen correo electrónico que, de lo contrario, se filtraría.
   >
   > - Si permite una dirección IP que está detrás de una puerta de enlace de traducción de direcciones de red (NAT), debe conocer los servidores que participan en el grupo de NAT para conocer el ámbito de la lista de direcciones IP permitidas. Las direcciones IP y los participantes de NAT pueden cambiar. Debe comprobar periódicamente sus entradas de la lista de direcciones IP permitidas como parte de los procedimientos de mantenimiento estándar.

3. **Condiciones opcionales**:

   - **El remitente** \> **es interno/externo** \> **Fuera de la organización**: esta condición es implícita, pero es correcto usarla para tener en cuenta los servidores de correo electrónico locales que podrían no estar configurados correctamente.

   - **El asunto o el cuerpo** \> el **asunto o el cuerpo incluye cualquiera de estas palabras** \> \<keywords\>: Si puede restringir aún más los mensajes por palabras clave o frases en la línea de asunto o en el cuerpo del mensaje, puede usar esas palabras como condición.

4. **Acción**: configure ambas acciones en la regla:

   a. **Modificación de las propiedades** \> del mensaje **establecer el nivel de confianza contra correo no deseado (SCL)** \> **Omitir el filtrado de correo no deseado**.

   b. **Modificación de las propiedades** \> del mensaje **establecer un encabezado de mensaje**: **establezca el encabezado del mensaje** \<CustomHeaderName\> **en el valor** \<CustomHeaderValue\> .

      Por ejemplo, `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`. Si tiene más de un dominio en la regla, puede personalizar el texto del encabezado según corresponda.

      Cuando un mensaje omite el filtrado de correo no deseado debido a una regla de flujo de correo, el valor del valor `SFV:SKN` se marca en el encabezado **X-Forefront-antispam-Report** . Si el mensaje procede de un origen que está en la lista de direcciones IP permitidas, `IPV:CAL` también se agrega el valor. Estos valores pueden ayudarle con la solución de problemas.

![Configuración de la regla de flujo de correo en el EAC para omitir el filtrado de correo no deseado.](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Usar remitentes seguros de Outlook

En lugar de una configuración de la organización, los usuarios o los administradores pueden agregar las direcciones de correo electrónico del remitente a la lista de remitentes seguros en el buzón. Para obtener instrucciones, consulte [configurar la configuración del correo electrónico no deseado en buzones de Exchange online en Office 365](configure-junk-email-settings-on-exo-mailboxes.md). Esto no es aconsejable en la mayoría de las situaciones, ya que los remitentes omitirán las partes de la pila de filtrado. Aunque confíe en el remitente, el remitente todavía puede estar en peligro y enviar contenido malintencionado. Es mejor dejar que los filtros hagan lo que se necesita para comprobar todos los mensajes y, a continuación, [informar del falso positivo/negativo a Microsoft](report-junk-email-messages-to-microsoft.md) si nuestros filtros no se han realizado correctamente. Omitir la pila de filtrado también interfiere con [Zap](zero-hour-auto-purge.md).

Cuando los mensajes omiten el filtrado de correo no deseado debido a la lista de remitentes seguros de un usuario, el campo de encabezado **X-Forefront-antispam-Report** contendrá el valor `SFV:SFE` , lo que indica que se omitirán los filtros de correo no deseado, suplantación de identidad (phishing).

## <a name="use-the-ip-allow-list"></a>Usar la lista de direcciones IP permitidas

Si no puede usar reglas de flujo de correo como se ha descrito anteriormente, la siguiente mejor opción es agregar el servidor o servidores de correo electrónico de origen a la lista de direcciones IP permitidas en la Directiva de filtro de conexión. Para obtener más información, vea [configurar el filtrado de conexiones en EOP](configure-the-connection-filter-policy.md).

**Notas**:

- Es importante que mantenga el número mínimo de direcciones IP permitidas, por lo que debe evitar usar intervalos de direcciones IP completos siempre que sea posible.

- No use intervalos de direcciones IP que pertenezcan a servicios de consumidor (por ejemplo, outlook.com) o infraestructuras compartidas.

- Revise periódicamente las entradas de la lista de direcciones IP permitidas y quite las entradas que ya no necesite.

> [!CAUTION]
> Sin una comprobación adicional, como las reglas de flujo de correo, el correo electrónico de las fuentes de la lista de direcciones IP permitidas omite el filtrado de correo no deseado y las comprobaciones de autenticación de remitente (SPF, DKIM y DMARC). Esto crea un riesgo alto de que los atacantes entreguen correctamente el correo electrónico a la bandeja de entrada que, de lo contrario, se filtraría.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>Usar listas de remitentes permitidos o listas de dominios permitidas

La opción menos deseable es usar la lista de remitentes permitidos o la lista de dominios permitidos en las directivas contra correo no deseado. Debe evitar esta opción *si es posible porque los* remitentes omiten todo el correo no deseado, la suplantación de identidad y la protección contra phishing y la autenticación de remitente (SPF, DKIM, DMARC). Este método es más adecuado solo para las pruebas temporales. Puede encontrar los pasos detallados en [configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md) .

El límite máximo de estas listas es de aproximadamente 1000 entradas; Aunque solo podrá especificar 30 entradas en el portal. Debe usar PowerShell para agregar más de 30 entradas.

> [!CAUTION]
>
> - Este método crea un riesgo alto de que los atacantes entreguen correo electrónico a la bandeja de entrada que, de lo contrario, se filtraría.
>
> - No use dominios de su propiedad (también conocidos como dominios aceptados) o dominios populares (por ejemplo, microsoft.com) en listas de dominios permitidos.

## <a name="considerations-for-bulk-email"></a>Consideraciones para el correo electrónico masivo

Un mensaje de correo electrónico SMTP estándar está compuesto por el *sobre del mensaje* y el contenido del mensaje. El sobre del mensaje contiene información necesaria para transmitir y entregar el mensaje entre servidores SMTP. El contenido del mensaje contiene el cuerpo del mensaje y campos de encabezado de mensaje, que se denominan de forma colectiva *encabezado del mensaje*. El sobre del mensaje se describe en RFC 5321 y el encabezado del mensaje se describe en RFC 5322. Los destinatarios nunca ven el sobre del mensaje real porque lo genera el proceso de transmisión del mensaje y, en realidad, no forma parte del mensaje.

- La `5321.MailFrom` dirección (también conocida como **correo de** la dirección de, P1 Sender o Envelope Sender) es la dirección de correo electrónico que se usa en la transmisión SMTP del mensaje. Esta dirección de correo electrónico suele registrarse en el campo de encabezado **Return-Path** del encabezado del mensaje (aunque es posible que el remitente designe otra dirección **de correo electrónico de ruta de regreso** ). Si el mensaje no se puede entregar, es el destinatario del informe de no entrega (también conocido como mensaje NDR o de devolución).

- El `5322.From` (también conocido como dirección **de de** o remitente P2) es la dirección de correo electrónico que aparece en el campo **de encabezado de** y es la dirección de correo electrónico del remitente que se muestra en los clientes de correo electrónico.

Con frecuencia, `5321.MailFrom` las `5322.From` direcciones y son las mismas (comunicación de persona a persona). Sin embargo, cuando se envía un correo electrónico en nombre de otra persona, las direcciones pueden ser diferentes. Esto ocurre con más frecuencia para los mensajes de correo masivo.

Por ejemplo, supongamos que Blue Yonder Airlines ha contratado el viaje de Ana para enviar su publicidad por correo electrónico. El mensaje que recibe en la bandeja de entrada tiene las siguientes propiedades:

- La `5321.MailFrom` dirección es blueyonder.Airlines@margiestravel.com.

- La `5322.From` dirección es blueyonder@news.blueyonderairlines.com, que es lo que verá en Outlook.

Las listas de remitentes seguros y las listas de dominios seguros en las directivas contra correo no deseado en EOP inspeccionan solo las `5322.From` direcciones, es similar a los remitentes seguros de Outlook que usan la `5322.From` dirección.

Para evitar que se filtre este mensaje, puede realizar los siguientes pasos:

- Agregue blueyonder@news.blueyonderairlines.com (la `5322.From` dirección) como un remitente seguro de Outlook.

- [Use una regla de flujo de correo](#recommended-use-mail-flow-rules) con una condición que busque mensajes de blueyonder@news.blueyonderairlines.com (la `5322.From` dirección, blueyonder.Airlines@margiestravel.com (el `5321.MailFrom` ) o ambos.

Para obtener más información, vea [crear listas de remitentes seguros en EOP](create-safe-sender-lists-in-office-365.md).
