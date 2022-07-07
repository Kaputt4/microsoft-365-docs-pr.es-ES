---
title: Informar de falsos positivos y falsos negativos en Outlook
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo notificar falsos positivos y falsos negativos en Outlook mediante la característica Mensaje de informe.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5955f6b5c4e376f296dcdad2d54a627bbcce04c3
ms.sourcegitcommit: 1734c95ce72d9c8af695cb4b49b1e40d921a1fee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2022
ms.locfileid: "66685687"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a>Informar de falsos positivos y falsos negativos en Outlook

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Si es administrador de una organización de Microsoft 365 con buzones de Exchange Online, se recomienda usar la página **Envíos** en el portal de Microsoft 365 Defender. Para obtener más información, consulte [Uso del portal envíos para enviar sospechas de correo no deseado, direcciones URL y archivos a Microsoft](admin-submission.md).

En las organizaciones de Microsoft 365 con buzones de correo en buzones de Exchange Online o locales mediante la autenticación moderna híbrida, puede enviar falsos positivos (buen correo electrónico que se bloqueó o envió a la carpeta de correo no deseado) y falsos negativos (correo electrónico no deseado o phish que se entregó a la bandeja de entrada) para Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Para obtener la mejor experiencia de envío de usuario, use el complemento Mensaje de informe o el complemento De suplantación de identidad de informe.

- El complemento Mensaje de informe y el complemento De suplantación de identidad de informe funcionan para Outlook en todas las plataformas (Outlook en la Web, iOS, Android y Escritorio).

- Si es administrador de una organización con buzones de Exchange Online, use el portal Envíos en el portal de Microsoft 365 Defender. Para obtener más información, consulte [Uso de Administración Envío para enviar sospechas de correo no deseado, fish, direcciones URL y archivos a Microsoft](admin-submission.md).

- Puede configurar para enviar mensajes directamente a Microsoft, un buzón que especifique o ambos. Para obtener más información, consulte [Directivas de envío de usuarios](user-submission.md).

- Para obtener más información sobre cómo obtener y habilitar el mensaje de informe o los complementos de suplantación de identidad de informe, vea [Habilitar el mensaje de informe o los complementos de suplantación de identidad de informe](enable-the-report-message-add-in.md).

- Para obtener más información sobre cómo informar de mensajes a Microsoft, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

Vea este breve vídeo para obtener información sobre cómo puede usar Microsoft Defender para Office 365 para investigar fácilmente los envíos de los usuarios para determinar el contenido de un mensaje y responder al envío aplicando la acción de corrección adecuada. 
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWBHof]

> [!IMPORTANT]
> Para ver los mensajes notificados a Microsoft en la pestaña <https://security.microsoft.com/reportsubmission>**Mensajes notificados** por el usuario en , no desactive la experiencia de informes integrada.

## <a name="use-the-report-message-feature"></a>Uso de la característica Mensaje de informe

### <a name="report-junk-and-phishing-messages"></a>Informar de mensajes no deseados y de suplantación de identidad

Para los mensajes de la Bandeja de entrada o de cualquier otra carpeta de correo electrónico excepto correo no deseado, use el siguiente método para notificar mensajes de spam y phishing:

1. Seleccione los puntos suspensivos **Más acciones** en la esquina superior derecha del mensaje seleccionado, seleccione **Mensaje** de informe en el menú desplegable y, a continuación, seleccione **Correo no deseado** o **Phishing**.

   :::image type="content" source="../../media/report-message-more-actions.png" alt-text="Icono Más acciones" lightbox="../../media/report-message-more-actions.png":::

   :::image type="content" source="../../media/report-message-junk-phishing.png" alt-text="Opción Correo no deseado y suplantación de identidad en el panel Mensaje de informe" lightbox="../../media/report-message-junk-phishing.png":::

2. Los mensajes seleccionados se enviarán a Microsoft para su análisis y:
   - Se ha movido a la carpeta Correo no deseado si se notificaron como correo no deseado.
   - Se eliminaron si se notificaron como suplantación de identidad (phishing).

### <a name="report-messages-that-are-not-junk"></a>Informar de mensajes que no son correo no deseado

1. Seleccione los puntos suspensivos **Más acciones** en la esquina superior derecha del mensaje seleccionado, seleccione **Mensaje** de informe en el menú desplegable y, a continuación, seleccione **No deseado**.

   :::image type="content" source="../../media/report-message-more-actions.png" alt-text="Icono que proporciona más acciones" lightbox="../../media/report-message-more-actions.png":::

   :::image type="content" source="../../media/report-message-not-junk.png" alt-text="La opción No no deseado en el panel Mensaje de informe" lightbox="../../media/report-message-not-junk.png":::

2. El mensaje seleccionado se enviará a Microsoft para su análisis y se moverá a la Bandeja de entrada o a cualquier otra carpeta especificada.

## <a name="view-and-review-reported-messages"></a>Visualización y revisión de los mensajes notificados

Para revisar los mensajes que los usuarios informan a Microsoft, tiene estas opciones:

- Use la página **Envíos** del portal de Microsoft 365 Defender. Para obtener más información, vea [Ver envíos de usuarios a Microsoft](admin-submission.md#view-user-submissions-to-microsoft).
- Cree una regla de flujo de correo (también conocida como regla de transporte) para enviar copias de los mensajes notificados. Para obtener instrucciones, consulte [Uso de reglas de flujo de correo para ver qué usuarios informan a Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).
