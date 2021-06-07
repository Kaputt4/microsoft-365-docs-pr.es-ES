---
title: Notificar correo electrónico no deseado y suplantación de identidad Outlook en la web
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre las opciones de informes de correo electrónico de correo no deseado, no correo no deseado y suplantación de identidad integradas en Outlook en la web (Outlook Web App) en Exchange Online y cómo deshabilitar estas opciones de informes para los usuarios.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1139871f5929ff9fef29e980b7614e5bc7b92570
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788312"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>Notificar correo electrónico no deseado y suplantación de identidad Outlook en la web en Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En Microsoft 365 organizaciones con buzones de correo en buzones de Exchange Online o locales mediante autenticación moderna [híbrida,](../../enterprise/hybrid-modern-auth-overview.md)puede enviar falsos positivos (correo electrónico bueno marcado como correo no deseado), falsos negativos (correo electrónico no permitido) y mensajes de suplantación de identidad a Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

> [!IMPORTANT]
> Se recomienda el complemento Report Message o el complemento Report Phishing para envíos de usuarios. Para obtener más información, vea [Enable the Report Message or the Report Phishing add-ins](./enable-the-report-message-add-in.md). No recomendamos la experiencia de informes integrada en Outlook porque no puede usar la directiva [de envío de usuario](./user-submission.md).

- Si es administrador de una organización con buzones de correo Exchange Online, le recomendamos que use el portal de envíos en el Centro de seguridad & cumplimiento. Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

- Los administradores pueden deshabilitar o habilitar la capacidad de los usuarios para notificar mensajes a Microsoft Outlook en la web. Para obtener más información, vea la sección Deshabilitar o habilitar informes de correo no deseado [en Outlook en la web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) más adelante en este artículo.

- Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique. Para obtener más información, vea [Directivas de envío de usuarios](user-submission.md).

- Para obtener más información acerca de cómo notificar mensajes a Microsoft, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Deshabilitar o habilitar los informes de correo no deseado Outlook en la web

De forma predeterminada, los usuarios pueden notificar falsos positivos de correo no deseado, falsos negativos y mensajes de suplantación de identidad a Microsoft para su análisis Outlook en la web. Los administradores pueden configurar Outlook directivas de buzones de correo web en Exchange Online PowerShell para evitar que los usuarios den a Microsoft informes de falsos positivos de correo no deseado y falsos negativos de correo no deseado. No puede deshabilitar la capacidad de los usuarios de notificar mensajes de suplantación de identidad a Microsoft.

### <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Debe tener asignados permisos en Exchange Online para poder realizar los procedimientos de este artículo. Específicamente, necesita los roles **Directivas de** destinatarios o Destinatarios de correo, que están **asignados** a **los** grupos de roles Administración de la organización y **Administración** de destinatarios de forma predeterminada. Para obtener más información acerca de los grupos de roles en Exchange Online, vea [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) y [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).

- Cada organización tiene una directiva predeterminada denominada OwaMailboxPolicy-Default, pero puede crear directivas personalizadas. Las directivas personalizadas se aplican a los usuarios con ámbito antes de la directiva predeterminada. Para obtener más información acerca Outlook en las directivas de buzones de correo web, vea Outlook [en las directivas de buzón](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)web en Exchange Online .

- Deshabilitar los informes de correo no deseado no elimina la capacidad de marcar un mensaje como correo no deseado o no deseado en Outlook en la web. Si selecciona un mensaje en la  carpeta Correo no deseado y hace clic en No deseado, el mensaje se vuelve a mover a \>  la Bandeja de entrada. Al seleccionar un mensaje en cualquier  otra carpeta de correo electrónico y hacer clic en No deseado, el mensaje se mueve a \>  la carpeta Correo no deseado. Lo que ya no está disponible es la opción de informar el mensaje a Microsoft.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Usar Exchange Online PowerShell para deshabilitar o habilitar los informes de correo no deseado Outlook en la web

1. Para buscar la información Outlook en las directivas de buzón de correo web y el estado de los informes de correo no deseado, ejecute el siguiente comando:

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Para deshabilitar o habilitar los informes de correo no deseado Outlook en la web, use la sintaxis siguiente:

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   En este ejemplo se deshabilitan los informes de correo no deseado en la directiva predeterminada.

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   En este ejemplo se habilitan los informes de correo no deseado en la directiva personalizada denominada Administradores de Contoso.

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) y [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?

Para comprobar que ha habilitado o deshabilitado correctamente los informes de correo no deseado en Outlook en la web, siga estos pasos:

- En Exchange Online PowerShell, ejecute el siguiente comando y compruebe el valor de la propiedad **ReportJunkEmailEnabled:**

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- Abra el buzón de un usuario afectado en Outlook en la web,  seleccione un mensaje en la Bandeja de entrada, haga clic en Correo no deseado y compruebe que el mensaje para notificarlo a Microsoft se muestra o \>  no.<sup>\*</sup>

- Abra el buzón de un usuario afectado en Outlook en la web, seleccione  un mensaje en la carpeta Correo no deseado, haga clic en Correo no deseado y compruebe que el mensaje para notificarlo a Microsoft está o no se \>  muestra.<sup>\*</sup>

<sup>\*</sup> Los usuarios pueden ocultar el mensaje para informar del mensaje mientras siguen informando del mensaje. Para comprobar esta configuración en Outlook en la web:

1. Haga **clic Configuración** Outlook en el icono de configuración web Ver todos los Outlook ![ ](../../media/owa-settings-icon.png) \> **configuración** correo no \> **deseado**.
2. En la **sección Informes,** compruebe el valor: **Pregúnteme antes de enviar un informe**.

   ![Outlook configuración de informes de correo no deseado en la web](../../media/owa-junk-email-reporting-options.png)
