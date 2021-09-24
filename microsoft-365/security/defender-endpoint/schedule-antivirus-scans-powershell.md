---
title: Programar los exámenes de antivirus con PowerShell
description: Programar los exámenes de antivirus con PowerShell
keywords: examen rápido, examen completo, antivirus, programación, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: 1c9dc7f6b5b34fbfd2eb2c6b76b62650d0d213ca
ms.sourcegitcommit: 584445b62cb82218597b62495fb76fcb5b12af9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2021
ms.locfileid: "59498237"
---
# <a name="schedule-antivirus-scans-using-powershell"></a>Programar los exámenes de antivirus con PowerShell

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

En este artículo se describe cómo configurar exámenes programados con cmdlets de PowerShell. Para obtener más información sobre la programación de exámenes y sobre los tipos de examen, vea [Configure scheduled quick or full Antivirus de Microsoft Defender scans](schedule-antivirus-scans.md). 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a>Usar cmdlets de PowerShell para programar exámenes

Use los cmdlets siguientes:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Para obtener más información, vea [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>Cmdlets de PowerShell para programar exámenes cuando un extremo no está en uso

Use los cmdlets siguientes:

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

Para más información, consulte [Usar cmdlets de PowerShell para configurar y ejecutar Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [cmdlets de Defender](/powershell/module/defender/).

> [!NOTE]
> Al programar exámenes para las horas en las que los puntos de conexión no están en uso, los exámenes no respetan la configuración de limitación de CPU y aprovechan al máximo los recursos disponibles para completar el examen lo más rápido posible.

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a>Cmdlets de PowerShell para programar exámenes para completar la corrección

Use los cmdlets siguientes:

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

Consulte [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a>Cmdlets de PowerShell para programar exámenes diarios

Use los cmdlets siguientes:

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

Para obtener más información acerca de cómo usar PowerShell con Antivirus de Microsoft Defender, vea [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/).


