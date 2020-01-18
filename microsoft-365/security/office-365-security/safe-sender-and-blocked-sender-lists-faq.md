---
title: Listas de remitentes seguros y bloqueados en Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: Como administrador de Exchange Online o Exchange Online Protection (EOP), puede ayudar a garantizar que un mensaje de correo que pasa a través del servicio no se marque como correo no deseado. Una forma de hacerlo es crear listas de remitentes bloqueados y de remitentes seguros para las personas de su organización.
ms.openlocfilehash: 9c281460aeff64226343af5e5608ccf42fc83799
ms.sourcegitcommit: a122fd1fce523171529c7f610bb7faf09d30a8bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/18/2020
ms.locfileid: "41238397"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a>Listas de remitentes seguros y bloqueados en Exchange Online

Como administrador de Exchange Online o Exchange Online Protection (EOP), puede ayudar a garantizar que un mensaje de correo que pasa a través del servicio no se marque como correo no deseado. Una forma de hacerlo es crear listas de remitentes bloqueados y de remitentes seguros para las personas de su organización.

*Vea la versión actualizada de las sugerencias y los procedimientos para trabajar con estas listas como administrador de* [Cómo evitar que el correo electrónico correcto se marque como correo no deseado en Office 365](prevent-email-from-being-marked-as-spam.md).

Si no es un administrador y solo desea administrar su propio correo electrónico no deseado en Outlook mediante una lista de remitentes seguros, consulte los pasos de la[información general del filtro de correo electrónico no deseado](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a>¿Qué son los límites de remitentes seguros y bloqueados en Exchange Online?

Los límites de remitentes seguros y bloqueados en Exchange Online difieren de los límites de Outlook y Active Directory. Son los siguientes:

- Límite de remitentes seguros: 1.024

- Límite de remitentes bloqueados: 500

Nota:

Puede experimentar el error que se describe en [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app). Para resolver este problema, desactive la casilla "confiar en mensajes de correo electrónico de mis contactos". También puede reducir la cantidad de direcciones de correo electrónico que se encuentran en la carpeta contactos predeterminada para que pasen al límite máximo permitido de 1024 en Exchange online que se establece para el atributo "parámetros maxsafesenders". Para obtener más información sobre este atributo y el cmdlet Set-Mailbox, sobre elscript siguiente tema:

[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a>Vea también

[Filtrado de remitentes en Exchange Server](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
