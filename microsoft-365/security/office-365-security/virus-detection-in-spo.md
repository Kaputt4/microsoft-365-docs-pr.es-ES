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
description: Obtenga información sobre la protección antivirus en SharePoint Online.
ms.openlocfilehash: f04cd18bb4880ab631816c90b4976beada436225
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630946"
---
# <a name="virus-detection-in-sharepoint-online"></a>Detección de virus en SharePoint Online

Microsoft 365 puede ayudarle a proteger su entorno del malware detectando virus en los archivos que los usuarios cargan en SharePoint Online. Los archivos pueden analizarse en busca de virus una vez cargados. Si se detecta que un archivo está infectado, se establece una propiedad para que los usuarios no puedan descargar ni sincronizar el archivo.

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
> Puede usar el parámetro *DisallowInfectedFileDownload* en el cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) de PowerShell de SharePoint Online para evitar que los usuarios descarguen un archivo infectado, incluso en la ventana de advertencia de antivirus.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>¿Qué sucede cuando el cliente de sincronización de OneDrive intenta sincronizar un archivo infectado?

Si los usuarios sincronizan archivos con el nuevo cliente de sincronización de OneDrive (OneDrive. exe) o el anterior cliente de sincronización de OneDrive para la empresa (Groove. exe), si un archivo contiene un virus, el cliente de sincronización no lo descargará. El cliente de sincronización mostrará una notificación de que el archivo no se puede sincronizar.
