---
title: Administrar Antivirus de Microsoft Defender en su empresa
description: Obtenga información sobre cómo usar la directiva de grupo, Configuration Manager, PowerShell, WMI, Intune y la línea de comandos para administrar Microsoft Defender AV
keywords: directiva de grupo, gpo, administrador de configuración, sccm, scep, powershell, wmi, intune, defender, antivirus, antimalware, seguridad, protección
ms.prod: m365-security
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
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 49d61529c966771004ae9c7aed881f98a718bdec
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2021
ms.locfileid: "60884114"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a>Administrar Antivirus de Microsoft Defender en su empresa

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)
- [Antivirus de Microsoft Defender](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-windows)

Puede administrar y configurar Antivirus de Microsoft Defender con las siguientes herramientas:

- [Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (ahora parte de Microsoft Endpoint Manager)
- [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (ahora parte de Microsoft Endpoint Manager)
- [Directiva de grupo](./use-group-policy-microsoft-defender-antivirus.md)
- [Cmdlets de PowerShell](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Windows Instrumental de administración (WMI)](./use-wmi-microsoft-defender-antivirus.md)
- Utilidad [de línea de comandos de Microsoft Malware Protection](./command-line-arguments-microsoft-defender-antivirus.md) (denominada utilidad *mpcmdrun.exe* protección contra malware

Los artículos siguientes proporcionan más información, vínculos y recursos para usar estas herramientas para administrar y configurar Antivirus de Microsoft Defender.

|Artículo|Descripción|
|:---|:---|
|[Administrar Antivirus de Microsoft Defender con Microsoft Intune y Microsoft Endpoint Configuration Manager](use-intune-config-manager-microsoft-defender-antivirus.md)|Información sobre cómo usar Intune y Configuration Manager para implementar, administrar, informar y configurar Antivirus de Microsoft Defender|
|[Administrar Antivirus de Microsoft Defender con la configuración de directiva de grupo](use-group-policy-microsoft-defender-antivirus.md)|Lista de todas las opciones de configuración de directiva de grupo ubicadas en plantillas ADMX|
|[Administrar Antivirus de Microsoft Defender con cmdlets de PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)|Instrucciones para usar cmdlets de PowerShell para administrar Antivirus de Microsoft Defender, además de vínculos a documentación para todos los cmdlets y parámetros permitidos|
|[Administrar Antivirus de Microsoft Defender con Windows Management Instrumentation (WMI)](use-wmi-microsoft-defender-antivirus.md)|Instrucciones para usar WMI para administrar Antivirus de Microsoft Defender, además de vínculos a la documentación de las API WMIv2 (incluidas todas las clases, métodos y propiedades)|
|[Administrar Antivirus de Microsoft Defender con la MpCmdRun.exe de línea de comandos](command-line-arguments-microsoft-defender-antivirus.md)|Instrucciones sobre cómo usar la herramienta de línea de comandos dedicada para administrar y usar Antivirus de Microsoft Defender|
