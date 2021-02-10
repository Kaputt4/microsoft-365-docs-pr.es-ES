---
title: Notificar mensajes de correo no deseado, correo no deseado y suplantación de identidad a Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
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
description: Los administradores pueden obtener información sobre las distintas formas de informar a Microsoft de los mensajes y archivos buenos y los que no son buenos para su análisis.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b75b05f33ab6c6a5827101ad2f5b14c94b932135
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166692"
---
# <a name="report-messages-and-files-to-microsoft"></a>Notificar mensajes y archivos a Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

En las organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, tanto los usuarios como los administradores tienen varios métodos diferentes para notificar mensajes de correo electrónico y archivos a Microsoft.

****

|Método|Descripción|
|---|---|
|[Usar el Envío para administradores para enviar correo no deseado, de suplantación de identidad, direcciones URL y archivos sospechosos a Microsoft](admin-submission.md)|El método de informes recomendado para administradores de organizaciones con buzones de Exchange Online (no disponible en EOP independiente).|
|[Habilitar el complemento de mensajes de informe](enable-the-report-message-add-in.md)|Funciona con Outlook y Outlook en la Web (anteriormente conocido como Outlook Web App). <p> Según la suscripción, los mensajes que los usuarios notificaron con el complemento están disponibles en el [](view-email-security-reports.md#user-reported-messages-report)portal de envíos de administración, en los resultados de investigación y respuesta [automatizadas (AIR),](air-view-investigation-results.md)en el informe de mensajes [notificados](admin-submission.md)por el usuario y en el Explorador de [amenazas.](threat-explorer-views.md#email--submissions) <p> Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique. Para obtener más información, consulta [Directivas de envío de usuarios.](user-submission.md)
|[Habilitar el complemento Informe de suplantación de identidad (phishing)](enable-the-report-phish-add-in.md)|Funciona con Outlook y Outlook en la Web (anteriormente conocido como Outlook Web App). <p> Según la suscripción, los mensajes que los usuarios notificaron con el complemento están disponibles en el [](view-email-security-reports.md#user-reported-messages-report)portal de envíos de administración, en los resultados de investigación y respuesta [automatizadas (AIR),](air-view-investigation-results.md)en el informe de mensajes [notificados](admin-submission.md)por el usuario y en el Explorador de [amenazas.](threat-explorer-views.md#email--submissions) <p> Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique. Para obtener más información, consulta [Directivas de envío de usuarios.](user-submission.md)|
|[Instalar y usar el complemento de notificación de correo no deseado para Microsoft Outlook](junk-email-reporting-add-in-for-microsoft-outlook.md)|Solo funciona en Outlook.|
|[Notificar correo electrónico no deseado y de suplantación de identidad en Outlook en la Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Use las funciones integradas en Outlook en la Web para organizaciones con buzones de Exchange Online (no disponible en EOP independiente). <p> Los mensajes que informan los usuarios están disponibles [en el portal de envíos de administrador.](admin-submission.md) <p> Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique. Para obtener más información, consulta [Directivas de envío de usuarios.](user-submission.md)|
|[Notificar correo electrónico no deseado y de suplantación de identidad en Outlook para iOS y Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|Use las funcionalidades integradas en Outlook para iOS y Android para organizaciones con buzones de Exchange Online (no disponible en EOP independiente). <p> Los mensajes que los usuarios informan están disponibles [en el portal de envíos de administrador.](admin-submission.md) <p> Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique. Para obtener más información, consulta [Directivas de envío de usuarios.](user-submission.md)|
|[Enviar manualmente mensajes a Microsoft para su análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Enviar manualmente mensajes adjuntos a direcciones de correo electrónico específicas de Microsoft para correo no deseado, no correo no deseado y suplantación de identidad.|
|[Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|Obtenga información sobre cómo crear una regla de flujo de correo (también conocida como regla de transporte) que le notifica cuando los usuarios notifican mensajes a Microsoft para su análisis.|
|[Enviar malware y no malware a Microsoft para su análisis](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Use el sitio de inteligencia de seguridad de Microsoft para enviar datos adjuntos y otros archivos.|

Si los mensajes de correo no deseado o de suplantación de identidad se han puesto en cuarentena en lugar de entregarse, los usuarios pueden notificar los mensajes a Microsoft desde el portal de cuarentena en el Centro de seguridad & cumplimiento. Para obtener más información, [consulte Buscar y liberar mensajes en cuarentena como un usuario en Microsoft 365.](find-and-release-quarantined-messages-as-a-user.md)

> [!NOTE]
> Los datos de envíos a Microsoft residen en el límite de cumplimiento de Office 365 en centros de datos de Norteamérica. Los analistas del equipo de ingeniería revisan los datos para ayudar a mejorar la eficacia de los filtros.
