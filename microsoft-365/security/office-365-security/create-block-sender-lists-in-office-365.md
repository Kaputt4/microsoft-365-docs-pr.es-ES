---
title: Crear listas de remitentes bloqueados
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
description: Los administradores pueden obtener información sobre las opciones disponibles y preferidas para bloquear los mensajes entrantes en Exchange Online Protection (EOP).
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 0f7538efa9eeaa5cbca2287aab3379bfb614cc3a
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68642379"
---
# <a name="create-blocked-sender-lists-in-eop"></a>Creación de listas de remitentes bloqueados en EOP

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con buzones de Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, EOP ofrece varias formas de bloquear el correo electrónico de remitentes no deseados. Colectivamente, puede considerar estas opciones como listas de _remitentes bloqueados_.

Las listas de remitentes bloqueados disponibles se describen en la lista siguiente en orden de la más recomendada a la menos recomendada:

1. Bloquee las entradas de dominios y direcciones de correo electrónico (incluidos los remitentes suplantados) en la lista de permitidos o bloqueados de inquilinos.
2. Remitentes bloqueados de Outlook (la lista Remitentes bloqueados que se almacena en cada buzón).
3. Listas de remitentes bloqueados o listas de dominios bloqueados (directivas contra correo no deseado).
4. Reglas de flujo de correo (también conocidas como reglas de transporte).
5. Lista de direcciones IP bloqueadas (filtrado de conexiones).

El resto de este artículo contiene detalles sobre cada método.

> [!NOTE]
> Envíe siempre mensajes en las listas de remitentes bloqueados a Microsoft para su análisis. Para obtener instrucciones, consulte [Informe de correo electrónico cuestionable a Microsoft](admin-submission.md#report-questionable-email-to-microsoft). Si se determina que los mensajes o orígenes de mensajes son dañinos, Microsoft puede bloquear automáticamente los mensajes y no tendrá que mantener manualmente la entrada en listas de remitentes bloqueados.
>
> En lugar de bloquear el correo electrónico, también tiene varias opciones para permitir el correo electrónico de orígenes específicos mediante _listas de remitentes seguros_. Para obtener más información, consulte [Crear listas de remitentes seguros](create-safe-sender-lists-in-office-365.md).

## <a name="email-message-basics"></a>Email conceptos básicos del mensaje

Un mensaje de correo electrónico SMTP estándar está compuesto por el _sobre del mensaje_ y el contenido del mensaje. El sobre del mensaje contiene información necesaria para transmitir y entregar el mensaje entre servidores SMTP. El contenido del mensaje contiene el cuerpo del mensaje y campos de encabezado de mensaje, que se denominan de forma colectiva _encabezado del mensaje_. El sobre del mensaje se describe en RFC 5321 y el encabezado del mensaje se describe en RFC 5322. Los destinatarios nunca ven el sobre del mensaje real porque lo genera el proceso de transmisión de mensajes y en realidad no forma parte del mensaje.

- La `5321.MailFrom` dirección (también conocida como dirección **MAIL FROM** , remitente P1 o remitente de sobre) es la dirección de correo electrónico que se usa en la transmisión SMTP del mensaje. Esta dirección de correo electrónico se registra normalmente en el campo de encabezado **Return-Path** del encabezado del mensaje (aunque es posible que el remitente designe una dirección de correo electrónico **return-path** diferente). Si el mensaje no se puede entregar, es el destinatario del informe de no entrega (también conocido como NDR o mensaje de devolución).

- `5322.From` (también conocido como remitente **De** dirección o P2) es la dirección de correo electrónico en el campo **De** encabezado y es la dirección de correo electrónico del remitente que se muestra en los clientes de correo electrónico.

Con frecuencia, las `5321.MailFrom` direcciones y `5322.From` son las mismas (comunicación de persona a persona). Sin embargo, cuando se envía correo electrónico en nombre de otra persona, las direcciones pueden ser diferentes.

Las listas de remitentes bloqueados y las listas de dominio bloqueadas en las directivas contra correo no deseado en EOP inspeccionan solo las `5322.From` direcciones. Este comportamiento es similar a los remitentes bloqueados de Outlook que usan la `5322.From` dirección.

## <a name="use-block-entries-in-the-tenant-allowblock-list"></a>Uso de entradas de bloque en la lista de permitidos o bloqueados de inquilinos

Nuestra opción recomendada número uno para bloquear el correo de remitentes o dominios específicos es la lista de permitidos o bloqueados de inquilinos. Para obtener instrucciones, consulte [Permitir o bloquear el correo electrónico mediante la Lista de permitidos o bloqueados de inquilinos](allow-block-email-spoof.md).

Email mensajes de estos remitentes se marcan como _spam de alta confianza_ (SCL = 9). Lo que sucede con los mensajes viene determinado por la [directiva antispam](configure-your-spam-filter-policies.md) que detectó el mensaje para el destinatario. En la directiva de antispam predeterminada y en las nuevas directivas personalizadas, los mensajes marcados como correo no deseado de alta confianza se entregan de forma predeterminada a la carpeta Junk Email. En las [directivas de seguridad preestablecidas](preset-security-policies.md) Estándar y Estricta, los mensajes de spam de alta confianza se ponen en cuarentena.

Como ventaja adicional, los usuarios de la organización no pueden enviar correo electrónico a estos dominios y direcciones bloqueados. Recibirán el siguiente informe de no entrega (también conocido como NDR o mensaje de devolución): `5.7.1  Your message can't be delivered because one or more recipients are blocked by your organization's tenant allow/block list policy.` todo el mensaje se bloquea a todos los destinatarios si el correo electrónico se envía a cualquiera de las entradas de la lista.

Solo si no puede usar la lista de permitidos o bloqueados de inquilinos por algún motivo, considere la posibilidad de usar un método diferente para bloquear a los remitentes.

## <a name="use-outlook-blocked-senders"></a>Uso de remitentes bloqueados de Outlook

Cuando solo un pequeño número de usuarios recibieron correo electrónico no deseado, los usuarios o administradores pueden agregar las direcciones de correo electrónico del remitente a la lista Remitentes bloqueados en el buzón. Para obtener instrucciones, consulte [Configuración del correo electrónico no deseado en Exchange Online buzones](configure-junk-email-settings-on-exo-mailboxes.md).

Cuando los mensajes se bloquean correctamente debido a la lista remitentes bloqueados de un usuario, el campo de encabezado **X-Forefront-Antispam-Report** contendrá el valor `SFV:BLK`.

> [!NOTE]
> Si los mensajes no deseados son boletines de noticias de una fuente de confianza y reconocible, anular la suscripción del correo electrónico es otra opción para impedir que el usuario reciba los mensajes.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Uso de listas de remitentes bloqueadas o listas de dominio bloqueadas

Cuando varios usuarios se ven afectados, el ámbito es más amplio, por lo que la siguiente mejor opción es bloquear listas de remitentes o listas de dominios bloqueados en directivas contra correo no deseado. Los mensajes de los remitentes de las listas se marcan como **spam de alta confianza** y la acción que ha configurado para el veredicto de filtro **de spam de alta confianza** se realiza en los mensajes. Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado](configure-your-spam-filter-policies.md).

El límite máximo para estas listas es de aproximadamente 1000 entradas.

## <a name="use-mail-flow-rules"></a>Uso de reglas de flujo de correo

Las reglas de flujo de correo también pueden buscar palabras clave u otras propiedades en los mensajes no deseados.

Independientemente de las condiciones o excepciones que use para identificar los mensajes, configure la acción para establecer el nivel de confianza de correo no deseado (SCL) del mensaje en 9, lo que marca el mensaje como **spam de alta confianza**. Para obtener más información, consulte [Uso de reglas de flujo de correo para establecer la SCL en los mensajes](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

> [!IMPORTANT]
> Es fácil crear reglas _excesivamente_ agresivas, por lo que es importante identificar solo los mensajes que desea bloquear con criterios muy específicos. Además, asegúrese de [supervisar el uso de la regla](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#monitor-rule-usage) para asegurarse de que todo funciona según lo esperado.

## <a name="use-the-ip-block-list"></a>Uso de la lista de direcciones IP bloqueadas

Cuando no es posible usar una de las otras opciones para bloquear un remitente, _solo entonces_ debe usar la lista de direcciones IP bloqueadas en la directiva de filtro de conexión. Para obtener más información, vea [Configurar la directiva de filtro de conexión](configure-the-connection-filter-policy.md). Es importante mantener el número mínimo de direcciones IP bloqueadas, por lo que _no_ se recomienda bloquear intervalos de direcciones IP completos.

Debe evitar _especialmente_ agregar intervalos de direcciones IP que pertenezcan a servicios de consumidor (por ejemplo, outlook.com) o infraestructuras compartidas, y también asegurarse de revisar la lista de direcciones IP bloqueadas como parte del mantenimiento normal.
