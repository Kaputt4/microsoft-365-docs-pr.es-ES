---
title: Informar a Microsoft de correo no deseado, mensajes de correo no deseado y mensajes de suplantación de identidad
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
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre las distintas formas de informar de los mensajes buenos y malos a Microsoft.
ms.openlocfilehash: 4578e3d29a89e94d23c04e4d80e45c79c18cfb85
ms.sourcegitcommit: 1d5db6e8411b45d0dd1c517339074c2840e33a63
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/10/2020
ms.locfileid: "43216880"
---
# <a name="report-messages-and-files-to-microsoft"></a>Notificar mensajes y archivos a Microsoft

Los usuarios y administradores de Office 365 organizaciones con buzones en Exchange online o las organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online tienen varios métodos diferentes para informar de mensajes y archivos a Microsoft.

|||
|---|---|
|**Método**|**Descripción**|
|[Usar el Envío para administradores para enviar correo no deseado, de suplantación de identidad, direcciones URL y archivos sospechosos a Microsoft](admin-submission.md)|El método de creación de informes recomendado para administradores de organizaciones con buzones de Exchange Online (no disponible en EOP independiente).|
|[Habilitar el complemento de mensajes de informe en Office 365](enable-the-report-message-add-in.md)|Funciona con Outlook, Outlook para Mac y Outlook en la web (anteriormente conocido como Outlook Web App) y es el complemento recomendado. <br/><br/> En función de la suscripción, los mensajes que los usuarios han notificado con el complemento están disponibles en [los resultados de investigación y respuesta automatizada (Air)](air-view-investigation-results.md), el [Informe de mensajes declarados por el usuario](view-email-security-reports.md#user-reported-messages-report)y el [Explorador de amenazas](threat-explorer-views.md#email--submissions).|
|[Instalar y usar el complemento de notificación de correo no deseado para Microsoft Outlook en Office 365](junk-email-reporting-add-in-for-microsoft-outlook.md)|Solo funciona en Outlook.|
|[Informar del correo electrónico no deseado y de suplantación de identidad en Outlook en la web en Office 365](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Use las funciones integradas en Outlook en la web para las organizaciones con buzones de Exchange Online (no disponible en EOP independiente).|
|[Enviar mensajes a Microsoft de forma manual para su análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Enviar manualmente mensajes adjuntos a direcciones de correo electrónico de Microsoft específicas para correo no deseado, no correo no deseado y suplantación de identidad. <br/><br/> Obtenga información sobre cómo crear una regla de flujo de correo (también denominada regla de transporte) que le notifique cuando los usuarios envían mensajes a estas direcciones de correo electrónico de informes.|
|[Enviar malware y no malware a Microsoft para su análisis](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Usar el sitio de inteligencia en seguridad de Microsoft para enviar datos adjuntos y otros archivos.|
|

Si los mensajes de correo no deseado o de suplantación de identidad se han puesto en cuarentena en lugar de entregarse, los usuarios pueden informar de los mensajes a Microsoft del portal de cuarentena en el centro de seguridad & cumplimiento de Office 365. Para obtener más información, vea [Buscar y liberar mensajes en cuarentena como un usuario en Office 365](find-and-release-quarantined-messages-as-a-user.md).