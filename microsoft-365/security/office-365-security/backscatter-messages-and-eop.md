---
title: Mensajes de reenvío masivo de correo electrónico y EOP
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Los mensajes de reenvío masivo son mensajes de devolución automatizados que se envían a direcciones de correo electrónico falsificadas. La DNSBL de la indispersión identifica los servidores que envían mensajes de reenvío masivo (que pueden incluir muchos orígenes de correo electrónico legítimos). Dado que no se trata de una lista de remitentes de correo no deseado, no tratamos de eliminarlas de la DNSBL.
ms.openlocfilehash: f6e8398565837f7a380c8a6a5c4cd8de422cc215
ms.sourcegitcommit: ca4ce9e8c7e4b433608cd059857740ffd5a472c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2019
ms.locfileid: "40840169"
---
# <a name="backscatter-messages-and-eop"></a>Mensajes de reenvío masivo de correo electrónico y EOP

*Los mensajes* de reenvío masivo son informes de no entrega (también conocidos como NDR o mensajes de devolución) que se reciben para los mensajes que no se enviaron. Los remitentes de correo no deseado falsifican (suplantan) la dirección de: de sus mensajes y suelen usar direcciones de correo electrónico reales para prestar credibilidad a sus mensajes. Por lo tanto, cuando envían mensajes inevitablemente a destinatarios no existentes (el correo no deseado es una operación de gran volumen), es posible que el servidor de correo electrónico de destino responda dutifully con un NDR, que se envía al remitente falsificado en la dirección from:.

Exchange Online Protection (EOP) hace todo lo posible para identificar y eliminar silenciosamente los mensajes de fuentes dudosas sin generar un NDR. Pero, a partir de la gran cantidad de correo electrónico que fluye a través del servicio, siempre hay la posibilidad de que EOP envíe mensajes posdispersos de forma involuntaria.

Backscatterer.org mantiene una lista de bloqueados (también conocida como una lista de bloqueados de DNS o DNSBL) de los servidores de correo electrónico responsables del envío de mensajes de reenvío masivo, y es posible que aparezcan en esta lista los servidores de EOP. Pero no estamos intentando eliminarlas de la lista de bloqueadores de Backscatterer.org porque no es una lista de remitentes de correo no deseado (por su propia admisión).

> [!TIP]
> De acuerdo con el servicio de dispersión. o`http://www.backscatterer.org/?target=usage`el sitio web (), se recomienda usar el servicio para comprobar el correo electrónico entrante en modo seguro en lugar de rechazar el modo (los servicios de correo electrónico grandes casi siempre envían mensajes de reenvío masivo).
