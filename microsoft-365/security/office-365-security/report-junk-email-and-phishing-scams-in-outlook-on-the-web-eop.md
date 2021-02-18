---
title: Notificar correo electrónico no deseado y de suplantación de identidad en Outlook en la Web
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
description: Los administradores pueden obtener información sobre las opciones integradas de notificación de correo electrónico no deseado, correo no deseado y suplantación de identidad en Outlook en la Web (Outlook Web App) en Exchange Online y cómo deshabilitar estas opciones de informes para los usuarios.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0bd2da9b774b3557ebb820102ba86c17ebe44c69
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289226"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>Notificar correo electrónico no deseado y de suplantación de identidad en Outlook en la Web en Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

En organizaciones de Microsoft 365 con buzones en Exchange Online, puede usar las opciones de informes integradas en Outlook en la Web (anteriormente conocida como Outlook Web App) para enviar falsos positivos (correo electrónico bueno marcado como correo no deseado), falsos negativos (correo electrónico no deseado permitido) y mensajes de suplantación de identidad a Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Si es administrador de una organización con buzones de Exchange Online, le recomendamos que use el portal de envíos en el Centro de & cumplimiento. Para obtener más información, vea Usar envío de administrador para enviar correos sospechosos de correo no [deseado, phishing, direcciones URL y archivos a Microsoft.](admin-submission.md)

- Los administradores pueden deshabilitar o habilitar la posibilidad de que los usuarios informen de mensajes a Microsoft en Outlook en la Web. Para obtener más información, vea la sección Deshabilitar o habilitar los informes de correo no deseado [en Outlook en la web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) más adelante en este artículo.

- Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique. Para obtener más información, consulta [Directivas de envío de usuarios.](user-submission.md)

- Para obtener más información acerca de la notificación de mensajes a Microsoft, vea Notificar mensajes [y archivos a Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a>Notificar mensajes de correo no deseado y suplantación de identidad en Outlook en la Web

1. Para los mensajes de la Bandeja de entrada o cualquier otra carpeta de correo electrónico excepto correo no deseado, use uno de los siguientes métodos para informar de mensajes de correo no deseado y de suplantación de identidad:

   - Seleccione el mensaje, haga clic en **Correo** no deseado en la barra de herramientas y, a continuación, seleccione **Correo** no deseado o **Suplantación de identidad**.

     ![Notificar correo electrónico no deseado o de suplantación de identidad desde la cinta de opciones](../../media/owa-report-junk.png)

   - Seleccione uno o más mensajes, haga clic con el botón secundario y, a continuación, **seleccione Marcar como correo no deseado.**

2. En el cuadro de diálogo que aparece, haga clic en **Informe.** Si cambia de opinión, haga clic **en No informar.**

   |Correo no deseado|Suplantación de identidad (phishing)|
   |:---:|:---:|
   |![Cuadro de diálogo Informar como correo no deseado](../../media/owa-report-as-junk-dialog.png)|![Cuadro de diálogo Informar como suplantación de identidad (phishing)](../../media/owa-report-as-phishing-dialog.png)|

3. Los mensajes seleccionados se enviarán a Microsoft para su análisis. Para confirmar que los mensajes se han enviado, abra la carpeta **Mensajes enviados** para ver los mensajes enviados.

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a>Notificar mensajes de correo no deseado y de suplantación de identidad de la carpeta Correo no deseado en Outlook en la Web

1. En la carpeta Correo no deseado, use uno de los métodos siguientes para notificar falsos positivos de correo no deseado o mensajes de suplantación de identidad:

   - Seleccione el mensaje, haga clic **en No** deseado en la barra de herramientas y, a continuación, seleccione Correo no deseado **o** **Suplantación de identidad**.

     ![Notificar correo electrónico no deseado o no de suplantación de identidad desde la cinta de opciones](../../media/owa-report-not-junk.png)

   - Seleccione uno o más mensajes, haga clic con el botón secundario y, a continuación, **seleccione Marcar como correo no deseado.**

2. En el cuadro de diálogo que aparece, lea la información y haga clic en **Informe.** Si cambia de opinión, haga clic **en No informar.**

   |Correo no deseado|Suplantación de identidad (phishing)|
   |:---:|:---:|
   |![Cuadro de diálogo Informar como correo no deseado](../../media/owa-report-as-not-junk-dialog.png)|![Cuadro de diálogo Informar como suplantación de identidad (phishing)](../../media/owa-report-as-phishing-dialog.png)|

3. Los mensajes seleccionados se enviarán a Microsoft para su análisis. Para confirmar que los mensajes se han enviado, abra la carpeta **Mensajes enviados** para ver los mensajes enviados.

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Deshabilitar o habilitar los informes de correo no deseado en Outlook en la Web

De forma predeterminada, los usuarios pueden informar a Microsoft de falsos positivos de correo no deseado, falsos negativos y mensajes de suplantación de identidad para su análisis en Outlook en la Web. Los administradores pueden configurar directivas de buzón de Outlook en la web en Exchange Online PowerShell para evitar que los usuarios informen a Microsoft de falsos positivos y falsos negativos de correo no deseado. No puede deshabilitar la capacidad de los usuarios de notificar mensajes de suplantación de identidad a Microsoft.

### <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Deberá tener asignados permisos en Exchange Online antes de poder realizar los procedimientos descritos en este artículo. Específicamente, necesita las  funciones **Directivas de** destinatarios o  Destinatarios de  correo, que se asignan de forma predeterminada a los grupos de roles Administración de la organización y Administración de destinatarios. Para obtener más información acerca de los grupos de roles en Exchange Online, vea [Permisos en Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) y Modificar grupos de roles en Exchange [Online.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)

- Cada organización tiene una directiva predeterminada denominada OwaMailboxPolicy-Default, pero puede crear directivas personalizadas. Las directivas personalizadas se aplican a los usuarios con ámbito antes de la directiva predeterminada. Para obtener más información acerca de las directivas de buzones de Correo de Outlook en la Web, vea Las directivas de buzón de Outlook en la [Web en Exchange Online.](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)

- Deshabilitar los informes de correo no deseado no elimina la capacidad de marcar un mensaje como correo no deseado o no deseado en Outlook en la Web. Al seleccionar un mensaje en la  carpeta de correo no deseado y hacer clic en No deseado, el mensaje se mueve de nuevo a \>  la Bandeja de entrada. Al seleccionar un mensaje en cualquier  otra carpeta de correo electrónico y hacer clic en Correo no deseado, el mensaje se mueve a la carpeta \>  Correo no deseado. Lo que ya no está disponible es la opción de notificar el mensaje a Microsoft.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Usar Exchange Online PowerShell para deshabilitar o habilitar los informes de correo no deseado en Outlook en la Web

1. Para encontrar las directivas de buzón de Outlook en la Web existentes y el estado de los informes de correo no deseado, ejecute el siguiente comando:

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Para deshabilitar o habilitar los informes de correo no deseado en Outlook en la Web, use la siguiente sintaxis:

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

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) y [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?

Para comprobar que ha habilitado o deshabilitado correctamente los informes de correo no deseado en Outlook en la Web, siga uno de estos pasos:

- En Exchange Online PowerShell, ejecute el siguiente comando y compruebe el valor de la propiedad **ReportJunkEmailEnabled:**

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- Abra el buzón de un usuario afectado en Outlook en la  Web, seleccione un mensaje en la Bandeja de entrada, haga clic en Correo no deseado y compruebe que la solicitud para notificar el mensaje a Microsoft está o no \>  se muestra.<sup>\*</sup>

- Abra el buzón de correo de un usuario afectado en Outlook en  la Web, seleccione un mensaje en la carpeta Correo no deseado, haga clic en Correo no deseado y compruebe que la solicitud para notificar el mensaje a Microsoft se muestra o \>  no.<sup>\*</sup>

<sup>\*</sup> Los usuarios pueden ocultar la solicitud para informar del mensaje mientras siguen informando del mensaje. Para comprobar esta configuración en Outlook en la Web:

1. Haga clic **en el** icono Configuración de Outlook en la web ![ Ver toda la configuración de ](../../media/owa-settings-icon.png) \> **Outlook** \> **correo electrónico no deseado.**
2. En la **sección Informes,** compruebe el valor: **Pregúnteme antes de enviar un informe.**

   ![Configuración de informes de correo no deseado de Outlook en la web](../../media/owa-junk-email-reporting-options.png)
