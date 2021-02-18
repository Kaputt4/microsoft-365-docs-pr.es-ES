---
title: Purga automática de cero horas (ZAP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre cómo la purga automática (ZAP) de cero horas puede mover retroactivamente los mensajes entregados en un buzón de Exchange Online a la carpeta de correo no deseado o a la cuarentena que se ha detectado retroactivamente como correo no deseado o suplantación de identidad.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5fd41cf45ad2a49d74684ae3e20dded5c1b8f034
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287310"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Purga automática de cero horas (ZAP) en Exchange Online

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a>Características básicas de ZAP

En organizaciones de Microsoft 365 con buzones en Exchange Online, la purga automática de cero horas (ZAP) es una característica de protección de correo electrónico que detecta y neutraliza retroactivamente mensajes de suplantación de identidad malintencionada, correo no deseado o malware que ya se han entregado a los buzones de Exchange Online.

ZAP no funciona en entornos independientes de Exchange Online Protection (EOP) que protegen los buzones de Exchange locales.

## <a name="how-zap-works"></a>Cómo funciona ZAP

Las firmas de correo no deseado y malware se actualizan diariamente en el servicio en tiempo real. Sin embargo, los usuarios pueden seguir recibiendo mensajes malintencionados por diversos motivos, incluido si el contenido se ha desatensado después de entregarlo a los usuarios. ZAP soluciona este problema supervisando continuamente las actualizaciones de las firmas de correo no deseado y malware en el servicio. ZAP puede buscar y quitar mensajes que ya están en el buzón de un usuario.

La acción ZAP es perfecta para el usuario; no se les notifica si se detecta y se mueve un mensaje.

[Las listas de remitentes](create-safe-sender-lists-in-office-365.md)seguros, las reglas de flujo de correo (también conocidas como reglas de transporte), las reglas de la Bandeja de entrada o los filtros adicionales tienen prioridad sobre ZAP. De forma similar a lo que sucede en el flujo de correo, esto significa que incluso si el servicio determina que el mensaje entregado necesita ZAP, el mensaje no se actúa debido a la configuración de remitentes seguros. Esta es otra razón para tener cuidado con la configuración de mensajes para omitir el filtrado.

### <a name="malware-zap"></a>Malware ZAP

Para **los mensajes leídos o no** leídos que se encuentran con malware después de la entrega, ZAP pone en cuarentena el mensaje que contiene los datos adjuntos de malware. Solo los administradores pueden ver y administrar mensajes de malware desde la cuarentena.

Zap de malware está habilitado de forma predeterminada en las directivas antimalware. Para obtener más información, vea [Configurar directivas antimalware en EOP.](configure-anti-malware-policies.md)

### <a name="phish-zap"></a>Phish ZAP

Para  los mensajes leídos o no leídos que se identifican como suplantación de identidad después de la entrega, el resultado de ZAP depende de la acción configurada para un veredicto de filtrado de correo electrónico de suplantación de identidad **(phishing)** en la directiva contra correo no deseado aplicable. Las acciones de veredicto de filtrado disponibles para la suplantación de identidad (phishing) y sus posibles resultados de ZAP se describen en la siguiente lista:

- **Agregar encabezado X**, **anteponer línea de asunto con texto:** ZAP no realiza ninguna acción en el mensaje.

- **Mover el mensaje a** correo no deseado: ZAP mueve el mensaje a la carpeta Correo no deseado, siempre y cuando la regla de correo no deseado esté habilitada en el buzón (está habilitada de forma predeterminada). Para obtener más información, vea [Configurar las opciones de correo no deseado en buzones de Exchange Online en Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

- **Redirigir el mensaje a la dirección de correo** electrónico , Eliminar **mensaje**, Mensaje **de cuarentena**: ZAP pone en cuarentena el mensaje.

De forma predeterminada, ZAP de suplantación de identidad  está habilitado en las directivas contra correo no deseado y la acción predeterminada para el veredicto de filtrado de correo electrónico de suplantación de identidad es cuarentena, lo que significa que ZAP de suplantación de identidad pone el mensaje en cuarentena de forma predeterminada.

Para obtener más información acerca de cómo configurar los veredictos de filtrado de correo no deseado, vea Configurar directivas contra correo no deseado [en Microsoft 365.](configure-your-spam-filter-policies.md)

### <a name="spam-zap"></a>ZAP de correo no deseado

Para los mensajes **no** leídos que se identifican como correo no deseado  después de la entrega, el resultado de ZAP depende de la acción configurada para el veredicto de filtrado de correo no deseado en la directiva contra correo no deseado aplicable. En la lista siguiente se describen las acciones de veredicto de filtrado disponibles para correo no deseado y sus posibles resultados de ZAP:

- **Agregar encabezado X**, **anteponer línea de asunto con texto:** ZAP no realiza ninguna acción en el mensaje.

- **Mover el mensaje a** correo no deseado: ZAP mueve el mensaje a la carpeta Correo no deseado, siempre y cuando la regla de correo no deseado esté habilitada en el buzón (está habilitada de forma predeterminada). Para obtener más información, vea [Configurar las opciones de correo no deseado en buzones de Exchange Online en Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

- **Redirigir el mensaje a la dirección de correo** electrónico , Eliminar **mensaje**, Mensaje **de cuarentena**: ZAP pone en cuarentena el mensaje. Los usuarios finales pueden ver y administrar sus propios mensajes de correo no deseado en cuarentena.

De forma predeterminada, ZAP de correo no deseado está  habilitado en las directivas contra correo no deseado y  la acción predeterminada para el veredicto de filtrado de correo no deseado es Mover mensaje a la carpeta correo no **deseado,** lo que significa que ZAP mueve mensajes no leídos a la carpeta correo no deseado de forma predeterminada.

Para obtener más información acerca de cómo configurar los veredictos de filtrado de correo no deseado, vea Configurar directivas contra correo no deseado [en Microsoft 365.](configure-your-spam-filter-policies.md)

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a>Consideraciones de ZAP para Microsoft Defender para Office 365

ZAP no pondrá en cuarentena ningún mensaje [](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) que se encuentra en el proceso de entrega dinámica en el examen de datos adjuntos seguros, o donde el filtrado de malware de EOP ya ha reemplazado los datos adjuntos por el archivo de Text.txtalerta **de malware.** Si se recibe una señal de suplantación de identidad (phishing) o correo no deseado para estos tipos de mensajes, y el veredicto de filtrado de la directiva contra correo no deseado está establecido para realizar alguna acción en el mensaje (Mover a correo no deseado, Redirigir, Eliminar o Cuarentena), ZAP tomará de forma predeterminada la acción "Mover a correo no deseado".

## <a name="how-to-see-if-zap-moved-your-message"></a>Cómo ver si ZAP movió el mensaje

Para determinar si ZAP movió el [](view-email-security-reports.md#threat-protection-status-report) mensaje, puede usar el informe de estado de protección contra amenazas o el Explorador de amenazas [(y detecciones en](threat-explorer.md)tiempo real). Tenga en cuenta que, como acción del sistema, ZAP no se registra en los registros de auditoría de buzones de Exchange.

## <a name="zap-faq"></a>Preguntas más frecuentes sobre ZAP

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>¿Qué sucede si se mueve un mensaje legítimo a la carpeta Correo no deseado?

Debe seguir el proceso normal de informes de [falsos positivos.](report-junk-email-messages-to-microsoft.md) La única razón por la que el mensaje se movía de la Bandeja de entrada a la carpeta correo no deseado sería porque el servicio determinó que el mensaje era correo no deseado o malintencionado.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>¿Qué ocurre si uso la carpeta Cuarentena en lugar de la carpeta Correo no deseado?

ZAP tomará medidas en un mensaje en función de la configuración de las directivas contra correo no deseado, tal como se describe anteriormente en este artículo.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>¿Qué ocurre si uso remitentes seguros, reglas de flujo de correo o listas de remitentes permitidos/bloqueados?

Los remitentes seguros, las reglas de flujo de correo o bloquear y permitir la configuración de la organización tienen prioridad. Estos mensajes se excluyen de ZAP, ya que el servicio está haciendo lo que ha configurado para hacer. Esta es otra razón para tener cuidado con la configuración de mensajes para omitir el filtrado.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>¿Qué ocurre si un mensaje se mueve a otra carpeta (por ejemplo, reglas de la Bandeja de entrada)?

ZAP sigue funcionando mientras no se haya eliminado el mensaje, o siempre que no se haya aplicado la misma acción, o mayor, aún. Por ejemplo, si la directiva contra suplantación de identidad está establecida en cuarentena y el mensaje ya está en el correo no deseado, ZAP tomará medidas para poner en cuarentena el mensaje.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>¿Cómo afecta ZAP a los buzones en retención?

ZAP no pone en cuarentena los mensajes de los buzones de correo en espera. ZAP puede mover mensajes a la carpeta de correo no deseado en función de la acción configurada para un veredicto de correo no deseado o de suplantación de identidad (phishing) en las directivas contra correo no deseado.

Para obtener más información acerca de las retenciones en Exchange Online, consulte Retención local y retención [por juicio en Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)
