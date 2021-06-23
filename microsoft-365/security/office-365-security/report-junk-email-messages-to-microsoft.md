---
title: Notificar mensajes de correo no deseado, no deseado y suplantación de identidad a Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre las distintas formas de notificar mensajes y archivos buenos y malos a Microsoft para su análisis.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a89ea8a41a31c9544284566fade0e603d48af759
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082821"
---
# <a name="report-messages-and-files-to-microsoft"></a>Notificar mensajes y archivos a Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En Microsoft 365 organizaciones con buzones de correo en organizaciones de Exchange Online o independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, tanto los usuarios como los administradores tienen varios métodos diferentes para notificar mensajes de correo electrónico y archivos a Microsoft.

<br>

****

|Método|Descripción|
|---|---|
|[Usar el Envío para administradores para enviar correo no deseado, de suplantación de identidad, direcciones URL y archivos sospechosos a Microsoft](admin-submission.md)|El método de informes recomendado para administradores de organizaciones con Exchange Online buzones de correo (no disponible en EOP independiente).|
|[Habilitar el mensaje de informe o los complementos de suplantación de identidad de informes](enable-the-report-message-add-in.md)|Funciona con Outlook y Outlook en la Web (anteriormente conocido como Outlook Web App). <p> En función de la suscripción, los mensajes que los usuarios notificaron con los complementos están disponibles [](view-email-security-reports.md#user-reported-messages-report)en el portal de envíos de administración, los [resultados](admin-submission.md)de investigación y respuesta [automatizadas (AIR),](air-view-investigation-results.md)el informe de mensajes notificados por el usuario y el [Explorador](threat-explorer-views.md#email--submissions). <p> Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique. Para obtener más información, vea [Directivas de envío de usuarios](user-submission.md).
|[Informar de falsos positivos y falsos negativos en Outlook](report-false-positives-and-false-negatives.md)|Enviar falsos positivos (correo electrónico bueno bloqueado o enviado a la carpeta de correo no deseado) y falsos negativos (correo electrónico no deseado o suplantación de identidad que se entregó a la bandeja de entrada) a Exchange Online Protection (EOP) mediante la característica Mensaje de informe.|
|[Enviar mensajes manualmente a Microsoft para su análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Envíe manualmente mensajes adjuntos a direcciones de correo electrónico específicas de Microsoft para correo no deseado, no correo no deseado y suplantación de identidad.|
|[Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|Obtenga información sobre cómo crear una regla de flujo de correo (también conocida como regla de transporte) que le notifica cuándo los usuarios notifican mensajes a Microsoft para su análisis.|
|[Enviar malware y no malware a Microsoft para su análisis](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Use el Inteligencia de seguridad de Microsoft web para enviar datos adjuntos y otros archivos.|
|

Si los mensajes de correo no deseado o suplantación de identidad se han puesto en cuarentena en lugar de entregarse, los usuarios pueden notificar los mensajes a Microsoft desde cuarentena en el portal Microsoft 365 Defender correo electrónico. Para obtener más información, vea Buscar y liberar mensajes en cuarentena [como un usuario en Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).

> [!NOTE]
> Los datos de envíos a Microsoft residen en el límite Office 365 cumplimiento normativo en los centros de datos de Norteamérica. Los analistas del equipo de ingeniería revisan los datos para ayudar a mejorar la eficacia de los filtros.
