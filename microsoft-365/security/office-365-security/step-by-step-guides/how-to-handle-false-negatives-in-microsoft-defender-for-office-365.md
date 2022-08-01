---
title: (Falsos negativos) Cómo controlar los correos electrónicos malintencionados que se entregan a los destinatarios mediante Microsoft Defender para Office 365
description: Los pasos para controlar los correos electrónicos malintencionados que llegan a los usuarios finales y las bandejas de entrada (como falsos negativos) con Microsoft Defender para Office 365 con el fin de evitar la pérdida de negocio.
search.product: ''
search.appverid: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: jarogers
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
ms.openlocfilehash: decbece049ea4f91deb529d2fd640816bf3f1d0c
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "66998213"
---
# <a name="how-to-handle-malicious-emails-that-are-delivered-to-recipients-false-negatives-using-microsoft-defender-for-office-365"></a>Cómo controlar los correos electrónicos malintencionados que se entregan a los destinatarios (falsos negativos), mediante Microsoft Defender para Office 365

Microsoft Defender para Office 365 ayuda a tratar los correos electrónicos malintencionados (falsos negativos) que se entregan a los destinatarios y que ponen en riesgo la productividad de la organización.
Defender para Office 365 puede ayudarle a comprender por qué se entregan correos electrónicos, cómo resolver la situación rápidamente y cómo evitar que se produzcan situaciones similares en el futuro.

## <a name="what-youll-need"></a>Lo que necesitará

- Microsoft Defender para Office 365 Plan 1 y 2 (incluidos como parte de E5). Exchange Online los clientes también pueden aprovechar esto.
- Permisos suficientes (rol administrador de seguridad).
- 5-10 minutos para realizar los pasos siguientes.

## <a name="handling-malicious-emails-in-the-inbox-folder-of-end-users"></a>Control de correos electrónicos malintencionados en la carpeta Bandeja de entrada de los usuarios finales

1. Pida a los usuarios finales que informen del correo electrónico como **suplantación de identidad (phishing** ) o **correo no deseado** mediante el complemento de mensajes de Microsoft, el complemento Microsoft Phish o los botones de Outlook.
2. Los usuarios finales también pueden agregar el remitente a la [lista de remitentes en bloque en](https://support.microsoft.com/en-us/office/block-a-mail-sender-b29fd867-cac9-40d8-aed1-659e06a706e4#:~:text=1%20On%20the%20Home%20tab%2C%20in%20the%20Delete,4%20Click%20OK%20in%20both%20open%20dialog%20boxes..) Outlook para evitar que los correos electrónicos de este remitente se entreguen a su bandeja de entrada.
3. Los administradores pueden evaluar los mensajes notificados por el usuario desde el portal de [contenido notificado](/microsoft-365/security/office-365-security/admin-submission?view=o365-worldwide#view-user-submissions-to-microsoft&preserve-view=true) por el usuario.
4. A partir de esos mensajes notificados, los administradores pueden **enviar a** [Microsoft para su análisis para](/microsoft-365/security/office-365-security/admin-submission?view=o365-worldwide#notify-users-from-within-the-portal&preserve-view=true) saber por qué se permitió ese correo electrónico en primer lugar.
5. Si es necesario, al enviar a Microsoft para su análisis, los administradores pueden crear un [bloque para que el remitente](/microsoft-365/security/office-365-security/manage-tenant-blocks?view=o365-worldwide&preserve-view=true) pueda mitigar el problema.
6. Una vez que estén disponibles los resultados de los envíos, lea el veredicto para comprender por qué se han permitido los correos electrónicos y cómo se podría mejorar la configuración del inquilino para evitar que se produzcan situaciones similares en el futuro.

## <a name="handling-malicious-emails-in-junk-folder-of-end-users"></a>Control de correos electrónicos malintencionados en la carpeta de correo no deseado de los usuarios finales

1. Pida a los usuarios finales que notifiquen el correo electrónico como **suplantación de identidad** mediante el complemento de mensajes de Microsoft, el complemento de Phish de Microsoft o los botones de Outlook.
2. Los administradores pueden evaluar los mensajes notificados por el usuario desde el portal de [contenido notificado](/microsoft-365/security/office-365-security/admin-submission?view=o365-worldwide#view-user-submissions-to-microsoft&preserve-view=true) por el usuario.
3. Desde esos mensajes notificados, los administradores pueden **enviar a** [Microsoft para su análisis](/microsoft-365/security/office-365-security/admin-submission?view=o365-worldwide#notify-users-from-within-the-portal&preserve-view=true) y saber por qué se permitió ese correo electrónico en primer lugar.
4. Si es necesario, al enviar a Microsoft para su análisis, los administradores pueden crear un [bloque para que el remitente](/microsoft-365/security/office-365-security/manage-tenant-blocks?view=o365-worldwide&preserve-view=true) pueda mitigar el problema.
5. Una vez que estén disponibles los resultados de los envíos, lea el veredicto para comprender por qué se han permitido los correos electrónicos y cómo se podría mejorar la configuración del inquilino para evitar que se produzcan situaciones similares en el futuro.

## <a name="handling-malicious-emails-landing-in-the-quarantine-folder-of-end-users"></a>Control de correos electrónicos malintencionados que aterrizan en la carpeta de cuarentena de los usuarios finales

1. Los usuarios finales reciben un [resumen de correo electrónico](/microsoft-365/security/office-365-security/use-spam-notifications-to-release-and-report-quarantined-messages?view=o365-worldwide&preserve-view=true) sobre los mensajes en cuarentena según la configuración habilitada por los administradores.
2. Los usuarios finales pueden obtener una vista previa de los mensajes en cuarentena, bloquear el remitente y enviar esos mensajes a Microsoft para su análisis.

## <a name="handling-malicious-emails-landing-in-the-quarantine-folder-of-admins"></a>Control de correos electrónicos malintencionados que aterrizan en la carpeta de cuarentena de los administradores

1. Los administradores pueden ver los correos electrónicos en cuarentena (incluidos los que solicitan permiso para solicitar la versión) desde la [página de revisión](/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files?view=o365-worldwide&preserve-view=true).
2. Los administradores pueden enviar mensajes malintencionados o sospechosos a Microsoft para su análisis y crear un bloque para mitigar la situación mientras esperan el veredicto.
3. Una vez que estén disponibles los resultados de los envíos, lea el veredicto para saber por qué se han permitido los correos electrónicos y cómo se podría mejorar la configuración del inquilino para evitar que se produzcan situaciones similares en el futuro.
