---
title: Reenvío masivo de correo electrónico en EOP
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: En este artículo, aprenderá sobre Backscatter y Microsoft Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 31af8d1467d1e38287c8308dcbac5e55fb7478bf
ms.sourcegitcommit: f88a0ec621e7d9bc5f376eeaf70c8a9800711f88
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2021
ms.locfileid: "59356118"
---
# <a name="backscatter-in-eop"></a>Reenvío masivo de correo electrónico en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Backscatter* son informes de no entrega (también conocidos como NDR o mensajes de despegar) que recibe para los mensajes que no envió. El backscatter se debe a que los spammers forjan (suplantan) la dirección From (también conocida como la dirección `5322.From` O P2) en sus mensajes. Los spammers suelen usar direcciones de correo electrónico reales como la dirección De para dar crédito a sus mensajes. Cuando el correo no deseado se envía a un destinatario inexistente, el servidor de correo electrónico de destino es esencialmente engañado para devolver el mensaje no entregado en un NDR al remitente falsificado en la dirección De.

En Microsoft 365 organizaciones con buzones en organizaciones de Exchange Online o independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP hace todo lo posible para identificar y colocar mensajes de orígenes dudosos sin generar un NDR. Pero, en función del gran volumen de correo electrónico que fluye a través del servicio, siempre existe la posibilidad de que EOP envíe de forma involuntaria backscatter.

Backscatterer.org mantiene una lista de bloqueo (también conocida como lista de bloqueo DNS o DNSBL) de servidores de correo electrónico que eran responsables de enviar backscatter, y los servidores EOP podrían aparecer en esta lista. Pero no intentamos quitarnos de la lista de bloqueo de Backscatterer.org porque (por su propia admisión) su lista no es una lista de spammers.

> [!TIP]
> El sitio Backscatterer.org web ( ) recomienda usar su servicio en modo Caja fuerte en lugar del modo de rechazo, ya que los servicios de correo electrónico grandes casi siempre envían algún <http://www.backscatterer.org/?target=usage> backscatter.
