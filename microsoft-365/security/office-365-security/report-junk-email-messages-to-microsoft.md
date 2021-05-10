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
ms.openlocfilehash: 8c87938a8716da36f027300d685f0caedcf69660
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52291132"
---
# <a name="report-messages-and-files-to-microsoft"></a>Notificar mensajes y archivos a Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En Microsoft 365 organizaciones con buzones de correo en organizaciones de Exchange Online o independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, tanto los usuarios como los administradores tienen varios métodos diferentes para notificar mensajes de correo electrónico y archivos a Microsoft.

****

|Método|Descripción|
|---|---|
|[Usar el Envío para administradores para enviar correo no deseado, de suplantación de identidad, direcciones URL y archivos sospechosos a Microsoft](admin-submission.md)|El método de informes recomendado para administradores de organizaciones con Exchange Online buzones de correo (no disponible en EOP independiente).|
|[Habilitar el mensaje de informe o los complementos de suplantación de identidad de informes](enable-the-report-message-add-in.md)|Funciona con Outlook y Outlook en la web (anteriormente conocido como Outlook Web App). <p> Según la suscripción, los mensajes que los usuarios notificaron con los complementos están disponibles en el [](view-email-security-reports.md#user-reported-messages-report)portal de envíos de administración, en los resultados de investigación y respuesta [automatizadas (AIR),](air-view-investigation-results.md)en el informe de mensajes [notificados](admin-submission.md)por el usuario y en el Explorador de [amenazas.](threat-explorer-views.md#email--submissions) <p> Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique. Para obtener más información, vea [Directivas de envío de usuarios](user-submission.md).
|[Notificar falsos positivos y falsos negativos a Outlook](report-false-positives-and-false-negatives.md)|Enviar falsos positivos (correo electrónico bueno bloqueado o enviado a la carpeta de correo no deseado) y falsos negativos (correo electrónico no deseado o suplantación de identidad que se entregó a la bandeja de entrada) a Exchange Online Protection (EOP) mediante la característica Mensaje de informe.|
|[Enviar mensajes manualmente a Microsoft para su análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Envíe manualmente mensajes adjuntos a direcciones de correo electrónico específicas de Microsoft para correo no deseado, no correo no deseado y suplantación de identidad.|
|[Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|Obtenga información sobre cómo crear una regla de flujo de correo (también conocida como regla de transporte) que le notifica cuándo los usuarios notifican mensajes a Microsoft para su análisis.|
|[Enviar malware y no malware a Microsoft para su análisis](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Use el Inteligencia de seguridad de Microsoft web para enviar datos adjuntos y otros archivos.|

Si los mensajes de correo no deseado o suplantación de identidad se han puesto en cuarentena en lugar de entregarse, los usuarios pueden notificar los mensajes a Microsoft desde el portal de cuarentena en el Centro de seguridad & cumplimiento. Para obtener más información, vea Buscar y liberar mensajes en cuarentena [como un usuario en Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).

> [!NOTE]
> Los datos de envíos a Microsoft residen en el límite Office 365 cumplimiento normativo en los centros de datos de Norteamérica. Los analistas del equipo de ingeniería revisan los datos para ayudar a mejorar la eficacia de los filtros.
