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
description: En este artículo, los administradores pueden obtener información sobre cómo el nivel de confianza contra correo no deseado (SCL) determina el likeliness de un mensaje como correo no deseado.
ms.openlocfilehash: 9448b1fd99878dbb85bc8699afc0719bc62dd951
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035253"
---
# <a name="spam-confidence-level-scl-in-office-365"></a>Nivel de confianza contra correo no deseado (SCL) en Office 365

Cuando Microsoft 365 (Exchange online o Exchange Online Protection (EOP) sin buzones de Exchange Online) recibe un mensaje de correo electrónico entrante, el mensaje pasa por el filtrado de correo no deseado y se le asigna una puntuación de correo no deseado. Esa puntuación se asigna a un nivel de confianza de correo no deseado (SCL) individual que se agrega al mensaje en un encabezado X. Un SCL más alto indica que un mensaje es más probable que sea correo no deseado. El servicio realiza una acción en el mensaje basado en el SCL.

En la tabla siguiente se describen los medios de SCL y las acciones predeterminadas que se realizan en los mensajes. Para obtener más información acerca de las acciones que puede realizar en los mensajes en función del veredicto de filtrado de correo no deseado, consulte [configurar directivas contra correo no deseado en Office 365](configure-your-spam-filter-policies.md).

||||
|:---:|---|---|
|**SCL**|**Definición**|**Acción predeterminada**|
|-1|El mensaje omitió el filtrado de correo no deseado. Por ejemplo, el mensaje proviene de un remitente seguro, se envió a un destinatario seguro o pertenece a un servidor de origen de correo electrónico en la lista de direcciones IP permitidas. Para obtener más información, vea [Crear listas de remitentes seguros en Office 365](create-safe-sender-lists-in-office-365.md).|Se entrega el mensaje a la bandeja de entrada de los destinatarios.|
|0, 1|El filtrado de correo no deseado determinó que el mensaje no era correo no deseado.|Se entrega el mensaje a la bandeja de entrada de los destinatarios.|
|5, 6|Filtrado de correo no deseado marcado el mensaje como **correo no deseado**|El mensaje se entrega a la carpeta de Correo no deseado de los destinatarios.|
|9 |Filtrado de correo no deseado marcado el mensaje como **correo no deseado de alta confianza**|El mensaje se entrega a la carpeta de Correo no deseado de los destinatarios.|
|

Verá que SCL 2, 3, 4, 7 y 8 no se usan en el filtrado de correo no deseado.

Puede usar reglas de flujo de correo (también conocidas como reglas de transporte) para marcar el SCL en los mensajes. Si usa una regla de flujo de correo para establecer el SCL, los valores 5 o 6 activarán la acción de filtrado de correo no deseado para **correo no deseado**, y los valores 7, 8 o 9 activarán la acción de filtrado de correo no deseado para **correo no deseado de alta confianza**. Para obtener más información, vea [usar reglas de flujo de correo para establecer el nivel de confianza contra correo no deseado (SCL) en los mensajes](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

Al igual que el SCL, el nivel de queja masiva (BCL) identifica un correo electrónico en masa malo (también conocido como _correo gris_). Una BCL superior indica que un mensaje de correo masivo es más probable que genere quejas (y, por lo tanto, sea más probable que sea correo no deseado). El umbral de BCL se configura en las directivas contra correo no deseado. Para obtener más información, vea [configurar directivas contra correo no deseado en office 365](configure-your-spam-filter-policies.md), [nivel de quejas masivas (BCL) en Office 365)](bulk-complaint-level-values.md)y [¿cuál es la diferencia entre el correo electrónico no deseado y el correo electrónico masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md).

||
|:-----|
|![El icono reducido de LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **¿Es la primera vez que usa Office 365?**         Descubra los cursos gratuitos de vídeo para **administradores y profesionales de TI de Microsoft 365**, que le ha ofrecido LinkedIn Learning.|
