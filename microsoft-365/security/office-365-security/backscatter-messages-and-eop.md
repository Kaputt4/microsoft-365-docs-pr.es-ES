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
description: En este artículo, aprenderá sobre protección contra correo electrónico no Microsoft Exchange Online (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d9556c69e5db460933b355e8bf12903d56f21b5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286974"
---
# <a name="backscatter-in-eop"></a>Reenvío masivo de correo electrónico en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

*El correo electrónico no* enviado son informes de no entrega (también conocidos como NDRs o mensajes de de rebote) que recibe para los mensajes que no envió. Los spammers falsificar (suplantan) la dirección De: de sus mensajes y a menudo usan direcciones de correo electrónico reales para dar crédito a sus mensajes. Por lo tanto, cuando los spammers inevitablemente envían mensajes a destinatarios inexistentes (el correo no deseado es una operación de gran volumen), el servidor de correo electrónico de destino es esencialmente complicado para devolver el mensaje que no se puede entregar en un NDR al remitente falsificado en la dirección De:.

En organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP hace todo lo posible para identificar y colocar mensajes de orígenes dudosos sin generar un NDR. Pero, en función del gran volumen de correo electrónico que fluye a través del servicio, siempre existe la posibilidad de que EOP envíe de forma involuntaria el correo electrónico no deseado.

Backscatterer.org mantiene una lista de bloqueados (también conocida como lista de bloqueados DNS o DNSBL) de servidores de correo electrónico que eran responsables de enviar reenvío de correo electrónico no deseado, y los servidores EOP pueden aparecer en esta lista. Pero no intentamos quitarnos de la lista de bloqueados de Backscatterer.org porque no es una lista de spammers (por su propia admisión).

> [!TIP]
> El Backscatter.org web de correo electrónico ( ) recomienda usar su servicio para comprobar el correo electrónico entrante en modo seguro en lugar del modo de rechazo (los servicios de correo electrónico grandes casi siempre envían algo de correo <http://www.backscatterer.org/?target=usage> electrónico no deseado).
