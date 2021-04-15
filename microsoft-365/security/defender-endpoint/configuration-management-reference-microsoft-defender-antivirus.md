---
title: Administrar Windows Defender en su empresa
description: Obtenga información sobre cómo usar la directiva de grupo, Configuration Manager, PowerShell, WMI, Intune y la línea de comandos para administrar Microsoft Defender AV
keywords: directiva de grupo, gpo, administrador de configuración, sccm, scep, powershell, wmi, intune, defender, antivirus, antimalware, seguridad, protección
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/16/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6b9845812763f9e3f1fdecf5566824eb76971dad
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764872"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a>Administrar antivirus de Microsoft Defender en su empresa

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Puede administrar y configurar Antivirus de Microsoft Defender con las siguientes herramientas:

- [Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (ahora parte de Microsoft Endpoint Manager)
- [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (ahora parte de Microsoft Endpoint Manager)
- [Directiva de grupo](./use-group-policy-microsoft-defender-antivirus.md)
- [Cmdlets de PowerShell](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Instrumental de administración de Windows (WMI)](./use-wmi-microsoft-defender-antivirus.md)
- Utilidad [de línea de comandos de Microsoft Malware Protection](./command-line-arguments-microsoft-defender-antivirus.md) (denominada utilidad *mpcmdrun.exe* protección contra malware

Los artículos siguientes proporcionan más información, vínculos y recursos para usar estas herramientas para administrar y configurar Antivirus de Microsoft Defender.

| Artículo | Descripción |
|:---|:---|
|[Administrar Antivirus de Microsoft Defender con Microsoft Intune y Microsoft Endpoint Configuration Manager](use-intune-config-manager-microsoft-defender-antivirus.md)|Información sobre cómo usar Intune y Configuration Manager para implementar, administrar, informar y configurar Antivirus de Microsoft Defender |
|[Administrar antivirus de Microsoft Defender con configuración de directiva de grupo](use-group-policy-microsoft-defender-antivirus.md)|Lista de todas las opciones de configuración de directiva de grupo ubicadas en plantillas ADMX |
|[Administrar Antivirus de Microsoft Defender con cmdlets de PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)|Instrucciones para usar cmdlets de PowerShell para administrar Antivirus de Microsoft Defender, además de vínculos a documentación para todos los cmdlets y parámetros permitidos |
|[Administrar Antivirus de Microsoft Defender con Instrumental de administración de Windows (WMI)](use-wmi-microsoft-defender-antivirus.md)| Instrucciones para usar WMI para administrar Microsoft Defender Antivirus, además de vínculos a la documentación de las API WMIv2 (incluidas todas las clases, métodos y propiedades) |
|[Administrar Antivirus de Microsoft Defender con la mpcmdrun.exe de línea de comandos](command-line-arguments-microsoft-defender-antivirus.md)|Instrucciones sobre cómo usar la herramienta de línea de comandos dedicada para administrar y usar Antivirus de Microsoft Defender |