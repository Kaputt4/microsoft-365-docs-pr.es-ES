---
title: Aplicar actualizaciones Microsoft Defender Antivirus después de ciertos eventos
description: Administre cómo Microsoft Defender Antivirus aplica las actualizaciones de inteligencia de seguridad después del inicio o la recepción de informes de detección entregados en la nube.
keywords: updates, protection, force updates, events, startup, check for latest, notifications
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.subservice: mde
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 0311f509f5c912cdfc72798f582e3f7b9c6a243d
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68233098"
---
# <a name="manage-event-based-forced-updates"></a>Administrar las actualizaciones forzadas basadas en eventos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Microsoft Defender Antivirus permite determinar si las actualizaciones deben producirse (o no) después de ciertos eventos, como al iniciarse o después de recibir informes específicos del servicio de protección entregado en la nube.

## <a name="check-for-protection-updates-before-running-a-scan"></a>Comprobación de actualizaciones de protección antes de ejecutar un examen

Puede usar microsoft endpoint Configuration Manager, directiva de grupo, cmdlets de PowerShell y WMI para forzar a Microsoft Defender Antivirus a comprobar y descargar las actualizaciones de protección antes de ejecutar un examen programado.

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a>Usar Configuration Manager para comprobar si hay actualizaciones de protección antes de ejecutar un examen

1. En la consola de Microsoft Endpoint Manager, abra la directiva antimalware que desea cambiar (haga clic en **Activos y compatibilidad** en el panel de navegación de la izquierda y, a continuación, expanda el árbol a Directivas **de antimalware** de **Endpoint Protection** \> **de información general**\>).

2. Vaya a la sección **Exámenes programados** y establezca **Buscar las últimas actualizaciones de inteligencia de seguridad antes de ejecutar un examen** en **Sí**.

3. Haga clic en **Aceptar**.

4. [Implemente la directiva actualizada como de costumbre](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a>Usar directiva de grupo para comprobar si hay actualizaciones de protección antes de ejecutar un examen

1. En la máquina de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y haga clic en **Editar**.

2. Con el **Editor de administración de directiva de grupo** vaya a **Configuración del equipo**.

3. Haga clic en **Directivas** y, a continuación, **en Plantillas administrativas**.

4. Expanda el árbol a **componentes** \> **de Windows Microsoft Defender Antivirus** \> **Scan**.

5. Haga doble clic en **Comprobar las definiciones de virus y spyware más recientes antes de ejecutar un examen programado** y establezca la opción **en Habilitado**.

6. Haga clic en **Aceptar**.

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a>Uso de cmdlets de PowerShell para comprobar si hay actualizaciones de protección antes de ejecutar un examen

Use los siguientes cmdlets:

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

Para obtener más información, vea [Usar cmdlets de PowerShell para configurar y ejecutar el Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [Cmdlets de Antivirus de Microsoft Defender](/powershell/module/defender/index).

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a>Uso de Instrucciones de administración de Windows (WMI) para comprobar si hay actualizaciones de protección antes de ejecutar un examen

Use el [método **Set** de la clase **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
CheckForSignaturesBeforeRunningScan
```

Para obtener más información, consulte [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

## <a name="check-for-protection-updates-on-startup"></a>Comprobación de actualizaciones de protección al iniciar

Puede usar directiva de grupo para forzar a Microsoft Defender Antivirus a comprobar y descargar las actualizaciones de protección cuando se inicie la máquina.

1. En el equipo de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y haga clic en **Editar**.

2. Con el **Editor de administración de directiva de grupo** vaya a **Configuración del equipo**.

3. Haga clic en **Directivas** y, a continuación, **en Plantillas administrativas**.

4. Expanda el árbol a **componentes** \> de Windows **Microsoft Defender Antivirus** \> **Security Intelligence Novedades**.

5. Haga doble clic en **Comprobar si hay las definiciones de virus y spyware más recientes en el inicio** y establezca la opción **en Habilitado**.

6. Haga clic en **Aceptar**.

También puede usar directiva de grupo, PowerShell o WMI para configurar Microsoft Defender Antivirus para comprobar si hay actualizaciones en el inicio, incluso cuando no se está ejecutando.

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Uso de directiva de grupo para descargar actualizaciones cuando Microsoft Defender Antivirus no está presente

1. En la máquina de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y haga clic en **Editar**.

2. Con el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo**.

3. Haga clic en **Directivas** y, a continuación, **en Plantillas administrativas**.

4. Expanda el árbol a **componentes** \> de Windows **Microsoft Defender Antivirus** \> **Security Intelligence Novedades**.

5. Haga doble clic en **Iniciar actualización de inteligencia de seguridad al iniciar** y establezca la opción **en Habilitado**.

6. Haga clic en **Aceptar**.

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Uso de cmdlets de PowerShell para descargar actualizaciones cuando Microsoft Defender Antivirus no está presente

Use los siguientes cmdlets:

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

Para obtener más información, consulte [Uso de cmdlets de PowerShell para administrar cmdlets Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [Antivirus de Defender](/powershell/module/defender/index) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Usar instrucciones de administración de Windows (WMI) para descargar actualizaciones cuando Microsoft Defender Antivirus no está presente

Use el [método **Set** de la clase **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

Para obtener más información, consulte [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a>Permitir cambios ad hoc en la protección basada en la protección entregada en la nube

Microsoft Defender Antivirus puede realizar cambios en su protección en función de la protección proporcionada en la nube. Estos cambios pueden producirse fuera de las actualizaciones de protección normales o programadas.

Si ha habilitado la protección proporcionada en la nube, Microsoft Defender Antivirus enviará archivos sospechosos a la nube de Windows Defender. Si el servicio en la nube informa de que el archivo es malintencionado y el archivo se detecta en una actualización de protección reciente, puede usar directiva de grupo para configurar Microsoft Defender Antivirus para recibir automáticamente esa actualización de protección. También se pueden aplicar otras actualizaciones de protección importantes.

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a>Uso de directiva de grupo para descargar automáticamente actualizaciones recientes basadas en la protección proporcionada en la nube

1. En la máquina de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y haga clic en **Editar**.

2. Con el **Editor de administración de directiva de grupo** vaya a **Configuración del equipo**.

3. Haga clic en **Directivas** y, a continuación, **en Plantillas administrativas**.

4. Expanda el árbol a **componentes** \> de Windows **Microsoft Defender Antivirus** \> **Security Intelligence Novedades**.

5. Haga doble clic en **Permitir actualizaciones de inteligencia de seguridad en tiempo real basadas en informes de Microsoft MAPS** y establezca la opción **en Habilitado**. Después, haga clic en **Aceptar**.

6. **Permitir que las notificaciones deshabiliten los informes basados en definiciones en Microsoft MAPS** y establezca la opción **en Habilitado**. Después, haga clic en **Aceptar**.

> [!NOTE]
> **Permitir que las notificaciones deshabiliten informes basados en definiciones** permite que Microsoft MAPS deshabilite esas definiciones conocidas por provocar informes falsos positivos. Debe configurar el equipo para que se una a Microsoft MAPS para que esta función funcione.

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características iOS](ios-configure-features.md)

## <a name="see-also"></a>Vea también

- [Implementación de Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Para obtener más información, consulte Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar bases de referencia.](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Administre cuándo deben descargarse y aplicarse las actualizaciones de protección](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [Administrar actualizaciones para puntos finales que están desactualizados](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Administrar las actualizaciones de dispositivos móviles y máquinas virtuales](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
