---
title: Aplicar actualizaciones de Antivirus de Microsoft Defender después de determinados eventos
description: Administrar cómo Antivirus de Microsoft Defender aplica actualizaciones de inteligencia de seguridad después del inicio o de recibir informes de detección entregados en la nube.
keywords: actualizaciones, protección, forzar actualizaciones, eventos, inicio, buscar más recientes, notificaciones
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b9f09878c645d54aadca21fe01749a0e73939c5f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691045"
---
# <a name="manage-event-based-forced-updates"></a>Administrar actualizaciones forzadas basadas en eventos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Antivirus de Microsoft Defender le permite determinar si las actualizaciones deben producirse (o no) después de determinados eventos, como al iniciarse o después de recibir informes específicos del servicio de protección entregado en la nube.

## <a name="check-for-protection-updates-before-running-a-scan"></a>Buscar actualizaciones de protección antes de ejecutar un examen

Puede usar Microsoft Endpoint Configuration Manager, la directiva de grupo, los cmdlets de PowerShell y WMI para forzar a Antivirus de Microsoft Defender a comprobar y descargar actualizaciones de protección antes de ejecutar un examen programado.

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a>Usar Configuration Manager para buscar actualizaciones de protección antes de ejecutar un examen

1. En la consola de Microsoft Endpoint Manager, abra la  directiva de antimalware que desea cambiar (haga clic en Activos y cumplimiento en el panel de navegación de la izquierda y, a continuación, expanda el árbol a **Overview**  >  **Endpoint Protection**  >  **Antimalware Policies**)

2. Vaya a la **sección Exámenes programados** y establezca **Comprobar las últimas** actualizaciones de inteligencia de seguridad antes de ejecutar un examen en **Sí**.

3. Haga clic en **Aceptar**.

4. [Implemente la directiva actualizada como de costumbre.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a>Usar la directiva de grupo para buscar actualizaciones de protección antes de ejecutar un examen

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

2. Con el **Editor de administración de directivas de grupo,** vaya a Configuración del **equipo**.

3. Haga clic **en Directivas** **y, a continuación, en Plantillas administrativas.**

4. Expande el árbol a **Componentes de Windows** Antivirus  >  Scan de Microsoft **Defender**  >  .

5. Haga doble clic **en Comprobar las definiciones de virus** y spyware más recientes antes de ejecutar un examen programado y establezca la opción en **Habilitado**.

6. Haga clic en **Aceptar**.

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a>Usar cmdlets de PowerShell para buscar actualizaciones de protección antes de ejecutar un examen

Use los cmdlets siguientes:

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

Para obtener más información, vea [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/index).

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a>Usar instrucciones de administración de Windows (WMI) para buscar actualizaciones de protección antes de ejecutar un examen

Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
CheckForSignaturesBeforeRunningScan
```

Para obtener más información, [vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

## <a name="check-for-protection-updates-on-startup"></a>Buscar actualizaciones de protección al inicio

Puedes usar la directiva de grupo para forzar a Antivirus de Microsoft Defender a comprobar y descargar actualizaciones de protección cuando se inicia la máquina.

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

2. Con el **Editor de administración de directivas de grupo,** vaya a Configuración del **equipo**.

3. Haga clic **en Directivas** **y, a continuación, en Plantillas administrativas.**

4. Expande el árbol a **Componentes de Windows** Actualizaciones de inteligencia de seguridad de Antivirus  >  de Microsoft **Defender.**  >  

5. Haz doble clic **en Comprobar las definiciones de virus y spyware** más recientes al iniciar y establece la opción en **Habilitado**. 

6. Haga clic en **Aceptar**.

También puede usar la directiva de grupo, PowerShell o WMI para configurar Antivirus de Microsoft Defender para buscar actualizaciones en el inicio incluso cuando no se esté ejecutando.

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Usar la directiva de grupo para descargar actualizaciones cuando antivirus de Microsoft Defender no está presente

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

2. Con el **Editor de administración de directivas de** grupo, vaya a Configuración del **equipo**.

3. Haga clic **en Directivas** **y, a continuación, en Plantillas administrativas.**

4. Expande el árbol a **Componentes de Windows** Actualizaciones de inteligencia de seguridad de Antivirus  >  de Microsoft **Defender.**  >  

5. Haz doble clic en **Iniciar actualización de inteligencia de seguridad al** inicio y establece la opción en **Habilitado**.

6. Haga clic en **Aceptar**.

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Usar cmdlets de PowerShell para descargar actualizaciones cuando antivirus de Microsoft Defender no está presente

Use los cmdlets siguientes:

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

Para obtener más información, vea [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Usar instrucciones de administración de Windows (WMI) para descargar actualizaciones cuando antivirus de Microsoft Defender no está presente

Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

Para obtener más información, [vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a>Permitir cambios ad hoc en la protección basada en la protección entregada en la nube

Microsoft Defender AV puede realizar cambios en su protección en función de la protección entregada en la nube. Estos cambios pueden producirse fuera de las actualizaciones de protección normales o programadas.

Si ha habilitado la protección de entrega en la nube, Microsoft Defender AV enviará archivos de los que es sospechoso a la Windows Defender nube. Si el servicio en la nube informa de que el archivo es malintencionado y el archivo se detecta en una actualización de protección reciente, puede usar la directiva de grupo para configurar Microsoft Defender AV para recibir automáticamente esa actualización de protección. También se pueden aplicar otras actualizaciones de protección importantes.

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a>Usar la directiva de grupo para descargar automáticamente las actualizaciones recientes basadas en la protección entregada en la nube

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

2. Con el **Editor de administración de directivas de grupo,** vaya a Configuración del **equipo**.

3. Haga clic **en Directivas** **y, a continuación, en Plantillas administrativas.**

4. Expande el árbol a **Componentes de Windows** Actualizaciones de inteligencia de seguridad de Antivirus  >  de Microsoft **Defender.**  >  

5. Haga doble clic en Permitir actualizaciones de inteligencia de seguridad en tiempo real basadas en informes **de Microsoft MAPS** y establezca la opción en **Habilitado**. Después, haga clic en **Aceptar**.

6. **Permitir que las notificaciones deshabilite informes basados en definiciones en Microsoft MAPS** y establezca la opción en **Habilitado**. Después, haga clic en **Aceptar**.
    
> [!NOTE]
> **Permitir que las notificaciones deshabilite los informes basados** en definiciones permite a Microsoft MAPS deshabilitar esas definiciones conocidas por causar informes falsos positivos. Debe configurar el equipo para que se una a Microsoft MAPS para que esta función funcione.

## <a name="see-also"></a>Vea también

- [Implementar antivirus de Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)
- [Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar líneas base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Administrar cuándo se deben descargar y aplicar las actualizaciones de protección](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [Administrar actualizaciones de puntos de conexión que están des actualizadas](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Administrar actualizaciones para dispositivos móviles y máquinas virtuales (VM)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)