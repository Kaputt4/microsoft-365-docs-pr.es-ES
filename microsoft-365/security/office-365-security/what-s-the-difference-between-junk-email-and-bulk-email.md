---
title: ¿Cuál &apos; es la diferencia entre correo electrónico no deseado y correo electrónico masivo?
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
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre las diferencias entre el correo electrónico no deseado y el correo electrónico masivo (correo en gris) en Exchange Online Protection (EOP).
ms.openlocfilehash: 1e11f897a145f7b34acc81e1d132d6babac08979
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195484"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo en EOP?

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En los clientes de Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, los clientes preguntan a veces: "¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?" En este tema se explica la diferencia y se describen los controles que están disponibles en EOP.

- El **correo no deseado** es correo no deseado, que son mensajes no solicitados y universales no deseados (cuando se identifica correctamente). De forma predeterminada, EOP rechaza el correo no deseado en función de la reputación del servidor de correo electrónico de origen. Si un mensaje pasa la inspección IP de origen, se envía al filtrado de correo no deseado. Si el mensaje se clasifica como correo no deseado por el filtrado de correo no deseado, el mensaje se entrega (de forma predeterminada) a los destinatarios correspondientes y se mueve a la carpeta de correo electrónico no deseado.

  - Puede configurar las acciones que se deben realizar en los veredictos del filtrado de correo no deseado. Para obtener instrucciones, vea [configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).

  - Si no está de acuerdo con el veredicto de filtrado de correo no deseado, puede informar de los mensajes que considera que son correo no deseado o correo no deseado de Microsoft de varias maneras, como se describe en [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

- El **correo electrónico masivo** (también conocido como _correo gris_) es más difícil de clasificar. Mientras que el correo no deseado es una amenaza constante, el correo electrónico masivo suele ser un mensaje publicitario de solo una vez o de marketing. Algunos usuarios quieren mensajes de correo electrónico masivo (y, de hecho, se han registrado deliberadamente para recibirlos), mientras que otros usuarios consideran el correo electrónico masivo como correo no deseado. Por ejemplo, algunos usuarios quieren recibir mensajes publicitarios de Contoso Corporation o invitaciones a una próxima Conferencia en la seguridad del ciberespacio, mientras que otros usuarios consideran que estos mismos mensajes son correo no deseado.

  Para obtener más información acerca de cómo se identifica el correo masivo, consulte [bulk reclamo LEVEL (BCL) in EOP](bulk-complaint-level-values.md).

## <a name="how-to-manage-bulk-email"></a>Cómo administrar el correo masivo

Debido a la reacción mixta del correo electrónico masivo, no hay ninguna orientación universal que se aplique a todas las organizaciones.

Las directivas contra el correo no deseado tienen un umbral de BCL predeterminado que se usa para identificar correo masivo como correo no deseado. Los administradores pueden aumentar o disminuir el umbral. Para obtener más información, consulte los siguientes temas:

- [Configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).

- [Configuración de la Directiva contra correo no deseado de EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

Otra opción que es fácil de pasar por alto: Si un usuario se queja de recibir correo masivo en masa, pero los mensajes son de remitentes de confianza que superan el filtrado de correo no deseado en EOP, pida al usuario que compruebe si hay una opción para cancelar la suscripción en el mensaje de correo electrónico masivo.
