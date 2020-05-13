---
title: Nivel de confianza de correo no deseado
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
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre el nivel de confianza contra correo no deseado (SCL) que se aplica a los mensajes en Exchange Online Protection (EOP).
ms.openlocfilehash: bc3a1e7e4b3e5f737b8861c14e0fd2c3d0841940
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208017"
---
# <a name="spam-confidence-level-scl-in-eop"></a>Nivel de confianza contra correo no deseado (SCL) en EOP

En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, los mensajes entrantes pasan por el filtrado de correo no deseado en EOP y se les asigna una puntuación de correo no deseado. Esa puntuación se asigna a un nivel de confianza de correo no deseado (SCL) individual que se agrega al mensaje en un encabezado X. Un SCL más alto indica que un mensaje es más probable que sea correo no deseado. EOP realiza una acción en el mensaje en función del SCL.

En la tabla siguiente se describen los medios de SCL y las acciones predeterminadas que se realizan en los mensajes. Para obtener más información sobre las acciones que puede realizar en los mensajes en función del veredicto de filtrado de correo no deseado, consulte [configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).

||||
|:---:|---|---|
|**SCL**|**Definición**|**Acción predeterminada**|
|-1|El mensaje omitió el filtrado de correo no deseado. Por ejemplo, el mensaje proviene de un remitente seguro, se envió a un destinatario seguro o pertenece a un servidor de origen de correo electrónico en la lista de direcciones IP permitidas. Para obtener más información, vea [crear listas de remitentes seguros en EOP](create-safe-sender-lists-in-office-365.md).|Se entrega el mensaje a la bandeja de entrada de los destinatarios.|
|0, 1|El filtrado de correo no deseado determinó que el mensaje no era correo no deseado.|Se entrega el mensaje a la bandeja de entrada de los destinatarios.|
|5, 6|Filtrado de correo no deseado marcado el mensaje como **correo no deseado**|El mensaje se entrega a la carpeta de Correo no deseado de los destinatarios.|
|9 |Filtrado de correo no deseado marcado el mensaje como **correo no deseado de alta confianza**|El mensaje se entrega a la carpeta de Correo no deseado de los destinatarios.|
|

Verá que SCL 2, 3, 4, 7 y 8 no se usan en el filtrado de correo no deseado.

Puede usar reglas de flujo de correo (también conocidas como reglas de transporte) para marcar el SCL en los mensajes. Si usa una regla de flujo de correo para establecer el SCL, los valores 5 o 6 activarán la acción de filtrado de correo no deseado para **correo no deseado**, y los valores 7, 8 o 9 activarán la acción de filtrado de correo no deseado para **correo no deseado de alta confianza**. Para obtener más información, vea [usar reglas de flujo de correo para establecer el nivel de confianza contra correo no deseado (SCL) en los mensajes](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

Al igual que el SCL, el nivel de queja masiva (BCL) identifica un correo electrónico en masa malo (también conocido como _correo gris_). Una BCL superior indica que un mensaje de correo masivo es más probable que genere quejas (y, por lo tanto, sea más probable que sea correo no deseado). El umbral de BCL se configura en las directivas contra correo no deseado. Para obtener más información, vea [configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md), [nivel de queja masiva (BCL) en EOP](bulk-complaint-level-values.md), y [¿cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md).

||
|:-----|
|![El icono corto de LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New a Microsoft 365?** Descubra los cursos gratuitos de vídeo para **administradores y profesionales de TI de Microsoft 365**, que le ha ofrecido LinkedIn Learning.|
