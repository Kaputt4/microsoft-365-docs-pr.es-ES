---
title: ¿Cuál &apos; es la diferencia entre el correo no deseado y el correo masivo?
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
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre las diferencias entre el correo no deseado (correo no deseado) y el correo masivo (correo gris) en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fc9c94946c3da2f9a14f45070a86c557a5c7dc85
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207554"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>¿Cuál es la diferencia entre el correo no deseado y el correo masivo en EOP?

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En Microsoft 365 organizaciones con buzones en organizaciones de Exchange Online o independientes de Exchange Online Protection (EOP) sin buzones de correo de Exchange Online, los clientes a veces preguntan: "¿cuál es la diferencia entre el correo electrónico no deseado y el correo masivo?". En este tema se explica la diferencia y se describen los controles que están disponibles en EOP.

- **El correo no** deseado es correo no deseado, que son mensajes no solicitados y universalmente no deseados (cuando se identifican correctamente). De forma predeterminada, EOP rechaza el correo no deseado en función de la reputación del servidor de correo electrónico de origen. Si un mensaje pasa la inspección IP de origen, se envía al filtrado de correo no deseado. Si el mensaje se clasifica como correo no deseado mediante el filtrado de correo no deseado, el mensaje se entrega (de forma predeterminada) a los destinatarios previstos y se mueve a su carpeta correo no deseado.

  - Puede configurar las acciones que deben realizarse en los veredictos de filtrado de correo no deseado. Para obtener instrucciones, vea [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

  - Si no está de acuerdo con el veredicto de filtrado de correo no deseado, puede notificar mensajes que considere correo no deseado o no deseado a Microsoft de varias maneras, como se describe en Notificar mensajes y archivos a [Microsoft](report-junk-email-messages-to-microsoft.md).

- **El correo electrónico masivo** (también conocido como _correo gris),_ es más difícil de clasificar. Mientras que el correo no deseado es una amenaza constante, el correo masivo suele ser anuncios únicos o mensajes de marketing. Algunos usuarios quieren mensajes de correo electrónico masivos (y de hecho, se han registrado deliberadamente para recibirlos), mientras que otros usuarios consideran que el correo electrónico masivo es correo no deseado. Por ejemplo, algunos usuarios desean recibir mensajes de publicidad de Contoso Corporation o invitaciones a una próxima conferencia sobre ciberseguridad, mientras que otros usuarios consideran que estos mismos mensajes son correo no deseado.

  Para obtener más información acerca de cómo se identifica el correo electrónico masivo, vea [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).

## <a name="how-to-manage-bulk-email"></a>Cómo administrar el correo masivo

Debido a la reacción mixta al correo electrónico masivo, no hay una guía universal que se aplique a todas las organizaciones.

Las policías contra correo no deseado tienen un umbral BCL predeterminado que se usa para identificar el correo electrónico masivo como correo no deseado. Los administradores pueden aumentar o disminuir el umbral. Para obtener más información, consulte los siguientes temas:

- [Configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).

- [Configuración de directiva contra correo no deseado de EOP](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

Otra opción que es fácil de pasar por alto: si un usuario se queja de recibir correo electrónico masivo, pero los mensajes son de remitentes de confianza que pasan el filtrado de correo no deseado en EOP, haga que el usuario compruebe si hay una opción de cancelación de suscripción en el mensaje de correo electrónico masivo.
