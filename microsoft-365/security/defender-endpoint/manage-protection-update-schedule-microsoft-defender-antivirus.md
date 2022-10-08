---
title: Programar Microsoft Defender actualizaciones de protección antivirus
description: Programar el día, la hora y el intervalo para cuándo se deben descargar las actualizaciones de protección
keywords: actualizaciones, líneas base de seguridad, actualizaciones de programación
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.collection:
- m365-security
- tier2
ms.openlocfilehash: 433ecbe6bef2b6af770a2572c7878e4ee2aabc42
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68228150"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a>Administrar la programación para cuándo se han de descargar y aplicar las actualizaciones de protección

> [!IMPORTANT]
> Los clientes que aplicaron la actualización del motor de Microsoft Defender de marzo de 2022 (**1.1.19100.5**) podrían haber encontrado un uso elevado de recursos (CPU o memoria). Microsoft ha publicado una actualización (**1.1.19200.5**) que resuelve los errores introducidos en la versión anterior. Se recomienda a los clientes actualizar a esta nueva compilación de motor de Antivirus Engine (**1.1.19200.5**). Para asegurarse de que los problemas de rendimiento están totalmente corregidos, se recomienda reiniciar las máquinas después de aplicar la actualización. Para obtener más información, consulte [Versiones mensuales de la plataforma y del motor](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions).

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Microsoft Defender Antivirus le permite determinar cuándo debe buscar y descargar actualizaciones.

Puede programar actualizaciones para los puntos de conexión mediante:

- Especificación del día de la semana para comprobar si hay actualizaciones de protección
- Especificación del intervalo para comprobar si hay actualizaciones de protección
- Especificar el tiempo para comprobar si hay actualizaciones de protección

También puede aleatorizar las veces en que cada punto de conexión comprueba y descarga las actualizaciones de protección. Consulte el tema [Programar exámenes](scheduled-catch-up-scans-microsoft-defender-antivirus.md) para obtener más información.

## <a name="use-configuration-manager-to-schedule-protection-updates"></a>Uso de Configuration Manager para programar actualizaciones de protección

1. En la consola de Microsoft Endpoint Manager, abra la directiva antimalware que desea cambiar (haga clic en **Activos y compatibilidad** en el panel de navegación de la izquierda y, a continuación, expanda el árbol a Directivas **de antimalware** de **Endpoint Protection** \> **de información general**\>).

2. Vaya a la sección **Actualizaciones de inteligencia de seguridad** .

3. Para comprobar y descargar actualizaciones en un momento determinado:
      1. Establezca **Comprobar las actualizaciones de inteligencia de seguridad de Endpoint Protection en un intervalo específico...** en **0**.
      2. Establezca **Comprobar las actualizaciones de inteligencia de seguridad de Endpoint Protection diariamente en... en** el momento en que se deben comprobar las actualizaciones.
      3
4. Para comprobar y descargar actualizaciones en un intervalo continuo, establezca **Comprobar las actualizaciones de inteligencia de seguridad de Endpoint Protection en un intervalo específico...** en el número de horas que deben producirse entre las actualizaciones.

5. [Implemente la directiva actualizada como de costumbre](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).

## <a name="use-group-policy-to-schedule-protection-updates"></a>Uso de directiva de grupo para programar actualizaciones de protección

> [!IMPORTANT]
> De forma predeterminada, "SignatureScheduleDay" se establece como "8" y "SignatureUpdateInterval" se establece como "0", por lo que Microsoft Defender Antivirus no programará las actualizaciones de protección.
La habilitación de esta configuración invalidará ese valor predeterminado.

1. En la máquina de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directiva de grupo** vaya a **Configuración del equipo**.

3. Haga clic en **Directivas** y, a continuación, **en Plantillas administrativas**.

4. Expanda el árbol a **componentes** \> de Windows Microsoft Defender **Novedades de firma** del **antivirus** \> y configure los siguientes valores:

    1. Haga doble clic en **la opción Especificar el día de la semana para comprobar si hay actualizaciones de inteligencia de seguridad** y establezca la opción **en Habilitado**. Escriba el día de la semana para comprobar si hay actualizaciones. Haga clic en **Aceptar**.

    2. Haga doble clic en **la opción Especificar el intervalo para comprobar si hay actualizaciones de definiciones** y establezca la opción **en Habilitado**. Escriba el número de horas entre las actualizaciones. Haga clic en **Aceptar**.

    3. Haga doble clic en **la opción Especificar el tiempo para comprobar si hay actualizaciones de definiciones** y establezca la opción **en Habilitado**. Escriba la hora en que se deben comprobar las actualizaciones. La hora se basa en la hora local del punto de conexión. Haga clic en **Aceptar**.

## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a>Uso de cmdlets de PowerShell para programar actualizaciones de protección

Use los siguientes cmdlets:

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

Consulte [Uso de cmdlets de PowerShell para configurar y ejecutar cmdlets Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [Antivirus de Defender](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a>Uso de Instrucciones de administración de Windows (WMI) para programar actualizaciones de protección

Use el [método **Set** de la clase **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

Consulte lo siguiente para obtener más información y los parámetros permitidos:

- [API Windows Defender WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)

## <a name="related-articles"></a>Artículos relacionados

- [Implementación de Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Para obtener más información, consulte Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar bases de referencia.](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Administrar actualizaciones para puntos finales que están desactualizados](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Administrar las actualizaciones forzadas basadas en eventos](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Administrar las actualizaciones de dispositivos móviles y máquinas virtuales](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus en Windows 10 y 11](microsoft-defender-antivirus-in-windows-10.md)
