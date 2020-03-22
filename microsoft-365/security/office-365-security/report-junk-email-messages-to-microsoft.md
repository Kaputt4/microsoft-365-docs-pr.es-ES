---
title: Informar a Microsoft sobre mensajes de correo electrónico no deseado
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 'El complemento de notificación de correo no deseado de Microsoft para Microsoft Office Outlook permite notificar mensajes de correo no deseado de varias formas:'
ms.openlocfilehash: b1ed918e4b954cc7b2d79e52abd6f58a99eda0f0
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895184"
---
# <a name="report-junk-email-messages-to-microsoft"></a>Informar a Microsoft sobre mensajes de correo electrónico no deseado

El complemento de notificación de correo no deseado de Microsoft para Microsoft Office Outlook permite notificar mensajes de correo no deseado de varias formas:

- Desde la cinta de Outlook

- Desde la bandeja de entrada

- Desde un mensaje de correo electrónico abierto

El complemento de notificación de correo no deseado permite enviar informes al servicio Microsoft Exchange Online Protection (EOP). Si su buzón no está protegido por el servicio, el envío de notificaciones de correo no deseado no afectará a los filtros de correo no deseado. Los administradores pueden obtener más información sobre la configuración de correo no deseado que se aplica a toda la organización en [crear listas de remitentes seguros en office 365](create-safe-sender-lists-in-office-365.md) y [crear listas de remitentes bloqueados en Office 365](create-block-sender-lists-in-office-365.md). Estos son útiles si tiene control de nivel de administrador y desea evitar falsos positivos o negativos falsos.

> [!TIP]
> También puede enviar mensajes de correo no deseado directamente a Microsoft con la dirección de correo electrónico de [Junk@office365.microsoft.com](mailto:junk@office365.microsoft.com) y los mensajes falsos positivos (correo no no deseado) mediante la dirección de correo electrónico [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com) . Para obtener más información, vea enviar correo electrónico no deseado, mensajes de correo [no deseado y mensajes de estafa de suplantación de identidad a Microsoft para su análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

### <a name="to-report-junk-email-messages-from-outlook"></a>Para notificar mensajes de correo electrónico no deseado desde Outlook

[Usar el complemento de mensajes de informe](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

### <a name="to-report-junk-email-messages-from-your-inbox"></a>Para notificar mensajes de correo electrónico no deseado desde la bandeja de entrada

1. Haga clic con el botón derecho en los mensajes que quiera notificar como correo no deseado.

2. Seleccione **No deseado** y, a continuación, haga clic en **Informar de correo electrónico no deseado**.
    ![Denunciar mensajes no deseados desde la bandeja de entrada](../../media/EOP-Outlook-Junk-Reporting-Tool-3.jpg)

3. Aparecerá el cuadro de diálogo del **complemento de notificación de correo no deseado de Microsoft**. Si está seguro de que desea enviar los mensajes que ha seleccionado como no deseado, haga clic en **Sí**.
    ![Confirmar denuncia como no deseado](../../media/EOP-Outlook-Junk-Reporting-Tool-2.jpg)

    > [!NOTE]
    > Si no desea recibir un mensaje de confirmación al enviar mensajes de correo no deseado, active la casilla **No volver a mostrar este mensaje**.

Los mensajes seleccionados se envían a Microsoft para su análisis y se mueven a la carpeta de correo no deseado. Para confirmar que los mensajes se han enviado, abra la carpeta **Mensajes enviados** para ver los mensajes enviados.

### <a name="to-report-a-junk-email-message-from-within-an-opened-message"></a>Para notificar mensajes de correo electrónico no deseado desde un mensaje abierto

1. En un mensaje abierto, haga clic en el botón **Informar de correo electrónico no deseado** en la cinta del mensaje. Por ejemplo **, haga clic** \> en enviar **correo no** ![deseado en el informe de correo no deseado de un mensaje](../../media/EOP-Outlook-Junk-Reporting-Tool-4.jpg)

2. Aparecerá el cuadro de diálogo del **complemento de notificación de correo no deseado de Microsoft**. Si está seguro de que desea enviar el mensaje que ha seleccionado como no deseado, haga clic en **Sí**.
    ![Confirmar denuncia como no deseado](../../media/EOP-Outlook-Junk-Reporting-Tool-2.jpg)

    > [!NOTE]
    > Si no desea recibir un mensaje de confirmación al enviar mensajes de correo no deseado, active la casilla **No volver a mostrar este mensaje**.

El mensaje seleccionado se envía a Microsoft para su análisis y se mueve a la carpeta de correo no deseado. Para confirmar que el mensaje se ha enviado, abra la carpeta **Mensajes enviados** para ver el mensaje enviado.
