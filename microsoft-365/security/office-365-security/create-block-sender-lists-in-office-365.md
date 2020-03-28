---
title: Crear listas de remitentes bloqueados en Office 365
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
- MET150s
description: Los administradores pueden obtener información sobre las opciones disponibles en Office 365 y EOP para bloquear los mensajes entrantes.
ms.openlocfilehash: 0bfab3024bc781e53600092ebc88fae25c5f4afc
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033427"
---
# <a name="create-blocked-sender-lists-in-office-365"></a>Crear listas de remitentes bloqueados en Office 365

Si es un cliente de Office 365 con buzones en Exchange online o un cliente independiente de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP ofrece varias formas de bloquear el correo electrónico de remitentes no deseados. Estas opciones incluyen a los remitentes bloqueados de Outlook, las listas de remitentes bloqueados o las listas de dominios bloqueados en directivas contra correo no deseado, reglas de flujo de correo de Exchange (también conocidas como reglas de transporte) y la lista de direcciones IP bloqueadas (filtrado de conexiones). De forma colectiva, puede considerar estas opciones como _listas de remitentes bloqueados_.

El mejor método para bloquear a los remitentes varía en el ámbito del impacto. Para un solo usuario, la solución correcta podría ser remitentes bloqueados de Outlook. Para muchos usuarios, una de las otras opciones sería más adecuada. Las siguientes opciones están ordenadas por ámbito y amplitud de impacto. La lista va de estrecho a amplio, pero *Lea los detalles específicos* para obtener recomendaciones completas.

1. Remitentes bloqueados de Outlook (la lista de remitentes bloqueados que se almacena en cada buzón de correo)

2. Listas de remitentes bloqueados o listas de dominios bloqueados (directivas contra correo no deseado)

3. Reglas de flujo de correo

4. La lista de direcciones IP bloqueadas (filtrado de la conexión)

> [!NOTE]
> Aunque puede usar la configuración de bloqueo de toda la organización para dirigirse a falsos negativos (correo no deseado), también debe enviar esos mensajes a Microsoft para su análisis. Administrar los falsos negativos mediante listas de bloqueo aumenta considerablemente la sobrecarga administrativa. Si usa listas de bloqueo para desviar el correo no deseado perdido, tiene que mantener los [mensajes y los archivos del informe de temas a Microsoft](report-junk-email-messages-to-microsoft.md) en su lista.

Por el contrario, también tiene varias opciones para permitir siempre el correo electrónico de orígenes específicos mediante _listas de remitentes seguros_. Para obtener más información, vea [crear listas de remitentes seguros en Office 365](create-safe-sender-lists-in-office-365.md).

## <a name="use-outlook-blocked-senders"></a>Usar los remitentes bloqueados de Outlook

Cuando sólo un pequeño número de usuarios reciben correo electrónico no deseado, los usuarios o los administradores pueden agregar las direcciones de correo electrónico de los remitentes a la lista de remitentes bloqueados en el buzón. Para obtener instrucciones, consulte [configurar la configuración del correo electrónico no deseado en buzones de Exchange online en Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

Cuando los mensajes se bloquean correctamente debido a la lista de remitentes bloqueados de un usuario, el campo de encabezado **X-Forefront-antispam-Report** contendrá el valor `SFV:BLK`.

> [!NOTE]
> Si los mensajes no deseados son boletines de un origen fiable y reconocible, la cancelación del correo electrónico es otra opción para impedir que el usuario reciba los mensajes.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Usar listas de remitentes bloqueados o listas de dominios bloqueados

Cuando se ven afectados varios usuarios, el ámbito es más amplio, por lo que la siguiente mejor opción son las listas de remitentes bloqueados o las listas de dominios bloqueados en las directivas contra correo no deseado. Los mensajes de los remitentes de las listas se marcan como **correo no deseado**y se toma la acción que haya configurado para el filtro de **correo no deseado** en el mensaje. Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado en Office 365 ](configure-your-spam-filter-policies.md).

El límite máximo de estas listas es de aproximadamente 1000 entradas; Aunque solo podrá especificar 30 entradas en el portal. Debe usar PowerShell para agregar más de 30 entradas.

## <a name="use-mail-flow-rules"></a>Usar reglas de flujo de correo

Si necesita bloquear los mensajes que se envían a usuarios específicos o en toda la organización, puede usar reglas de flujo de correo. Las reglas de flujo de correo son más flexibles que las listas de remitentes bloqueados o las listas de dominios de remitentes bloqueados, ya que también pueden buscar palabras clave u otras propiedades en los mensajes no deseados.

Independientemente de las condiciones o excepciones que use para identificar los mensajes, configure la acción para establecer el nivel de confianza contra correo no deseado (SCL) del mensaje en 9, que marca el mensaje como un **correo no deseado de alta confianza**. Para obtener más información, vea [usar reglas de flujo de correo para establecer el SCL en los mensajes](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

> [!IMPORTANT]
> Es fácil crear reglas *excesivamente* agresivas, por lo que es importante que identifique solo los mensajes que desea bloquear usando el uso de criterios muy específicos. Además, asegúrese de habilitar la auditoría en la regla y pruebe los resultados de la regla para asegurarse de que todo funciona según lo esperado.

## <a name="use-the-ip-block-list"></a>Usar la lista de direcciones IP bloqueadas

Cuando no es posible usar una de las otras opciones para *bloquear a un remitente, debe usar* la lista de direcciones IP bloqueadas en la Directiva de filtro de conexión. Para obtener más información, vea [Configurar la directiva de filtro de conexión](configure-the-connection-filter-policy.md). Es importante mantener el número de IP bloqueadas en un mínimo, por lo que *no* se recomienda bloquear intervalos de direcciones IP completos.

En *especial* , debe evitar agregar intervalos de direcciones IP que pertenecen a los servicios de consumo (por ejemplo, Outlook.com) o infraestructuras compartidas, y también asegurarse de que revisa la lista de direcciones IP bloqueadas como parte del mantenimiento regular.
