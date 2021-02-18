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
ms.openlocfilehash: e3e3a2d77c978649e7496d09f78301add397fb9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289178"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Notificar correo electrónico no deseado y de suplantación de identidad en Outlook para iOS y Android en Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

En organizaciones de Microsoft 365 con buzones en Exchange Online o buzones locales mediante la autenticación moderna [híbrida,](../../enterprise/hybrid-modern-auth-overview.md)puede usar las opciones de informes integradas en Outlook para iOS y Android para enviar falsos positivos (correo electrónico bueno marcado como correo no deseado), falsos negativos (correo electrónico no deseado permitido) y mensajes de suplantación de identidad a Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Para obtener la mejor experiencia de envío de usuario, se recomienda usar el mensaje de informe y los complementos de suplantación de identidad de informes. Para [obtener más información, vea Habilitar](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) el complemento Mensaje de informe y Habilitar el complemento de [suplantación](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) de identidad de informes.

- Si es administrador de una organización con buzones de Exchange Online, le recomendamos que use el portal de envíos en el Centro de & cumplimiento. Para obtener más información, vea Usar envío de administrador para enviar correos sospechosos de correo no [deseado, phishing, direcciones URL y archivos a Microsoft.](admin-submission.md)

- Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique. Para obtener más información, consulta [Directivas de envío de usuarios.](user-submission.md)

- Para obtener más información acerca de la notificación de mensajes a Microsoft, vea Notificar mensajes [y archivos a Microsoft.](report-junk-email-messages-to-microsoft.md)

  > [!NOTE]
  > Si los informes de correo no deseado están deshabilitados para Outlook en la directiva de envío de usuario, los mensajes de correo no deseado o de suplantación de identidad se mueven a la carpeta de correo no deseado y no se notifican a su administrador o Microsoft.