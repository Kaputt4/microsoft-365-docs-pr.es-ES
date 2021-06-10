---
title: Protección contra virus integrada en SharePoint Online, OneDrive y Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo SharePoint Online detecta virus en archivos que los usuarios cargan e impide que los usuarios descarguen o sincronicen los archivos.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dd38b196c106a36fb1a1bfc0a441620b1c5b8ba5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205330"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Protección contra virus integrada en SharePoint Online, OneDrive y Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

Microsoft 365 un motor de detección de virus común para examinar los archivos que los usuarios cargan en SharePoint Online, OneDrive y Microsoft Teams. Esta protección se incluye con todas las suscripciones que incluyen SharePoint Online, OneDrive y Microsoft Teams.

> [!IMPORTANT]
> Las funcionalidades antivirus integradas son una forma de ayudar a contener virus. No están pensados como un único punto de defensa contra malware para su entorno. Animamos a todos los clientes a investigar e implementar la protección antimalware en varias capas y aplicar procedimientos recomendados para proteger su infraestructura empresarial. Para obtener más información sobre estrategias y procedimientos recomendados, vea [Security roadmap](security-roadmap.md).

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a>¿Qué sucede si un archivo infectado se carga en SharePoint Online?

El Microsoft 365 de detección de virus se ejecuta de forma asincrónica (independiente de las cargas de archivos) en SharePoint Online. **Todos los archivos no se examinan automáticamente.** La heurística determina los archivos que se examinarán. Cuando se encuentra que un archivo contiene un virus, se marca el archivo. En abril de 2018, se eliminó el límite de 25 MB para los archivos analizados.

Esto es lo que sucede:

1. Un usuario carga un archivo en SharePoint Online.
2. SharePoint En línea, como parte de sus procesos de detección de virus, más adelante determina si el archivo cumple los criterios para un examen.
3. Si el archivo cumple los criterios para un examen, el motor de detección de virus examina el archivo.
4. Si se encuentra un virus en el archivo examinado, el motor de virus establece una propiedad en el archivo que indica que está infectado.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>¿Qué sucede cuando un usuario intenta descargar un archivo infectado mediante el explorador?

Si un archivo está infectado, los usuarios no pueden descargar el archivo desde SharePoint Online mediante un explorador.

Esto es lo que sucede:

1. Un usuario abre un explorador web e intenta descargar un archivo infectado desde SharePoint Online.
2. El usuario recibe una advertencia de que se ha detectado un virus. De forma predeterminada, el usuario tiene la opción de descargar el archivo e intentar limpiarlo con el software antivirus en su propio dispositivo.

> [!NOTE]
>
> Los administradores pueden usar el parámetro *DisallowInfectedFileDownload* en el cmdlet [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) de SharePoint Online PowerShell para impedir que los usuarios descarguen archivos infectados, incluso en la ventana de advertencia antivirus. Para obtener instrucciones, vea [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).
>
> Tan pronto como habilite el parámetro *DisallowInfectedFileDownload,* el acceso a los archivos detectados o bloqueados se bloqueará completamente para usuarios y administradores.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>¿Qué sucede cuando el OneDrive de sincronización intenta sincronizar un archivo infectado?

OneDrive de sincronización no descargarán archivos que contengan virus. El cliente de sincronización mostrará una notificación de que el archivo no se puede sincronizar.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Funcionalidades extendidas con Microsoft Defender para Office 365

Microsoft 365 las organizaciones que tienen [Microsoft Defender](defender-for-office-365.md) para Office 365 incluidos en su suscripción o comprados como complemento pueden habilitar los datos adjuntos de Caja fuerte para SharePoint, OneDrive y Microsoft Teams para mejorar la protección y los informes. Para obtener más información, [vea Caja fuerte attachments for SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md).

## <a name="related-articles"></a>Artículos relacionados

[Protección contra malware y ransomware en Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)

Para obtener más información acerca de los antivirus en SharePoint Online, OneDrive y Microsoft Teams, vea [Protect against threats](protect-against-threats.md) y Turn on Caja fuerte Attachments for [SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).
