---
title: Programar Antivirus de Microsoft Defender de protección
description: Programar el día, la hora y el intervalo para el momento en que se deben descargar las actualizaciones de protección
keywords: actualizaciones, líneas base de seguridad, actualizaciones de programación
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: f1a163b2f56e84b7c93be99972d5aa62894edfed
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207756"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a>Administrar la programación para cuándo se han de descargar y aplicar las actualizaciones de protección

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Antivirus de Microsoft Defender permite determinar cuándo debe buscar y descargar actualizaciones.

Puede programar actualizaciones para los puntos de conexión mediante:

- Especificar el día de la semana para comprobar si hay actualizaciones de protección
- Especificación del intervalo para comprobar si hay actualizaciones de protección
- Especificar el tiempo para comprobar si hay actualizaciones de protección

También puede aleatorizar las horas en las que cada extremo comprueba y descarga actualizaciones de protección. Vea el [tema Programar exámenes](scheduled-catch-up-scans-microsoft-defender-antivirus.md) para obtener más información.

## <a name="use-configuration-manager-to-schedule-protection-updates"></a>Usar Configuration Manager para programar actualizaciones de protección

1. En la consola Microsoft Endpoint Manager, abra la directiva de antimalware  que desea cambiar (haga clic en Activos  y cumplimiento en el panel de navegación de la izquierda y, a continuación, expanda el árbol a Información general Endpoint Protection Directivas \>  \> **antimalware**)

2. Vaya a la **sección Actualizaciones de inteligencia de** seguridad.

3. Para comprobar y descargar actualizaciones en un momento determinado:
      1. Establezca **Comprobar si Endpoint Protection de inteligencia de seguridad en un intervalo específico...** en **0**.
      2. Establezca **Comprobar si Endpoint Protection de inteligencia de seguridad diariamente en...** en el momento en que deben comprobarse las actualizaciones.
      3
4. Para comprobar y descargar actualizaciones en un intervalo continuo, establezca Comprobar si Endpoint Protection actualizaciones de inteligencia de seguridad en un intervalo **específico...** en el número de horas que deben producirse entre actualizaciones.

5. [Implemente la directiva actualizada como de costumbre.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

## <a name="use-group-policy-to-schedule-protection-updates"></a>Usar la directiva de grupo para programar actualizaciones de protección

> [!IMPORTANT]
> De forma predeterminada, Antivirus de Microsoft Defender comprobará si hay una actualización 15 minutos antes de la hora de los exámenes programados. Si se habilita esta configuración, se invalidará el valor predeterminado.

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**

3. Haga clic **en Directivas** **y, a continuación, en Plantillas administrativas.**

4. Expanda el árbol para Windows **componentes Antivirus de Microsoft Defender** de inteligencia \>  \> **de firma** y configure las siguientes opciones:

    1. Haga doble clic en **la opción Especificar el día de la** semana para comprobar si hay actualizaciones de inteligencia de seguridad y establezca la opción en **Habilitado**. Escriba el día de la semana para buscar actualizaciones. Haga clic en **Aceptar**.
    2. Haga doble clic en **la opción Especificar el intervalo para comprobar si** hay actualizaciones de inteligencia de seguridad y establezca la opción en **Habilitado**. Escriba el número de horas entre actualizaciones. Haga clic en **Aceptar**.
    3. Haga doble clic en **la opción Especificar la hora para comprobar si** hay actualizaciones de inteligencia de seguridad y establezca la opción en **Habilitado**. Escriba la hora en la que deben comprobarse las actualizaciones. La hora se basa en la hora local del extremo. Haga clic en **Aceptar**.

## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a>Usar cmdlets de PowerShell para programar actualizaciones de protección

Use los cmdlets siguientes:

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

Consulte [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a>Usar Windows de administración de archivos (WMI) para programar actualizaciones de protección

Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

Vea lo siguiente para obtener más información y parámetros permitidos:

- [Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="related-articles"></a>Artículos relacionados

- [Implementar Antivirus de Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)
- [Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Administrar actualizaciones de puntos de conexión que están des actualizadas](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Administrar las actualizaciones forzadas basadas en eventos](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Administrar las actualizaciones de dispositivos móviles y máquinas virtuales](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
