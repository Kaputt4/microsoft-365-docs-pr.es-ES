---
title: Purga automática de cero horas en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.localizationpriority: medium
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
description: La purga automática de cero horas (ZAP) mueve retroactivamente los mensajes entregados en un buzón de Exchange Online a la carpeta correo no deseado o a la cuarentena que se detecta como correo no deseado, suplantación de identidad (phishing) o que contienen malware después de la entrega.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bd9bb3f231e42c625c87669417210281d1d5a3df
ms.sourcegitcommit: a8fbaf4b441b5325004f7a2dacd9429ec9d80534
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2022
ms.locfileid: "65739469"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Purga automática de cero horas (ZAP) en Exchange Online

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

## <a name="zero-hour-auto-purge-zap-basics"></a>Conceptos básicos de purga automática de hora cero (ZAP)

En Microsoft 365 organizaciones con buzones de correo en Exchange Online, la purga automática de cero horas (ZAP) es una característica de protección de correo electrónico que detecta y neutraliza de forma retroactiva mensajes malintencionados de phishing, spam o malware que ya se han entregado a Exchange Online buzones.

ZAP no funciona en entornos de Exchange Online Protection independientes (EOP) que protegen los buzones de Exchange locales.

## <a name="how-zap-works"></a>Funcionamiento de ZAP

Las firmas de spam y malware se actualizan diariamente en el servicio en tiempo real. Sin embargo, los usuarios pueden seguir recibiendo mensajes malintencionados por diversos motivos, incluido si el contenido está armado después de entregarse a los usuarios. ZAP soluciona este problema supervisando continuamente las actualizaciones de las firmas de spam y malware en el servicio. ZAP puede buscar y quitar mensajes que ya están en el buzón de un usuario.

La acción ZAP es perfecta para el usuario; no se les notifica si se detecta y mueve un mensaje.

[Caja fuerte listas de remitentes](create-safe-sender-lists-in-office-365.md), reglas de flujo de correo (también conocidas como reglas de transporte), reglas de bandeja de entrada o filtros adicionales tienen prioridad sobre ZAP. De forma similar a lo que sucede en el flujo de correo, esto significa que incluso si el servicio determina que el mensaje entregado necesita ZAP, el mensaje no se actúa en debido a la configuración de remitentes seguros. Esta es otra razón para tener cuidado con la configuración de mensajes para omitir el filtrado.

Vea este breve vídeo para aprender cómo ZAP en Microsoft Defender para Office 365 detecta y neutraliza automáticamente las amenazas en el correo electrónico. 
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGrLg]

### <a name="zero-hour-auto-purge-zap-for-malware"></a>Purga automática de cero horas (ZAP) para malware

Para **los mensajes leídos o no leídos** que contienen malware después de la entrega, ZAP pone en cuarentena el mensaje que contiene los datos adjuntos de malware. De forma predeterminada, solo los administradores pueden ver y administrar mensajes de malware en cuarentena. Sin embargo, los administradores pueden crear y usar _directivas de cuarentena_ para definir qué pueden hacer los usuarios en los mensajes que se pusieron en cuarentena como malware. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).

ZAP para malware está habilitado de forma predeterminada en las directivas antimalware. Para obtener más información, vea [Configurar directivas antimalware en EOP](configure-anti-malware-policies.md).

### <a name="zero-hour-auto-purge-zap-for-phishing"></a>Purga automática de cero horas (ZAP) para suplantación de identidad (phishing)

Para **los mensajes leídos o no leídos** que se identifican como suplantación de identidad (phishing) después de la entrega, el resultado de ZAP depende de la acción configurada para un veredicto de filtrado de **correo electrónico de phishing** en la directiva antispam aplicable. Las acciones de veredicto de filtrado disponibles para la suplantación de identidad (phishing) y sus posibles resultados de ZAP se describen en la lista siguiente:

- **Agregar encabezado X**, **anteponer la línea de asunto con texto**, **Redirigir el mensaje a la dirección de correo electrónico**, **Eliminar mensaje**: ZAP no realiza ninguna acción en el mensaje.

- **Mover el mensaje al correo electrónico no deseado**: ZAP mueve el mensaje a la carpeta Correo electrónico no deseado. Para obtener más información, consulte [Configuración del correo electrónico no deseado en Exchange Online buzones de Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Mensaje de cuarentena**: ZAP pone en cuarentena el mensaje.

De forma predeterminada, ZAP para suplantación de identidad está habilitado en las directivas contra correo no deseado y la acción predeterminada para el veredicto de filtrado de **correo electrónico de suplantación** de identidad es **Mensaje de cuarentena**, lo que significa que ZAP para suplantación de identidad pone en cuarentena el mensaje de forma predeterminada.

Para obtener más información sobre cómo configurar los veredictos de filtrado de correo no deseado, consulte [Configurar directivas contra correo no deseado en Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="zero-hour-auto-purge-zap-for-high-confidence-phishing"></a>Purga automática de cero horas (ZAP) para suplantación de identidad de alta confianza

Para **los mensajes leídos o no leídos** que se identifican como suplantación de identidad de alta confianza después de la entrega, ZAP pone en cuarentena el mensaje. De forma predeterminada, solo los administradores pueden ver y administrar mensajes de phish de alta confianza en cuarentena. Sin embargo, los administradores pueden crear y usar _directivas de cuarentena_ para definir lo que los usuarios pueden hacer en los mensajes que se pusieron en cuarentena como suplantación de identidad de alta confianza. Para obtener más información, consulte [Directivas de cuarentena](quarantine-policies.md).

Zap para la phish de alta confianza está habilitado de forma predeterminada. Para obtener más información, vea [Proteger de forma predeterminada en Office 365](secure-by-default.md).

### <a name="zero-hour-auto-purge-zap-for-spam"></a>Purga automática de cero horas (ZAP) para correo no deseado

En el caso de **los mensajes no leídos** que se identifican como correo no deseado después de la entrega, el resultado de ZAP depende de la acción configurada para el veredicto de filtrado de **correo no deseado** en la directiva antispam aplicable. Las acciones de veredicto de filtrado disponibles para el correo no deseado y sus posibles resultados zap se describen en la lista siguiente:

- **Agregar encabezado X**, **anteponer la línea de asunto con texto**, **Redirigir el mensaje a la dirección de correo electrónico**, **Eliminar mensaje**: ZAP no realiza ninguna acción en el mensaje.

- **Mover el mensaje al correo electrónico no deseado**: ZAP mueve el mensaje a la carpeta Correo electrónico no deseado. Para obtener más información, consulte [Configuración del correo electrónico no deseado en Exchange Online buzones de Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Mensaje de cuarentena**: ZAP pone en cuarentena el mensaje. De forma predeterminada, los usuarios finales pueden ver y administrar los mensajes en cuarentena de correo no deseado donde son destinatarios. Sin embargo, los administradores pueden crear y usar _directivas de cuarentena_ para definir qué pueden hacer los usuarios en los mensajes que se pusieron en cuarentena como correo no deseado. Para obtener más información, consulte [Directivas de cuarentena](quarantine-policies.md).

De forma predeterminada, el zap de correo no deseado está habilitado en las directivas de antispam y la acción predeterminada para el veredicto de filtrado de **correo no deseado** es **Mover mensaje a la carpeta Correo electrónico no deseado**, lo que significa que el correo no deseado ZAP mueve los mensajes **no leídos** a la carpeta Correo no deseado de forma predeterminada.

Para obtener más información sobre cómo configurar los veredictos de filtrado de correo no deseado, consulte [Configurar directivas contra correo no deseado en Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="zero-hour-auto-purge-zap-considerations-for-microsoft-defender-for-office-365"></a>Consideraciones sobre la purga automática de cero horas (ZAP) para Microsoft Defender para Office 365

ZAP no pondrá en cuarentena ningún mensaje que esté en proceso de [entrega dinámica](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) en Caja fuerte examen de directivas de datos adjuntos, o donde el filtrado de malware EOP ya ha reemplazado los datos adjuntos por el archivo **Text.txtalerta de malware**. Si se recibe una señal de suplantación de identidad (phishing) o spam para estos tipos de mensajes y el veredicto de filtrado de la directiva contra correo no deseado está establecido para realizar alguna acción en el mensaje (Mover a correo no deseado, redirigir, eliminar o poner en cuarentena), ZAP tendrá como valor predeterminado una acción "Mover a correo no deseado".

## <a name="how-to-see-if-zap-moved-your-message"></a>Cómo ver si ZAP movió el mensaje

Para determinar si ZAP movió el mensaje, tiene las siguientes opciones:

- **Número de mensajes**: use la [vista Flujo de correo en el informe de estado de Flujo de correo](view-email-security-reports.md#mailflow-view-for-the-mailflow-status-report) para ver el número de mensajes afectados por ZAP para el intervalo de fechas especificado.
- **Detalles del mensaje**: use [el Explorador de amenazas (y las detecciones en tiempo real)](threat-explorer.md) para filtrar **todos los eventos de correo electrónico** por el valor **ZAP** de la columna **Acción adicional** .

> [!NOTE]
> ZAP no se registra en los registros de auditoría del buzón de Exchange como una acción del sistema.

## <a name="zero-hour-auto-purge-zap-faq"></a>Preguntas más frecuentes sobre la purga automática de cero horas (ZAP)

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>¿Qué ocurre si un mensaje legítimo se mueve a la carpeta Correo no deseado?

Debe seguir el proceso normal de generación de informes para [falsos positivos](report-junk-email-messages-to-microsoft.md). La única razón por la que el mensaje se movería de la Bandeja de entrada a la carpeta Correo no deseado sería porque el servicio ha determinado que el mensaje era spam o malintencionado.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>¿Qué ocurre si utilizo la carpeta Cuarentena en lugar de la carpeta Correo no deseado?

ZAP tomará medidas en un mensaje en función de la configuración de las directivas contra correo no deseado, como se describió anteriormente en este artículo.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>¿Qué ocurre si uso remitentes seguros, reglas de flujo de correo o listas de remitentes permitidos o bloqueados?

Caja fuerte remitentes, reglas de flujo de correo o bloquear y permitir la configuración de la organización tienen prioridad. Estos mensajes se excluyen de ZAP, ya que el servicio está haciendo lo que ha configurado para hacerlo. Esta es otra razón para tener cuidado con la configuración de mensajes para omitir el filtrado.

### <a name="what-are-the-licensing-requirements-for-zero-hour-auto-purge-zap-to-work"></a>¿Cuáles son los requisitos de licencia para que funcione la purga automática de hora cero (ZAP)?

No hay limitaciones en las licencias. ZAP funciona en todos los buzones hospedados en Exchange en línea. ZAP no funciona en entornos de Exchange Online Protection independientes (EOP) que protegen los buzones de Exchange locales.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>¿Qué ocurre si un mensaje se mueve a otra carpeta (por ejemplo, reglas de bandeja de entrada)?

La purga automática de cero horas sigue funcionando siempre y cuando el mensaje no se haya eliminado, o siempre que no se haya aplicado la misma acción o más fuerte. Por ejemplo, si la directiva contra suplantación de identidad está establecida en cuarentena y el mensaje ya está en el correo electrónico no deseado, ZAP tomará medidas para poner en cuarentena el mensaje.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>¿Cómo afecta ZAP a los buzones en espera?

La purga automática de cero horas pondrá en cuarentena los mensajes de los buzones en espera. ZAP puede mover mensajes a la carpeta Correo no deseado en función de la acción configurada para un veredicto de correo no deseado o phishing en las directivas contra correo no deseado.

Para obtener más información sobre las retenciones en Exchange Online, consulte [Suspensión local y retención por juicio en Exchange Online](/Exchange/security-and-compliance/in-place-and-litigation-holds).
