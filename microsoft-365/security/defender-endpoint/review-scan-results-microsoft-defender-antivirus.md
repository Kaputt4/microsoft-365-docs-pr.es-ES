---
title: Revisar los resultados de los exámenes antivirus de Microsoft Defender
description: Revisar los resultados de los exámenes con Microsoft Endpoint Configuration Manager, Microsoft Intune o la aplicación Seguridad de Windows
keywords: resultados del examen, corrección, examen completo, examen rápido
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b8a299f41541be878a9e9023ab330ea973646fd
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764150"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>Revisar los resultados del examen del Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Una vez completado el examen de Antivirus [](run-scan-microsoft-defender-antivirus.md) de Microsoft Defender, tanto si se trata de un examen a petición como [programado,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)los resultados se registran y puede ver los resultados. 


## <a name="use-configuration-manager-to-review-scan-results"></a>Usar Configuration Manager para revisar los resultados del examen

Consulte [How to monitor Endpoint Protection status](/configmgr/protect/deploy-use/monitor-endpoint-protection).

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>Usar cmdlets de PowerShell para revisar los resultados del examen

El siguiente cmdlet devolverá cada detección en el extremo. Si hay varias detecciones de la misma amenaza, cada detección se enumerará por separado, en función del tiempo de cada detección:

```PowerShell
Get-MpThreatDetection
```

![captura de pantalla de cmdlets y salidas de PowerShell](images/defender/wdav-get-mpthreatdetection.png)

Puede especificar limitar `-ThreatID` el resultado para mostrar solo las detecciones de una amenaza específica.

Si desea enumerar las detecciones de amenazas, pero combinar las detecciones de la misma amenaza en un solo elemento, puede usar el siguiente cmdlet:

```PowerShell
Get-MpThreat
```

![captura de pantalla de PowerShell](images/defender/wdav-get-mpthreat.png)

Consulte [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>Usar Windows Management Instruction (WMI) para revisar los resultados del examen

Use el [ **método Get** de las **MSFT_MpThreat** y **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) clases.


## <a name="related-articles"></a>Artículos relacionados

- [Personalizar, iniciar y revisar los resultados de los exámenes y la corrección del Antivirus de Microsoft Defender](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)