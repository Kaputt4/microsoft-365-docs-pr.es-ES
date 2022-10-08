---
title: Administrar Microsoft Defender Antivirus en su empresa
description: Aprenda a usar directiva de grupo, Configuration Manager, PowerShell, WMI, Intune y la línea de comandos para administrar Microsoft Defender Antivirus
keywords: directiva de grupo, gpo, administrador de configuración, sccm, scep, powershell, wmi, intune, defender, antivirus, antimalware, security, protection
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.topic: article
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: dcf6baf8c2c161d5b8390ef62f08307daa3f7715
ms.sourcegitcommit: b9282493c371d59c2e583b9803825096499b5e2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68151571"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a>Administrar Microsoft Defender Antivirus en su empresa

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Puede administrar y configurar Microsoft Defender Antivirus con las siguientes herramientas:

- [Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (ahora parte de Microsoft Endpoint Manager)
- [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (ahora parte de Microsoft Endpoint Manager)
- [Directiva de grupo](./use-group-policy-microsoft-defender-antivirus.md)
- [Cmdlets de PowerShell](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Instrumental de administración de Windows (WMI)](./use-wmi-microsoft-defender-antivirus.md)
- [Utilidad de línea de comandos de Protección contra malware de Microsoft](./command-line-arguments-microsoft-defender-antivirus.md) (denominada utilidad *dempcmdrun.exe*

En los artículos siguientes se proporciona más información, vínculos y recursos para usar estas herramientas para administrar y configurar Microsoft Defender Antivirus.

|Artículo|Descripción|
|:---|:---|
|[Administrar Microsoft Defender Antivirus con Microsoft Intune y microsoft endpoint Configuration Manager](use-intune-config-manager-microsoft-defender-antivirus.md)|Información sobre el uso de Intune y Configuration Manager para implementar, administrar, notificar y configurar Microsoft Defender Antivirus|
|[Administrar Microsoft Defender Antivirus con la configuración de directiva de grupo](use-group-policy-microsoft-defender-antivirus.md)|Lista de todas las configuraciones de directiva de grupo que se encuentran en las plantillas de ADMX|
|[Administración de Microsoft Defender Antivirus con cmdlets de PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)|Instrucciones para usar cmdlets de PowerShell para administrar Microsoft Defender Antivirus, además de vínculos a la documentación de todos los cmdlets y parámetros permitidos|
|[Administrar Microsoft Defender Antivirus con Instrumental de administración de Windows (WMI)](use-wmi-microsoft-defender-antivirus.md)|Instrucciones para usar WMI para administrar Microsoft Defender Antivirus, además de vínculos a la documentación de las API WMIv2 (incluidas todas las clases, métodos y propiedades)|
|[Administración de Microsoft Defender Antivirus con la herramienta de línea de comandos de MpCmdRun.exe](command-line-arguments-microsoft-defender-antivirus.md)|Instrucciones sobre el uso de la herramienta de línea de comandos dedicada para administrar y usar Microsoft Defender Antivirus|

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)