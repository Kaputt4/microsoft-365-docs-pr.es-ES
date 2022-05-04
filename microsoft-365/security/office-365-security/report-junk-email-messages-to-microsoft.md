---
title: Notificar mensajes de correo no deseado, no correo no deseado y suplantación de identidad (phishing) a Microsoft
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre las distintas formas de notificar mensajes y archivos correctos y incorrectos a Microsoft para su análisis.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 56ef5cd5a376f4d10af1ad8c592dad02dbc8ef0a
ms.sourcegitcommit: 7e0094ddff54bcbe5d691dba58d4c4fb86f8b1a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "65188446"
---
# <a name="report-messages-and-files-to-microsoft"></a>Notificar mensajes y archivos a Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En Microsoft 365 organizaciones con buzones de correo en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin Exchange Online buzones, tanto los usuarios como los administradores tienen varios métodos diferentes para notificar mensajes de correo electrónico y archivos a Microsoft.

|Método|Descripción|
|---|---|
|[Uso del portal envíos para enviar sospechas de correo no deseado, direcciones URL y archivos a Microsoft](admin-submission.md)|Método de informes recomendado para administradores de organizaciones con buzones de Exchange Online (no disponible en EOP independiente).|
|[Habilitar los complementos Informar de mensajes o Informar de phishing](enable-the-report-message-add-in.md)|Funciona con Outlook y Outlook en la Web (anteriormente conocido como Outlook Web App). <br/><br/> En función de la suscripción, los mensajes que los usuarios notificaron con los complementos están disponibles en [el portal Envíos de administradores](admin-submission.md), [los resultados de investigación y respuesta automatizadas (AIR](air-view-investigation-results.md)), el [informe de mensajes notificados](view-email-security-reports.md#user-reported-messages-report) por el usuario y [el Explorador](threat-explorer-views.md#email--submissions). <br/><br/> Puede configurar los mensajes notificados para copiarlos o redirigirlos a un buzón que especifique. Para obtener más información, consulte [Directivas de envío de usuarios](user-submission.md).
|[Informar de falsos positivos y falsos negativos en Outlook](report-false-positives-and-false-negatives.md)|Envíe falsos positivos (correo electrónico correcto que se bloqueó o envió a la carpeta de correo no deseado) y falsos negativos (correo electrónico no deseado o phishing que se entregó en la bandeja de entrada) a Exchange Online Protection (EOP) mediante la característica Notificar mensaje.|
|[Usar reglas de flujo de correo para ver lo que los usuarios reportan a Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|Obtenga información sobre cómo crear una regla de flujo de correo (también conocida como regla de transporte) que le notifique cuando los usuarios informen de mensajes a Microsoft para su análisis.|
|[Enviar malware y no malware a Microsoft para su análisis](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Use el sitio de Inteligencia de seguridad de Microsoft para enviar datos adjuntos y otros archivos.|

> [!NOTE]
> Al informar de una entidad de correo electrónico a Microsoft, hacemos una copia de todo lo asociado al correo electrónico para incluirla en nuestras revisiones continuas del algoritmo. Esta copia incluye el contenido del correo electrónico, los encabezados de correo electrónico y los datos relacionados sobre el enrutamiento de correo electrónico. También se incluyen los datos adjuntos del mensaje.
>
> Microsoft trata sus comentarios como el permiso de su organización para que analicemos toda la información descrita anteriormente y trabajemos para ajustar los algoritmos de higiene de mensajes. Guardamos su mensaje en nuestros centros de datos auditados seguros en LOS EE. UU. hasta que eliminemos su envío no más tarde de 30 días después de que nos lo haya proporcionado. El personal de Microsoft puede leer el mensaje enviado y los datos adjuntos, que normalmente no se permiten para el correo electrónico en Office 365. Sin embargo, su correo electrónico sigue siendo tratado como confidencial entre usted y Microsoft, y no proporcionaremos su envío a ninguna otra parte para leer el correo electrónico o sus datos adjuntos para este proceso de revisión.
