---
title: Aplicar actualizaciones de protección antivirus de Microsoft Defender a puntos de conexión no actualizados
description: Defina cuándo y cómo deben aplicarse las actualizaciones para los puntos de conexión que no se han actualizado en un tiempo.
keywords: actualizaciones, protección, desactualizado, obsoleto, antiguo, de ponerse al día
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4199f55488ef0dc5989af88e8be83a3d51190d1f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275065"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a>Administrar las actualizaciones y análisis del Antivirus de Windows Defender para puntos de conexión que están obsoletos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Antivirus de Microsoft Defender permite definir cuánto tiempo puede evitar una actualización un extremo o cuántos exámenes puede perder antes de que sea necesario actualizarse y examinarse por sí mismo. Esto es especialmente útil en entornos donde los dispositivos no suelen estar conectados a una red corporativa o externa, o dispositivos que no se usan a diario.

Por ejemplo, un empleado que usa un equipo determinado está en pausa durante tres días y no inicia sesión en su equipo durante ese tiempo.

Cuando el usuario vuelva al trabajo e inicie sesión en su equipo, Antivirus de Microsoft Defender comprobará y descargará inmediatamente las actualizaciones de protección más recientes y ejecutará un examen.

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a>Configurar actualizaciones de protección de ponerse al día para puntos de conexión que no se han actualizado durante un tiempo

Si Antivirus de Microsoft Defender las actualizaciones de protección durante un período especificado, puede configurarlo para comprobar y descargar automáticamente la actualización más reciente en el siguiente inicio de sesión. Esto resulta útil si ha deshabilitado [globalmente las descargas](manage-event-based-updates-microsoft-defender-antivirus.md)automáticas de actualizaciones al iniciar .

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a>Usar Configuration Manager para configurar actualizaciones de protección de ponerse al día

1.  En la consola Microsoft Endpoint Manager, abra la directiva de antimalware  que desea cambiar (haga clic en Activos y cumplimiento en el panel de navegación de la izquierda y, a continuación, expanda el árbol a Información general Endpoint Protection Directivas  >    >  **antimalware**)

2.  Vaya a la **sección Actualizaciones de inteligencia de** seguridad y configure las siguientes opciones:

    1. Establece Forzar una actualización de inteligencia de seguridad si el equipo cliente está sin conexión durante más de dos actualizaciones **programadas consecutivas** en **Sí**.
    2. For the  **If Configuration Manager is used as a source for security intelligence updates...**, specify the hours before which the protection updates delivered by Configuration Manager should be considered out-of-date. Esto hará que se utilice la siguiente ubicación de actualización, en función del orden de origen [de reserva definido.](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)

3. Haga clic en **Aceptar**.

4.  [Implemente la directiva actualizada como de costumbre.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a>Usar la directiva de grupo para habilitar y configurar la característica de actualización de ponerse al día

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**

3. Haga clic **en Directivas** **y, a continuación, en Plantillas administrativas.**

4. Expanda el árbol para Windows **componentes > Antivirus de Microsoft Defender > actualizaciones de firma**.

5. Haga doble clic en **la opción Definir el número** de días después de los cuales es necesaria una actualización de inteligencia de seguridad de ponerse al día y establezca la opción en **Habilitado**. Escribe el número de días después de los cuales quieres que Microsoft Defender AV compruebe y descargue la actualización de protección más reciente.

6. Haga clic en **Aceptar**.

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a>Usar cmdlets de PowerShell para configurar actualizaciones de protección de ponerse al día

Use los cmdlets siguientes:

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

Consulte [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a>Usar Windows de administración de datos (WMI) para configurar actualizaciones de protección de ponerse al día

Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
SignatureUpdateCatchupInterval
```

Vea lo siguiente para obtener más información y parámetros permitidos:
- [Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a>Establecer el número de días antes de que se notifica la protección como desaprotección

También puede especificar el número de días después de los cuales Antivirus de Microsoft Defender protección se considera antigua o desaprotebada. Después del número de días especificado, el cliente se presentará como desa fecha y mostrará un error al usuario del equipo. También puede hacer que Antivirus de Microsoft Defender intente descargar una actualización de otros orígenes (en función del orden de origen de reserva [definido),](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)como cuando se usa MMPC como origen secundario después de establecer WSUS o Microsoft Update como el primer origen.

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a>Usar la directiva de grupo para especificar el número de días antes de que la protección se considere des actualizada

1.  En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

3.  En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**

4.  Haga clic **en Directivas** **y, a continuación, en Plantillas administrativas.**

5.  Expanda el árbol para Windows **componentes > Antivirus de Microsoft Defender > de firma y** configure las siguientes opciones:

    1.  Haga doble clic en Definir el número de días antes de que las definiciones de spyware se consideren **des actualizadas** y establezca la opción en **Habilitado**. Escriba el número de días después de los cuales desea que Microsoft Defender AV considere que la inteligencia de seguridad de spyware está des actualizada.

    2. Haga clic en **Aceptar**.

    3.  Haga doble clic en Definir el número de días antes de que las definiciones de virus se consideren **des actualizadas** y establezca la opción en **Habilitado**. Escriba el número de días después de los cuales desea que Microsoft Defender AV considere que la inteligencia de seguridad de virus está des actualizada.

    4. Haga clic en **Aceptar**.


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a>Configurar exámenes de ponerse al día para los puntos de conexión que no se han analizado durante un tiempo

Puede establecer el número de exámenes programados consecutivos que se pueden perder antes Antivirus de Microsoft Defender forzar un examen.

El proceso para habilitar esta característica es:

1. Configure al menos un examen programado (consulte el [tema Programar exámenes).](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
2. Habilite la característica de examen de ponerse al día.
3. Defina el número de exámenes que se pueden omitir antes de que se produzca un examen de ponerse al día.

Esta característica se puede habilitar para exámenes completos y rápidos.

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a>Usar la directiva de grupo para habilitar y configurar la característica de examen de ponerse al día

1.  Asegúrese de haber configurado al menos un examen programado.

2.  En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

3.  En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**

4.  Haga clic **en Directivas** **y, a continuación, en Plantillas administrativas.**

5.  Expanda el árbol para **Windows componentes > Antivirus de Microsoft Defender > Scan** y configure las siguientes opciones:

    1.  Si ha configurado los exámenes rápidos programados, haga doble clic en la configuración Activar detección rápida y establezca la opción en **Habilitado**.  
    2. Si ha configurado exámenes completos programados,  haga doble clic en la configuración Activar examen completo de puesta al día y establezca la opción en **Habilitado**. Haga clic en **Aceptar**.
    3. Haga doble clic en **la opción Definir el** número de días después de los cuales se forzará la configuración de un examen de puesta al día y establezca la opción en **Habilitado**. 
    4. Escriba el número de exámenes que se pueden perder antes de que se ejecute automáticamente un examen cuando el siguiente usuario inicie sesión en el equipo. El tipo de examen que se ejecuta viene determinado por el parámetro **Specify the scan type to use for a scheduled scan** (vea el tema Schedule [scans).](scheduled-catch-up-scans-microsoft-defender-antivirus.md) Haga clic en **Aceptar**.

> [!NOTE]
> El título de configuración de directiva de grupo hace referencia al número de días. Sin embargo, la configuración se aplica al número de exámenes (no días) antes de que se ejecute el examen de puesta al día.

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a>Usar cmdlets de PowerShell para configurar exámenes de ponerse al día

Use los cmdlets siguientes:

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

Consulte [Use PowerShell cmdlets to manage Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a>Usar Windows de administración de datos (WMI) para configurar exámenes de ponerse al día

Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

Vea lo siguiente para obtener más información y parámetros permitidos:
- [Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a>Usar Configuration Manager para configurar exámenes de ponerse al día

1.  En la consola Microsoft Endpoint Manager, abra la directiva de antimalware  que desea cambiar (haga clic en Activos y cumplimiento en el panel de navegación de la izquierda y, a continuación, expanda el árbol a Información general Endpoint Protection Directivas  >    >  **antimalware**)

2.  Vaya a la **sección Exámenes programados** y Forzar un examen del tipo de examen seleccionado si el equipo cliente **está sin conexión...** a **Sí**. 

3. Haga clic en **Aceptar**.

4.  [Implemente la directiva actualizada como de costumbre.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

## <a name="related-articles"></a>Artículos relacionados

- [Implementar Antivirus de Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)
- [Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Administrar cuándo se deben descargar y aplicar las actualizaciones de protección](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [Administrar las actualizaciones forzadas basadas en eventos](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Administrar las actualizaciones de dispositivos móviles y máquinas virtuales](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)