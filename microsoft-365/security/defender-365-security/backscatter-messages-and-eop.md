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
ms.openlocfilehash: e5882f611c3feec9a22760e696973cd0713649b2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073491"
---
# <a name="backscatter-in-eop"></a>Reenvío masivo de correo electrónico en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Backscatter* son informes de no entrega (también conocidos como NDR o mensajes de rebote) que recibe para los mensajes que no envió. Los emisores de correo electrónico no deseado falsifican (suplantan electrónicamente) la dirección De: de sus mensajes y, a menudo, utilizan direcciones de correo electrónico reales para dar credibilidad a sus mensajes. Por lo tanto, cuando los spammers envían mensajes inevitablemente a destinatarios inexistentes (el correo no deseado es una operación de gran volumen), el servidor de correo electrónico de destino es esencialmente engañado para devolver el mensaje no entregado en un NDR al remitente falsificado en la dirección De: .

En organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP hace todo lo posible para identificar y colocar mensajes de orígenes dudosos sin generar un NDR. Pero, en función del gran volumen de correo electrónico que fluye a través del servicio, siempre existe la posibilidad de que EOP envíe de forma involuntaria backscatter.

Backscatterer.org mantiene una lista de bloqueo (también conocida como lista de bloques DNS o DNSBL) de servidores de correo electrónico que eran responsables de enviar backscatter, y los servidores EOP podrían aparecer en esta lista. Pero no intentamos quitarnos de la lista de Backscatterer.org porque no es una lista de spammers (por su propia admisión).

> [!TIP]
> El Backscatter.org web ( ) recomienda usar su servicio para comprobar el correo electrónico entrante en modo seguro en lugar del modo de rechazo (los servicios de correo electrónico grandes casi siempre envían algo de <http://www.backscatterer.org/?target=usage> backscatter).
