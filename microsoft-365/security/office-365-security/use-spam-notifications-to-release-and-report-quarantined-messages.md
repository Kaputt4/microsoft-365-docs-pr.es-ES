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
description: Los administradores pueden obtener información sobre las notificaciones de correo no deseado del usuario final para los mensajes en cuarentena en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c1688e4a56787c9593aae7006a05d52b16558647
ms.sourcegitcommit: 54bc063818779e351ca24f04ba571f762d85751d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "65393488"
---
# <a name="use-quarantine-notifications-to-release-and-report-quarantined-messages"></a>Uso de notificaciones de cuarentena para liberar e informar de mensajes en cuarentena

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 que tienen buzones de Exchange Online o en las organizaciones con Exchange Online Protection (EOP) independientes sin buzones de Exchange Online, la cuarentena retiene los mensajes que pueden ser peligrosos o no deseados. Para obtener más información, vea [Mensajes en cuarentena en EOP](quarantine-email-messages.md).

_Las directivas de cuarentena_ definen lo que los usuarios pueden hacer en los mensajes en cuarentena en función de por qué se puso en cuarentena el mensaje (para las características admitidas). Para más información, vea [Directivas de cuarentena](quarantine-policies.md). Las directivas de cuarentena también controlan si los destinatarios afectados (incluidos los _buzones compartidos) reciben notificaciones periódicas de cuarentena_ sobre sus mensajes en cuarentena. Las notificaciones de cuarentena son el reemplazo de las notificaciones de correo no deseado del usuario final para todas las características de protección admitidas (no solo los veredictos de la directiva contra correo no deseado).

Las notificaciones de cuarentena no están activadas en las notificaciones de cuarentena integradas denominadas AdminOnlyAccessPolicy o DefaultFullAccessPolicy. Las notificaciones de cuarentena están activadas en la directiva de cuarentena integrada denominada NotificationEnabledPolicy [si la organización la tiene](quarantine-policies.md#full-access-permissions-and-quarantine-notifications). De lo contrario, para activar las notificaciones de cuarentena en las directivas de cuarentena, debe [crear y configurar una nueva directiva de cuarentena](quarantine-policies.md#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal).

Además, para permitir que la opción "Bloquear remitente" en las notificaciones de cuarentena funcione correctamente, los usuarios deben estar habilitados para PowerShell remoto. Para obtener instrucciones, consulte [Habilitar o deshabilitar el acceso a Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell).

Los administradores también pueden usar la configuración global de las directivas de cuarentena para personalizar el nombre para mostrar del remitente, el texto de la declinación de responsabilidades en diferentes idiomas y el logotipo de la empresa que se usa en las notificaciones de cuarentena. Para obtener instrucciones, consulte [Configuración de las notificaciones de cuarentena global](quarantine-policies.md#configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal).

En el caso de los buzones compartidos, las notificaciones de cuarentena solo se admiten para los usuarios a los que se les concede permiso FullAccess para el buzón compartido. Para obtener más información, vea [Uso del EAC para editar la delegación de buzones compartidos](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).

> [!NOTE]
> De forma predeterminada, los mensajes que se ponen en cuarentena como suplantación de identidad de alta confianza, malware, por reglas de flujo de correo (también conocidas como reglas de transporte) o Caja fuerte directivas de datos adjuntos en Defender para Office 365 solo están disponibles para los administradores (de forma predeterminada, se usa la directiva de cuarentena AdminOnlyAccessPolicy). Para más información, consulte [Administrar mensajes en cuarentena y archivos como administrador en EOP](manage-quarantined-messages-and-files.md).
>
> Actualmente, las notificaciones de cuarentena no se admiten para grupos.

Cuando recibe una notificación de cuarentena, la siguiente información siempre está disponible para cada mensaje en cuarentena:

- **Remitente**: nombre de envío y dirección de correo electrónico del mensaje en cuarentena.
- **Asunto**: texto de la línea de asunto del mensaje en cuarentena.
- **Fecha**: fecha y hora (en UTC) en que se puso en cuarentena el mensaje.

Las acciones que están disponibles en la notificación de cuarentena dependen de por qué se puso en cuarentena el mensaje y de los permisos asignados por la directiva de cuarentena asociada. Para obtener más información, consulte [Detalles del permiso de directiva de cuarentena](quarantine-policies.md#quarantine-policy-permission-details).

De forma predeterminada, las siguientes acciones están disponibles en la notificación de cuarentena para los mensajes que se pusieron en cuarentena como correo no deseado, spam de alta confianza o de forma masiva:

- **Bloquear remitente**: haga clic en este vínculo para agregar el remitente a la lista Remitentes bloqueados en _el_ buzón. Para más información, consulte [Bloquear un remitente de correo](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).
- **Versión**: puede liberar el mensaje aquí sin ir a **Cuarentena** en el portal de Microsoft 365 Defender.
- **Revisión**: haga clic en este vínculo para ir a **Cuarentena** en el portal de Microsoft 365 Defender, donde puede (en función de por qué se puso en cuarentena el mensaje) ver, liberar, eliminar o notificar los mensajes en cuarentena. Para obtener más información, vea [Buscar y liberar mensajes en cuarentena como usuario en EOP](find-and-release-quarantined-messages-as-a-user.md).

:::image type="content" source="../../media/end-user-spam-notification.png" alt-text="Ejemplo de una notificación de cuarentena" lightbox="../../media/end-user-spam-notification.png":::

> [!NOTE]
> Un remitente bloqueado todavía puede enviarle correo. Los mensajes de este remitente que lo hagan al buzón se moverán inmediatamente a la carpeta Correo no deseado. Los mensajes futuros de este remitente irán a la carpeta correo no deseado o a la cuarentena. Si desea eliminar estos mensajes a la llegada en lugar de ponerlos en cuarentena, use reglas de [flujo de correo](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (también conocidas como reglas de transporte) para eliminar los mensajes a la llegada.
