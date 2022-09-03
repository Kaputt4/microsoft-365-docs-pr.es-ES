---
title: Seguimiento de mensajes en el portal de Microsoft 365 Defender
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden usar el vínculo de seguimiento de mensajes en el portal de Microsoft 365 Defender para averiguar qué pasó con los mensajes.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 66ec435e4776cbf52bcf3bbd262210d4dc77ef87
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67597490"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a>Seguimiento de mensajes en el portal de Microsoft 365 Defender

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Seguimiento de los mensajes de correo electrónico a medida que se desplazan por la organización de Exchange Online. Puede determinar si el servicio recibió, rechazó, aplazó o entregó un mensaje. También muestra qué acciones se realizaron en el mensaje antes de que alcanzara su estado final.

Puede usar la información del seguimiento de mensajes para responder de forma eficaz a las preguntas del usuario sobre lo que ha ocurrido con los mensajes, solucionar problemas de flujo de correo y validar los cambios de directiva.

> [!NOTE]
> El seguimiento de mensajes en el portal de Microsoft 365 Defender es solo un paso a través del seguimiento de mensajes en el Centro de administración de Exchange. Para obtener más información, vea [Seguimiento de mensajes en el centro de administración moderno de Exchange](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Debe ser miembro de los grupos de roles **Administración** de la organización, **Administración de cumplimiento** o **Departamento de soporte técnico** de **Exchange Online** para usar el seguimiento de mensajes. Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Notas**: La pertenencia al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos _y_ permisos necesarios para otras características de Microsoft 365. Para más información, consulte[Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

- El número máximo de mensajes que se muestran en los resultados de un seguimiento de mensajes depende del tipo de informe seleccionado (consulte la sección [Elegir tipo de informe](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) para obtener más información). El cmdlet [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) en Exchange Online PowerShell o PowerShell EOP independiente devuelve todos los mensajes de los resultados.

## <a name="open-message-trace"></a>Abrir seguimiento de mensajes

En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a Email & **seguimiento de mensajes de Exchange** de **colaboración**\>. Para ir directamente a la página de seguimiento del mensaje, use <https://admin.exchange.microsoft.com/#/messagetrace>.

En este momento, se abre el seguimiento de mensajes en el EAC. Para obtener más información, vea [Seguimiento de mensajes en el centro de administración moderno de Exchange](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).
