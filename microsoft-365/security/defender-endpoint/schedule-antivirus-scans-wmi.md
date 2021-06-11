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
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a>Programar exámenes antivirus con Windows Management Instrumentation (WMI)

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

En este artículo se describe cómo configurar exámenes programados con WMI. Para obtener más información sobre la programación de exámenes y sobre los tipos de examen, vea [Configure scheduled quick or full Antivirus de Microsoft Defender scans](schedule-antivirus-scans.md). 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Usar Windows de administración de documentos (WMI) para programar exámenes

Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Para obtener más información y parámetros permitidos, [vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>WMI para programar exámenes cuando un extremo no está en uso

Utilice el [método Set de la clase MSFT_MpPreference para](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) las siguientes propiedades:

```WMI
ScanOnlyIfIdleEnabled
```

Para obtener más información acerca de las API y los [parámetros permitidos, vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

> [!NOTE]
> Al programar exámenes para las horas en las que los puntos de conexión no están en uso, los exámenes no respetan la configuración de limitación de CPU y aprovechan al máximo los recursos disponibles para completar el examen lo más rápido posible.


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a>WMI para programar exámenes para completar la corrección

Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Para obtener más información y parámetros [permitidos, vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

## <a name="wmi-for-scheduling-daily-scans"></a>WMI para programar exámenes diarios

Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
ScanScheduleQuickScanTime
```

Para obtener más información y parámetros [permitidos, vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

