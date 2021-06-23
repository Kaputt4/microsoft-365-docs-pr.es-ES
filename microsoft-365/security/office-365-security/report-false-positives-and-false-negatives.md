---
title: Informar de falsos positivos y falsos negativos en Outlook
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo notificar falsos positivos y falsos negativos en Outlook la característica Mensaje de informe.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 458e7d16e2614e7bac3a0aac5a4310e6353ab569
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082929"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a>Informar de falsos positivos y falsos negativos en Outlook

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Si es administrador de una organización Microsoft 365 con buzones de correo Exchange Online, se recomienda usar la página **Envíos** en el portal de Microsoft 365 Defender. Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

En las organizaciones de Microsoft 365 con buzones en buzones de Exchange Online o locales mediante autenticación moderna híbrida, puede enviar falsos positivos (correo electrónico bueno bloqueado o enviado a la carpeta no deseado) y falsos negativos (correo electrónico no deseado o suplantación de identidad que se entregó a la bandeja de entrada) a Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Para obtener la mejor experiencia de envío de usuario, use el complemento Report Message o el complemento Report Phishing.

  > [!IMPORTANT]
  > La experiencia integrada para informar de correo no deseado o suplantación de identidad en Outlook no puede usar la [directiva de envío de usuario](./user-submission.md). Se recomienda usar el complemento Report Message o el complemento Report Phishing en su lugar.

- El complemento Report Message y el complemento Report Phishing funcionan para Outlook en todas las plataformas (Outlook en la Web, iOS, Android y Escritorio).

- Si es administrador de una organización con buzones de correo Exchange Online, use el portal de envíos en el portal de Microsoft 365 Defender web. Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

- Puede configurar para enviar mensajes directamente a Microsoft, un buzón que especifique o ambos. Para obtener más información, vea [Directivas de envío de usuarios](user-submission.md).

- Para obtener más información sobre cómo obtener y habilitar el mensaje de informe o los complementos de suplantación de identidad de informes, vea Habilitar el mensaje de informe o los complementos de suplantación [de identidad de informe](enable-the-report-message-add-in.md).

- Para obtener más información acerca de cómo notificar mensajes a Microsoft, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="use-the-report-message-feature"></a>Usar la característica Mensaje de informe

### <a name="report-junk-and-phishing-messages"></a>Notificar mensajes de correo no deseado y suplantación de identidad

Para los mensajes de la Bandeja de entrada o cualquier otra carpeta de correo electrónico excepto correo no deseado, use el siguiente método para notificar mensajes de correo no deseado y suplantación de identidad:

1. Seleccione los **puntos suspensivos** Más acciones en la  esquina superior derecha del mensaje seleccionado, seleccione Informar del mensaje en el menú desplegable y, a continuación, seleccione Correo no deseado **o** **Suplantación de identidad**.

   ![Mensaje de informe: más acciones](../../media/report-message-more-actions.png)

   ![Mensaje de informe: correo no deseado y suplantación de identidad](../../media/report-message-junk-phishing.png)

2. Los mensajes seleccionados se enviarán a Microsoft para su análisis y:
   - Se ha movido a la carpeta correo no deseado si se han notificado como correo no deseado.
   - Se elimina si se han notificado como suplantación de identidad.

### <a name="report-messages-that-are-not-junk"></a>Informar de mensajes que no son correo no deseado

1. Seleccione los **puntos suspensivos** Más acciones en la  esquina superior derecha del mensaje seleccionado, seleccione Informar mensaje en el menú desplegable y, a continuación, **seleccione No deseado**.

   ![Mensaje de informe: más acciones](../../media/report-message-more-actions.png)

   ![Mensaje de informe: no deseado](../../media/report-message-not-junk.png)

2. El mensaje seleccionado se enviará a Microsoft para su análisis y se trasladará a la Bandeja de entrada o a cualquier otra carpeta especificada.

## <a name="view-and-review-reported-messages"></a>Ver y revisar los mensajes notificados

Para revisar los mensajes que los usuarios informan a Microsoft, tiene estas opciones:

- Use la **página Envíos** en el Microsoft 365 Defender portal. Para obtener más información, vea [Ver envíos de usuarios a Microsoft](admin-submission.md#view-user-submissions-to-microsoft).
- Cree una regla de flujo de correo (también conocida como regla de transporte) para enviar copias de los mensajes notificados. Para obtener instrucciones, vea [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).
