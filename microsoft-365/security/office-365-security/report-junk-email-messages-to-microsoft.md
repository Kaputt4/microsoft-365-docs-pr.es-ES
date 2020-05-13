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
description: Los administradores pueden obtener información sobre las distintas formas de informar de los mensajes y los archivos buenos y no válidos a Microsoft para su análisis.
ms.openlocfilehash: f77346b1f7551ade572c695e1c2d29e402c6c2a2
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206459"
---
# <a name="report-messages-and-files-to-microsoft"></a>Notificar mensajes y archivos a Microsoft

En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, los usuarios y los administradores tienen varios métodos diferentes para informar de los mensajes de correo electrónico y los archivos a Microsoft.

|||
|---|---|
|**Método**|**Descripción**|
|[Usar el Envío para administradores para enviar correo no deseado, de suplantación de identidad, direcciones URL y archivos sospechosos a Microsoft](admin-submission.md)|El método de creación de informes recomendado para administradores de organizaciones con buzones de Exchange Online (no disponible en EOP independiente).|
|[Habilitar el complemento de mensajes de informe](enable-the-report-message-add-in.md)|Funciona con Outlook, Outlook para Mac y Outlook en la web (anteriormente conocido como Outlook Web App) y es el complemento recomendado. <br/><br/> En función de la suscripción, los mensajes que los usuarios han notificado con el complemento están disponibles en [el portal de envíos de administración](admin-submission.md), en los [resultados de investigación y respuesta automáticas (Air)](air-view-investigation-results.md), en el [Informe de mensajes de notificación de usuario y en](view-email-security-reports.md#user-reported-messages-report)el [Explorador de amenazas](threat-explorer-views.md#email--submissions). <br/><br/> Puede configurar los mensajes notificados para que se copien o redirijan a un buzón de correo que especifique. Para obtener más información, vea [especificar un buzón para los envíos de usuarios de mensajes de correo no deseado y suplantación de identidad en EOP](user-submission.md).|
|[Instalar y usar el complemento de notificación de correo no deseado para Microsoft Outlook](junk-email-reporting-add-in-for-microsoft-outlook.md)|Solo funciona en Outlook.|
|[Informar del correo electrónico no deseado y de suplantación de identidad en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Use las funciones integradas en Outlook en la web para las organizaciones con buzones de Exchange Online (no disponible en EOP independiente). <br/><br/> Mensajes que los informes de usuarios están disponibles en [el portal de envíos de administración](admin-submission.md). <br/><br/> Puede configurar los mensajes notificados para que se copien o redirijan a un buzón de correo que especifique. Para obtener más información, vea [especificar un buzón para los envíos de usuarios de correo no deseado y mensajes de suplantación de identidad en Exchange Online](user-submission.md).|
|[Enviar mensajes a Microsoft de forma manual para su análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Enviar manualmente mensajes adjuntos a direcciones de correo electrónico de Microsoft específicas para correo no deseado, no correo no deseado y suplantación de identidad.|
|[Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|Obtenga información sobre cómo crear una regla de flujo de correo (también denominada regla de transporte) que le notifica cuando los usuarios notifican mensajes a Microsoft para su análisis.|
|||
|[Enviar malware y no malware a Microsoft para su análisis](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Usar el sitio de inteligencia en seguridad de Microsoft para enviar datos adjuntos y otros archivos.|
|

Si los mensajes de correo no deseado o de suplantación de identidad se han puesto en cuarentena en lugar de entregarse, los usuarios pueden informar de los mensajes a Microsoft del portal de cuarentena en el centro de seguridad & cumplimiento. Para obtener más información, vea [Buscar y liberar mensajes en cuarentena como un usuario en Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).
