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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: En este artículo, obtendrá información sobre Backscatter y Microsoft Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d132ed56c02989987da9e0ce32e7d4593e85e651
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2022
ms.locfileid: "65648225"
---
# <a name="backscatter-in-eop"></a>Reenvío masivo de correo electrónico en EOP

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Backscatter* son informes de no entrega (también conocidos como NDR o mensajes de rebote) que recibe por los mensajes que no envió. Backscatter se debe a que los spammers falsifican (suplantan) la dirección From (también conocida como dirección `5322.From` O P2) en sus mensajes. Los spammers suelen usar direcciones de correo electrónico reales como dirección De para dar credibilidad a sus mensajes. Cuando se envía correo no deseado a un destinatario inexistente, el servidor de correo electrónico de destino se engaña básicamente para devolver el mensaje no entregado en un NDR al remitente falsificado en la dirección From.

En Microsoft 365 organizaciones con buzones de correo en organizaciones Exchange Online o independientes de Exchange Online Protection (EOP) sin Exchange Online buzones, EOP realiza todos los esfuerzos para identificar y quitar de forma silenciosa mensajes de orígenes dudosos sin generar un NDR. Pero, en función del gran volumen de correo electrónico que fluye a través del servicio, siempre existe la posibilidad de que EOP envíe de forma involuntaria backscatter.

Backscatterer.org mantiene una lista de bloqueos (también conocida como lista de bloqueo DNS o DNSBL) de los servidores de correo electrónico responsables de enviar backscatter, y los servidores EOP podrían aparecer en esta lista. Pero no intentamos quitarnos de la Backscatterer.org lista de bloqueados porque (por su propia admisión) su lista no es una lista de spammers.

> [!TIP]
> El sitio web de Backscatterer.org (<http://www.backscatterer.org/?target=usage>) recomienda usar su servicio en Caja fuerte modo en lugar del modo rechazar, ya que los servicios de correo electrónico de gran tamaño casi siempre envían algunos backscatter.
