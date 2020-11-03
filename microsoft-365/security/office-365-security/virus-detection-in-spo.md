---
title: Protección antivirus integrada en SharePoint Online, OneDrive y Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo SharePoint Online detecta los virus en los archivos que los usuarios cargan y evita que los usuarios descarguen o sincronicen los archivos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f774c9afd0988c504d6207b0e71ee9561312e6b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844241"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Protección antivirus integrada en SharePoint Online, OneDrive y Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Microsoft 365 usa un motor de detección de virus común para analizar los archivos que los usuarios cargan en SharePoint Online, OneDrive y Microsoft Teams. Esta protección se incluye con todas las suscripciones que incluyen SharePoint Online, OneDrive y Microsoft Teams.

> [!IMPORTANT]
> Las capacidades antivirus integradas son una forma de ayudar a contener virus. No pretenden ser un punto único de defensa contra el malware en su entorno. Recomendamos a todos los clientes que investiguen y implementen la protección antimalware en varias capas y que apliquen los procedimientos recomendados para proteger su infraestructura empresarial. Para obtener más información acerca de las estrategias y los procedimientos recomendados, consulte [plan de seguridad](security-roadmap.md).

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>¿Qué ocurre cuando se carga un archivo infectado en SharePoint Online?

El motor de detección de virus de Microsoft 365 se ejecuta de forma asincrónica dentro de SharePoint Online. **No se examinan automáticamente todos los archivos al cargarlos**. La heurística determina los archivos que se van a analizar. Cuando se encuentra un archivo que contiene un virus, el archivo se marca para que no se pueda descargar de nuevo. En abril de 2018, eliminamos el límite de 25 MB para los archivos examinados.

Esto es lo que sucede:

1. Un usuario carga un archivo en SharePoint Online.
2. SharePoint Online determina si el archivo cumple los criterios de un examen.
3. El motor de detección de virus examina el archivo.
4. Si se encuentra un virus, el motor del virus establece una propiedad en el archivo que indica que está infectado.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>¿Qué sucede cuando un usuario intenta descargar un archivo infectado con el explorador?

Si un archivo está infectado, los usuarios no pueden descargar el archivo de SharePoint Online con un explorador.

Esto es lo que sucede:

1. Un usuario abre un explorador web e intenta descargar un archivo infectado de SharePoint Online.
2. Al usuario se le advierte de que se ha detectado un virus. De forma predeterminada, se ofrece al usuario la opción de descargar el archivo e intentar limpiarlo mediante el software antivirus en su propio dispositivo.

> [!NOTE]
>
> Los administradores pueden usar el parámetro *DisallowInfectedFileDownload* en el cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) de SharePoint Online PowerShell para evitar que los usuarios descarguen archivos infectados, incluso en la ventana de advertencia de antivirus. Para obtener instrucciones, vea [usar SharePoint Online PowerShell para evitar que los usuarios descarguen archivos malintencionados](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).
>
> En cuanto se habilita el parámetro *DisallowInfectedFileDownload* , el acceso a los archivos detectados o bloqueados se bloquea completamente para los usuarios y los administradores.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>¿Qué sucede cuando el cliente de sincronización de OneDrive intenta sincronizar un archivo infectado?

Los clientes de sincronización de OneDrive no podrán descargar archivos que contengan virus. El cliente de sincronización mostrará una notificación de que el archivo no se puede sincronizar.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Capacidades ampliadas con Microsoft defender para Office 365

Microsoft 365 organizaciones que tienen [Microsoft defender para Office 365](office-365-atp.md) incluidas en su suscripción o que se han comprado como complementos pueden habilitar ATP para SharePoint, OneDrive y Microsoft Teams para mejorar el informe y la protección. Para obtener más información, consulte [ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md).

## <a name="more-information"></a>Más información

Para obtener más información sobre los antivirus en SharePoint Online, OneDrive y Microsoft Teams, consulte [proteger contra amenazas](protect-against-threats.md) y [Activar ATP para SharePoint, OneDrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).
