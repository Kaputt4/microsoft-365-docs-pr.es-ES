---
title: (Falsos positivos) Cómo controlar los correos electrónicos legítimos que se bloquean para que no se entreguen con Microsoft Defender para Office 365
description: Los pasos para controlar el bloqueo del correo electrónico legítimo (falso positivo) por Microsoft Defender para Office 365 con el fin de evitar la pérdida de negocio.
search.product: ''
search.appverid: ''
ms.service: microsoft-365-security
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
ms.subservice: mdo
ms.openlocfilehash: ae7b66a2dc8c8b4fb96360ca2bc0625bfcdf6b43
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67596685"
---
# <a name="how-to-handle-legitimate-emails-getting-blocked-false-positive-using-microsoft-defender-for-office-365"></a>Cómo controlar el bloqueo de correos electrónicos legítimos (falso positivo), mediante Microsoft Defender para Office 365

Microsoft Defender para Office 365 ayuda a tratar con correos electrónicos comerciales legítimos importantes que se bloquean por error como amenazas (falsos positivos). Defender para Office 365 puede ayudar a los administradores a comprender *por qué* se bloquean los correos electrónicos legítimos, cómo resolver la situación rápidamente y evitar que se produzcan situaciones similares en el futuro.

## <a name="what-youll-need"></a>Lo que necesitará

- Microsoft Defender para Office 365 Plan 1 o 2 (incluido como parte de E5). Exchange Online los clientes también pueden aprovechar esta característica.
- Permisos suficientes (rol administrador de seguridad).
- 5-10 minutos para realizar los pasos siguientes.

## <a name="handling-legitimate-emails-in-to-junk-folder-of-end-users"></a>Control de correos electrónicos legítimos en la carpeta No deseado de los usuarios finales

1. Pida a los usuarios finales que notifiquen el correo electrónico como **no deseado** mediante el complemento de mensajes de Microsoft o los botones de Outlook.
2. Los usuarios finales también pueden agregar el remitente a la [**lista de remitentes seguros**](https://support.microsoft.com/en-us/office/safe-senders-in-outlook-com-470d4ee6-e3b6-402b-8cd9-a6f00eda7339) en Outlook para evitar que el correo electrónico de estos remitentes desembarque en la carpeta No deseado.
3. Los administradores pueden evaluar los mensajes notificados por el usuario desde el portal [de contenido notificado por el usuario](/microsoft-365/security/office-365-security/admin-submission?view=o365-worldwide#view-user-submissions-to-microsoft&preserve-view=true) .
4. A partir de esos mensajes notificados, los administradores pueden enviar a [**Microsoft para su análisis**](/microsoft-365/security/office-365-security/admin-submission?view=o365-worldwide#notify-users-from-within-the-portal&preserve-view=true) y comprender por qué se bloqueó ese correo electrónico en primer lugar.
5. Si es necesario, al enviar a Microsoft para su análisis, los administradores pueden crear con criterio un [**permiso para que** un remitente](/microsoft-365/security/office-365-security/manage-tenant-allows?view=o365-worldwide#add-sender-allows-using-the-submissions-portal&preserve-view=true) mitigue el problema.
6. Una vez que estén disponibles los resultados del envío del administrador, léelo para comprender por qué se bloquearon los correos electrónicos y cómo se pudo mejorar la configuración del inquilino para *evitar* que se produzcan situaciones similares en el futuro.

## <a name="handling-legitimate-emails-that-are-in-quarantine-folder-of-end-users"></a>Control de correos electrónicos legítimos que están en la carpeta de cuarentena de los usuarios finales

1. Un usuario final recibe un [resumen de correo electrónico](/microsoft-365/security/office-365-security/use-spam-notifications-to-release-and-report-quarantined-messages?view=o365-worldwide&preserve-view=true) sobre los mensajes en cuarentena según la configuración habilitada por los administradores de seguridad.
2. Los usuarios finales pueden obtener una vista previa de los mensajes en cuarentena, bloquear el remitente, liberar los mensajes, enviar esos mensajes a Microsoft para su análisis y solicitar la liberación de esos correos electrónicos de los administradores.

## <a name="handling-legitimate-emails-in-quarantine-folder-of-an-admin"></a>Control de correos electrónicos legítimos en la carpeta de cuarentena de un administrador

1. Los administradores pueden ver los correos electrónicos en cuarentena (incluidos los que solicitan permiso para solicitar la versión) desde la [página de revisión](/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files?view=o365-worldwide&preserve-view=true).
2. Los administradores pueden liberar el mensaje de la cuarentena mientras lo envían a Microsoft para su análisis y crear un permiso para mitigar la situación.
3. Una vez disponibles los resultados de los envíos, los administradores deben leer el veredicto para comprender por qué se bloquearon los correos electrónicos y cómo se podría mejorar la configuración del inquilino para evitar que se produzcan situaciones similares en el futuro.
