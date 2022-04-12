---
title: Programar los exámenes de antivirus con PowerShell
description: Programar los exámenes de antivirus con PowerShell
keywords: examen rápido, examen completo, antivirus, programación, PowerShell
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: 8961428acee5d166b0cdad4982aa5f9ed48020af
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788840"
---
# <a name="schedule-antivirus-scans-using-powershell"></a>Programar los exámenes de antivirus con PowerShell

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

En este artículo se describe cómo configurar exámenes programados mediante cmdlets de PowerShell. Para obtener más información sobre la programación de exámenes y sobre los tipos de examen, consulte [Configuración de exámenes programados rápidos o completos Antivirus de Microsoft Defender](schedule-antivirus-scans.md). 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a>Uso de cmdlets de PowerShell para programar exámenes

Use los siguientes cmdlets:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Para obtener más información, consulte [Uso de cmdlets de PowerShell para configurar y ejecutar cmdlets Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [Antivirus de Defender](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>Cmdlets de PowerShell para la programación de exámenes cuando un punto de conexión no está en uso

Use los siguientes cmdlets:

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

Para obtener más información, vea [Usar cmdlets de PowerShell para configurar y ejecutar el Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [Cmdlets de Antivirus de Microsoft Defender](/powershell/module/defender/).

> [!NOTE]
> Al programar exámenes en busca de tiempos en los que los puntos de conexión no están en uso, los exámenes no respetan la configuración de limitación de CPU y aprovecharán al máximo los recursos disponibles para completar el examen lo más rápido posible.

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a>Cmdlets de PowerShell para programar exámenes para completar la corrección

Use los siguientes cmdlets:

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

Consulte [Uso de cmdlets de PowerShell para configurar y ejecutar](use-powershell-cmdlets-microsoft-defender-antivirus.md) [cmdlets](/powershell/module/defender/) Antivirus de Microsoft Defender y Antivirus de Defender para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a>Cmdlets de PowerShell para programar exámenes diarios

Use los siguientes cmdlets:

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

Para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender, consulte Uso de [cmdlets de PowerShell para configurar y ejecutar cmdlets Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [Antivirus de Defender](/powershell/module/defender/).

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configuración de características de Defender para punto de conexión en Android](android-configure.md)
> - [Configuración de Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)