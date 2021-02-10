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
localization_priority: Normal
search.appverid:
- MET150s
description: Los administradores pueden obtener información sobre las opciones disponibles y preferidas para bloquear los mensajes entrantes en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d77457567d4c3f9f4a8620021a7fb41615f0594d
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165660"
---
# <a name="create-blocked-sender-lists-in-eop"></a>Crear listas de remitentes bloqueados en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

En organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP ofrece varias formas de bloquear el correo electrónico de remitentes no deseados. Estas opciones incluyen remitentes bloqueados de Outlook, listas de remitentes bloqueados o listas de dominios bloqueados en directivas contra correo no deseado, reglas de flujo de correo de Exchange (también conocidas como reglas de transporte) y la lista de direcciones IP bloqueadas (filtrado de conexiones). Colectivamente, puede pensar en estas opciones como listas de _remitentes bloqueados._

El mejor método para bloquear remitentes varía en función del ámbito de impacto. Para un solo usuario, la solución correcta podría ser Remitentes bloqueados de Outlook. Para muchos usuarios, una de las otras opciones sería más apropiada. Las siguientes opciones se clasifican por ámbito de impacto y amplitud. La lista va de estrecha a amplia, pero *lee los* detalles para obtener recomendaciones completa.

1. Remitentes bloqueados de Outlook (la lista de remitentes bloqueados que se almacena en cada buzón)

2. Listas de remitentes bloqueados o listas de dominios bloqueados (directivas contra correo no deseado)

3. Reglas de flujo de correo

4. La lista de direcciones IP no activas (filtrado de conexiones)

> [!NOTE]
> Aunque puede usar la configuración de bloqueo en toda la organización para solucionar los falsos negativos (correo no deseado perdido), también debe enviar esos mensajes a Microsoft para su análisis. Administrar falsos negativos mediante listas de bloqueados aumenta considerablemente la sobrecarga administrativa. Si usa listas de bloqueados para desviar el correo no deseado perdido, debe mantener el tema Informar de mensajes y archivos a [Microsoft](report-junk-email-messages-to-microsoft.md) a la vez.

Por el contrario, también tiene varias opciones para permitir siempre el correo electrónico de orígenes específicos mediante listas _de remitentes seguros._ Para obtener más información, consulte [Crear listas de remitentes seguros](create-safe-sender-lists-in-office-365.md).

## <a name="email-message-basics"></a>Conceptos básicos de los mensajes de correo electrónico

Un mensaje de correo electrónico SMTP estándar está compuesto por el *sobre del mensaje* y el contenido del mensaje. El sobre del mensaje contiene información necesaria para transmitir y entregar el mensaje entre servidores SMTP. El contenido del mensaje contiene el cuerpo del mensaje y campos de encabezado de mensaje, que se denominan de forma colectiva *encabezado del mensaje*. El sobre del mensaje se describe en RFC 5321 y el encabezado del mensaje se describe en RFC 5322. Los destinatarios nunca ven el sobre del mensaje real porque lo genera el proceso de transmisión de mensajes y, en realidad, no forma parte del mensaje.

- La dirección (también conocida como dirección MAIL FROM, remitente P1 o remitente del sobre) es la dirección de correo electrónico que se usa en la transmisión `5321.MailFrom` SMTP del mensaje.  Esta dirección de correo electrónico normalmente se registra en el campo de encabezado **Return-Path** en el encabezado del mensaje (aunque es posible que el remitente designe una dirección de correo electrónico de **return-path** diferente). Si el mensaje no se puede entregar, es el destinatario del informe de no entrega (también conocido como NDR o mensaje de de rebote).

- El (también conocido como la dirección De o el remitente P2) es la dirección de correo electrónico en el campo de encabezado De y es la dirección de correo electrónico del remitente que se muestra en los clientes de `5322.From` correo electrónico.  

Con frecuencia, las direcciones y son las mismas (comunicación de persona `5321.MailFrom` `5322.From` a persona). Sin embargo, cuando el correo electrónico se envía en nombre de otra persona, las direcciones pueden ser diferentes.

Las listas de remitentes bloqueados y las listas de dominios bloqueados en las directivas contra correo no deseado de EOP inspeccionan las `5321.MailFrom` direcciones y las listas de `5322.From` remitentes bloqueados. Los remitentes bloqueados de Outlook solo usan la `5322.From` dirección.

## <a name="use-outlook-blocked-senders"></a>Usar remitentes bloqueados de Outlook

Cuando solo un pequeño número de usuarios recibe correo electrónico no deseado, los usuarios o administradores pueden agregar las direcciones de correo electrónico del remitente a la lista de remitentes bloqueados en el buzón. Para obtener instrucciones, consulte [Configurar las opciones de correo no deseado en los buzones de Exchange Online.](configure-junk-email-settings-on-exo-mailboxes.md)

Cuando los mensajes se bloquean correctamente debido a la lista de remitentes bloqueados de un usuario, el campo de encabezado **X-Forefront-Antispam-Report** contendrá el valor `SFV:BLK` .

> [!NOTE]
> Si los mensajes no deseados son boletines de una fuente confiable y reconocible, cancelar la suscripción del correo electrónico es otra opción para impedir que el usuario reciba los mensajes.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Usar listas de remitentes bloqueados o listas de dominios bloqueados

Cuando se ven afectados varios usuarios, el ámbito es más amplio, por lo que la siguiente mejor opción son las listas de remitentes bloqueados o las listas de dominios bloqueados en las directivas contra correo no deseado. Los mensajes de remitentes de las listas se marcan como  correo no deseado y la acción que ha configurado para el veredicto de filtro de correo no deseado se toma en el mensaje. Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado](configure-your-spam-filter-policies.md).

El límite máximo para estas listas es de aproximadamente 1000 entradas.

## <a name="use-mail-flow-rules"></a>Usar reglas de flujo de correo

Si necesita bloquear los mensajes que se envían a usuarios específicos o a toda la organización, puede usar reglas de flujo de correo. Las reglas de flujo de correo son más flexibles que las listas de remitentes bloqueados o las listas de dominios de remitentes bloqueados, ya que también pueden buscar palabras clave u otras propiedades en los mensajes no deseados.

Independientemente de las condiciones o excepciones que use para identificar los mensajes, configure la acción para establecer el nivel de confianza contra correo no deseado (SCL) del mensaje en 9, que marca el mensaje como correo no deseado de confianza **alta.** Para obtener más información, vea [Usar reglas de flujo de correo para establecer el SCL en mensajes.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

> [!IMPORTANT]
> Es fácil crear reglas demasiado  agresivas, por lo que es importante que identifique solo los mensajes que desea bloquear usando criterios muy específicos. Además, asegúrese de habilitar la auditoría de la regla y probar los resultados de la regla para asegurarse de que todo funciona según lo esperado.

## <a name="use-the-ip-block-list"></a>Usar la lista de direcciones IP bloqueados

Cuando no es posible usar una de las otras opciones para bloquear un *remitente,* solo entonces debe usar la lista de direcciones IP bloqueados en la directiva de filtro de conexión. Para obtener más información, vea [Configurar la directiva de filtro de conexión](configure-the-connection-filter-policy.md). Es importante mantener el número de direcciones IP bloqueadas al mínimo, por lo que no se recomienda bloquear intervalos de direcciones IP *completos.*

Debe  evitar agregar intervalos de direcciones IP que pertenezcan a servicios de consumidor (por ejemplo, outlook.com) o infraestructuras compartidas, y también debe asegurarse de revisar la lista de direcciones IP bloqueadas como parte del mantenimiento normal.
