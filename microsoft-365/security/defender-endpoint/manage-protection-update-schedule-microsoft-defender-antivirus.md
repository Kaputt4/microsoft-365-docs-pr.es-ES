---
title: Programar actualizaciones de protección Antivirus de Microsoft Defender
description: Programar el día, la hora y el intervalo para cuándo se deben descargar las actualizaciones de protección
keywords: actualizaciones, líneas base de seguridad, actualizaciones de programación
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
ms.openlocfilehash: 566b79c534ed13bbdf5f1d66e6ffdbc5ab43a5b2
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2022
ms.locfileid: "64714998"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a>Administrar la programación para cuándo se han de descargar y aplicar las actualizaciones de protección

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Antivirus de Microsoft Defender permite determinar cuándo debe buscar y descargar actualizaciones.

Puede programar actualizaciones para los puntos de conexión mediante:

- Especificación del día de la semana para comprobar si hay actualizaciones de protección
- Especificación del intervalo para comprobar si hay actualizaciones de protección
- Especificar el tiempo para comprobar si hay actualizaciones de protección

También puede aleatorizar las veces en que cada punto de conexión comprueba y descarga las actualizaciones de protección. Consulte el tema [Programar exámenes](scheduled-catch-up-scans-microsoft-defender-antivirus.md) para obtener más información.

## <a name="use-configuration-manager-to-schedule-protection-updates"></a>Uso de Configuration Manager para programar actualizaciones de protección

1. En la consola de Microsoft Endpoint Manager, abra la directiva antimalware que desea cambiar (haga clic en **Activos y compatibilidad** en el panel de navegación de la izquierda y, a continuación, expanda el árbol a **Información general** \> **Endpoint Protection** \> **directivas antimalware**)

2. Vaya a la sección **Actualizaciones de inteligencia de seguridad** .

3. Para comprobar y descargar actualizaciones en un momento determinado:
      1. Establezca **Comprobar Endpoint Protection actualizaciones de inteligencia de seguridad en un intervalo específico... en** **0**.
      2. Establezca **Check for Endpoint Protection security intelligence updates daily at... (Comprobar Endpoint Protection actualizaciones de inteligencia de seguridad diariamente en... en** el momento en que se deben comprobar las actualizaciones).
      3
4. Para comprobar y descargar actualizaciones en un intervalo continuo, establezca **Comprobar Endpoint Protection actualizaciones de inteligencia de seguridad en un intervalo específico...** en el número de horas que deben producirse entre las actualizaciones.

5. [Implemente la directiva actualizada como de costumbre](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).

## <a name="use-group-policy-to-schedule-protection-updates"></a>Uso de directiva de grupo para programar actualizaciones de protección

> [!IMPORTANT]
> De forma predeterminada, "SignatureScheduleDay" se establece como "8" y "SignatureUpdateInterval" se establece como "0", por lo que Antivirus de Microsoft Defender no programará las actualizaciones de protección.
La habilitación de esta configuración invalidará ese valor predeterminado.

1. En la máquina de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directiva de grupo** vaya a **Configuración del equipo**.

3. Haga clic en **Directivas** y, a continuación, **en Plantillas administrativas**.

4. Expanda el árbol para **Windows componentes** \> **Antivirus de Microsoft Defender** \> **actualizaciones de Signature Intelligence** y configure los siguientes valores:

    1. Haga doble clic en **la opción Especificar el día de la semana para comprobar si hay actualizaciones de inteligencia de seguridad** y establezca la opción **en Habilitado**. Escriba el día de la semana para comprobar si hay actualizaciones. Haga clic en **Aceptar**.
    2. Haga doble clic en **la opción Especificar el intervalo para comprobar si hay actualizaciones de inteligencia de seguridad** y establezca la opción **en Habilitado**. Escriba el número de horas entre las actualizaciones. Haga clic en **Aceptar**.
    3. Haga doble clic en **la opción Especificar el tiempo para comprobar si hay actualizaciones de inteligencia de seguridad** y establezca la opción **en Habilitado**. Escriba la hora en que se deben comprobar las actualizaciones. La hora se basa en la hora local del punto de conexión. Haga clic en **Aceptar**.

## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a>Uso de cmdlets de PowerShell para programar actualizaciones de protección

Use los siguientes cmdlets:

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

Consulte [Uso de cmdlets de PowerShell para configurar y ejecutar](use-powershell-cmdlets-microsoft-defender-antivirus.md) [cmdlets](/powershell/module/defender/) Antivirus de Microsoft Defender y Antivirus de Defender para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a>Uso de Windows Management Instruction (WMI) para programar actualizaciones de protección

Use el [método **Set** de la clase **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

Consulte lo siguiente para obtener más información y los parámetros permitidos:

- [API Windows Defender WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="related-articles"></a>Artículos relacionados

- [Implementación de Antivirus de Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)
- [Administración de actualizaciones Antivirus de Microsoft Defender y aplicación de líneas base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Administrar las actualizaciones de los puntos de conexión que están obsoletos](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Administrar las actualizaciones forzadas basadas en eventos](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Administrar las actualizaciones de dispositivos móviles y máquinas virtuales](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
