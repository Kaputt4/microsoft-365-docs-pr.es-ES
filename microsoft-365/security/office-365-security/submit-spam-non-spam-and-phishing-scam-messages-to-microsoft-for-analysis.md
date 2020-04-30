---
title: Enviar mensajes a Microsoft de forma manual para su análisis
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'Usted y sus usuarios pueden enviar mensajes de correo no deseado falsos negativos y falsos positivos a Microsoft para su análisis. '
ms.openlocfilehash: 928809a8d00e082bf3150abb27dc493c2b82c070
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939432"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Enviar mensajes a Microsoft de forma manual para su análisis

> [!NOTE]
> Si es administrador de una organización de Microsoft 365 con buzones de correo de Exchange Online, le recomendamos que use el portal de envíos del centro de seguridad & cumplimiento. Para obtener más información, vea [usar el envío de administración para enviar un correo no deseado, phish, direcciones URL y archivos sospechosos a Microsoft](admin-submission.md).

Puede resultar frustrante cuando los usuarios de la organización reciben mensajes de correo no deseado o mensajes de suplantación de identidad (phishing) en su bandeja de entrada, o si no reciben un mensaje de correo electrónico legítimo porque está marcado como correo no deseado. Estamos ajustando constantemente los filtros de correo no deseado para que sean más precisos.

Usted y sus usuarios pueden ayudar a este proceso mediante el envío de falsos positivos (correo electrónico bueno marcado como no válido), los falsos negativos (correo erróneo permitido) y los mensajes de suplantación de identidad a Microsoft para su análisis.

> [!NOTE]
> Debido al elevado volumen de envíos que recibimos, es posible que no podamos contestar todas las solicitudes de análisis.

## <a name="submit-false-negatives-to-microsoft"></a>Enviar falsos negativos a Microsoft

> [!TIP]
> En lugar de usar los siguientes procedimientos para informar sobre falsos negativos, los usuarios de Outlook y Outlook en la web (anteriormente conocido como Outlook Web App) pueden usar el complemento de mensajes de informe para Microsoft Outlook. Para obtener información sobre cómo instalar y usar esta herramienta, consulte [Habilitar el complemento de mensajes de informe](enable-the-report-message-add-in.md).

Si recibe un mensaje que pasa a través del filtrado de correo no deseado que debería haberse identificado como correo no deseado o suplantación de identidad, puede enviar el mensaje a Microsoft spam Analysis y Microsoft phishing Analysis Teams según corresponda. Los analistas revisarán el mensaje y lo agregarán a los filtros de todo el servicio si cumple con los criterios de clasificación.

1. Cree un mensaje de correo electrónico nuevo en blanco con uno de los siguientes destinatarios:

   - **Correo no deseado**:`junk@office365.microsoft.com`

   - **Suplantación de identidad**:`phish@office365.microsoft.com`

2. Arrastre y coloque el mensaje no deseado o de suplantación de identidad en el nuevo mensaje. Se guardará el mensaje no deseado o de suplantación de identidad (phishing) como datos adjuntos en el nuevo mensaje. No copie y pegue el contenido del mensaje o lo reenvíe (necesitamos el mensaje original para que podamos inspeccionar los encabezados del mensaje).

   > [!NOTE]
   > <ul><li>Puede adjuntar varios mensajes en el nuevo mensaje. Asegúrese de que todos los mensajes sean del mismo tipo: mensajes de suplantación de identidad (phishing) o mensajes de correo electrónico no deseado.</li><li>Deje el cuerpo del nuevo mensaje en blanco.</li><li>Use cualquiera de los formatos. msg (formato predeterminado de Outlook) o. eml (formato predeterminado de Outlook en la web) para los mensajes adjuntos.</li></ul>

3. Cuando haya terminado, haga clic en **Enviar**.

> [!TIP]
> Los administradores tienen varias formas diferentes de bloquear mensajes específicos que se identifican como correo no deseado. Para obtener más información, vea [crear listas de remitentes bloqueados en Office 365](create-block-sender-lists-in-office-365.md).

## <a name="submit-false-positives-to-microsoft"></a>Enviar falsos positivos a Microsoft

> [!TIP]
> En lugar de usar los siguientes procedimientos para notificar falsos positivos, los usuarios de Outlook y Outlook en la web pueden usar el complemento de mensajes de informe para Microsoft Outlook. Para obtener información sobre cómo instalar y usar esta herramienta, consulte [Habilitar el complemento de mensajes de informe](enable-the-report-message-add-in.md).

Si un mensaje se identificó incorrectamente como correo no deseado, puede enviar el mensaje al equipo de análisis de correo no deseado de Microsoft. Los analistas evaluarán el mensaje y (según los resultados del análisis) se pueden ajustar los filtros de todo el servicio para permitir el paso del mensaje.

1. Cree un nuevo mensaje de correo electrónico en `not_junk@office365.microsoft.com` blanco con como destinatario:

2. Arrastre y coloque el mensaje con identificación indebido en el nuevo mensaje. De este modo, se guardará el mensaje identificado indebido como datos adjuntos en el nuevo mensaje. No copie y pegue el contenido del mensaje o lo reenvíe (necesitamos el mensaje original para que podamos inspeccionar los encabezados del mensaje).

   > [!NOTE]
   > <ul><li>Puede adjuntar varios mensajes en el nuevo mensaje. Asegúrese de que todos los mensajes sean del mismo tipo: mensajes de suplantación de identidad o mensajes de correo electrónico no deseado.</li><li>Deje el cuerpo del nuevo mensaje en blanco.</li><li>Use cualquiera de los formatos. msg (formato predeterminado de Outlook) o. eml (formato predeterminado de Outlook en la web) para los mensajes adjuntos.</li></ul>

3. Cuando haya terminado, haga clic en **Enviar**.

> [!TIP]
> Los administradores tienen varias formas diferentes de permitir que mensajes específicos omitan el filtrado de correo no deseado. Para obtener más información, consulte [crear listas de remitentes seguros en Office 365](create-safe-sender-lists-in-office-365.md).

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Crear una regla de flujo de correo para recibir copias de mensajes que se notifican a Microsoft

Para obtener instrucciones, vea [usar reglas de flujo de correo para ver qué están notificando los usuarios a Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).
