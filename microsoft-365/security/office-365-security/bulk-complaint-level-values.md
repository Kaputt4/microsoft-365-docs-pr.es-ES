---
title: Valores de nivel de queja masiva
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre los valores del nivel de cumplimiento masivo (BCL) que se usan en Exchange Online Protection (EOP).
ms.openlocfilehash: d59bb152de075bb807e3cae72839fe459d7da40f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203532"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>Nivel de queja masiva (BCL) en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP asigna un nivel compatible con masa (BCL) a los mensajes entrantes de los correos masivos. La BCL se agrega al mensaje en un encabezado X y es similar al [nivel de confianza contra correo no deseado (SCL)](spam-confidence-levels.md) que se usa para identificar mensajes como correo no deseado. Una BCL superior indica que un mensaje masivo tiene más probabilidades de generar quejas (y, por lo tanto, es más probable que sea correo no deseado). Microsoft usa orígenes internos y de terceros para identificar el correo masivo y determinar la BCL adecuada.

Los remitentes de correo masivo varían en sus patrones de envío, creación de contenido y prácticas de adquisición de destinatarios. Los envíos de correo en masa correctos envían los mensajes deseados con contenido relevante a sus suscriptores. Estos mensajes generan pocas quejas por parte de los destinatarios. Otros troyanos de envío masivo de correo electrónico envían mensajes no solicitados muy similares al correo no deseado y generan muchas quejas por parte de los destinatarios. Los mensajes de un correo masivo se denominan correo masivo o gris.

 El filtrado de correo no deseado marca los mensajes como **correo masivo** en función del umbral de BCL (el valor predeterminado o un valor especificado) y toma la acción especificada en el mensaje (la acción predeterminada es entregar el mensaje en la carpeta de correo no deseado del destinatario). Para obtener más información, vea [configurar directivas contra correo no deseado](configure-your-spam-filter-policies.md) y [¿cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md)

Los umbrales de BCL se describen en la tabla siguiente.

****

|BCL|Descripción|
|:---:|---|
|comprendi|El mensaje no es de un remitente de correo masivo.|
|1, 2, 3|El mensaje proviene de un remitente de correo masivo que genera pocas quejas.|
|4, 5, 6, 7|El mensaje proviene de un remitente de correo masivo que genera un número mixto de quejas.|
|8, 9|El mensaje proviene de un remitente masivo que genera un gran número de quejas.|
|
