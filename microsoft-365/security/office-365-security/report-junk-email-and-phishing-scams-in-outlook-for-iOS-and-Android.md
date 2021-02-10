---
title: Notificar correo electrónico no deseado y de suplantación de identidad en Outlook para iOS y Android
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
description: Los administradores pueden obtener información sobre las opciones integradas de notificación de correo electrónico no deseado, correo no deseado y suplantación de identidad en Outlook para iOS y Android.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 58027f7589280b1266cddc8cfbf44db9e4f0ece4
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166824"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Notificar correo electrónico no deseado y de suplantación de identidad en Outlook para iOS y Android en Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

En organizaciones de Microsoft 365 con buzones en Exchange Online o buzones locales mediante la autenticación moderna [híbrida,](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)puede usar las opciones de informes integradas en Outlook para iOS y Android para enviar falsos positivos (correo electrónico bueno marcado como correo no deseado), falsos negativos (correo electrónico no deseado permitido) y mensajes de suplantación de identidad a Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Si es administrador de una organización con buzones de Exchange Online, le recomendamos que use el portal de envíos en el Centro de & cumplimiento. Para obtener más información, vea Usar envío de administrador para enviar correos sospechosos de correo no [deseado, phishing, direcciones URL y archivos a Microsoft.](admin-submission.md)

- Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique. Para obtener más información, consulta [Directivas de envío de usuarios.](user-submission.md)

- Para obtener más información acerca de la notificación de mensajes a Microsoft, vea Notificar mensajes [y archivos a Microsoft.](report-junk-email-messages-to-microsoft.md)

  > [!NOTE]
  > Si los informes de correo no deseado están deshabilitados para Outlook en la directiva de envío de usuario, los mensajes de correo no deseado o de suplantación de identidad se mueven a la carpeta de correo no deseado y no se notifican a su administrador o Microsoft.

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a>Notificar mensajes de correo no deseado y suplantación de identidad en Outlook para iOS y Android

Para los mensajes de la Bandeja de entrada o cualquier otra carpeta de correo electrónico excepto correo no deseado, siga estos pasos para notificar mensajes de correo no deseado y de suplantación de identidad (phishing) para iOS y Android:

1. Seleccione uno o más mensajes.
2. En la esquina superior derecha, pulsa en los tres puntos verticales. Se abre el menú de acciones.

   ![Notificar correo no deseado o de suplantación de identidad desde el menú de acción](../../media/Android-report-as-junk-dialog.png)

3. Puntee **Informar de correo** no deseado y, a **continuación,** seleccione Correo no deseado o **Suplantación de identidad**.

   ![Notificar correo electrónico no deseado o de suplantación de identidad](../../media/Android-report-junk-or-phishing.png)

4. En el cuadro de diálogo que aparece, puede elegir **Informe** o **No gracias.** Al seleccionar **No** gracias, si  ha pulsado Correo no deseado, el  mensaje se mueve a la carpeta Correo no deseado, si pulsa suplantación de identidad, el mensaje se mueve a la carpeta Elementos eliminados. Seleccione **Informe** para enviar también una copia del mensaje a Microsoft.

   ![Informar sobre las opciones de notificación de correo no deseado o de suplantación de identidad](../../media/Android-junk-email-reporting-options.png)

Si cambias de opinión, selecciona **Deshacer** en la notificación del sistema que aparece. El mensaje permanece en la carpeta Bandeja de entrada.

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a>Notificar mensajes que no son correo no deseado desde la carpeta de correo no deseado en Outlook para iOS y Android

En la carpeta Correo no deseado, siga estos pasos para notificar falsos positivos de correo no deseado:

1. Seleccione uno o más mensajes.
2. En la esquina superior derecha, pulsa en los tres puntos verticales. Se abre el menú de acciones.

   ![Notificar correo no deseado desde el menú de acción](../../media/Android-not-junk-email.png)

3. Pulse **No deseado.**

Aparece una notificación del sistema que muestra que el correo electrónico se ha movido a la Bandeja de entrada. Si cambias de opinión, selecciona **Deshacer en** la notificación del sistema. El correo electrónico permanece en la carpeta Correo no deseado.
