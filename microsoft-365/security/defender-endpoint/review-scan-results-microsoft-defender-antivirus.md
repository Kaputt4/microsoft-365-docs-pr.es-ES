---
title: Revisar los resultados de los exámenes antivirus de Microsoft Defender
description: Revisar los resultados de los exámenes mediante Microsoft Endpoint Configuration Manager, Microsoft Intune o la aplicación Seguridad de Windows examen
keywords: resultados del examen, corrección, examen completo, examen rápido
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: bc7c84e089b08c440512f8a8bf7583f41394f2ca
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007640"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>Revisar Antivirus de Microsoft Defender de examen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Una vez Antivirus de Microsoft Defender examen completo, tanto si [](run-scan-microsoft-defender-antivirus.md) se trata de un examen a petición como [programado,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)los resultados se registran y se pueden ver los resultados. 


## <a name="use-configuration-manager-to-review-scan-results"></a>Usar Configuration Manager para revisar los resultados del examen

Consulte [How to monitor Endpoint Protection status](/configmgr/protect/deploy-use/monitor-endpoint-protection).

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>Usar cmdlets de PowerShell para revisar los resultados del examen

El siguiente cmdlet devolverá cada detección en el extremo. Si hay varias detecciones de la misma amenaza, cada detección se enumerará por separado, en función del tiempo de cada detección:

```PowerShell
Get-MpThreatDetection
```

:::image type="content" source="../../media/wdav-get-mpthreatdetection.png" alt-text="captura de pantalla de cmdlets y salidas de PowerShell":::

Puede especificar limitar `-ThreatID` el resultado para mostrar solo las detecciones de una amenaza específica.

Si desea enumerar las detecciones de amenazas, pero combinar las detecciones de la misma amenaza en un solo elemento, puede usar el siguiente cmdlet:

```PowerShell
Get-MpThreat
```

:::image type="content" source="../../media/wdav-get-mpthreat.png" alt-text="Código de PowerShell":::

Consulte [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>Usar Windows de administración de documentos (WMI) para revisar los resultados del examen

Use el [ **método Get** de las **MSFT_MpThreat** y **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) clases.


## <a name="related-articles"></a>Artículos relacionados

- [Personalizar, iniciar y revisar los resultados de Antivirus de Microsoft Defender análisis y corrección](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)