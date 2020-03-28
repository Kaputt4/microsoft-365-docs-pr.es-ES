---
title: Valores de nivel de queja masiva, correo masivo, niveles de BCL, cómo funciona BCL, clasificaciones BCL, antispam, encabezado contra correo electrónico no deseado, filtrado de correo masivo, detener correo masivo
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
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
description: Obtenga información sobre los valores del nivel de cumplimiento masivo (BCL) en Office 365.
ms.openlocfilehash: aa839fc1bcab141fe71c76e7f27b4f6bb23048b2
ms.sourcegitcommit: ce6121a8e3ca7438071d73b0c76e2b6f33ac1cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "43030157"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a>Nivel de queja masiva (BCL) en Office 365

Los remitentes de correo masivo varían en sus patrones de envío, creación de contenido y prácticas de adquisición de destinatarios. Algunos son buenos correos masivos que envían mensajes deseados con contenido relevante a sus suscriptores. Estos mensajes generan pocas quejas por parte de los destinatarios. Otros troyanos de envío masivo de correo electrónico envían mensajes no solicitados muy similares al correo no deseado y generan muchas quejas por parte de los destinatarios. Los mensajes de un envío masivo de correo se conoce como correo masivo o de correo gris.

Para distinguir mensajes de distintos tipos de correo masivo, el correo electrónico entrante de correo masivo a Office 365 (Exchange online o Exchange Online Protection (EOP) sin buzones de correo de Exchange Online) tiene asignado un nivel de queja masiva (BCL) que se agrega a mensaje en un encabezado X. La BCL es similar al [nivel de confianza contra correo no deseado (SCL)](spam-confidence-levels.md) que se usa para identificar mensajes como correo no deseado. Una BCL superior indica que un mensaje masivo tiene más probabilidades de generar quejas (y, por lo tanto, es más probable que sea correo no deseado). Microsoft usa orígenes internos y de terceros para identificar el correo masivo y determinar la BCL adecuada.

 El filtrado de correo no deseado marca los mensajes como **correo masivo** en función del umbral de BCL (el valor predeterminado o un valor especificado) y toma la acción especificada en el mensaje (la acción predeterminada es entregar el mensaje en la carpeta de correo no deseado del destinatario). Para obtener más información, vea [configurar directivas contra correo no deseado en Office 365](configure-your-spam-filter-policies.md) y [¿cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md)

Los umbrales de BCL se describen en la tabla siguiente.

|||
|:---:|---|
|**BCL**|**Descripción**|
|comprendi|El mensaje no es de un remitente de correo masivo.|
|1, 2, 3|El mensaje proviene de un remitente de correo masivo que genera pocas quejas.|
|4, 5, 6, 7|El mensaje proviene de un remitente de correo masivo que genera un número mixto de quejas.|
|8, 9|El mensaje proviene de un remitente masivo que genera un gran número de quejas.|
|
