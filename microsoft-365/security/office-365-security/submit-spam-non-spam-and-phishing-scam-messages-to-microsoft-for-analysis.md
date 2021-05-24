---
title: Enviar mensajes manualmente a Microsoft para su análisis
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Los administradores y los usuarios finales pueden aprender a enviar mensajes de correo electrónico (correo bueno marcado como correo malo o mal permitido) a Microsoft para su análisis.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9c3a02c710472a996245a38d996ff4485efd1748
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624030"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Enviar mensajes manualmente a Microsoft para su análisis

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Si es administrador de una organización con buzones de correo Exchange Online, le recomendamos que use el portal de envíos en el Centro de seguridad & cumplimiento. Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

Puede ser frustrante cuando los usuarios de la organización reciben mensajes de correo no deseado o mensajes de suplantación de identidad en su Bandeja de entrada, o si no reciben un mensaje de correo electrónico legítimo porque está marcado como correo no deseado. Estamos ajustando constantemente nuestros filtros de correo no deseado para que sean más precisos.

Usted y sus usuarios pueden ayudar a este proceso enviando falsos positivos (buen correo electrónico marcado como malo), falsos negativos (correo no permitido) y mensajes de suplantación de identidad a Microsoft para su análisis.

> [!NOTE]
> Debido al gran volumen de envíos que recibimos, es posible que no podamos responder a todas las solicitudes de análisis.

## <a name="submit-false-negatives-to-microsoft"></a>Enviar falsos negativos a Microsoft

> [!TIP]
> En lugar de usar los siguientes procedimientos para notificar falsos negativos, los usuarios de Outlook y Outlook en la web (anteriormente conocidos como Outlook Web App) pueden usar el complemento Report Message o el complemento Report Phishing. Para obtener información sobre cómo instalar y usar estas herramientas, vea [Enable the Report Message add-in](enable-the-report-message-add-in.md) and Enable the Report [Phishing add-in](enable-the-report-phish-add-in.md).

Si recibe un mensaje que pasó por el filtrado de correo no deseado que debería haber sido identificado como correo no deseado o phishing, puede enviar el mensaje a los equipos análisis de correo no deseado de Microsoft y Análisis de suplantación de identidad de Microsoft según corresponda. Los analistas revisarán el mensaje y lo agregarán a los filtros de todo el servicio si cumple los criterios de clasificación.

1. Cree un nuevo mensaje de correo electrónico en blanco con uno de los siguientes destinatarios:

   - **Correo no deseado**: `junk@office365.microsoft.com`
   - **Phishing**: `phish@office365.microsoft.com`

2. Arrastre y coloque el mensaje de correo no deseado o suplantación de identidad en el nuevo mensaje. Esto guardará el mensaje de correo no deseado o suplantación de identidad como datos adjuntos en el nuevo mensaje. No copie y pegue el contenido del mensaje o reenvía el mensaje (necesitamos el mensaje original para poder inspeccionar los encabezados del mensaje).

   > [!NOTE]
   >
   > - Puede adjuntar varios mensajes en el nuevo mensaje. Asegúrese de que todos los mensajes son del mismo tipo: mensajes de suplantación de identidad (phishing) o mensajes de correo no deseado.
   > - Deje el cuerpo del nuevo mensaje en blanco.
   > - Use los formatos .msg (Outlook predeterminado) o .eml (Outlook predeterminado en el formato web) para los mensajes adjuntos.

3. Cuando haya terminado, haga clic en **Enviar**.

> [!TIP]
> Los administradores tienen varias formas diferentes de bloquear mensajes específicos que se están identificación erróneamente como correo no deseado. Para obtener más información, vea [Crear listas de remitentes bloqueados en EOP](create-block-sender-lists-in-office-365.md).

## <a name="submit-false-positives-to-microsoft"></a>Enviar falsos positivos a Microsoft

> [!TIP]
> En lugar de usar los siguientes procedimientos para notificar falsos positivos, los usuarios de Outlook y Outlook en la web (anteriormente conocidos como Outlook Web App) pueden usar el complemento Report Message o el complemento Report Phishing. Para obtener información sobre cómo instalar y usar estas herramientas, vea [Enable the Report Message add-in](enable-the-report-message-add-in.md) and Enable the Report [Phishing add-in](enable-the-report-phish-add-in.md).

Si un mensaje se identificó incorrectamente como correo no deseado, puede enviar el mensaje al equipo de análisis de correo no deseado de Microsoft. Los analistas evaluarán el mensaje y (según los resultados del análisis) los filtros de todo el servicio se pueden ajustar para permitir que el mensaje pase.

1. Cree un nuevo mensaje de correo electrónico en blanco `not_junk@office365.microsoft.com` con como destinatario.

2. Arrastre y coloque el mensaje no identificado en el nuevo mensaje. Esto guardará el mensaje no identificado como datos adjuntos en el nuevo mensaje. No copie y pegue el contenido del mensaje o reenvía el mensaje (necesitamos el mensaje original para poder inspeccionar los encabezados del mensaje).

   > [!NOTE]
   >
   > - Puede adjuntar varios mensajes en el nuevo mensaje. Asegúrese de que todos los mensajes son del mismo tipo: mensajes de suplantación de identidad (phishing) o mensajes de correo no deseado.
   > - Deje el cuerpo del nuevo mensaje en blanco.
   > - Use los formatos .msg (Outlook predeterminado) o .eml (Outlook predeterminado en el formato web) para los mensajes adjuntos.

3. Cuando haya terminado, haga clic en **Enviar**.

> [!TIP]
> Los administradores tienen varias formas diferentes de permitir que mensajes específicos omitan el filtrado de correo no deseado. Para obtener más información, vea [Crear listas de remitentes seguros en EOP](create-safe-sender-lists-in-office-365.md).

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a>¿Dónde se almacenan los datos de los envíos a Microsoft?

Los datos residen en el límite Office 365 cumplimiento normativo en los centros de datos de Norteamérica. Los analistas del equipo de ingeniería revisan los datos para ayudar a mejorar la eficacia de los filtros.

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Crear una regla de flujo de correo para recibir copias de los mensajes que se notifican a Microsoft

Para obtener instrucciones, vea [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).
