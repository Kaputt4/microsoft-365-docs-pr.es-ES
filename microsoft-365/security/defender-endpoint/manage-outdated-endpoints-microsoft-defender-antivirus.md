---
title: Aplicación de actualizaciones de protección antivirus de Microsoft Defender a puntos de conexión obsoletos
description: Defina cuándo y cómo se deben aplicar las actualizaciones para los puntos de conexión que no se han actualizado en un tiempo.
keywords: actualizaciones, protección, desactualizado, obsoleto, antiguo, al día
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: f5acf05a95e8c3034bf963f8413693ec1aad057d
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67520739"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a>Administrar las actualizaciones y análisis del Antivirus de Windows Defender para puntos de conexión que están obsoletos

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**

- Windows

Con el Antivirus de Microsoft Defender, el equipo de seguridad puede definir cuánto tiempo puede evitar una actualización un punto de conexión o cuántos exámenes puede perder antes de que sea necesario para recibir la actualización y ejecutar un examen. Esta funcionalidad es especialmente útil en entornos en los que los dispositivos no suelen estar conectados a una red corporativa o externa, o para dispositivos que no se usan diariamente.

Por ejemplo, un empleado que usa un equipo determinado tarda tres días fuera del trabajo y no inicia sesión en su equipo durante ese tiempo. Cuando el empleado vuelve al trabajo e inicia sesión en su equipo, Antivirus de Microsoft Defender comprobará y descargará inmediatamente las actualizaciones de protección más recientes y, a continuación, ejecutará un examen.

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a>Configuración de actualizaciones de protección de puesta al día para los puntos de conexión que no se han actualizado durante un tiempo

Si Antivirus de Microsoft Defender no descargó las actualizaciones de protección durante un período especificado, puede configurarlo para comprobar y descargar automáticamente la actualización más reciente la próxima vez que alguien inicie sesión en un punto de conexión. Esta configuración es útil si ha [deshabilitado globalmente las descargas de actualizaciones automáticas durante el inicio](manage-event-based-updates-microsoft-defender-antivirus.md).

Puede usar uno de varios métodos para configurar las actualizaciones de protección de puesta al día:

- [Configuration Manager](#use-configuration-manager-to-configure-catch-up-protection-updates)
- [Directiva de grupo](#use-group-policy-to-enable-and-configure-the-catch-up-update-feature)
- [Cmdlets de PowerShell](#use-powershell-cmdlets-to-configure-catch-up-protection-updates)
- [Instrucciones de administración de Windows (WMI)](#use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates)

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a>Uso de Configuration Manager para configurar actualizaciones de protección de puesta al día

1. En la consola de Microsoft Endpoint Manager, abra la directiva antimalware que desea cambiar (seleccione **Activos y cumplimiento** en el panel de navegación de la izquierda y, a continuación, expanda el árbol a Directivas **antimalware** de **Endpoint Protection** \> **de información general**\>).

2. Vaya a la sección **Actualizaciones de inteligencia de seguridad** y configure los siguientes valores:

    - Establezca **Forzar una actualización de inteligencia de seguridad si el equipo cliente está sin conexión durante más de dos actualizaciones programadas consecutivas** en **Sí**.
    - En **If Configuration Manager is used as a source for security intelligence updates...**, especifique las horas antes de las cuales las actualizaciones de protección entregadas por Configuration Manager deben considerarse obsoletas. Esta configuración hace que se use la siguiente ubicación de actualización, en función del [orden de origen de reserva](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order) definido.

3. Seleccione **Aceptar**.

4. [Implemente la directiva actualizada como de costumbre](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a>Uso de directiva de grupo para habilitar y configurar la característica de actualización de puesta al día

1. En el equipo de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón derecho en el objeto de directiva de grupo que desea configurar y, a continuación, seleccione **Editar**.

2. En el **Editor de administración de directiva de grupo** vaya a **Configuración del equipo**.

3. Seleccione **Directivas** y plantillas **administrativas**.

4. Expanda el árbol a **componentes de Windows > antivirus de Microsoft Defender > Signature Novedades**.

5. Haga doble clic en **la opción Definir el número de días después de los cuales se requiere una actualización de inteligencia de seguridad** actualizada y establezca la opción **en Habilitado**. Escriba el número de días después de los cuales desea que Antivirus de Microsoft Defender compruebe y descargue la actualización de protección más reciente.

6. Seleccione **Aceptar**.

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a>Uso de cmdlets de PowerShell para configurar actualizaciones de protección de puesta al día

Use el siguiente cmdlet:

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

Para obtener más información sobre el uso de PowerShell con el Antivirus de Microsoft Defender, consulte los artículos siguientes:

- [Uso de cmdlets de PowerShell para configurar y ejecutar el Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Cmdlets de Antivirus de Defender](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a>Uso de Instrucciones de administración de Windows (WMI) para configurar actualizaciones de protección de puesta al día

Use el [método **Set** de la clase **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
SignatureUpdateCatchupInterval
```

Consulte el artículo siguiente para obtener más información y parámetros permitidos:

- [API Windows Defender WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a>Establecer el número de días antes de que la protección se notifique como obsoleta

También puede especificar el número de días después de los cuales la protección antivirus de Microsoft Defender se considera antigua o obsoleta. Después del número de días especificado, el cliente se notificará a sí mismo como "obsoleto" y mostrará un error al usuario del punto de conexión. Cuando un punto de conexión se considera obsoleto, antivirus de Microsoft Defender podría intentar descargar una actualización de otros orígenes (en función del [orden de origen de reserva](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order) definido).

Puede usar directiva de grupo para especificar el número de días después de los cuales endpoint protection se considera obsoleto.

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a>Use directiva de grupo para especificar el número de días antes de que la protección se considere obsoleta.

1. En la máquina de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón derecho en el objeto de directiva de grupo que desea configurar y, a continuación, seleccione **Editar**.

2. En el **Editor de administración de directiva de grupo** vaya a **Configuración del equipo**.

3. Seleccione **Directivas** y plantillas **administrativas**.

4. Expanda el árbol a **componentes de Windows > antivirus de Microsoft Defender > Signature Novedades** y configure los siguientes valores:

    1. Haga doble clic en **Definir el número de días antes de que las definiciones de spyware se consideren obsoletas** y establezca la opción **en Habilitado**. Escriba el número de días después de los cuales desea que Antivirus de Microsoft Defender considere que la inteligencia de seguridad de spyware está obsoleta.

    2. Seleccione **Aceptar**.

    3. Haga doble clic en **Definir el número de días antes de que las definiciones de virus se consideren obsoletas** y establezca la opción **en Habilitado**. Escriba el número de días después de los cuales desea que Antivirus de Microsoft Defender considere que la inteligencia de seguridad de virus está obsoleta.

    4. Seleccione **Aceptar**.

## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a>Configuración de exámenes de puesta al día para los puntos de conexión que no se han examinado durante un tiempo

Puede establecer el número de exámenes programados consecutivos que se pueden perder antes de que antivirus de Microsoft Defender forzúe un examen.

El proceso para habilitar esta característica es:

1. Configure al menos un examen programado (consulte el artículo [Exámenes programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md) ).

2. Habilite la característica de examen de puesta al día.

3. Defina el número de exámenes que se pueden omitir antes de que se produzca un examen de puesta al día.

Esta característica se puede habilitar para exámenes completos y rápidos. 

> [!TIP]
> Se recomienda usar exámenes rápidos para la mayoría de las situaciones. Para obtener más información, consulte [Examen rápido, examen completo y examen personalizado](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan). 

Puede usar uno de varios métodos para configurar exámenes de puesta al día:

- [Directiva de grupo](#use-group-policy-to-enable-and-configure-the-catch-up-scan-feature)
- [Uso de cmdlets de PowerShell para configurar exámenes de puesta al día](#use-powershell-cmdlets-to-configure-catch-up-scans)
- [Instrucciones de administración de Windows (WMI)](#use-windows-management-instruction-wmi-to-configure-catch-up-scans)
- [Configuration Manager](#use-configuration-manager-to-configure-catch-up-scans)

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a>Uso de directiva de grupo para habilitar y configurar la característica de examen de puesta al día

1. Asegúrese de que ha configurado al menos un examen programado.

2. En la máquina de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón derecho en el objeto de directiva de grupo que desea configurar y seleccione **Editar**.

3. En el **Editor de administración de directiva de grupo** vaya a **Configuración del equipo**.

4. Seleccione **Directivas** y plantillas **administrativas**.

5. Expanda el árbol a **componentes de Windows > Antivirus de Microsoft Defender > Scan** y configure los siguientes valores:

    - Si ha configurado exámenes rápidos programados, haga doble clic en la opción **Activar examen rápido de puesta al día** y establezca la opción **en Habilitado**.
    - Si ha configurado exámenes completos programados, haga doble clic en la opción **Activar el examen completo de puesta al día** y establezca la opción **en Habilitado**. Seleccione **Aceptar**.
    - Haga doble clic en **la opción Definir el número de días después de los cuales se fuerza un examen de puesta al día** y establezca la opción **en Habilitado**.
    - Escriba el número de exámenes que se pueden perder antes de que se ejecute automáticamente un examen cuando el usuario inicie sesión en el punto de conexión. El tipo de examen que se ejecuta viene determinado por especificar **el tipo de examen que se va a usar para un examen programado** (consulte el artículo [Programación de exámenes](scheduled-catch-up-scans-microsoft-defender-antivirus.md) ). Seleccione **Aceptar**.

> [!NOTE]
> El título de la configuración de directiva de grupo hace referencia al número de días. Sin embargo, la configuración se aplica al número de exámenes (no a los días) antes de que se ejecute el examen de puesta al día.

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a>Uso de cmdlets de PowerShell para configurar exámenes de puesta al día

Use los siguientes cmdlets:

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

Para obtener más información sobre el uso de PowerShell con el Antivirus de Microsoft Defender, consulte los artículos siguientes:

- [Usar cmdlets PowerShell para administrar el Antivirus de Windows Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) 
- [Cmdlets de Antivirus de Defender](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a>Uso de Instrucciones de administración de Windows (WMI) para configurar exámenes de puesta al día

Use el [método **Set** de la clase **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

Consulte el artículo siguiente para obtener más información y parámetros permitidos:

- [API Windows Defender WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

### <a name="use-configuration-manager-to-configure-catch-up-scans"></a>Uso de Configuration Manager para configurar exámenes de puesta al día

1. En la consola de Microsoft Endpoint Manager, abra la directiva antimalware que desea cambiar (seleccione **Activos y cumplimiento** en el panel de navegación de la izquierda y, a continuación, expanda el árbol a Directivas **antimalware** de **Endpoint Protection** \> **de información general**\>).

2. Vaya a la sección **Exámenes programados** y **Force a scan of the selected scan type if client computer is offline... to Yes (Forzar un examen del tipo de examen seleccionado si el equipo cliente está sin conexión...** ) a **Sí**.

3. Seleccione **Aceptar**.

4. [Implemente la directiva actualizada como de costumbre](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).

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

- [Implementación del Antivirus de Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)
- [Para obtener más información, consulte Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar bases de referencia.](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Administre cuándo deben descargarse y aplicarse las actualizaciones de protección](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [Administrar las actualizaciones forzadas basadas en eventos](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Administrar las actualizaciones de dispositivos móviles y máquinas virtuales](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
