---
title: compatibilidad de Microsoft Defender Antivirus con otros productos de seguridad
description: Obtenga información sobre Microsoft Defender Antivirus con otros productos de seguridad y sistemas operativos.
keywords: windows defender, defender para punto de conexión, de última generación, antivirus, compatibilidad, modo pasivo
ms.pagetype: security
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.date: 10/31/2022
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: mkaminska, pahuijbr
manager: dansimp
ms.subservice: mde
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: c935c9e6131f602c582edb5a98787cc8871afbec
ms.sourcegitcommit: 4bae15909267a70c8842bd0cd3dceb8459b4cc29
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68798351"
---
# <a name="microsoft-defender-antivirus-compatibility-with-other-security-products"></a>compatibilidad de Microsoft Defender Antivirus con otros productos de seguridad

**Se aplica a:**

- Antivirus de Microsoft Defender
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

**Plataformas**
- Windows

Microsoft Defender Antivirus se instala automáticamente en puntos de conexión que ejecutan las siguientes versiones de Windows:

- Windows 10 o posterior
- Windows Server 2022
- Windows Server 2019
- Windows Server, versión 1803 o posterior
- Windows Server 2016

¿Qué ocurre cuando se usa otra solución antivirus o antimalware que no es de Microsoft? ¿Puede ejecutar Microsoft Defender Antivirus junto con otro producto antivirus? Las respuestas dependen de varios factores, como el sistema operativo y si usa [Microsoft Defender para punto de conexión](microsoft-defender-endpoint.md) junto con la protección antivirus.

En este artículo se describe lo que sucede con Microsoft Defender Antivirus y una solución antivirus o antimalware que no es de Microsoft, con y sin Defender para punto de conexión.

> [!IMPORTANT]
> - Microsoft Defender Antivirus está disponible en dispositivos que ejecutan Windows 10 y 11, Windows Server 2022, Windows Server 2019, Windows Server, versión 1803 o posterior y Windows Server 2016. 
> - Microsoft Defender Antivirus también está disponible en Windows Server 2012 R2 cuando se incorpora mediante la [solución moderna y unificada](/microsoft-365/security/defender-endpoint/configure-server-endpoints).
> - En Windows 8.1, la protección antivirus de punto de conexión de nivel empresarial se ofrece como [System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10)), que se administra a través de Microsoft Endpoint Configuration Manager.
> - Windows Defender también se ofrece para [dispositivos de consumidor en Windows 8.1](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender), aunque Windows Defender no proporciona administración de nivel empresarial.

## <a name="antivirus-protection-without-defender-for-endpoint"></a>Protección antivirus sin Defender para punto de conexión

En esta sección se describe lo que sucede cuando se usa Microsoft Defender Antivirus junto con productos antivirus o antimalware que no son de Microsoft en puntos de conexión que no están incorporados a Defender para punto de conexión. 

> [!NOTE]
> En general, Microsoft Defender Antivirus no se ejecuta en modo pasivo en dispositivos que no están incorporados a Defender para punto de conexión.

En la tabla siguiente se resume lo que se debe esperar:

|Versión de Windows|Solución antivirus/antimalware principal|Microsoft Defender estado antivirus|
|:---|:---|:---|
|Windows 10 <br/> Windows 11|Antivirus de Microsoft Defender|Modo activo|
|Windows 10 <br/> Windows 11|Una solución antivirus o antimalware que no es de Microsoft|Modo deshabilitado (se produce automáticamente)|
|Windows Server 2022 <br/> Windows Server 2019<br/> Windows Server, versión 1803 o posterior <br/> Windows Server 2016 <br/> Windows Server 2012 R2 |Antivirus de Microsoft Defender|Modo activo|
|Windows Server 2022<br/>Windows Server 2019<br/>Windows Server, versión 1803 o posterior <br/> Windows Server 2016 |Una solución antivirus o antimalware que no es de Microsoft|Deshabilitado (se establece manualmente) <sup>[[1](#fn1)]</sup>|

(<a id="fn1">1</a>) En Windows Server, si ejecuta un producto antivirus que no es de Microsoft, puede desinstalar Microsoft Defender Antivirus para evitar conflictos. Si el dispositivo está incorporado a Microsoft Defender para punto de conexión, puede usar Microsoft Defender Antivirus en modo pasivo (consulte a continuación).

> [!TIP]
> En Windows Server 2016, es posible que vea *Windows Defender Antivirus* en lugar de *Microsoft Defender Antivirus*.

## <a name="microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions"></a>Microsoft Defender antivirus y soluciones antivirus o antimalware que no son de Microsoft

> [!NOTE]
> En general, Microsoft Defender Antivirus solo se puede establecer en modo pasivo en los puntos de conexión que se incorporan a Defender para punto de conexión.

Si Microsoft Defender Antivirus se ejecuta en modo activo, modo pasivo o está deshabilitado depende de varios factores, como:

- Qué versión de Windows está instalada en un punto de conexión
- Si Microsoft Defender Antivirus es la solución antivirus o antimalware principal en el punto de conexión
- Si el punto de conexión está incorporado a Defender para punto de conexión

En la tabla siguiente se resume el estado de Microsoft Defender Antivirus en varios escenarios. 

| Versión de Windows   | Solución antivirus/antimalware  | Incorporado a <br/> ¿Defender para punto de conexión? | Microsoft Defender estado antivirus     |
|:------|:------|:-------|:-------|
| Windows 10 <br/> Windows 11| Antivirus de Microsoft Defender | Yes  | Modo activo | 
| Windows 10 <br/> Windows 11 | Antivirus de Microsoft Defender | No   | Modo activo |
| Windows 10 <br/> Windows 11  | Una solución antivirus o antimalware que no es de Microsoft | Sí  | Modo pasivo (automáticamente) |
| Windows 10 <br/> Windows 11  | Una solución antivirus o antimalware que no es de Microsoft | No   | Modo deshabilitado (automáticamente)    |
| Windows Server 2022 <br/> Windows Server 2019 <br/>Windows Server, versión 1803 o posterior  | Antivirus de Microsoft Defender  | Sí |         Modo activo  |
| Windows Server 2022 <br/> Windows Server 2019 <br/> Windows Server, versión 1803 o posterior   | Antivirus de Microsoft Defender | No  | Modo activo |
| Windows Server 2022 <br/> Windows Server 2019 <p> Windows Server, versión 1803 o posterior  | Una solución antivirus o antimalware que no es de Microsoft | Yes  | Microsoft Defender Antivirus debe establecerse en modo pasivo (manualmente) <sup>[[2](#fn2)]<sup>  | 
| Windows Server 2022 <br/> Windows Server 2019 <p> Windows Server, versión 1803 o posterior  | Una solución antivirus o antimalware que no es de Microsoft | No  | Microsoft Defender Antivirus debe deshabilitarse (manualmente) <sup>[[3](#fn3)]<sup></sup>  |
| Windows Server 2016 <br/> Windows Server 2012 R2   | Antivirus de Microsoft Defender | Yes | Modo activo |
|Windows Server 2016 <br/> Windows Server 2012 R2  | Antivirus de Microsoft Defender | No | Modo activo |
| Windows Server 2016 <br/> Windows Server 2012 R2  | Una solución antivirus o antimalware que no es de Microsoft | Yes | Microsoft Defender Antivirus debe establecerse en modo pasivo (manualmente) <sup>[[2](#fn2)]<sup> |
|Windows Server 2016 <br/> Windows Server 2012 R2  | Una solución antivirus o antimalware que no es de Microsoft | No | Microsoft Defender Antivirus debe deshabilitarse (manualmente) <sup>[[3](#fn3)]<sup> |

(<a id="fn2">2</a>) En Windows Server 2019, Windows Server, versión 1803 o posterior, Windows Server 2016 o Windows Server 2012 R2, Microsoft Defender Antivirus no entra en modo pasivo automáticamente al instalar un producto antivirus que no es de Microsoft. En esos casos, establezca Microsoft Defender Antivirus en modo pasivo para evitar problemas causados por tener varios productos antivirus instalados en un servidor. Puede establecer Microsoft Defender Antivirus en modo pasivo mediante una clave del Registro como se indica a continuación:
- Camino: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Nombre: `ForceDefenderPassiveMode`
- Tipo: `REG_DWORD`
- Valor: `1`

Puede ver el estado de protección en PowerShell mediante el comando [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus). Compruebe el valor de `AMRunningMode`. Debería ver El modo de bloqueo **normal**, **pasivo** o **EDR** si Microsoft Defender Antivirus está habilitado en el punto de conexión. 

 > [!NOTE]
 > Para que el modo pasivo funcione en puntos de conexión que ejecutan Windows Server 2016 y Windows Server 2012 R2, esos puntos de conexión deben incorporarse con la solución moderna y unificada que se describe en [Incorporación de servidores Windows](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016). 

(<a id="fn3">3</a>) En Windows Server 2016, Windows Server 2012 R2, Windows Server versión 1803 o posterior, Windows Server 2019 y Windows Server 2022, si usa un producto antivirus que no es de Microsoft en un punto de conexión que *no* está incorporado a Microsoft Defender para punto de conexión , deshabilite o desinstale Microsoft Defender Antivirus manualmente para evitar problemas causados por tener varios productos antivirus instalados en un servidor.

> [!TIP]
> En Windows Server 2016, es posible que vea *Windows Defender Antivirus* en lugar de *Microsoft Defender Antivirus*.

Defender para punto de conexión incluye funcionalidades que amplían aún más la protección antivirus instalada en el punto de conexión. Puede beneficiarse de la ejecución de Microsoft Defender Antivirus junto con otra solución antivirus.

Por ejemplo, la [detección y respuesta de puntos de conexión (EDR) en modo de bloque](edr-in-block-mode.md) proporciona protección adicional contra artefactos malintencionados incluso si Microsoft Defender Antivirus no es el producto antivirus principal. Estas funcionalidades requieren que Microsoft Defender Antivirus se instale y ejecute en modo pasivo o en modo activo.

## <a name="requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode"></a>Requisitos para que Microsoft Defender Antivirus se ejecute en modo pasivo

Para que Microsoft Defender Antivirus se ejecute en modo pasivo, los puntos de conexión deben cumplir los siguientes requisitos:

- Sistema operativo: Windows 10 o posterior; Windows Server 2022, Windows Server 2019 o Windows Server, versión 1803 o posterior <br/>(Windows Server 2012 R2 y Windows Server 2016 si se incorporan mediante la [solución moderna y unificada](/microsoft-365/security/defender-endpoint/configure-server-endpoints)). 
- Microsoft Defender Antivirus debe estar instalado. 
- Otro producto antivirus o antimalware que no sea de Microsoft debe instalarse y usarse como solución antivirus principal. 
- Los puntos de conexión deben incorporarse a Defender para punto de conexión. 

> [!IMPORTANT]
> - Microsoft Defender Antivirus solo está disponible en dispositivos que ejecutan Windows 10 y 11, Windows Server 2022, Windows Server 2016, Windows Server 2019, Windows Server, versión 1803 o posterior, Windows Server 2016 y Windows Server 2012 R2.
> - El modo pasivo solo se admite en Windows Server 2012 R2 & 2016 cuando el dispositivo se incorpora mediante la [solución moderna y unificada](/microsoft-365/security/defender-endpoint/configure-server-endpoints). 
> - En Windows 8.1, la protección antivirus de punto de conexión de nivel empresarial se ofrece como [System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10)), que se administra a través de Microsoft Endpoint Configuration Manager.
> - Windows Defender también se ofrece para [dispositivos de consumidor en Windows 8.1](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender), aunque Windows Defender no proporciona administración de nivel empresarial.

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>Cómo afecta Microsoft Defender Antivirus a la funcionalidad de Defender para punto de conexión

Defender para punto de conexión afecta a si Microsoft Defender Antivirus puede ejecutarse en modo pasivo. Además, el estado de Microsoft Defender Antivirus puede afectar a determinadas funcionalidades de Defender para punto de conexión. Por ejemplo, la protección en tiempo real funciona cuando Microsoft Defender Antivirus está en modo activo o pasivo, pero no cuando Microsoft Defender Antivirus está deshabilitado o desinstalado.

> [!IMPORTANT]
> - En la tabla de esta sección se resumen las características y funcionalidades que funcionan activamente o no, según si Microsoft Defender Antivirus está en modo activo, modo pasivo o deshabilitado o desinstalado. Esta tabla está diseñada para ser solo informativa.   
> - **No desactive las funcionalidades**, como la protección en tiempo real, la protección entregada en la nube o el examen periódico limitado si usa Microsoft Defender Antivirus en modo pasivo, o si usa [EDR en modo de bloque](edr-in-block-mode.md), que funciona en segundo plano para detectar y corregir artefactos malintencionados detectados después de la infracción.

| Protección | Antivirus de Microsoft Defender <br/>(*Modo activo*) | Antivirus de Microsoft Defender <br/>(*modo pasivo*) | Antivirus de Microsoft Defender <br/>(*Deshabilitado o desinstalado*) | [EDR en modo bloqueo](edr-in-block-mode.md) | 
|:---|:---|:---|:---|:---| 
| [Protección en tiempo real](configure-real-time-protection-microsoft-defender-antivirus.md) | Yes | Vea la nota <sup>[[4](#fn4)]</sup> | No | No | 
| [Protección entregada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md) | Yes | No  | No | No | 
| [Protección de red](network-protection.md)  | Yes | No | No | No | 
| [Reglas de la reducción de la superficie expuesta a ataques](attack-surface-reduction.md)  | Yes | No | No  | No | 
| [Disponibilidad limitada del examen periódico](limited-periodic-scanning-microsoft-defender-antivirus.md) | No | Sí | No | No | 
| [Información de detección y detección de archivos](review-scan-results-microsoft-defender-antivirus.md) | Yes | Sí <sup>[[5](#fn5)]</sup> | No | Sí | 
| [Corrección de amenazas](configure-remediation-microsoft-defender-antivirus.md) | Yes | Vea la nota <sup>[[6](#fn6)]</sup> | No | Sí | 
| [Actualizaciones de inteligencia de seguridad](manage-updates-baselines-microsoft-defender-antivirus.md) | Yes | Sí <sup>[[7](#fn7)]</sup> | No | Sí <sup>[[7](#fn7)]</sup> | 
| [Prevención de pérdida de datos](../../compliance/endpoint-dlp-learn-about.md) | Sí | Sí | No | No |
| [Acceso controlado a carpetas](controlled-folders.md) | Yes |No | No | No |
| [Filtrado de contenido web](web-content-filtering.md) | Yes | Vea la nota <sup>[[8](#fn8)]</sup> | No | No |
| [Control de dispositivos](device-control-report.md) | Sí | Sí | No | No |
| [Protección PUA](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | Yes | No | No | No |

(<a id="fn4">4</a>) En general, cuando Microsoft Defender Antivirus está en modo pasivo, la protección en tiempo real no proporciona ningún bloqueo o aplicación, aunque esté habilitado y en modo pasivo.

(<a id="fn5">5</a>) Cuando Microsoft Defender Antivirus está en modo pasivo, los exámenes no están programados.

(<a id="fn6">6</a>) Cuando Microsoft Defender Antivirus está en modo pasivo, no corrige las amenazas. Sin embargo, las amenazas se pueden corregir mediante la [detección y respuesta de puntos de conexión (EDR) en modo de bloque](edr-in-block-mode.md). En este caso, es posible que vea alertas que muestran Microsoft Defender Antivirus como origen, incluso cuando Microsoft Defender Antivirus está en modo pasivo.

(<a id="fn7">7</a>) La cadencia de actualización de inteligencia de seguridad solo se controla mediante Windows Update configuración. Los programadores de actualizaciones específicos de Defender (diarios y semanales en un momento específico, basados en intervalos) solo funcionan cuando Microsoft Defender Antivirus está en modo activo. Se ignoran en modo pasivo.

(<a id="fn8">8</a>) Cuando Microsoft Defender Antivirus está en modo pasivo, el filtrado de contenido web solo funciona con el explorador Microsoft Edge. 

> [!IMPORTANT]
> - La protección contra [la pérdida de datos de punto de conexión](/microsoft-365/compliance/endpoint-dlp-learn-about) sigue funcionando normalmente cuando Microsoft Defender Antivirus está en modo activo o pasivo.
>
> - No deshabilite, detenga ni modifique ninguno de los servicios asociados que usa Microsoft Defender Antivirus, Defender para punto de conexión o la aplicación Seguridad de Windows. Esta recomendación incluye los servicios y *procesos wscsvc*, *SecurityHealthService*, *MsSense*, *Sense*, *WinDefend* o *MsMpEng* . La modificación manual de estos servicios puede provocar una inestabilidad grave en los dispositivos y puede hacer que la red sea vulnerable. Deshabilitar, detener o modificar esos servicios también puede causar problemas al usar soluciones antivirus que no son de Microsoft y cómo se muestra su información en la [aplicación Seguridad de Windows](microsoft-defender-security-center-antivirus.md).
>
> - En Defender para punto de conexión, puede activar EDR en modo de bloque, incluso si Microsoft Defender Antivirus no es la solución antivirus principal. EDR en modo de bloque detecta y corrige los elementos malintencionados que se encuentran en el dispositivo (después de la infracción). Para más información, consulte [EDR en modo de bloque](edr-in-block-mode.md).

## <a name="how-to-confirm-the-state-of-microsoft-defender-antivirus"></a>Cómo confirmar el estado de Microsoft Defender Antivirus

Puede usar uno de varios métodos para confirmar el estado de Microsoft Defender Antivirus. Puede:

- [Use la aplicación Seguridad de Windows para identificar la aplicación antivirus](#use-the-windows-security-app-to-identify-your-antivirus-app).
- [Use el Administrador de tareas para confirmar que Microsoft Defender Antivirus está en ejecución](#use-task-manager-to-confirm-that-microsoft-defender-antivirus-is-running).
- [Use Windows PowerShell para confirmar que Microsoft Defender Antivirus está en ejecución](#use-windows-powershell-to-confirm-that-microsoft-defender-antivirus-is-running).
- [Use Windows PowerShell para confirmar que se está ejecutando la protección antivirus](#use-windows-powershell-to-confirm-that-antivirus-protection-is-running).

> [!IMPORTANT]
> A partir de la [versión de la plataforma 4.18.2208.0 y versiones posteriores](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions): si un servidor se ha incorporado a Microsoft Defender para punto de conexión, la configuración de directiva de [grupo](configure-endpoints-gp.md#update-endpoint-protection-configuration) "Desactivar Windows Defender" ya no deshabilitará completamente Windows Defender Antivirus activado. Windows Server 2012 R2 y versiones posteriores. En su lugar, lo colocará en modo pasivo. Además, la característica de [protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md) permitirá cambiar al modo activo, pero no al modo pasivo.
> 
> - Si ya se ha implementado "Desactivar Windows Defender" antes de incorporarse a Microsoft Defender para punto de conexión, no habrá ningún cambio y Antivirus de Defender permanecerá deshabilitado.
> - Para cambiar antivirus de Defender al modo pasivo, incluso si se deshabilitó antes de la incorporación, puede aplicar la [configuración de ForceDefenderPassiveMode](switch-to-mde-phase-2.md#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server) con un valor de `1`. Para colocarlo en modo activo, cambie este valor a `0` en su lugar.
> 
> Tenga en cuenta la lógica modificada para `ForceDefenderPassiveMode` cuando se habilita la protección contra alteraciones: una vez que Microsoft Defender Antivirus cambia al modo activo, la protección contra alteraciones impedirá que vuelva al modo pasivo incluso cuando `ForceDefenderPassiveMode` se establezca en `1`.

### <a name="use-the-windows-security-app-to-identify-your-antivirus-app"></a>Usar la aplicación Seguridad de Windows para identificar la aplicación antivirus

1. En un dispositivo Windows, abra la aplicación Seguridad de Windows.

2. Seleccione **Protección antivirus y contra amenazas**.

3. En **¿Quién me protege?** seleccione **Administrar proveedores**.

4. En la página **Proveedores de seguridad**, en **Antivirus**, debería ver **Microsoft Defender Antivirus está activado**.

### <a name="use-task-manager-to-confirm-that-microsoft-defender-antivirus-is-running"></a>Use el Administrador de tareas para confirmar que Microsoft Defender Antivirus está en ejecución

1. En un dispositivo Windows, abra la aplicación Administrador de tareas.

2. Seleccione la pestaña **Detalles** .

3. Busque **MsMpEng.exe** en la lista.

### <a name="use-windows-powershell-to-confirm-that-microsoft-defender-antivirus-is-running"></a>Use Windows PowerShell para confirmar que Microsoft Defender Antivirus está en ejecución

> [!NOTE]
> Use este procedimiento solo para confirmar si Microsoft Defender Antirivus se ejecuta en un punto de conexión.

1. En un dispositivo Windows, abra Windows PowerShell. 

2. Ejecute el siguiente cmdlet de PowerShell: `Get-Process`.

3. Revisar los resultados. Debería ver **MsMpEng.exe** si Microsoft Defender Antivirus está habilitado.

### <a name="use-windows-powershell-to-confirm-that-antivirus-protection-is-running"></a>Uso de Windows PowerShell para confirmar que se está ejecutando la protección antivirus

> [!NOTE]
> Use este procedimiento solo para confirmar si la protección antivirus está habilitada en un punto de conexión.

1. En un dispositivo Windows, abra Windows PowerShell.

2. Ejecute el siguiente cmdlet de PowerShell: `Get-MpComputerStatus | select AMRunningMode`.

3. Revisar los resultados. Debería ver El modo de bloqueo **normal**, **pasivo** o **EDR** si la protección antivirus está habilitada en el punto de conexión. 

> [!NOTE]
> Tenga en cuenta que este procedimiento solo sirve para confirmar si la protección antivirus está habilitada en un punto de conexión.

## <a name="more-details-about-microsoft-defender-antivirus-states"></a>Más detalles sobre Microsoft Defender estados del Antivirus

En las secciones siguientes se describe qué esperar cuando Microsoft Defender Antivirus es:

- [En modo activo](#active-mode)
- [En modo pasivo, o cuando EDR en modo de bloque está activado](#passive-mode-or-edr-block-mode)
- [Deshabilitado o desinstalado](#disabled-or-uninstalled)

### <a name="active-mode"></a>Modo activo

En modo activo, Microsoft Defender Antivirus se usa como aplicación antivirus en el equipo. Se aplicarán los valores configurados mediante Configuration Manager, directiva de grupo, Microsoft Intune u otros productos de administración. Los archivos se examinan, se corrigen las amenazas y se notifica información de detección en la herramienta de configuración (por ejemplo, en el Centro de administración de Microsoft Endpoint Manager o la aplicación antivirus Microsoft Defender en el punto de conexión).  

### <a name="passive-mode-or-edr-block-mode"></a>Modo pasivo o modo de bloque EDR

En el modo pasivo, Microsoft Defender Antivirus no se usa como aplicación antivirus y *Microsoft Defender Antivirus no* corrige las amenazas. Sin embargo, las amenazas se pueden corregir mediante la [detección y respuesta de puntos de conexión (EDR) en modo de bloque](edr-in-block-mode.md). EDR examina los archivos y se proporcionan informes para las detecciones de amenazas que se comparten con el servicio Defender para punto de conexión. Es posible que vea alertas que muestran Microsoft Defender Antivirus como origen, incluso cuando Microsoft Defender Antivirus está en modo pasivo. 

Cuando Microsoft Defender Antivirus está en modo pasivo, todavía puede [administrar las actualizaciones de Microsoft Defender Antivirus](manage-updates-baselines-microsoft-defender-antivirus.md); sin embargo, no puede mover Microsoft Defender Antivirus al modo activo si los dispositivos tienen un producto antivirus que no es de Microsoft que proporciona protección en tiempo real contra malware.

**Asegúrese de obtener las actualizaciones de antivirus y antimalware, incluso si Microsoft Defender Antivirus se ejecuta en modo pasivo**. Consulte [Administración de actualizaciones Microsoft Defender Antivirus y aplicación de líneas base](manage-updates-baselines-microsoft-defender-antivirus.md).<br/><br/>Tenga en cuenta que el modo pasivo solo se admite en Windows Server 2012 R2 & 2016 cuando la máquina se incorpora mediante la [solución moderna y unificada](/microsoft-365/security/defender-endpoint/configure-server-endpoints). 

### <a name="disabled-or-uninstalled"></a>Deshabilitado o desinstalado

Cuando se deshabilita o desinstala, Microsoft Defender Antivirus no se usa como aplicación antivirus. Los archivos no se examinan y las amenazas no se corrigen. No se recomienda deshabilitar o desinstalar Microsoft Defender Antivirus en general; si es posible, mantenga Microsoft Defender Antivirus en modo pasivo si usa una solución antimalware o antivirus que no sea de Microsoft.

En los casos en los que Microsoft Defender Antivirus se deshabilita automáticamente, se puede volver a habilitar automáticamente si el producto antivirus o antimalware que no es de Microsoft expira, se desinstala o deja de proporcionar protección en tiempo real contra virus, malware u otras amenazas. La habilitación automática de Microsoft Defender Antivirus ayuda a garantizar que la protección antivirus se mantenga en los puntos de conexión.

También puede usar el [examen periódico limitado](limited-periodic-scanning-microsoft-defender-antivirus.md), que funciona con el motor Microsoft Defender Antivirus para comprobar periódicamente si usa una aplicación antivirus que no es de Microsoft.  | 

## <a name="what-about-non-windows-devices"></a>¿Qué ocurre con los dispositivos que no son de Windows?

 Si busca información relacionada con el antivirus para otras plataformas, consulte:

- [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
- [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
- [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
- [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
- [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
- [Configurar Defender para punto de conexión en características de Android](android-configure.md)
- [Configurar Microsoft Defender para punto de conexión en las características iOS](ios-configure-features.md)

## <a name="see-also"></a>Vea también

- [Microsoft Defender Antivirus en clientes Windows](microsoft-defender-antivirus-in-windows-10.md)
- [EDR en modo bloqueo](edr-in-block-mode.md)
- [Obtenga más información sobre la prevención de pérdida de datos en punto de conexión](/microsoft-365/compliance/endpoint-dlp-learn-about)
