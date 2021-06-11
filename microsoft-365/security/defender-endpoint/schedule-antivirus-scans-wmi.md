---
title: Programar exámenes antivirus con Windows Management Instrumentation
description: Programar exámenes antivirus con WMI
keywords: examen rápido, examen completo, WMI, programación, antivirus
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
ms.openlocfilehash: 1aa174f4601fb57eebbc4fb7c78e1809b9f072c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879771"
---
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a><span data-ttu-id="4e740-104">Programar exámenes antivirus con Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="4e740-104">Schedule antivirus scans using Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="4e740-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="4e740-105">**Applies to:**</span></span>

- [<span data-ttu-id="4e740-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4e740-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="4e740-107">En este artículo se describe cómo configurar exámenes programados con WMI.</span><span class="sxs-lookup"><span data-stu-id="4e740-107">This article describes how to configure scheduled scans using WMI.</span></span> <span data-ttu-id="4e740-108">Para obtener más información sobre la programación de exámenes y sobre los tipos de examen, vea [Configure scheduled quick or full Antivirus de Microsoft Defender scans](schedule-antivirus-scans.md).</span><span class="sxs-lookup"><span data-stu-id="4e740-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="4e740-109">Usar Windows de administración de documentos (WMI) para programar exámenes</span><span class="sxs-lookup"><span data-stu-id="4e740-109">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="4e740-110">Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="4e740-110">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="4e740-111">Para obtener más información y parámetros permitidos, [vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="4e740-111">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="4e740-112">WMI para programar exámenes cuando un extremo no está en uso</span><span class="sxs-lookup"><span data-stu-id="4e740-112">WMI for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="4e740-113">Utilice el [método Set de la clase MSFT_MpPreference para](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="4e740-113">Use the [Set method of the MSFT_MpPreference class](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="4e740-114">Para obtener más información acerca de las API y los [parámetros permitidos, vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="4e740-114">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="4e740-115">Al programar exámenes para las horas en las que los puntos de conexión no están en uso, los exámenes no respetan la configuración de limitación de CPU y aprovechan al máximo los recursos disponibles para completar el examen lo más rápido posible.</span><span class="sxs-lookup"><span data-stu-id="4e740-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="4e740-116">WMI para programar exámenes para completar la corrección</span><span class="sxs-lookup"><span data-stu-id="4e740-116">WMI for scheduling scans to complete remediation</span></span>

<span data-ttu-id="4e740-117">Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="4e740-117">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="4e740-118">Para obtener más información y parámetros [permitidos, vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="4e740-118">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="wmi-for-scheduling-daily-scans"></a><span data-ttu-id="4e740-119">WMI para programar exámenes diarios</span><span class="sxs-lookup"><span data-stu-id="4e740-119">WMI for scheduling daily scans</span></span>

<span data-ttu-id="4e740-120">Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="4e740-120">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="4e740-121">Para obtener más información y parámetros [permitidos, vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="4e740-121">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

