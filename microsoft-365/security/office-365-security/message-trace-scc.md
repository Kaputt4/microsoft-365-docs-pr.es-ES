---
title: Seguimiento de mensajes en el Microsoft 365 Defender web
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden usar el vínculo seguimiento de mensajes en el portal de Microsoft 365 Defender para averiguar qué sucedió con los mensajes.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7b6f7b12086e46c6ad93b60e8c510ea533815a1
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108132"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a>Seguimiento de mensajes en el Microsoft 365 Defender web

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

El seguimiento de mensajes en el portal Microsoft 365 Defender sigue los mensajes de correo electrónico a medida que se desplazan por la Exchange Online organización. Puede determinar si el servicio recibió, rechazó, aplazó o entregó un mensaje. También muestra qué acciones se realizaron en el mensaje antes de alcanzar su estado final.

Puede usar la información del seguimiento de mensajes para responder eficazmente a las preguntas del usuario sobre lo que ocurrió con los mensajes, solucionar problemas de flujo de correo y validar los cambios de directiva.

> [!NOTE]
> El seguimiento de mensajes en el portal Microsoft 365 Defender es solo un paso a través del seguimiento de mensajes en el centro Exchange administración. Para obtener más información, vea [Seguimiento de mensajes en el centro de administración Exchange moderna.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Debe ser miembro de los grupos de  roles **Administración** de  la **organización,** Administración de cumplimiento o Servicio de Exchange Online para usar el seguimiento de mensajes. Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Notas:** La pertenencia al rol Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos y permisos necesarios para _otras_ características de Microsoft 365. Para más información, consulte [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

- El número máximo de mensajes que se muestran en los resultados de un seguimiento de mensajes depende del tipo de informe seleccionado (vea la sección Elegir tipo [de](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) informe para obtener más información). El cmdlet [Get-HistoricalSearch de](/powershell/module/exchange/get-historicalsearch) Exchange Online PowerShell o PowerShell independiente de EOP devuelve todos los mensajes de los resultados.

## <a name="open-message-trace"></a>Seguimiento de mensajes abierto

En el portal de Microsoft 365 Defender ( ), vaya a <https://security.microsoft.com> **Correo electrónico & colaboración Exchange** seguimiento de \> **mensajes**. O bien, para ir directamente a la página de seguimiento de mensajes, use <https://admin.exchange.microsoft.com/#/messagetrace> .

En este momento, se abre el seguimiento de mensajes en el EAC. Para obtener más información, vea [Seguimiento de mensajes en el centro de administración Exchange moderna.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)
