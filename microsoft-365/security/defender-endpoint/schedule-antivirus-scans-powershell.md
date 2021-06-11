---
title: Programar exámenes antivirus con PowerShell
description: Programar exámenes antivirus con PowerShell
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
ms.openlocfilehash: 73ba654dd312c63651f0cf43244796e94e8ad55b
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879774"
---
# <a name="schedule-antivirus-scans-using-powershell"></a><span data-ttu-id="51edc-104">Programar exámenes antivirus con PowerShell</span><span class="sxs-lookup"><span data-stu-id="51edc-104">Schedule antivirus scans using PowerShell</span></span>

<span data-ttu-id="51edc-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="51edc-105">**Applies to:**</span></span>

- [<span data-ttu-id="51edc-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="51edc-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="51edc-107">En este artículo se describe cómo configurar exámenes programados con cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51edc-107">This article describes how to configure scheduled scans using PowerShell cmdlets.</span></span> <span data-ttu-id="51edc-108">Para obtener más información sobre la programación de exámenes y sobre los tipos de examen, vea [Configure scheduled quick or full Antivirus de Microsoft Defender scans](schedule-antivirus-scans.md).</span><span class="sxs-lookup"><span data-stu-id="51edc-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="51edc-109">Usar cmdlets de PowerShell para programar exámenes</span><span class="sxs-lookup"><span data-stu-id="51edc-109">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="51edc-110">Use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="51edc-110">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="51edc-111">Para obtener más información, vea [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="51edc-111">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="51edc-112">Cmdlets de PowerShell para programar exámenes cuando un extremo no está en uso</span><span class="sxs-lookup"><span data-stu-id="51edc-112">PowerShell cmdlets for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="51edc-113">Use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="51edc-113">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="51edc-114">Para más información, consulte [Usar cmdlets de PowerShell para configurar y ejecutar Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [cmdlets de Defender](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="51edc-114">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

> [!NOTE]
> <span data-ttu-id="51edc-115">Al programar exámenes para las horas en las que los puntos de conexión no están en uso, los exámenes no respetan la configuración de limitación de CPU y aprovechan al máximo los recursos disponibles para completar el examen lo más rápido posible.</span><span class="sxs-lookup"><span data-stu-id="51edc-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="51edc-116">Cmdlets de PowerShell para programar exámenes para completar la corrección</span><span class="sxs-lookup"><span data-stu-id="51edc-116">PowerShell cmdlets for scheduling scans to complete remediation</span></span>

<span data-ttu-id="51edc-117">Use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="51edc-117">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="51edc-118">Consulte [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="51edc-118">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a><span data-ttu-id="51edc-119">Cmdlets de PowerShell para programar exámenes diarios</span><span class="sxs-lookup"><span data-stu-id="51edc-119">PowerShell cmdlets for scheduling daily scans</span></span>

<span data-ttu-id="51edc-120">Use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="51edc-120">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="51edc-121">Para obtener más información acerca de cómo usar PowerShell con Antivirus de Microsoft Defender, vea [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="51edc-121">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>


