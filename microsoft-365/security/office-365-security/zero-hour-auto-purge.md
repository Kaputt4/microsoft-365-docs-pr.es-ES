---
title: 'Depuración automática de cero horas (ZAP): característica de protección de correo electrónico'
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
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
description: Obtenga información sobre la purga automática de cero horas (ZAP), una característica de protección de correo electrónico de Microsoft 365 que detecta mensajes de correo no deseado, malware o de suplantación de identidad (phishing) que ya se han entregado a Exchange Online.
ms.openlocfilehash: ba7aa74dd9152990ce327d1b1564c3246d15cbb8
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173303"
---
# <a name="zero-hour-auto-purge-zap---protection-against-spam-and-malware-in-microsoft-365"></a>Depuración automática de cero horas (ZAP): protección contra correo no deseado y malware en Microsoft 365

## <a name="overview"></a>Información general

La purga automática de cero horas (ZAP) es una característica de protección de correo electrónico de Microsoft 365 que detecta y neutraliza de forma retroactiva y neutraliza los mensajes malintencionados de suplantación de identidad, correo no deseado o malware que ya se han entregado a los buzones de Exchange Online.

ZAP está disponible con la protección de Exchange Online (EOP) predeterminada que se incluye con cualquier suscripción a Microsoft 365 que contenga buzones de correo de Exchange Online. ZAP no funciona en entornos de EOP independientes que protejan los buzones de correo de Exchange local.

## <a name="how-zap-works"></a>Cómo funciona el ZAP

Microsoft 365 actualiza las firmas de correo no deseado y malware en tiempo real a diario. Sin embargo, los usuarios aún pueden recibir mensajes malintencionados por diversos motivos, incluso si el contenido se ha armado después de que se entregue a los usuarios. ZAP soluciona este problema al supervisar continuamente las actualizaciones de las firmas de correo no deseado y malware de Microsoft 365. ZAP puede buscar y eliminar mensajes que ya están en el buzón de un usuario.

La acción ZAP es fluida para el usuario; no se notifican si un mensaje se ha detectado y movido.

Las [listas de remitentes seguros](create-safe-sender-lists-in-office-365.md), las reglas de flujo de correo (también conocidas como reglas de transporte), las reglas de bandeja de entrada o los filtros adicionales tienen prioridad sobre Zap. De forma similar a lo que sucede en el flujo de correo, esto significa que incluso si el servicio determina que el mensaje entregado necesita ZAP, el mensaje no se ha realizado con la configuración de remitentes seguros. Este es otro motivo para tener cuidado con la configuración de mensajes para omitir el filtrado.

### <a name="malware-zap"></a>ZAP de malware

En el caso de **los mensajes leídos o no leídos** que contienen malware después de la entrega, ZAP pone en cuarentena el mensaje que contiene los datos adjuntos de malware. Solo los administradores pueden ver y administrar los mensajes de malware desde la cuarentena.

ZAP de malware está habilitado de forma predeterminada en las directivas antimalware. Para obtener más información, vea [Configure anti-malware policies in Microsoft 365](configure-anti-malware-policies.md).

### <a name="phish-zap"></a>ZAP de phish

En el caso de **los mensajes leídos o no leídos** que se identifican como phish tras la entrega, el resultado de zap depende de la acción configurada para un veredicto de filtrado de **correo de suplantación de identidad** en la Directiva contra correo no deseado aplicable. En la lista siguiente se describen las acciones de veredicto disponibles para el filtrado de phish y sus posibles resultados de ZAP:

- **Agregar encabezado X**, **anteponer la línea de asunto con el texto**: Zap no realiza ninguna acción en el mensaje.

- **Mover mensaje a correo no deseado**: Zap mueve el mensaje a la carpeta de correo no deseado, siempre y cuando la regla de correo no deseado esté habilitada en el buzón (está habilitada de forma predeterminada). Para obtener más información, consulte [configurar la configuración del correo electrónico no deseado en buzones de Exchange online en Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Redirigir el mensaje a la dirección de correo electrónico**, **eliminar mensaje**, **poner en cuarentena**el mensaje: Zap pone en cuarentena el mensaje. Solo los administradores pueden ver y administrar los mensajes de phish en cuarentena.

De forma predeterminada, la opción ZAP de phish está habilitada en las directivas contra correo no deseado y la acción predeterminada para el veredicto del filtrado de **correo de phishing** es el **mensaje en cuarentena**, lo que significa que el Zap de phish pone en cuarentena el mensaje de forma predeterminada.

Para obtener más información acerca de cómo configurar los veredictos de filtrado de correo no deseado, vea [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="spam-zap"></a>ZAP de correo no deseado

Para **los mensajes no leídos** que se identifican como correo no deseado después de la entrega, el resultado de zap depende de la acción configurada para el veredicto filtrado de **correo no deseado** en la Directiva de correo no deseado aplicable. En la lista siguiente se describen las acciones de veredicto de filtrado disponibles para el correo no deseado y sus posibles resultados de ZAP:

- **Agregar encabezado X**, **anteponer la línea de asunto con el texto**: Zap no realiza ninguna acción en el mensaje.

- **Mover mensaje a correo no deseado**: Zap mueve el mensaje a la carpeta de correo no deseado, siempre y cuando la regla de correo no deseado esté habilitada en el buzón (está habilitada de forma predeterminada). Para obtener más información, consulte [configurar la configuración del correo electrónico no deseado en buzones de Exchange online en Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Redirigir el mensaje a la dirección de correo electrónico**, **eliminar mensaje**, **poner en cuarentena**el mensaje: Zap pone en cuarentena el mensaje. Los usuarios finales pueden ver y administrar sus propios mensajes de correo electrónico no deseado en cuarentena.

De forma predeterminada, la ZAP de correo no deseado está habilitada en las directivas contra correo no deseado y la acción predeterminada para el veredicto del filtrado de **correo no** deseado es **mover el mensaje a**la carpeta de correo no deseado, lo que significa que el Zap mueve los mensajes no **leídos** a la carpeta correo electrónico no deseado de forma predeterminada.

Para obtener más información acerca de cómo configurar los veredictos de filtrado de correo no deseado, vea [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="zap-considerations-for-office-365-advanced-threat-protection-atp"></a>Consideraciones de ZAP para la protección contra amenazas avanzada de Office 365 (ATP)

ZAP no pondrá en cuarentena ningún mensaje que se encuentre en el proceso de análisis de [entregas dinámicos](dynamic-delivery-and-previewing.md) o donde el filtrado de malware ya haya reemplazado los datos adjuntos con el archivo **Text. txt de alerta de malware** . Si se recibe una señal de phish o correo no deseado para estos tipos de mensajes y se establece el veredicto de filtrado en la Directiva contra correo no deseado para realizar alguna acción en el mensaje (mover a correo no deseado, redirigir, eliminar, cuarentena), el valor de ZAP será la acción "migrar a correo no deseado".

## <a name="how-to-see-if-zap-moved-your-message"></a>Cómo ver si el ZAP movió el mensaje

Para determinar si la ZAP movió el mensaje, puede usar el informe de estado de la [protección contra amenazas](view-email-security-reports.md#threat-protection-status-report) o el [Explorador de amenazas (y detecciones en tiempo real)](threat-explorer.md). Tenga en cuenta que, como acción del sistema, ZAP no se registra en los registros de auditoría de buzones de Exchange.

## <a name="zap-faq"></a>PREGUNTAS MÁS FRECUENTES SOBRE ZAP

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>¿Qué sucede si un mensaje legítimo se mueve a la carpeta de correo electrónico no deseado?

Debe seguir el proceso normal de informes para [falsos positivos](report-junk-email-messages-to-microsoft.md). La única razón por la que el mensaje se movería de la bandeja de entrada a la carpeta de correo electrónico no deseado sería porque el servicio determinó que el mensaje era correo no deseado o malintencionado.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>¿Qué ocurre si utilizo la carpeta cuarentena en lugar de la carpeta correo no deseado?

ZAP realizará una acción en un mensaje en función de la configuración de las directivas contra correo electrónico no deseado, como se ha descrito anteriormente en este tema.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>¿Qué sucede si estoy usando remitentes seguros, reglas de flujo de correo o listas de remitentes permitidos o bloqueados?

Los remitentes seguros, reglas de flujo de correo o bloquear y permitir la configuración de la organización tienen prioridad. Estos mensajes se excluyen de ZAP, ya que el servicio hace lo que lo configuró. Este es otro motivo para tener cuidado con la configuración de mensajes para omitir el filtrado.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>¿Qué ocurre si un mensaje se mueve a otra carpeta (por ejemplo, reglas de la bandeja de entrada)?

ZAP sigue funcionando siempre que no se haya eliminado el mensaje, o siempre y cuando no se haya aplicado aún la misma acción o más segura. Por ejemplo, si la Directiva de phish se establece en cuarentena y el usuario o el administrador ya ha no deseado el correo electrónico, la cuarentena tendrá que hacer una acción para poner en cuarentena el archivo.

### <a name="does-zap-change-the-message-header"></a>¿ZAP cambia el encabezado del mensaje?

Una acción ZAP no realiza ningún cambio en el encabezado del mensaje.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>¿Cómo afecta el ZAP a los buzones en retención?

ZAP no va a poner en cuarentena los mensajes de los buzones en retención. ZAP puede mover mensajes a la carpeta de correo no deseado en función de la acción configurada para un veredicto de correo no deseado o de suplantación de identidad en directivas contra correo no deseado.

Para obtener más información acerca de las suspensiones en Exchange Online, consulte conservación [local y retención por juicio en Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).
