---
title: ¿Cuál &apos; es la diferencia entre el correo electrónico no deseado y el correo electrónico masivo?
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
description: Los administradores pueden obtener información sobre las diferencias entre el correo no deseado y el correo masivo (correo gris) en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c656ed1807b451ae03ecfeb0f220f5d7b902c7ac
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290650"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>¿Cuál es la diferencia entre el correo electrónico no deseado y el correo electrónico masivo en EOP?

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

En las organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, los clientes a veces preguntan: "¿Cuál es la diferencia entre el correo electrónico no deseado y el correo electrónico masivo?" En este tema se explica la diferencia y se describen los controles disponibles en EOP.

- **El correo no** deseado es correo no deseado, que son mensajes no solicitados y universalmente no deseados (cuando se identifican correctamente). De forma predeterminada, EOP rechaza el correo no deseado en función de la reputación del servidor de correo electrónico de origen. Si un mensaje pasa la inspección de IP de origen, se envía al filtrado de correo no deseado. Si el mensaje se clasifica como correo no deseado mediante el filtrado de correo no deseado, el mensaje se entrega (de forma predeterminada) a los destinatarios previstos y se mueve a su carpeta de correo no deseado.

  - Puede configurar las acciones que se realizarán en los veredictos de filtrado de correo no deseado. Para obtener instrucciones, vea [Configurar directivas contra correo no deseado en EOP.](configure-your-spam-filter-policies.md)

  - Si no está de acuerdo con el veredicto de filtrado de correo no deseado, puede notificar mensajes que considere correo no deseado o correo no deseado a Microsoft de varias maneras, como se describe en Notificar mensajes y archivos a [Microsoft.](report-junk-email-messages-to-microsoft.md)

- **El correo electrónico** masivo (también conocido como _correo gris)_ es más difícil de clasificar. Mientras que el correo no deseado es una amenaza constante, el correo masivo suele ser anuncios únicos o mensajes de marketing. Algunos usuarios desean mensajes de correo electrónico masivo (y, de hecho, se han registrado deliberadamente para recibirlos), mientras que otros consideran que el correo masivo es correo no deseado. Por ejemplo, algunos usuarios desean recibir mensajes de publicidad de Contoso Corporation o invitaciones a una próxima conferencia sobre ciberseguridad, mientras que otros usuarios consideran que estos mismos mensajes son correo no deseado.

  Para obtener más información acerca de cómo se identifica el correo electrónico masivo, vea Nivel de [quejas masivas (BCL) en EOP.](bulk-complaint-level-values.md)

## <a name="how-to-manage-bulk-email"></a>Cómo administrar el correo masivo

Debido a la reacción mixta al correo electrónico masivo, no hay una guía universal que se aplique a todas las organizaciones.

Las políticas contra correo no deseado tienen un umbral BCL predeterminado que se usa para identificar el correo electrónico masivo como correo no deseado. Los administradores pueden aumentar o disminuir el umbral. Para obtener más información, consulte los siguientes temas:

- [Configurar directivas contra correo no deseado en EOP.](configure-your-spam-filter-policies.md)

- [Configuración de directiva contra correo no deseado de EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

Otra opción que es fácil de pasar por alto: si un usuario se queja de recibir correo electrónico masivo, pero los mensajes son de remitentes de confianza que pasan el filtrado de correo no deseado en EOP, haga que el usuario compruebe si hay una opción de cancelación de suscripción en el mensaje de correo electrónico masivo.
