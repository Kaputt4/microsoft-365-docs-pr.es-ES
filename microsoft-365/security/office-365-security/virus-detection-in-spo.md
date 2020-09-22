---
title: Detección de virus en SharePoint Online
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
ms.openlocfilehash: 8c65db566f165939d72429bcd61b7d0a880814e0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196516"
---
# <a name="virus-detection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Detección de virus en SharePoint Online, OneDrive y Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Microsoft 365 puede ayudarle a proteger su entorno del malware detectando virus en los archivos que los usuarios cargan en SharePoint Online, OneDrive y Microsoft Teams. Los archivos pueden analizarse en busca de virus una vez cargados. Si se detecta que un archivo está infectado, se establece una propiedad para que los usuarios no puedan descargar ni sincronizar el archivo.

> [!IMPORTANT]
> Estas capacidades antivirus de SharePoint Online son una forma de contener virus. No pretenden ser un punto único de defensa contra el malware en su entorno. Recomendamos a todos los clientes que evalúen e implementen la protección antimalware en varias capas y que apliquen los procedimientos recomendados para proteger la infraestructura de la empresa. Para obtener más información acerca de las estrategias y los procedimientos recomendados, consulte [plan de seguridad](security-roadmap.md).

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>¿Qué ocurre cuando se carga un archivo infectado en SharePoint Online?

Microsoft 365 usa un motor de detección de virus común. El motor se ejecuta de forma asincrónica dentro de SharePoint Online y examina algunos archivos después de que se carguen. Se usan heurísticas para determinar qué archivos se examinan. Cuando se encuentra un archivo que contiene un virus, se marca para que no se pueda descargar de nuevo. En abril de 2018, eliminamos el límite de 25 MB para los archivos examinados.

Esto es lo que sucede:

1. Un usuario carga un archivo en SharePoint Online.

2. SharePoint Online determina si el archivo cumple los criterios de un examen.

3. El motor de detección de virus examina el archivo.

4. Si se encuentra un virus, el motor del virus establece una propiedad en el archivo que indica que está infectado.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>¿Qué sucede cuando un usuario intenta descargar un archivo infectado con el explorador?

Si un archivo está infectado, los usuarios no pueden descargar el archivo de SharePoint Online con el explorador.

Esto es lo que sucede:

1. Un usuario abre un explorador web e intenta descargar un archivo infectado de SharePoint Online.

2. Al usuario se le advierte de que se ha detectado un virus. Al usuario se le ofrece la opción de descargar el archivo e intentar limpiarlo mediante su propio software antivirus.

> [!NOTE]
>
> Puede usar el parámetro *DisallowInfectedFileDownload* en el cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) de PowerShell de SharePoint Online para evitar que los usuarios descarguen un archivo infectado, incluso en la ventana de advertencia de antivirus.
>
> Tenga en cuenta también que, en cuanto habilite el parámetro *DisallowInfectedFileDownload* , el acceso a los archivos detectados o bloqueados queda bloqueado completamente para los usuarios y los administradores.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>¿Qué sucede cuando el cliente de sincronización de OneDrive intenta sincronizar un archivo infectado?

Si los usuarios sincronizan archivos con el nuevo cliente de sincronización de OneDrive (OneDrive.exe) o el anterior cliente de sincronización de OneDrive para la empresa (Groove.exe), si un archivo contiene un virus, el cliente de sincronización no lo descargará. El cliente de sincronización mostrará una notificación de que el archivo no se puede sincronizar.

## <a name="extended-capabilities-with-office-365-atp"></a>Capacidades ampliadas con Office 365 ATP

Los clientes que habilitaron Office 365 ATP para SharePoint, OneDrive y Microsoft Teams [activan ATP para SharePoint, onedrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) pueden usar el centro de seguridad & cumplimiento para administrar los archivos en cuarentena para detecciones AV y ATP. [Solo ATP: Use el centro de seguridad & cumplimiento para administrar los archivos en cuarentena](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).

## <a name="more-information"></a>Más información

Consulte [proteger contra amenazas](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) y [Activar ATP para SharePoint, OneDrive y Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) para obtener más información sobre cómo configurar el antivirus de SharePoint Online.


