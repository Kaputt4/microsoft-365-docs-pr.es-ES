---
title: Programar exámenes rápidos y completos regulares con Antivirus de Microsoft Defender
description: Configurar exámenes periódicos (programados), incluso cuándo deben ejecutarse y si se ejecutan como exámenes rápidos o completos
keywords: examen rápido, examen completo, rápido vs completo, examen de programación, diario, semanal, hora, programado, periódico, regular
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: f1344026878b7fbd6242d82b1afb0e6671c32073
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789273"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Configurar los análisis programados rápidos o completos del Antivirus de Windows Defender

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> De forma predeterminada, Antivirus de Microsoft Defender busca una actualización 15 minutos antes de la hora de los exámenes programados. Puede administrar [la programación de cuándo se](manage-protection-update-schedule-microsoft-defender-antivirus.md) deben descargar y aplicar las actualizaciones de protección para invalidar este valor predeterminado. 

Además de la protección siempre activa [](run-scan-microsoft-defender-antivirus.md) en tiempo real y los exámenes a petición, puede configurar exámenes regulares programados. 

Puede configurar el tipo de examen, cuándo debe producirse el [](manage-protection-updates-microsoft-defender-antivirus.md) examen y si el examen debe producirse después de una actualización de protección o si se está utilizando el extremo. También puede especificar cuándo deben producirse exámenes especiales para completar la corrección.

En este artículo se describe cómo configurar exámenes programados con directiva de grupo, cmdlets de PowerShell y WMI. También puede configurar exámenes de programación [con Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) o [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>Para configurar las opciones de directiva de grupo descritas en este artículo

1. En el equipo de administración de directivas de grupo, en el Editor de directivas de grupo, vaya a Configuración del equipo Plantillas administrativas  >    >  **Windows componentes**  >  **Antivirus de Microsoft Defender**  >  **Examinar**.

2. Haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, **seleccione Editar**.

3. Especifique la configuración del objeto de directiva de grupo y, a continuación, seleccione **Aceptar**. 

4. Repita los pasos del 1 al 4 para cada configuración que desee configurar.

5. Implemente el objeto de directiva de grupo como lo hace normalmente. Si necesita ayuda con objetos de directiva de grupo, vea [Crear un objeto de directiva de grupo](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).

Vea también administrar cuándo [se deben](manage-protection-update-schedule-microsoft-defender-antivirus.md) descargar y aplicar las actualizaciones de protección y Evitar o permitir que los usuarios [modifiquen localmente los](configure-local-policy-overrides-microsoft-defender-antivirus.md) temas de configuración de directivas.

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>Examen rápido frente a examen completo y examen personalizado

Al configurar exámenes programados, puede configurar si el examen debe ser un examen completo o rápido.


|Examen rápido  |Examen completo  | Examen personalizado |
|---------|---------|---------|
|Un examen rápido examina todas las ubicaciones donde podría haber malware registrado para empezar con el sistema, como las claves del Registro y las carpetas de inicio Windows de inicio. <p>En la mayoría de los casos, un examen rápido es suficiente y se recomienda para exámenes programados. |Un examen completo comienza ejecutando un examen rápido y, a continuación, continúa con un examen secuencial de archivos de todos los discos fijos montados y unidades extraíbles/de red (si el examen completo está configurado para hacerlo). <p>Un examen completo puede tardar unas horas o días en completarse, según la cantidad y el tipo de datos que se deben examinar.<p>Cuando se completa el examen completo, hay nueva inteligencia de seguridad disponible y se requiere un nuevo examen para asegurarse de que no se detecten otras amenazas con la nueva inteligencia de seguridad.   | Un examen personalizado es un examen rápido que se ejecuta en los archivos y carpetas que especifique. Por ejemplo, puedes optar por examinar una unidad USB o una carpeta específica en la unidad local del dispositivo. <p> | 

>[!NOTE]
>De forma predeterminada, los exámenes rápidos se ejecutan en dispositivos extraíbles montados, como unidades USB.

### <a name="how-do-i-know-which-scan-type-to-choose"></a>¿Cómo sé qué tipo de examen elegir?

Use la tabla siguiente para elegir un tipo de examen.


|Escenario  |Tipo de examen recomendado  |
|---------|---------|
|Desea configurar exámenes regulares y programados     | Examen rápido <p>Un examen rápido comprueba los procesos, la memoria, los perfiles y determinadas ubicaciones del dispositivo. Combinado con la protección siempre activa en tiempo [real,](configure-real-time-protection-microsoft-defender-antivirus.md)un examen rápido ayuda a proporcionar una cobertura sólida tanto para malware que comienza con el malware del sistema como del nivel de kernel. La protección en tiempo real revisa los archivos cuando se abren y cierran, y siempre que un usuario navega a una carpeta.         |
|Las amenazas, como el malware, se detectan en un dispositivo individual     | Examen rápido <p>En la mayoría de los casos, un examen rápido detectará y limpiará el malware detectado.   |
|Desea ejecutar un examen a [petición](run-scan-microsoft-defender-antivirus.md)     | Examen rápido       |
| Quieres asegurarte de que un dispositivo portátil, como una unidad USB, no contiene malware | Examen personalizado <p>Un examen personalizado permite seleccionar ubicaciones, carpetas o archivos específicos y ejecuta un examen rápido. |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>¿Qué más necesito saber sobre los exámenes rápidos y completos?

- Los archivos malintencionados se pueden almacenar en ubicaciones que no se incluyen en un examen rápido. Sin embargo, la protección siempre activa en tiempo real revisa todos los archivos que se abren y cierran y los archivos que se encuentran en carpetas a las que un usuario tiene acceso. La combinación de protección en tiempo real y un examen rápido ayuda a proporcionar una protección segura contra malware.

- La protección en tiempo de acceso [con](cloud-protection-microsoft-defender-antivirus.md) protección entregada en la nube ayuda a garantizar que todos los archivos a los que se accede en el sistema se examinan con los modelos de inteligencia de seguridad y aprendizaje automático en la nube más recientes.

- Cuando la protección en tiempo real detecta malware y el alcance de los archivos afectados no se determina inicialmente, Antivirus de Microsoft Defender inicia un examen completo como parte del proceso de corrección.

- Un examen completo puede detectar archivos malintencionados que no fueron detectados por otros exámenes, como un examen rápido. Sin embargo, un examen completo puede tardar un tiempo y usar valiosos recursos del sistema para completarse.

- Si un dispositivo está sin conexión durante un período prolongado de tiempo, un examen completo puede tardar más tiempo en completarse. 

## <a name="set-up-scheduled-scans"></a>Configurar exámenes programados

Los exámenes programados se ejecutan en el día y la hora que especifique. Puede usar la directiva de grupo, PowerShell y WMI para configurar exámenes programados.

> [!NOTE]
> Si un dispositivo se desconecta y se ejecuta en la batería durante un examen completo programado, el examen programado se detendrá con el evento 1002, que indica que el examen se detuvo antes de finalizar. Antivirus de Microsoft Defender se ejecutará un examen completo en la próxima hora programada.

### <a name="use-group-policy-to-schedule-scans"></a>Usar directiva de grupo para programar exámenes

|Ubicación | Configuración | Descripción | Configuración predeterminada (si no está configurada) |
|:---|:---|:---|:---|
|Examinar | Especificar el tipo de examen que se usará para un examen programado | Examen rápido |
|Examinar | Especificar el día de la semana para ejecutar un examen programado | Especifique el día (o nunca) para ejecutar un examen. | Nunca |
|Examinar | Especificar la hora del día para ejecutar un examen programado | Especifique el número de minutos después de medianoche (por ejemplo, escriba **60** para la 1 a.m.). | 2 a. m. |
|Raíz | Randomize scheduled task times |En Antivirus de Microsoft Defender, aleatorice la hora de inicio del examen a cualquier intervalo de 0 a 4 horas. <p>En [SCEP,](/mem/intune/protect/certificates-scep-configure)aleatorice los exámenes a cualquier intervalo más o menos 30 minutos. Esto puede ser útil en máquinas virtuales o implementaciones de VDI. | Habilitado |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>Usar cmdlets de PowerShell para programar exámenes

Use los cmdlets siguientes:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Para obtener más información, vea [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Usar Windows de administración de documentos (WMI) para programar exámenes

Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Para obtener más información y parámetros permitidos, [vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


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

Para más información, consulte [Usar cmdlets de PowerShell para configurar y ejecutar Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [cmdlets de Defender](/powershell/module/defender/).

### <a name="use-windows-management-instruction-wmi"></a>Use Windows Management Instruction (WMI)

Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
ScanOnlyIfIdleEnabled
```

Para obtener más información acerca de las API y los [parámetros permitidos, vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>Configurar cuándo deben ejecutarse exámenes completos para completar la corrección

Algunas amenazas pueden requerir un examen completo para completar su eliminación y corrección. Puede especificar cuándo deben producirse estos exámenes con la directiva de grupo, PowerShell o WMI.

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

Consulte [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.

### <a name="use-windows-management-instruction-wmi"></a>Use Windows Management Instruction (WMI)

Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Para obtener más información y parámetros [permitidos, vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).


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

Para obtener más información acerca de cómo usar PowerShell con Antivirus de Microsoft Defender, vea [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/).

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>Usar Windows de administración de documentos (WMI) para programar exámenes diarios

Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
ScanScheduleQuickScanTime
```

Para obtener más información y parámetros [permitidos, vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).


## <a name="enable-scans-after-protection-updates"></a>Habilitar exámenes después de actualizaciones de protección

Puede forzar que se produzca un examen después de cada actualización [de protección con](manage-protection-updates-microsoft-defender-antivirus.md) la directiva de grupo.

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a>Usar la directiva de grupo para programar exámenes después de las actualizaciones de protección

|Ubicación | Configuración | Descripción | Configuración predeterminada (si no está configurada)|
|:---|:---|:---|:---|
|Actualizaciones de firmas | Activar el examen después de la actualización de inteligencia de seguridad | Un examen se realizará inmediatamente después de descargar una nueva actualización de protección | Habilitado |

## <a name="see-also"></a>Consulte también

- [Impedir o permitir que los usuarios modifiquen localmente la configuración de directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [Configurar y ejecutar análisis bajo petición en el Antivirus de Microsoft Defender](run-scan-microsoft-defender-antivirus.md)
- [Configurar opciones de análisis del Antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Administrar cuándo se deben descargar y aplicar las actualizaciones de protección](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)