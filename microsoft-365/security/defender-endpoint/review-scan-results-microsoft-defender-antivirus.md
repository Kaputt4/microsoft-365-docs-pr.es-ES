---
title: Revisar los resultados de los exámenes antivirus de Microsoft Defender
description: Revisar los resultados de los exámenes con Microsoft Endpoint Configuration Manager, Microsoft Intune o la aplicación Seguridad de Windows
keywords: resultados del examen, corrección, examen completo, examen rápido
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8fe2810ce18589d3131aa17f25ccfb01ec26b892
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691208"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a><span data-ttu-id="a1403-104">Revisar los resultados del examen del Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a1403-104">Review Microsoft Defender Antivirus scan results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a1403-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a1403-105">**Applies to:**</span></span>

- [<span data-ttu-id="a1403-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="a1403-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a1403-107">Una vez completado el examen de Antivirus [](run-scan-microsoft-defender-antivirus.md) de Microsoft Defender, tanto si se trata de un examen a petición como [programado,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)los resultados se registran y puede ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="a1403-107">After a Microsoft Defender Antivirus scan completes, whether it is an [on-demand](run-scan-microsoft-defender-antivirus.md) or [scheduled scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md), the results are recorded and you can view the results.</span></span> 


## <a name="use-configuration-manager-to-review-scan-results"></a><span data-ttu-id="a1403-108">Usar Configuration Manager para revisar los resultados del examen</span><span class="sxs-lookup"><span data-stu-id="a1403-108">Use Configuration Manager to review scan results</span></span>

<span data-ttu-id="a1403-109">Consulte [How to monitor Endpoint Protection status](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span><span class="sxs-lookup"><span data-stu-id="a1403-109">See [How to monitor Endpoint Protection status](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span>

## <a name="use-powershell-cmdlets-to-review-scan-results"></a><span data-ttu-id="a1403-110">Usar cmdlets de PowerShell para revisar los resultados del examen</span><span class="sxs-lookup"><span data-stu-id="a1403-110">Use PowerShell cmdlets to review scan results</span></span>

<span data-ttu-id="a1403-111">El siguiente cmdlet devolverá cada detección en el extremo.</span><span class="sxs-lookup"><span data-stu-id="a1403-111">The following cmdlet will return each detection on the endpoint.</span></span> <span data-ttu-id="a1403-112">Si hay varias detecciones de la misma amenaza, cada detección se enumerará por separado, en función del tiempo de cada detección:</span><span class="sxs-lookup"><span data-stu-id="a1403-112">If there are multiple detections of the same threat, each detection will be listed separately, based on the time of each detection:</span></span>

```PowerShell
Get-MpThreatDetection
```

![captura de pantalla de cmdlets y salidas de PowerShell](images/defender/wdav-get-mpthreatdetection.png)

<span data-ttu-id="a1403-114">Puede especificar limitar `-ThreatID` el resultado para mostrar solo las detecciones de una amenaza específica.</span><span class="sxs-lookup"><span data-stu-id="a1403-114">You can specify `-ThreatID` to limit the output to only show the detections for a specific threat.</span></span>

<span data-ttu-id="a1403-115">Si desea enumerar las detecciones de amenazas, pero combinar las detecciones de la misma amenaza en un solo elemento, puede usar el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a1403-115">If you want to list threat detections, but combine detections of the same threat into a single item, you can use the following cmdlet:</span></span>

```PowerShell
Get-MpThreat
```

![captura de pantalla de PowerShell](images/defender/wdav-get-mpthreat.png)

<span data-ttu-id="a1403-117">Consulte [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="a1403-117">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a><span data-ttu-id="a1403-118">Usar Windows Management Instruction (WMI) para revisar los resultados del examen</span><span class="sxs-lookup"><span data-stu-id="a1403-118">Use Windows Management Instruction (WMI) to review scan results</span></span>

<span data-ttu-id="a1403-119">Use el [ **método Get** de las **MSFT_MpThreat** y **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) clases.</span><span class="sxs-lookup"><span data-stu-id="a1403-119">Use the [**Get** method of the **MSFT_MpThreat** and **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) classes.</span></span>


## <a name="related-articles"></a><span data-ttu-id="a1403-120">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="a1403-120">Related articles</span></span>

- [<span data-ttu-id="a1403-121">Personalizar, iniciar y revisar los resultados de los exámenes y la corrección del Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a1403-121">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a1403-122">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="a1403-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)