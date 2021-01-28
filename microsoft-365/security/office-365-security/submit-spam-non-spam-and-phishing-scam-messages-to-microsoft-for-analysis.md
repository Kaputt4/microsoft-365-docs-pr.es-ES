---
title: Enviar manualmente mensajes a Microsoft para su análisis
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
description: Los administradores y los usuarios finales pueden aprender a enviar mensajes de correo electrónico (correo bueno marcado como correo no deseado o no permitido) a Microsoft para su análisis.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d5d3b7a51c39b85af8a6fae84f525da6d806789c
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029589"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Enviar manualmente mensajes a Microsoft para su análisis

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Si es administrador de una organización con buzones de Exchange Online, le recomendamos que use el portal de envíos en el Centro de & cumplimiento. Para obtener más información, vea Usar envío de administrador para enviar correos sospechosos de correo no [deseado, phishing, direcciones URL y archivos a Microsoft.](admin-submission.md)

Puede resultar frustrante cuando los usuarios de su organización reciben mensajes de correo no deseado o mensajes de suplantación de identidad en su Bandeja de entrada, o si no reciben un mensaje de correo electrónico legítimo porque está marcado como correo no deseado. Estamos ajustando constantemente nuestros filtros de correo no deseado para que sean más precisos.

Usted y sus usuarios pueden ayudar a este proceso enviando falsos positivos (correo electrónico bueno marcado como falso), falsos negativos (correo no deseado permitido) y mensajes de suplantación de identidad a Microsoft para su análisis.

> [!NOTE]
> Debido al gran volumen de envíos que recibimos, es posible que no podamos responder a todas las solicitudes de análisis.

## <a name="submit-false-negatives-to-microsoft"></a>Enviar falsos negativos a Microsoft

> [!TIP]
> En lugar de usar los siguientes procedimientos para informar de falsos negativos, los usuarios de Outlook y Outlook en la Web (anteriormente conocidos como Outlook Web App) pueden usar el complemento de mensaje de informe o el complemento de suplantación de identidad de informes. Para obtener información acerca de cómo [](enable-the-report-message-add-in.md) instalar y usar estas herramientas, vea Habilitar el complemento De informe de mensajes y Habilitar el complemento de suplantación de identidad [de informes.](enable-the-report-phish-add-in.md)

Si recibe un mensaje que pasó por el filtrado de correo no deseado que debería haber sido identificado como correo no deseado o suplantación de identidad, puede enviar el mensaje a los equipos de análisis de correo no deseado de Microsoft y análisis de suplantación de identidad de Microsoft según corresponda. Los analistas revisarán el mensaje y lo agregarán a los filtros de todo el servicio si cumplen los criterios de clasificación.

1. Cree un nuevo mensaje de correo electrónico en blanco con uno de los siguientes destinatarios:

   - **Correo no deseado:**`junk@office365.microsoft.com`

   - **Suplantación de identidad**: `phish@office365.microsoft.com`

2. Arrastre y coloque el mensaje de correo no deseado o de suplantación de identidad en el nuevo mensaje. Esto guardará el mensaje de correo no deseado o de suplantación de identidad (phishing) como datos adjuntos en el nuevo mensaje. No copie ni pegue el contenido del mensaje ni reenvía el mensaje (necesitamos el mensaje original para que podamos inspeccionar los encabezados del mensaje).

   > [!NOTE]
   >
   > - Puede adjuntar varios mensajes en el nuevo mensaje. Asegúrese de que todos los mensajes son del mismo tipo: mensajes de suplantación de identidad o mensajes de correo no deseado.
   >
   > - Deje el cuerpo del nuevo mensaje en blanco.
   >
   > - Use los formatos .msg (formato predeterminado de Outlook) o .eml (formato predeterminado de Outlook en la Web) para los mensajes adjuntos.

3. Cuando haya terminado, haga clic en **Enviar**.

> [!TIP]
> Los administradores tienen varias formas diferentes de bloquear mensajes específicos que se están identificar erróneamente como correo no deseado. Para obtener más información, vea [Crear listas de remitentes bloqueados en EOP.](create-block-sender-lists-in-office-365.md)

## <a name="submit-false-positives-to-microsoft"></a>Enviar falsos positivos a Microsoft

> [!TIP]
> En lugar de usar los siguientes procedimientos para informar de falsos positivos, los usuarios de Outlook y Outlook en la Web (anteriormente conocidos como Outlook Web App) pueden usar el complemento de mensaje de informe o el complemento de suplantación de identidad de informes. Para obtener información acerca de cómo [](enable-the-report-message-add-in.md) instalar y usar estas herramientas, vea Habilitar el complemento Mensaje de informe y Habilitar el complemento de suplantación de identidad [de informes.](enable-the-report-phish-add-in.md)


Si un mensaje se identificó incorrectamente como correo no deseado, puede enviarlo al equipo de análisis de correo no deseado de Microsoft. Los analistas evaluarán el mensaje y, según los resultados del análisis, los filtros de todo el servicio se pueden ajustar para permitir que pase el mensaje.

1. Cree un nuevo mensaje de correo electrónico en blanco `not_junk@office365.microsoft.com` con el destinatario:

2. Arrastre y coloque el mensaje identificado erróneamente en el nuevo mensaje. Esto guardará el mensaje identificado erróneamente como datos adjuntos en el nuevo mensaje. No copie ni pegue el contenido del mensaje ni reenvía el mensaje (necesitamos el mensaje original para que podamos inspeccionar los encabezados del mensaje).

   > [!NOTE]
   >
   > - Puede adjuntar varios mensajes en el nuevo mensaje. Asegúrese de que todos los mensajes son del mismo tipo: mensajes de suplantación de identidad o mensajes de correo no deseado.
   >
   > - Deje el cuerpo del nuevo mensaje en blanco.
   >
   > - Use los formatos .msg (formato predeterminado de Outlook) o .eml (formato predeterminado de Outlook en la Web) para los mensajes adjuntos.

3. Cuando haya terminado, haga clic en **Enviar**.

> [!TIP]
> Los administradores tienen varias formas diferentes de permitir que mensajes específicos omitan el filtrado de correo no deseado. Para obtener más información, [vea Crear listas de remitentes seguros en EOP.](create-safe-sender-lists-in-office-365.md)

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a>¿Dónde se almacenan los datos de los envíos a Microsoft?

Los datos residen en el límite de cumplimiento de Office 365 en los centros de datos de Norteamérica. Los analistas del equipo de ingeniería revisan los datos para ayudar a mejorar la eficacia de los filtros.

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Crear una regla de flujo de correo para recibir copias de los mensajes que se notifican a Microsoft

Para obtener instrucciones, consulte Usar reglas de flujo de correo para ver lo que los [usuarios están informando a Microsoft.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)
