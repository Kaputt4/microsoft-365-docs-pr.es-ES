---
title: Programar exámenes rápidos y completos regulares con Antivirus de Microsoft Defender
description: Configurar exámenes periódicos (programados), incluso cuándo deben ejecutarse y si se ejecutan como exámenes rápidos o completos
keywords: examen rápido, examen completo, rápido vs completo, examen de programación, diario, semanal, hora, programado, periódico, regular
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 66907fca7a117eeba7ca0b9bd95d59af24c31341
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691303"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Configurar exámenes programados rápidos o completos de Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> De forma predeterminada, Antivirus de Microsoft Defender busca una actualización 15 minutos antes de la hora de los exámenes programados. Puede administrar [la programación de cuándo se](manage-protection-update-schedule-microsoft-defender-antivirus.md) deben descargar y aplicar las actualizaciones de protección para invalidar este valor predeterminado. 

Además de la protección siempre activa [](run-scan-microsoft-defender-antivirus.md) en tiempo real y los exámenes a petición, puede configurar exámenes regulares programados. 

Puede configurar el tipo de examen, cuándo debe producirse el [](manage-protection-updates-microsoft-defender-antivirus.md) examen y si el examen debe producirse después de una actualización de protección o si se está utilizando el extremo. También puede especificar cuándo deben producirse exámenes especiales para completar la corrección.

En este artículo se describe cómo configurar exámenes programados con directiva de grupo, cmdlets de PowerShell y WMI. También puede configurar exámenes de programación con [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) o Microsoft [Intune](/mem/intune/configuration/device-restrictions-windows-10).

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>Para configurar las opciones de directiva de grupo descritas en este artículo

1.  En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

3.  En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**

4.  Haga clic **en Plantillas administrativas**.

5.  Expande el árbol a **componentes de Windows > Antivirus** de Microsoft Defender y, a continuación, la **ubicación** especificada en la tabla siguiente.

6. Haga doble clic en la configuración **de directiva** especificada en la tabla siguiente y establezca la opción en la configuración deseada. 

7. Haga **clic en** Aceptar y repita cualquier otra configuración.

Vea también administrar cuándo [se deben](manage-protection-update-schedule-microsoft-defender-antivirus.md) descargar y aplicar las actualizaciones de protección y Evitar o permitir que los usuarios [modifiquen localmente los](configure-local-policy-overrides-microsoft-defender-antivirus.md) temas de configuración de directivas.

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>Examen rápido frente a examen completo y examen personalizado

Al configurar exámenes programados, puede configurar si el examen debe ser un examen completo o rápido.

Los exámenes rápidos examinan todas las ubicaciones donde podría haber malware registrado para empezar con el sistema, como las claves del Registro y las carpetas de inicio conocidas de Windows. 

Combinado con la funcionalidad de protección siempre activa en tiempo [real](configure-real-time-protection-microsoft-defender-antivirus.md) , que revisa los archivos cuando se abren y cierran, y siempre que un usuario navega a una carpeta, un examen rápido ayuda a proporcionar una cobertura segura tanto para malware que comienza con el malware del sistema como del nivel de kernel.  

En la mayoría de los casos, esto significa que un examen rápido es adecuado para encontrar malware que no fue detectado por la protección en tiempo real.

Un examen completo puede ser útil en los puntos de conexión que han encontrado una amenaza de malware para identificar si hay componentes inactivos que requieren una limpieza más exhaustiva. En este caso, es posible que desee usar un examen completo al ejecutar un examen a [petición.](run-scan-microsoft-defender-antivirus.md)

Un examen personalizado le permite especificar los archivos y carpetas que desea examinar, como una unidad USB. 

>[!NOTE]
>De forma predeterminada, los exámenes rápidos se ejecutan en dispositivos extraíbles montados, como unidades USB.

## <a name="set-up-scheduled-scans"></a>Configurar exámenes programados

Los exámenes programados se ejecutarán en el día y la hora que especifique. Puede usar la directiva de grupo, PowerShell y WMI para configurar exámenes programados.

>[!NOTE]
>Si un equipo se desconecta y se ejecuta en la batería durante un examen completo programado, el examen programado se detendrá con el evento 1002, que indica que el examen se detuvo antes de finalizar. Antivirus de Microsoft Defender ejecutará un examen completo en la próxima hora programada.

### <a name="use-group-policy-to-schedule-scans"></a>Usar directiva de grupo para programar exámenes

|Ubicación | Configuración | Descripción | Configuración predeterminada (si no está configurada) |
|:---|:---|:---|:---|
|Examinar | Especificar el tipo de examen que se usará para un examen programado | Examen rápido |
|Examinar | Especificar el día de la semana para ejecutar un examen programado | Especifique el día (o nunca) para ejecutar un examen. | Nunca |
|Examinar | Especificar la hora del día para ejecutar un examen programado | Especifique el número de minutos después de medianoche (por ejemplo, escriba **60** para la 1 a.m.). | 2 a. m. |
|Raíz | Randomize scheduled task times |En Antivirus de Microsoft Defender: aleatorice la hora de inicio del examen a cualquier intervalo de 0 a 4 horas. <br>En FEP/SCEP: aleatorizar a cualquier intervalo más o menos 30 minutos. Esto puede ser útil en implementaciones de VM o VDI. | Habilitado |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>Usar cmdlets de PowerShell para programar exámenes

Use los cmdlets siguientes:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Consulte [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Usar instrucciones de administración de Windows (WMI) para programar exámenes

Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Vea lo siguiente para obtener más información y parámetros permitidos:
- [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a>Iniciar exámenes programados solo cuando el extremo no esté en uso

Puede establecer que el examen programado solo se produzca cuando el extremo está activado pero no se usa con la directiva de grupo, PowerShell o WMI.

> [!NOTE]
> Estos exámenes no respetarán la configuración de limitación de CPU y aprovecharán al máximo los recursos disponibles para completar el examen lo más rápido posible.

### <a name="use-group-policy-to-schedule-scans"></a>Usar directiva de grupo para programar exámenes

|Ubicación | Configuración | Descripción | Configuración predeterminada (si no está configurada) |
|:---|:---|:---|:---|
|Examinar | Iniciar el examen programado solo cuando el equipo está en uso pero no está en uso | Los exámenes programados no se ejecutarán, a menos que el equipo esté en uso pero no esté en uso | Habilitado |

### <a name="use-powershell-cmdlets"></a>Usar cmdlets de PowerShell

Use los cmdlets siguientes:

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

Consulte [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi"></a>Usar instrucciones de administración de Windows (WMI)

Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
ScanOnlyIfIdleEnabled
```

Vea lo siguiente para obtener más información y parámetros permitidos:
- [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>Configurar cuándo deben ejecutarse exámenes completos para completar la corrección

Algunas amenazas pueden requerir un examen completo para completar su eliminación y corrección. Puede programar cuándo deben producirse estos exámenes con la directiva de grupo, PowerShell o WMI.

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a>Usar la directiva de grupo para programar exámenes necesarios para la corrección

| Ubicación | Configuración | Descripción | Configuración predeterminada (si no está configurada) |
|---|---|---|---|
|Corrección | Especificar el día de la semana para ejecutar un examen completo programado para completar la corrección | Especifique el día (o nunca) para ejecutar un examen. | Nunca |
|Corrección | Especificar la hora del día para ejecutar un examen completo programado para completar la corrección | Especifique el número de minutos después de la medianoche (por ejemplo, escriba **60** para la 1 a.m.) | 2 a. m. |

### <a name="use-powershell-cmdlets"></a>Usar cmdlets de PowerShell

Use los cmdlets siguientes:

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

Consulte [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi"></a>Usar instrucciones de administración de Windows (WMI)

Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Vea lo siguiente para obtener más información y parámetros permitidos:
- [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a>Configurar exámenes rápidos diarios

Puede habilitar un examen rápido diario que se puede ejecutar además de los otros exámenes programados con la directiva de grupo, PowerShell o WMI.


### <a name="use-group-policy-to-schedule-daily-scans"></a>Usar directiva de grupo para programar exámenes diarios


|Ubicación | Configuración | Descripción | Configuración predeterminada (si no está configurada) |
|:---|:---|:---|:---|
|Examinar | Especificar el intervalo para ejecutar exámenes rápidos por día | Especifique cuántas horas debe transcurrir antes del siguiente examen rápido. Por ejemplo, para ejecutarse cada dos horas, escriba **2**, para una vez al día, escriba **24**. Escriba **0** para nunca ejecutar un examen rápido diario. | Nunca |
|Examinar | Especificar la hora de un examen rápido diario | Especifique el número de minutos después de la medianoche (por ejemplo, escriba **60** para la 1 a.m.) | 2 a. m. |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a>Usar cmdlets de PowerShell para programar exámenes diarios

Use los cmdlets siguientes:

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

Consulte [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>Usar Windows Management Instruction (WMI) para programar exámenes diarios

Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
ScanScheduleQuickScanTime
```

Vea lo siguiente para obtener más información y parámetros permitidos:
- [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a>Habilitar exámenes después de actualizaciones de protección

Puede forzar que se produzca un examen después de cada actualización [de protección con](manage-protection-updates-microsoft-defender-antivirus.md) la directiva de grupo.

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a>Usar la directiva de grupo para programar exámenes después de las actualizaciones de protección

|Ubicación | Configuración | Descripción | Configuración predeterminada (si no está configurada)|
|:---|:---|:---|:---|
|Actualizaciones de firmas | Activar el examen después de la actualización de inteligencia de seguridad | Un examen se realizará inmediatamente después de descargar una nueva actualización de protección | Habilitado |

## <a name="see-also"></a>Vea también
- [Impedir o permitir que los usuarios modifiquen localmente la configuración de directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [Configurar y ejecutar exámenes de Antivirus de Microsoft Defender a petición](run-scan-microsoft-defender-antivirus.md)
- [Configurar opciones de análisis de Antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar líneas base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Administrar cuándo se deben descargar y aplicar las actualizaciones de protección](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)