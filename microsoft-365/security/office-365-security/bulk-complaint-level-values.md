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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- m365-security
description: Los administradores pueden obtener información sobre los valores de nivel de queja masiva (BCL) que se usan en Exchange Online Protection (EOP).
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 1e7da11302109a17d9a80c466aa1ed338a0cc6ae
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68066770"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>Nivel de queja masiva (BCL) en EOP

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con buzones de Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP asigna un nivel de queja masiva (BCL) a los mensajes entrantes de los buzones masivos. La BCL se agrega al mensaje en un encabezado X y es similar al [nivel de confianza de correo no deseado (SCL)](spam-confidence-levels.md) que se usa para identificar mensajes como correo no deseado. Una mayor BCL indica que es más probable que un mensaje masivo genere quejas (y, por lo tanto, es más probable que sea correo no deseado). Microsoft usa orígenes internos y de terceros para identificar el correo masivo y determinar la BCL adecuada.

Los correos masivos varían en función de sus patrones de envío, creación de contenido y prácticas de adquisición de destinatarios. Los buenos mailers masivos envían los mensajes deseados con contenido relevante a sus suscriptores. Estos mensajes generan pocas quejas por parte de los destinatarios. Otros troyanos de envío masivo de correo electrónico envían mensajes no solicitados muy similares al correo no deseado y generan muchas quejas por parte de los destinatarios. Los mensajes de un correo masivo se conocen como correo masivo o correo gris.

 El filtrado de correo no deseado marca los mensajes como **correo electrónico masivo** en función del umbral de BCL (el valor predeterminado o un valor especificado) y realiza la acción especificada en el mensaje (la acción predeterminada es entregar el mensaje a la carpeta junk Email del destinatario). Para obtener más información, vea [Configurar directivas contra correo no deseado](configure-your-spam-filter-policies.md) y [¿Cuál es la diferencia entre correo no deseado y correo electrónico masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md)

Los umbrales de BCL se describen en la tabla siguiente.

|BCL|Descripción|
|:---:|---|
|0|El mensaje no es de un remitente de correo masivo.|
|1, 2, 3|El mensaje proviene de un remitente de correo masivo que genera pocas quejas.|
|4, 5, 6, 7<sup>\*</sup>|El mensaje proviene de un remitente de correo masivo que genera un número mixto de quejas.|
|8, 9|El mensaje procede de un remitente masivo que genera un gran número de quejas.|

<sup>\*</sup> Este es el valor de umbral predeterminado que se usa en las directivas contra correo no deseado.
