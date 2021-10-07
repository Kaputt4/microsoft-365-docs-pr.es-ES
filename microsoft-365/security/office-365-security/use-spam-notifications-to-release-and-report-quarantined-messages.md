---
title: Notificaciones de cuarentena (notificaciones de correo no deseado del usuario final) en Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre las notificaciones de correo no deseado del usuario final para mensajes en cuarentena en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 31cfebba6d7bde610ac855dc4c7985d2432fabe3
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190250"
---
# <a name="use-quarantine-notifications-to-release-and-report-quarantined-messages"></a>Usar notificaciones de cuarentena para liberar e informar de mensajes en cuarentena

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 que tienen buzones de Exchange Online o en las organizaciones con Exchange Online Protection (EOP) independientes sin buzones de Exchange Online, la cuarentena retiene los mensajes que pueden ser peligrosos o no deseados. Para obtener más información, vea [Mensajes en cuarentena en EOP](quarantine-email-messages.md).

_Las directivas de_ cuarentena definen lo que los usuarios pueden hacer a los mensajes en cuarentena en función del motivo por el que el mensaje se ha puesto en cuarentena (para las características compatibles). Para más información, consulte [Políticas de cuarentena](quarantine-policies.md). Las policías de cuarentena también controlan si los destinatarios afectados (incluidos los _buzones compartidos)_ reciben notificaciones periódicas de cuarentena sobre sus mensajes en cuarentena. Las notificaciones en cuarentena son el reemplazo de las notificaciones de correo no deseado del usuario final para todas las características de protección admitidas (no solo los veredictos de directivas contra correo no deseado).

Los administradores también pueden usar la configuración global de las directivas de cuarentena para personalizar el nombre para mostrar del remitente, el texto de declinación de responsabilidades en diferentes idiomas y el logotipo de la compañía que se usa en las notificaciones. Para obtener instrucciones, vea [Configure global quarantine notification settings in the Microsoft 365 Defender portal](quarantine-policies.md#configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal).

En los buzones compartidos, las notificaciones de cuarentena solo se admiten para los usuarios a los que se les concede permiso FullAccess para el buzón compartido. Para obtener más información, [vea Use the EAC to edit shared mailbox delegation](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).

> [!NOTE]
> De forma predeterminada, los mensajes que se ponen en cuarentena como phishing de elevada confianza, malware, por reglas de flujo de correo (también conocidas como reglas de transporte) o directivas de datos adjuntos de Caja fuerte en Defender para Office 365 solo están disponibles para los administradores. Para más información, consulte [Administrar mensajes en cuarentena y archivos como administrador en EOP](manage-quarantined-messages-and-files.md).
>
> Las notificaciones en cuarentena no son compatibles con los grupos.

Cuando recibe una notificación de cuarentena, la siguiente información siempre está disponible para cada mensaje en cuarentena:

- **Remitente:** el nombre de envío y la dirección de correo electrónico del mensaje en cuarentena.
- **Asunto:** el texto de la línea de asunto del mensaje en cuarentena.
- **Fecha:** la fecha y hora (en UTC) en que el mensaje se ha puesto en cuarentena.

Las acciones que están disponibles en la notificación de cuarentena dependen del motivo por el que el mensaje se ha puesto en cuarentena y de los permisos asignados por la directiva de cuarentena asociada. Para obtener más información, vea [Quarantine policy permission details](quarantine-policies.md#quarantine-policy-permission-details).

De forma predeterminada, las siguientes acciones están disponibles en la notificación de cuarentena para los mensajes que se han puesto en cuarentena como correo no deseado, correo no deseado de elevada confianza o en masa:

- **Bloquear remitente:** haga clic en este vínculo para agregar el remitente a la lista Remitentes bloqueados del _buzón._ Para más información, consulte [Bloquear un remitente de correo](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).
- **Versión:** puede liberar el mensaje aquí sin ir a **Cuarentena** en el portal de Microsoft 365 Defender.
- **Revisión:** haga clic en este vínculo para ir a **Cuarentena** en el portal de Microsoft 365 Defender, donde puede (según por qué el mensaje se ha puesto en cuarentena), liberar, eliminar o notificar los mensajes en cuarentena. Para obtener más información, vea Buscar y liberar mensajes [en cuarentena como usuario en EOP](find-and-release-quarantined-messages-as-a-user.md).

![Ejemplo de notificación en cuarentena.](../../media/end-user-spam-notification.png)

> [!NOTE]
> Un remitente bloqueado aún puede enviarle correo. Los mensajes de este remitente que se envían a su buzón se mueven inmediatamente a la carpeta Correo no deseado. Los mensajes futuros de este remitente irán a la carpeta correo no deseado o a la cuarentena. Si desea eliminar estos mensajes al llegar en lugar de anularlos, use las reglas de flujo de correo [(también](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) conocidas como reglas de transporte) para eliminar los mensajes al llegar.
