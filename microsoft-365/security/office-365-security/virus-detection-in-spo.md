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
ms.openlocfilehash: a651d198f441c26525cbfb5d7406ae350db8b79e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908087"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Protección contra virus integrada en SharePoint Online, OneDrive y Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)

Microsoft 365 usa un motor de detección de virus común para examinar los archivos que los usuarios cargan en SharePoint Online, OneDrive y Microsoft Teams. Esta protección se incluye con todas las suscripciones que incluyen SharePoint Online, OneDrive y Microsoft Teams.

> [!IMPORTANT]
> Las funcionalidades antivirus integradas son una forma de ayudar a contener virus. No están pensados como un único punto de defensa contra malware para su entorno. Animamos a todos los clientes a investigar e implementar la protección antimalware en varias capas y aplicar procedimientos recomendados para proteger su infraestructura empresarial. Para obtener más información sobre estrategias y procedimientos recomendados, vea [Security roadmap](security-roadmap.md).

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a>¿Qué sucede si se carga un archivo infectado en SharePoint Online?

El motor de detección de virus de Microsoft 365 se ejecuta de forma asincrónica (independiente de las cargas de archivos) en SharePoint Online. **Todos los archivos no se examinan automáticamente.** La heurística determina los archivos que se examinarán. Cuando se encuentra que un archivo contiene un virus, se marca el archivo. En abril de 2018, se eliminó el límite de 25 MB para los archivos analizados.

Esto es lo que sucede:

1. Un usuario carga un archivo en SharePoint Online.
2. SharePoint Online, como parte de sus procesos de análisis de virus, determina más adelante si el archivo cumple los criterios para un examen.
3. Si el archivo cumple los criterios para un examen, el motor de detección de virus examina el archivo.
4. Si se encuentra un virus en el archivo examinado, el motor de virus establece una propiedad en el archivo que indica que está infectado.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>¿Qué sucede cuando un usuario intenta descargar un archivo infectado mediante el explorador?

Si un archivo está infectado, los usuarios no pueden descargar el archivo desde SharePoint Online mediante un explorador.

Esto es lo que sucede:

1. Un usuario abre un explorador web e intenta descargar un archivo infectado de SharePoint Online.
2. El usuario recibe una advertencia de que se ha detectado un virus. De forma predeterminada, el usuario tiene la opción de descargar el archivo e intentar limpiarlo con el software antivirus en su propio dispositivo.

> [!NOTE]
>
> Los administradores pueden usar el parámetro *DisallowInfectedFileDownload* en el cmdlet [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) en PowerShell de SharePoint Online para impedir que los usuarios descarguen archivos infectados, incluso en la ventana de advertencia antivirus. Para obtener instrucciones, [vea Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).
>
> Tan pronto como habilite el parámetro *DisallowInfectedFileDownload,* el acceso a los archivos detectados o bloqueados se bloqueará completamente para usuarios y administradores.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>¿Qué sucede cuando el cliente de sincronización de OneDrive intenta sincronizar un archivo infectado?

Los clientes de sincronización de OneDrive no descargarán archivos que contengan virus. El cliente de sincronización mostrará una notificación de que el archivo no se puede sincronizar.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Funcionalidades extendidas con Microsoft Defender para Office 365

Las organizaciones de Microsoft 365 que tienen [Microsoft Defender para Office 365](office-365-atp.md) incluidas en su suscripción o compradas como complemento pueden habilitar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams para mejorar la protección y los informes. Para obtener más información, vea [Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md).

## <a name="related-articles"></a>Artículos relacionados

[Protección contra malware y ransomware en Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)

Para obtener más información sobre antivirus en SharePoint Online, OneDrive y Microsoft Teams, vea [Proteger](protect-against-threats.md) contra amenazas y Activar datos adjuntos seguros para [SharePoint, OneDrive](turn-on-atp-for-spo-odb-and-teams.md)y Microsoft Teams .