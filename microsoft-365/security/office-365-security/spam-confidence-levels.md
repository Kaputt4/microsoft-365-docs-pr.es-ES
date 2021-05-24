---
title: Nivel de confianza del correo no deseado
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
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre el nivel de confianza de correo no deseado (SCL) que se aplica a los mensajes de Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 55e64c72cc472e98baa8eb71e23dafb6b276ba01
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625286"
---
# <a name="spam-confidence-level-scl-in-eop"></a>Nivel de confianza de correo no deseado (SCL) en EOP

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

En Microsoft 365 organizaciones con buzones en organizaciones de Exchange Online o independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, los mensajes entrantes pasan por el filtrado de correo no deseado en EOP y se les asigna una puntuación de correo no deseado. Esa puntuación se asigna a un nivel de confianza de correo no deseado (SCL) individual que se agrega al mensaje en un encabezado X. Un SCL superior indica que es más probable que un mensaje sea correo no deseado. EOP realiza acciones en el mensaje en función del SCL.

Lo que significa SCL y las acciones predeterminadas que se toman en los mensajes se describen en la tabla siguiente. Para obtener más información acerca de las acciones que puede realizar en los mensajes en función del veredicto de filtrado de correo no deseado, vea [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

****

|SCL|Definición|Acción predeterminada|
|:---:|---|---|
|-1|El mensaje omitió el filtrado de correo no deseado. Por ejemplo, el mensaje es de un remitente seguro, se envió a un destinatario seguro o es de un servidor de origen de correo electrónico en la lista de direcciones IP permitidos. Para obtener más información, vea [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).|Se entrega el mensaje a la bandeja de entrada de los destinatarios.|
|0, 1|El filtrado de correo no deseado determinó que el mensaje no era correo no deseado.|Se entrega el mensaje a la bandeja de entrada de los destinatarios.|
|5, 6|El filtrado de correo no deseado marcó el mensaje como **Correo no deseado**|El mensaje se entrega a la carpeta de Correo no deseado de los destinatarios.|
|9 |El filtrado de correo no deseado marcó el mensaje **como correo no deseado de elevada confianza**|El mensaje se entrega a la carpeta de Correo no deseado de los destinatarios.|
|

Observará que el filtrado de correo no deseado no usa SCL 2, 3, 4, 7 y 8.

Puede usar reglas de flujo de correo (también conocidas como reglas de transporte) para marcar el SCL en los mensajes. Si usa una regla de flujo de correo para establecer el SCL, los valores 5 o 6 desencadenan la acción de filtrado de correo no deseado para **correo** no deseado y los valores 7, 8 o 9 desencadenan la acción de filtrado de correo no deseado para correo no deseado de elevada **confianza.** Para obtener más información, vea Usar reglas de flujo de correo para establecer el nivel de confianza de correo no deseado [(SCL) en los mensajes](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

Al igual que el SCL, el nivel de queja masiva (BCL) identifica el correo electrónico masivo malo (también conocido como _correo gris)._ Un BCL superior indica que es más probable que un mensaje de correo masivo generen quejas (y, por lo tanto, es más probable que sea correo no deseado). El umbral BCL se configura en directivas contra correo no deseado. Para obtener más información, vea [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md)y [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).

****

![El icono corto de LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?** Descubra cursos de vídeo gratuitos **para Microsoft 365 administradores** y profesionales de TI, que LinkedIn Learning le ha presentado.
