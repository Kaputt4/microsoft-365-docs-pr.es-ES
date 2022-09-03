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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre el nivel de confianza de correo no deseado (SCL) que se aplica a los mensajes de Exchange Online Protection (EOP).
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 4f041fe92d6ba295a11dab7904316b238686a34f
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67595947"
---
# <a name="spam-confidence-level-scl-in-eop"></a>Nivel de confianza de correo no deseado (SCL) en EOP

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin Exchange Online buzones, los mensajes entrantes pasan por el filtrado de correo no deseado en EOP y se les asigna una puntuación de correo no deseado. Esa puntuación se asigna a un nivel de confianza de correo no deseado (SCL) individual que se agrega al mensaje en un encabezado X. Un SCL superior indica que es más probable que un mensaje sea correo no deseado. EOP toma medidas en el mensaje en función de la SCL.

En la tabla siguiente se describe lo que significa SCL y las acciones predeterminadas que se realizan en los mensajes. Para obtener más información sobre las acciones que puede realizar en los mensajes en función del veredicto de filtrado de correo no deseado, consulte [Configuración de directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).

|SCL|Definición|Acción predeterminada|
|:---:|---|---|
|-1|El mensaje omitió el filtrado de correo no deseado. Por ejemplo, el mensaje procede de un remitente seguro, se envió a un destinatario seguro o es de un servidor de origen de correo electrónico en la lista de direcciones IP permitidas. Para obtener más información, consulte [Creación de listas de remitentes seguros en EOP](create-safe-sender-lists-in-office-365.md).|Se entrega el mensaje a la bandeja de entrada de los destinatarios.|
|0, 1|El filtrado de correo no deseado determinó que el mensaje no era spam.|Se entrega el mensaje a la bandeja de entrada de los destinatarios.|
|5, 6|El filtrado de correo no deseado marcó el mensaje como **Correo no deseado**|El mensaje se entrega a la carpeta de Correo no deseado de los destinatarios.|
|9 |El filtrado de correo no deseado marcó el mensaje como **spam de alta confianza**.|El mensaje se entrega a la carpeta de Correo no deseado de los destinatarios.|

Observará que el filtrado de correo no deseado no usa SCL 2, 3, 4, 7 y 8.

Puede usar reglas de flujo de correo (también conocidas como reglas de transporte) para marcar la SCL en los mensajes. Si usa una regla de flujo de correo para establecer la SCL, los valores 5 o 6 desencadenan la acción de filtrado de correo no **deseado para spam** y los valores 7, 8 o 9 desencadenan la acción de filtrado de correo no deseado para el **correo no deseado de alta confianza**. Para obtener más información, vea [Usar reglas de flujo de mensajes para establecer el nivel de confianza de spam (SCL) en los mensajes](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

De forma similar a la SCL, el nivel de queja masiva (BCL) identifica el correo electrónico masivo incorrecto (también conocido como _correo gris_). Un BCL superior indica que es más probable que un mensaje de correo masivo generen quejas (y, por lo tanto, es más probable que sea correo no deseado). El umbral de BCL se configura en las directivas contra correo no deseado. Para obtener más información, vea [Configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md), [Nivel de queja masiva (BCL) en EOP)](bulk-complaint-level-values.md) y [¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md).

****

![Icono corto de LinkedIn Learning.](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **¿Es nuevo en Microsoft 365?** Descubra cursos de vídeo **gratuitos para administradores y profesionales de TI de Microsoft 365**, que LinkedIn Learning le ofrece.
