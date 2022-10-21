---
title: Informar de correo no deseado, no correo no deseado, phishing, correos electrónicos y archivos sospechosos a Microsoft
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- m365-security
description: Cómo notificar un correo electrónico o un archivo sospechosos a Microsoft? Informe de mensajes, direcciones URL, datos adjuntos de correo electrónico y archivos a Microsoft para su análisis. Aprenda a notificar correos electrónicos no deseados y correos electrónicos de suplantación de identidad (phishing).
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 3d27b7d3e76454245c7d429fc025237b1c84f690
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68662981"
---
# <a name="how-do-i-report-a-suspicious-email-or-file-to-microsoft"></a>Cómo notificar un correo electrónico o un archivo sospechosos a Microsoft?

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

¿Se pregunta qué hacer con correos electrónicos o archivos sospechosos? En las organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin Exchange Online buzones de correo, *los usuarios* y administradores tienen diferentes *maneras* de notificar un mensaje de correo electrónico sospechoso, una dirección URL o datos adjuntos de correo electrónico a Microsoft.

Además, las organizaciones de Microsoft 365 con administradores de Microsoft Defender para punto de conexión también tienen varios métodos para informar de archivos.

Vea este vídeo que muestra más información sobre la experiencia de envíos unificados.
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE50HhM]

## <a name="report-a-suspicious-email-to-microsoft"></a>Notificar un correo electrónico sospechoso a Microsoft

|Método|Tipo de envío|Descripción|
|---|---|---|
|[Uso del portal envíos para enviar datos adjuntos sospechosos de correo no deseado, correo no deseado, direcciones URL y correo electrónico a Microsoft](admin-submission.md)|Admin|Método de informes recomendado para administradores de organizaciones con buzones de Exchange Online (no disponible en EOP independiente).|
|[Habilitar los complementos Informar de mensajes o Informar de phishing](enable-the-report-message-add-in.md)|User|Funciona con Outlook y Outlook en la Web (anteriormente conocido como Outlook Web App). <br/><br/> En función de la suscripción, los mensajes que los usuarios notificaron con los complementos están disponibles en [el portal de envíos de Administración](admin-submission.md), [los resultados de investigación y respuesta automatizadas (AIR](air-view-investigation-results.md)), el [informe de mensajes notificados](view-email-security-reports.md#user-reported-messages-report) por el usuario y [el Explorador](threat-explorer-views.md#email--submissions). <br/><br/> Puede configurar los mensajes notificados para copiarlos o redirigirlos a un buzón que especifique. Para obtener más información, consulte [Directivas de envío de usuarios](user-submission.md).
|[Informar de falsos positivos y falsos negativos en Outlook](report-false-positives-and-false-negatives.md)|User|Envíe falsos positivos (correo electrónico correcto que se bloqueó o envió a la carpeta de correo no deseado) y falsos negativos (correo electrónico no deseado o phishing que se entregó en la bandeja de entrada) a Exchange Online Protection (EOP) mediante la característica Notificar mensaje.|
|[Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|Admin|Obtenga información sobre cómo crear una regla de flujo de correo (también conocida como regla de transporte) que le notifique cuando los usuarios informen de mensajes a Microsoft para su análisis.|
|[Enviar archivos para su análisis](../intelligence/submission-guide.md)|Admin|Envíe datos adjuntos de correo electrónico y otros archivos sospechosos a Microsoft para su análisis.|

> [!NOTE]
> Al informar de una entidad de correo electrónico a Microsoft, copiamos todo lo asociado al correo electrónico para incluirla en nuestras revisiones continuas de algoritmos. Esta copia incluye el contenido del correo electrónico, los encabezados de correo electrónico y los datos relacionados sobre el enrutamiento de correo electrónico. También se incluyen los datos adjuntos de los mensajes.
>
> Microsoft trata sus comentarios como permiso de su organización para que analicemos toda la información descrita anteriormente para ajustar los algoritmos de higiene de mensajes. Guardamos su mensaje en nuestros centros de datos auditados seguros en ee. UU. El envío se elimina a más tardar 30 días después de que usted nos lo proporcione. El personal de Microsoft podría leer los mensajes enviados y los datos adjuntos, que normalmente no se permiten para el correo electrónico en Microsoft 365. Sin embargo, su correo electrónico sigue siendo tratado como confidencial entre usted y Microsoft, y no proporcionaremos su correo electrónico o datos adjuntos a ninguna otra parte como parte del proceso de revisión.
