---
title: Valores de nivel de queja masiva, correo masivo, niveles de BCL, cómo funciona BCL, clasificaciones BCL, antispam, encabezado contra correo electrónico no deseado, filtrado de correo masivo, detener correo masivo
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Obtenga información sobre los valores de nivel de queja masiva (BCL) en Office 365.
ms.openlocfilehash: 6f9314a5b96dbd641e461dfb564ed8605372a949
ms.sourcegitcommit: b0396171d24c6298b809b43bb109d3afed4de5b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2019
ms.locfileid: "37451102"
---
# <a name="bulk-complaint-level-values"></a>Valores de nivel de queja de correo masivo

Los troyanos de envío masivo de correo electrónico varían en sus patrones de envío, la creación de contenido y las prácticas de adquisición de listas. Algunos son buenos troyanos de envío de correo electrónico que envían mensajes deseados con contenido relevante a sus suscriptores. Estos mensajes generan pocas quejas por parte de los destinatarios. Otros troyanos de envío masivo de correo electrónico envían mensajes no solicitados muy similares al correo no deseado y generan muchas quejas por parte de los destinatarios.

Para distinguir estos tipos de troyanos de envío masivo de correo, se asigna una clasificación de nivel de queja de correo masivo (BCL) a los troyanos de envío masivo de correo electrónico. Las clasificaciones de BCL oscilan entre 1 y 9, según la probabilidad con la que el troyano de envío masivo de correo electrónico generará quejas. Es probable que un remitente que tiene una clasificación 9 de BCL genere muchas quejas por parte de los destinatarios, mientras que es poco probable que una clasificación 3 de BCL genere muchas quejas. Microsoft usa fuentes internas y de terceros para identificar el correo masivo y determinar el BCL adecuado. Para obtener más información sobre este encabezado de mensaje, vea [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md).

Dado que es probable que un correo masivo con una clasificación de 9 genere quejas, la BCL predeterminada es 7. Esto significa que los mensajes de correo masivo se aceptarán hasta que no se acepte el nivel de queja de 7 y el correo a partir de ese momento. Cuanto menor sea la clasificación, se aceptará el correo menos masivo. Si los usuarios son, y su trabajo es, sensible al correo masivo y su BCL está establecido en 4, se aceptará correo masivo con una BCL superior a 4.

Para usar los valores de BCL a fin de establecer el nivel deseado de filtrado de correo masivo que requiere su organización, siga estos pasos en [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).

En la tabla siguiente se describen los valores de BCL que están actualmente en uso.

|||
|:-----|:-----|
|**Valor de BCL**|**Descripción**|
|comprendi|El mensaje no es de un remitente de correo masivo.|
|1, 2, 3|El mensaje proviene de un remitente de correo masivo que genera pocas quejas.|
|4, 5, 6, 7|El mensaje proviene de un remitente de correo masivo que genera un número mixto de quejas.|
|8, 9|El mensaje proviene de un remitente de correo masivo que genera un número elevado de quejas.|
