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
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo SharePoint Online detecta virus en los archivos que los usuarios cargan e impide que los usuarios descarguen o sincronicen los archivos.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0eafb9e5e2f0c9d86791fe83931276e420afcd9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286506"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Protección antivirus integrada en SharePoint Online, OneDrive y Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)

Microsoft 365 usa un motor de detección de virus común para examinar los archivos que los usuarios cargan en SharePoint Online, OneDrive y Microsoft Teams. Esta protección se incluye con todas las suscripciones que incluyen SharePoint Online, OneDrive y Microsoft Teams.

> [!IMPORTANT]
> Las funcionalidades antivirus integradas son una forma de ayudar a contener virus. No están pensadas como un único punto de defensa contra el malware para su entorno. Animamos a todos los clientes a investigar e implementar la protección antimalware en varias capas y aplicar procedimientos recomendados para proteger su infraestructura empresarial. Para obtener más información acerca de las estrategias y los procedimientos recomendados, vea [el mapa de ruta de seguridad.](security-roadmap.md)

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>¿Qué sucede cuando se carga un archivo infectado en SharePoint Online?

El motor de detección de virus de Microsoft 365 se ejecuta asincrónicamente en SharePoint Online. **Todos los archivos no se examinan automáticamente al cargarse.** La heurística determina los archivos que se examinarán. Cuando se encuentra que un archivo contiene un virus, el archivo se marca para que no se pueda volver a descargar. En abril de 2018, eliminamos el límite de 25 MB para los archivos examinados.

Esto es lo que sucede:

1. Un usuario carga un archivo en SharePoint Online.
2. SharePoint Online determina si el archivo cumple los criterios para un examen.
3. El motor de detección de virus examina el archivo.
4. Si se encuentra un virus, el motor de virus establece una propiedad en el archivo que indica que está infectado.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>¿Qué sucede cuando un usuario intenta descargar un archivo infectado mediante el explorador?

Si un archivo está infectado, los usuarios no pueden descargar el archivo desde SharePoint Online mediante un explorador.

Esto es lo que sucede:

1. Un usuario abre un explorador web e intenta descargar un archivo infectado de SharePoint Online.
2. El usuario recibe una advertencia de que se ha detectado un virus. De forma predeterminada, el usuario tiene la opción de descargar el archivo e intentar limpiarlo con el software antivirus en su propio dispositivo.

> [!NOTE]
>
> Los administradores pueden usar el parámetro *DisallowInfectedFileDownload* en el cmdlet [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) en SharePoint Online PowerShell para evitar que los usuarios descarguen archivos infectados, incluso en la ventana de advertencia antivirus. Para obtener instrucciones, [vea Usar SharePoint Online PowerShell para evitar que los usuarios descarguen archivos malintencionados.](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)
>
> Tan pronto como habilites el parámetro *DisallowInfectedFileDownload,* el acceso a los archivos detectados o bloqueados se bloqueará completamente para los usuarios y administradores.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>¿Qué sucede cuando el cliente de sincronización de OneDrive intenta sincronizar un archivo infectado?

Los clientes de sincronización de OneDrive no descargarán archivos que contengan virus. El cliente de sincronización mostrará una notificación de que no se puede sincronizar el archivo.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Funcionalidades extendidas con Microsoft Defender para Office 365

Las organizaciones de Microsoft 365 que tienen Microsoft Defender para [Office 365](office-365-atp.md) incluidas en su suscripción o adquiridas como complemento pueden habilitar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams para mejorar la protección y los informes. Para obtener más información, vea Datos adjuntos [seguros para SharePoint, OneDrive y Microsoft Teams.](atp-for-spo-odb-and-teams.md)

## <a name="related-articles"></a>Artículos relacionados

[Protección contra malware y ransomware en Microsoft 365](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)

Para obtener más información acerca de los antivirus en SharePoint [](protect-against-threats.md) Online, OneDrive y Microsoft Teams, vea Protección contra amenazas y Activar datos adjuntos seguros para [SharePoint, OneDrive](turn-on-atp-for-spo-odb-and-teams.md)y Microsoft Teams.
