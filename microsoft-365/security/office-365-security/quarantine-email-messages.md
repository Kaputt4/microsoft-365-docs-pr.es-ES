---
title: Mensajes de correo electrónico en cuarentena
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre la cuarentena en Exchange Online Protection (EOP) que contiene mensajes potencialmente peligrosos o no deseados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 47742008af9c1cd0a0a17df9e43ebc0228a825b0
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288770"
---
# <a name="quarantined-email-messages-in-eop"></a>Mensajes de correo electrónico en cuarentena en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

En organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, la cuarentena está disponible para contener mensajes potencialmente peligrosos o no deseados.

Las directivas antimalware ponen automáticamente en cuarentena un mensaje si *se* encuentra algún dato adjunto que contenga malware. Para obtener más información, vea [Configurar directivas antimalware en EOP.](configure-anti-malware-policies.md)

De forma predeterminada, las políticas contra correo no deseado ponen en cuarentena los mensajes de suplantación de identidad y entregan mensajes de correo no deseado y de correo masivo a la carpeta de correo no deseado del usuario. Pero también puede crear y personalizar directivas contra correo no deseado para poner en cuarentena los mensajes de correo no deseado y de correo masivo. Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).

Tanto los usuarios como los administradores pueden trabajar con mensajes en cuarentena:

- Los administradores pueden trabajar con todos los tipos de mensajes en cuarentena para todos los usuarios. Solo los administradores pueden trabajar con mensajes que se han puesto en cuarentena como malware, suplantación de identidad de confianza alta o como resultado de reglas de flujo de correo (también conocidas como reglas de transporte). Para más información, consulte [Administrar mensajes en cuarentena y archivos como administrador en EOP](manage-quarantined-messages-and-files.md).

- Los usuarios pueden trabajar con mensajes en cuarentena donde son un destinatario si el mensaje se ha puesto en cuarentena como correo no deseado, correo masivo o suplantación de identidad (a partir de abril de 2020). Para obtener más información, vea [Buscar y liberar mensajes en cuarentena como un usuario en EOP.](find-and-release-quarantined-messages-as-a-user.md)

  Para evitar que los usuarios puedan administrar sus propios mensajes  de suplantación de identidad en cuarentena, los administradores pueden configurar una acción diferente para el veredicto de filtrado de correo electrónico de suplantación de identidad en las directivas contra correo no deseado. Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).

- Los administradores y usuarios pueden notificar falsos positivos a Microsoft en cuarentena.

Para obtener más información acerca de la cuarentena, consulte [Preguntas más frecuentes sobre cuarentena.](quarantine-faq.md)
