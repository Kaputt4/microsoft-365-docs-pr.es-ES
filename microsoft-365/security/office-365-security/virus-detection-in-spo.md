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
ms.localizationpriority: medium
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
ms.openlocfilehash: e57865d0c8ec3993080c822438b7c4037ccab765
ms.sourcegitcommit: e6595be36bbaba244439bd59dbae935e2b258ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2022
ms.locfileid: "67450067"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Protección antivirus integrada en SharePoint Online, OneDrive y Microsoft Teams

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

Microsoft 365 usa un motor de detección de virus común para examinar archivos que los usuarios cargan en SharePoint Online, OneDrive y Microsoft Teams. Esta protección se incluye con todas las suscripciones que incluyen SharePoint Online, OneDrive y Microsoft Teams.

> [!IMPORTANT]
> Las funcionalidades antivirus integradas son una manera de ayudar a contener virus. No están pensadas como un único punto de defensa contra malware para su entorno. Animamos a todos los clientes a investigar e implementar la protección contra malware en varias capas y aplicar los procedimientos recomendados para proteger su infraestructura empresarial. Para obtener más información sobre estrategias y procedimientos recomendados, consulte [Plan de desarrollo de seguridad](security-roadmap.md).

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a>¿Qué ocurre si se carga un archivo infectado en SharePoint Online?

El motor de detección de virus de Microsoft 365 examina los archivos de forma asincrónica (en algún momento después de la carga). Si el proceso de detección de virus asincrónico aún no ha examinado un archivo y un usuario intenta descargar el archivo desde el explorador o desde Teams, SharePoint desencadena un examen al descargarlo antes de que se permita la descarga. **Todos los tipos de archivo no se examinan automáticamente**. La heurística determina los archivos que se van a examinar. Cuando se detecta que un archivo contiene un virus, el archivo se marca. 

Esto es lo que sucede:

1. Un usuario carga un archivo en SharePoint Online.
2. SharePoint Online, como parte de sus procesos de detección de virus, determina más adelante si el archivo cumple los criterios para un examen.
3. Si el archivo cumple los criterios para un examen, el motor de detección de virus examina el archivo.
4. Si se encuentra un virus en el archivo examinado, el motor de virus establece una propiedad en el archivo que indica que el archivo está infectado.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>¿Qué ocurre cuando un usuario intenta descargar un archivo infectado mediante el explorador?

De forma predeterminada, los usuarios pueden descargar archivos infectados desde SharePoint Online. Esto es lo que sucede:

1. En un explorador web, un usuario intenta descargar un archivo de SharePoint Online que resulta estar infectado.
2. Al usuario se le muestra una advertencia de que se ha detectado un virus en el archivo. El usuario tiene la opción de continuar con la descarga e intentar limpiarla mediante software antivirus en su dispositivo.

Para cambiar este comportamiento para que los usuarios no puedan descargar archivos infectados, incluso desde la ventana de advertencia antivirus, los administradores pueden usar el parámetro *DisallowInfectedFileDownload* en el cmdlet **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** en PowerShell de SharePoint Online. El valor $true para el parámetro *DisallowInfectedFileDownload* bloquea completamente el acceso a los archivos detectados o bocked para los usuarios.

Para obtener instrucciones, consulte [Uso de PowerShell de SharePoint Online para evitar que los usuarios descarguen archivos malintencionados](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).

## <a name="can-admins-bypass-disallowinfectedfiledownload-and-extract-infected-files"></a>¿Pueden los administradores omitir *DisallowInfectedFileDownload* y extraer archivos infectados?

Los administradores de SharePoint y los administradores globales pueden realizar extracciones de archivos forenses de archivos infectados por malware en PowerShell de SharePoint Online con el cmdlet [Get-SPOMalwareFileContent](/powershell/module/sharepoint-online/get-spomalwarefilecontent) . Los administradores no necesitan acceso al sitio que hospeda el contenido infectado. Siempre que el archivo se haya marcado como malware, los administradores pueden usar **Get-SPOMalwareFileContent** para extraer el archivo. 

Para obtener más información sobre el archivo infectado, los administradores pueden usar el cmdlet **[Get-SPOMalwareFile](/powershell/module/sharepoint-online/get-spomalwarefile)** para ver el tipo de malware detectado y el estado de la infección. 

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>¿Qué ocurre cuando el cliente de Sincronización de OneDrive intenta sincronizar un archivo infectado?

Cuando se carga un archivo malintencionado en OneDrive, se sincronizará con la máquina local antes de que se marque como malware. Una vez marcado como malware, el usuario ya no puede abrir el archivo sincronizado desde su equipo local.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Funcionalidades extendidas con Microsoft Defender para Office 365

Las organizaciones de Microsoft 365 que tienen [Microsoft Defender para Office 365](defender-for-office-365.md) incluidas en su suscripción o compradas como complemento pueden habilitar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams para la creación de informes y protección mejoradas. Para obtener más información, vea [Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md).

## <a name="related-articles"></a>Artículos relacionados

[Protección contra malware y ransomware en Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)

Para obtener más información sobre antivirus en SharePoint Online, OneDrive y Microsoft Teams, vea [Proteger contra amenazas](protect-against-threats.md) y [Activar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).
