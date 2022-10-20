---
title: Revisión de los resultados de los exámenes de Microsoft Defender Antivirus
description: Revise los resultados de los exámenes mediante Microsoft Endpoint Configuration Manager, Microsoft Intune o la aplicación Seguridad de Windows
keywords: resultados del examen, corrección, examen completo, examen rápido
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
ms.topic: conceptual
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 6f346e56d9e422c1308363097c22523689da8022
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68637626"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>Revisión de los resultados del examen de Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Una vez completado un examen antivirus de Microsoft Defender, ya sea un [examen a](scheduled-catch-up-scans-microsoft-defender-antivirus.md) [petición](run-scan-microsoft-defender-antivirus.md) o programado, los resultados se registran y puede ver los resultados. 


## <a name="use-configuration-manager-to-review-scan-results"></a>Uso de Configuration Manager para revisar los resultados del examen

Consulte [Supervisión del estado de Endpoint Protection](/configmgr/protect/deploy-use/monitor-endpoint-protection).

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>Uso de cmdlets de PowerShell para revisar los resultados del examen

El siguiente cmdlet devolverá cada detección en el punto de conexión. Si hay varias detecciones de la misma amenaza, cada detección se mostrará por separado, en función de la hora de cada detección:

```PowerShell
Get-MpThreatDetection
```

:::image type="content" source="../../media/wdav-get-mpthreatdetection.png" alt-text="Los cmdlets y salidas de PowerShell" lightbox="../../media/wdav-get-mpthreatdetection.png":::

Puede especificar `-ThreatID` para limitar la salida para mostrar solo las detecciones de una amenaza específica.

Si desea enumerar las detecciones de amenazas, pero combinar las detecciones de la misma amenaza en un solo elemento, puede usar el siguiente cmdlet:

```PowerShell
Get-MpThreat
```

:::image type="content" source="../../media/wdav-get-mpthreat.png" alt-text="El código de PowerShell" lightbox="../../media/wdav-get-mpthreat.png":::

Consulte [Uso de cmdlets de PowerShell para configurar y ejecutar cmdlets Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [Antivirus de Defender](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>Uso de Instrucciones de administración de Windows (WMI) para revisar los resultados del examen

Use el [método **Get** de las clases **MSFT_MpThreat** y **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)


## <a name="related-articles"></a>Artículos relacionados

- [Personalización, inicio y revisión de los resultados de los exámenes y correcciones de Microsoft Defender Antivirus](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
