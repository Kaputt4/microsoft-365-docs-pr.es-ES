---
title: Cuarentena de mensajes de correo electrónico en Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: Quarantine in Office 365 contiene mensajes potencialmente peligrosos o no deseados. Los administradores y los usuarios finales pueden acceder a la cuarentena.
ms.openlocfilehash: 9c82ba9821c42fe6c3dd78dbcecf63327d176e93
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857314"
---
# <a name="quarantine-in-office-365"></a>Poner en cuarentena en Office 365

Si es un cliente de Office 365 con buzones en Exchange online o un cliente independiente de Exchange Online Protection (EOP) sin buzones de Exchange Online, la cuarentena estará disponible para contener mensajes potencialmente peligrosos o no deseados.

Las directivas antimalware ponen en cuarentena automáticamente un mensaje si se encuentra *algún* archivo adjunto que contenga malware. Para obtener más información, vea [Configure anti-malware policies in Office 365](configure-anti-malware-policies.md).

De forma predeterminada, las directivas contra correo no deseado ponen en cuarentena los mensajes de suplantación de identidad y envían mensajes de correo no deseado y masivo a la carpeta de correo no deseado del usuario. Pero también puede crear y personalizar directivas contra correo no deseado para poner en cuarentena el correo no deseado y los mensajes de correo electrónico masivo. Para obtener más información, vea [configurar directivas contra correo no deseado en Office 365](configure-your-spam-filter-policies.md).

Los usuarios y los administradores pueden trabajar con los mensajes en cuarentena:

- Los administradores pueden trabajar con todos los tipos de mensajes en cuarentena para todos los usuarios. Solo los administradores pueden trabajar con mensajes que se pusieron en cuarentena como malware, la suplantación de identidad de confianza alta o como resultado de las reglas de flujo de correo (también conocidas como reglas de transporte). Para obtener más información, consulte [Manage Quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).

- Los usuarios pueden trabajar con mensajes en cuarentena en los que son destinatarios si el mensaje se puso en cuarentena como correo no deseado, correo electrónico masivo o (a partir de abril de 2020) suplantación de identidad. Para obtener más información, vea [Buscar y liberar mensajes en cuarentena como un usuario en Office 365](find-and-release-quarantined-messages-as-a-user.md).

  Para evitar que los usuarios administren sus propios mensajes de suplantación de identidad (phishing) en cuarentena, los administradores pueden configurar una acción diferente para el veredicto de filtrado de **correo** no deseado en las directivas contra correo no deseado. Para obtener más información, vea [configurar directivas contra correo no deseado en Office 365](configure-your-spam-filter-policies.md).

- Los administradores y los usuarios pueden informar de falsos positivos a Microsoft en cuarentena.

Para obtener más información acerca de, vea [preguntas más frecuentes sobre cuarentena](quarantine-faq.md).
