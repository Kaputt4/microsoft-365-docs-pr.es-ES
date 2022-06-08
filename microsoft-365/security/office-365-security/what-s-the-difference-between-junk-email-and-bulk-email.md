---
title: ¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre las diferencias entre el correo no deseado (correo no deseado) y el correo electrónico masivo (correo gris) en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dd876b522a0d565b84e8bb9043e277cd3bc34495
ms.sourcegitcommit: 61bdfa84f2d6ce0b61ba5df39dcde58df6b3b59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2022
ms.locfileid: "65940456"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>¿Cuál es la diferencia entre el correo electrónico no deseado y el correo electrónico masivo en EOP?

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, los clientes a veces preguntan: "¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?" En este tema se explica la diferencia y se describen los controles que están disponibles en EOP.

- **El correo no deseado** es correo no deseado, que son mensajes no solicitados y universalmente no deseados (cuando se identifican correctamente). De forma predeterminada, el EOP rechaza el correo no deseado en función de la reputación del servidor de correo electrónico de origen. Si un mensaje pasa la inspección de ip de origen, se envía al filtrado de correo no deseado. Si el mensaje se clasifica como correo no deseado mediante el filtrado de correo no deseado, el mensaje se entrega (de forma predeterminada) a los destinatarios previstos y se mueve a su carpeta Correo no deseado.

  - Puede configurar las acciones que se llevarán a cabo en los veredictos de filtrado de correo no deseado. Para obtener instrucciones, consulte [Configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).

  - Si no está de acuerdo con el veredicto de filtrado de correo no deseado, puede notificar a Microsoft los mensajes que considere como correo no deseado o no spam de varias maneras, como se describe en [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

- **El correo electrónico masivo** (también conocido como _correo gris_) es más difícil de clasificar. Mientras que el correo no deseado es una amenaza constante, el correo electrónico masivo suele ser anuncios únicos o mensajes de marketing. Algunos usuarios quieren mensajes de correo electrónico masivos (y de hecho, se han registrado deliberadamente para recibirlos), mientras que otros usuarios consideran que el correo electrónico masivo es correo no deseado. Por ejemplo, algunos usuarios quieren recibir mensajes publicitarios de Contoso Corporation o invitaciones a una próxima conferencia sobre ciberseguridad, mientras que otros usuarios consideran que estos mismos mensajes son correo no deseado.

  Para obtener más información sobre cómo se identifica el correo electrónico masivo, consulte [Nivel de quejas masivas (BCL) en EOP](bulk-complaint-level-values.md).

## <a name="how-to-manage-bulk-email"></a>Cómo administrar el correo masivo

Debido a la reacción mixta al correo electrónico masivo, no hay una guía universal que se aplique a todas las organizaciones.

Las directivas contra correo no deseado tienen un umbral de BCL predeterminado que se usa para identificar el correo electrónico masivo como correo no deseado. Los administradores pueden aumentar o reducir el umbral. Para obtener más información, consulte los siguientes temas:

- [Configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).

- [Configuración de directivas contra correo no deseado de EOP](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

Otra opción fácil de pasar por alto: si un usuario se queja de recibir correo electrónico masivo, pero los mensajes proceden de remitentes de confianza que pasan el filtrado de correo no deseado en EOP, haga que el usuario compruebe si hay una opción de cancelación de suscripción en el mensaje de correo electrónico masivo.
