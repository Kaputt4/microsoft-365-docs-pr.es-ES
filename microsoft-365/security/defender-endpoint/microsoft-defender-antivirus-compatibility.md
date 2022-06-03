---
title: Antivirus de Microsoft Defender compatibilidad con otros productos de seguridad
description: Obtenga información sobre Antivirus de Microsoft Defender con otros productos de seguridad y los sistemas operativos.
keywords: windows defender, defender para punto de conexión, de última generación, antivirus, compatibilidad, modo pasivo
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: mkaminska, pahuijbr
manager: dansimp
ms.technology: mde
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: 2000d10918c7e351c7e4bedfe8281b6a011cca9d
ms.sourcegitcommit: 35f167725bec5fd4fe131781a53d96b060cf232d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "65872432"
---
# <a name="microsoft-defender-antivirus-compatibility-with-other-security-products"></a>Antivirus de Microsoft Defender compatibilidad con otros productos de seguridad

**Se aplica a:**

- Antivirus de Microsoft Defender
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

**Plataformas**
- Windows

Antivirus de Microsoft Defender se instala automáticamente en puntos de conexión que ejecutan las siguientes versiones de Windows:

- Windows 10 o posterior
- Windows Server 2022
- Windows Server 2019
- Windows Server, versión 1803 o posterior
- Windows Server 2016

¿Qué ocurre cuando se usa otra solución antivirus o antimalware que no es de Microsoft? ¿Puede ejecutar Antivirus de Microsoft Defender junto con otro producto antivirus? Las respuestas dependen de varios factores, como el sistema operativo y si usa [Microsoft Defender para punto de conexión](microsoft-defender-endpoint.md) junto con la protección antivirus.

En este artículo se describe lo que sucede con Antivirus de Microsoft Defender y una solución antivirus o antimalware que no es de Microsoft, con y sin Defender para punto de conexión.

> [!IMPORTANT]
> - Antivirus de Microsoft Defender está disponible en dispositivos que ejecutan Windows 10 y 11, Windows Server 2022, Windows Server 2019, Windows Server, versión 1803 o posterior y Windows Server 2016. 
> - Antivirus de Microsoft Defender también está disponible en Windows Server 2012 R2 cuando se incorpora mediante la [solución moderna y unificada](/microsoft-365/security/defender-endpoint/configure-server-endpoints).
> - En Windows 8.1, la protección antivirus de punto de conexión de nivel empresarial se ofrece como [System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10)), que se administra a través de Microsoft Endpoint Configuration Manager.
> - Windows Defender también se ofrece para [dispositivos de consumidor en Windows 8.1](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender), aunque Windows Defender no proporciona administración de nivel empresarial.

## <a name="antivirus-protection-without-defender-for-endpoint"></a>Protección antivirus sin Defender para punto de conexión

En esta sección se describe lo que sucede al usar Antivirus de Microsoft Defender junto con productos antivirus o antimalware que no son de Microsoft en puntos de conexión que no están incorporados a Defender para punto de conexión. 

> [!NOTE]
> En general, Antivirus de Microsoft Defender no se ejecuta en modo pasivo en dispositivos que no están incorporados a Defender para punto de conexión.

En la tabla siguiente se resume lo que se debe esperar:

|Versión de Windows|Solución antivirus/antimalware principal|Antivirus de Microsoft Defender estado|
|:---|:---|:---|
|Windows 10 <br/> Windows 11|Antivirus de Microsoft Defender|Modo activo|
|Windows 10 <br/> Windows 11|Una solución antivirus o antimalware que no es de Microsoft|Modo deshabilitado (se produce automáticamente)|
|Windows Server 2022 <br/> Windows Server 2019<br/> Windows Server, versión 1803 o posterior <br/> Windows Server 2016 <br/> Windows Server 2012 R2 |Antivirus de Microsoft Defender|Modo activo|
|Windows Server 2022<br/>Windows Server 2019<br/>Windows Server, versión 1803 o posterior <br/> Windows Server 2016 |Una solución antivirus o antimalware que no es de Microsoft|Deshabilitado (se establece manualmente) <sup>[[1](#fn1)]</sup>|

(<a id="fn1">1</a>) En Windows Server, si ejecuta un producto antivirus que no es de Microsoft, puede desinstalar Antivirus de Microsoft Defender para evitar conflictos. Si el dispositivo está incorporado a Microsoft Defender para punto de conexión, puede usar Antivirus de Microsoft Defender en modo pasivo (consulte a continuación).

> [!TIP]
> En Windows Server 2016, es posible que vea *Antivirus de Windows Defender* en lugar de *Antivirus de Microsoft Defender*.

## <a name="microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions"></a>soluciones antivirus o antimalware Antivirus de Microsoft Defender y que no son de Microsoft

> [!NOTE]
> En general, Antivirus de Microsoft Defender se puede establecer en modo pasivo solo en los puntos de conexión que se incorporan a Defender para punto de conexión.

Si Antivirus de Microsoft Defender se ejecuta en modo activo, modo pasivo o está deshabilitado depende de varios factores, como:

- Qué versión de Windows está instalada en un punto de conexión
- Si Antivirus de Microsoft Defender es la solución antivirus o antimalware principal en el punto de conexión
- Si el punto de conexión está incorporado a Defender para punto de conexión

En la tabla siguiente se resume el estado de Antivirus de Microsoft Defender en varios escenarios. 

| Versión de Windows   | Solución antivirus/antimalware  | Incorporado a <br/> ¿Defender para punto de conexión? | Antivirus de Microsoft Defender estado     |
|:------|:------|:-------|:-------|
| Windows 10 <br/> Windows 11| Antivirus de Microsoft Defender | Sí  | Modo activo | 
| Windows 10 <br/> Windows 11 | Antivirus de Microsoft Defender | No   | Modo activo |
| Windows 10 <br/> Windows 11  | Una solución antivirus o antimalware que no es de Microsoft | Sí  | Modo pasivo (automáticamente) |
| Windows 10 <br/> Windows 11  | Una solución antivirus o antimalware que no es de Microsoft | No   | Modo deshabilitado (automáticamente)    |
| Windows Server 2022 <br/> Windows Server 2019 <br/>Windows Server, versión 1803 o posterior  | Antivirus de Microsoft Defender  | Sí |         Modo activo  |
| Windows Server 2022 <br/> Windows Server 2019 <br/> Windows Server, versión 1803 o posterior   | Antivirus de Microsoft Defender | No  | Modo activo |
| Windows Server 2022 <br/> Windows Server 2019 <p> Windows Server, versión 1803 o posterior  | Una solución antivirus o antimalware que no es de Microsoft | Sí  | Antivirus de Microsoft Defender debe establecerse en modo pasivo (manualmente) <sup>[[2](#fn2)]<sup>  | 
| Windows Server 2022 <br/> Windows Server 2019 <p> Windows Server, versión 1803 o posterior  | Una solución antivirus o antimalware que no es de Microsoft | No  | Antivirus de Microsoft Defender debe deshabilitarse (manualmente) <sup>[[3](#fn3)]<sup></sup>  |
| Windows Server 2016 <br/> Windows Server 2012 R2   | Antivirus de Microsoft Defender | Sí | Modo activo |
|Windows Server 2016 <br/> Windows Server 2012 R2  | Antivirus de Microsoft Defender | No | Modo activo |
| Windows Server 2016 <br/> Windows Server 2012 R2  | Una solución antivirus o antimalware que no es de Microsoft | Sí | Antivirus de Microsoft Defender debe establecerse en modo pasivo (manualmente) <sup>[[2](#fn2)]<sup> |
|Windows Server 2016 <br/> Windows Server 2012 R2  | Una solución antivirus o antimalware que no es de Microsoft | No | Antivirus de Microsoft Defender debe deshabilitarse (manualmente) <sup>[[3](#fn3)]<sup> |

(<a id="fn2">2</a>) En Windows Server 2019, Windows Server, versión 1803 o posterior, Windows Server 2016 o Windows Server 2012 R2, Antivirus de Microsoft Defender no entra en modo pasivo automáticamente al instalar un producto antivirus que no es de Microsoft. En esos casos, establezca Antivirus de Microsoft Defender en modo pasivo para evitar problemas causados por la instalación de varios productos antivirus en un servidor. Puede establecer Antivirus de Microsoft Defender en modo pasivo mediante PowerShell, directiva de grupo o una clave del Registro. 

  Puede establecer Antivirus de Microsoft Defender en modo pasivo estableciendo la siguiente clave del Registro:
- Camino: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Nombre: `ForceDefenderPassiveMode`
- Tipo: `REG_DWORD`
- Valor: `1`

 > [!NOTE]
 > Para que el modo pasivo funcione en puntos de conexión que ejecutan Windows Server 2016 y Windows Server 2012 R2, esos puntos de conexión deben incorporarse con la solución moderna y unificada que se describe en [Incorporación de servidores Windows](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016). 

(<a id="fn3">3</a>) En Windows Server 2016, Windows Server 2012 R2, Windows Server versión 1803 o posterior, Windows Server 2019 y Windows Server 2022, si usa un producto antivirus que no es de Microsoft en un punto de conexión que *no* está incorporado a Microsoft Defender para punto de conexión, deshabilite o desinstale Antivirus de Microsoft Defender manualmente para evitar problemas causados por la instalación de varios productos antivirus en un servidor.

> [!TIP]
> En Windows Server 2016, es posible que vea *Antivirus de Windows Defender* en lugar de *Antivirus de Microsoft Defender*.

> [!IMPORTANT]
> Antivirus de Microsoft Defender solo está disponible en dispositivos que ejecutan Windows 10 y 11, Windows Server 2022, Windows Server 2019, Windows Server, versión 1803 o posterior, Windows Server 2016 y Windows Server 2012 R2.
>
> En Windows 8.1, la protección antivirus de punto de conexión de nivel empresarial se ofrece como [System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10)), que se administra a través de Microsoft Endpoint Configuration Manager.
>
> Windows Defender también se ofrece para [dispositivos de consumidor en Windows 8.1](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender), aunque Windows Defender no proporciona administración de nivel empresarial.

Defender para punto de conexión incluye funcionalidades que amplían aún más la protección antivirus instalada en el punto de conexión. Puede beneficiarse de la ejecución de Antivirus de Microsoft Defender junto con otra solución antivirus.

Por ejemplo, la [detección y respuesta de puntos de conexión (EDR) en modo de bloque](edr-in-block-mode.md) proporciona protección adicional contra artefactos malintencionados incluso si Antivirus de Microsoft Defender no es el producto antivirus principal. Estas funcionalidades requieren que Antivirus de Microsoft Defender se instalen y ejecuten en modo pasivo o en modo activo.

### <a name="requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode"></a>Requisitos para que Antivirus de Microsoft Defender se ejecute en modo pasivo

Para que Antivirus de Microsoft Defender se ejecute en modo pasivo, los puntos de conexión deben cumplir los siguientes requisitos:

- Sistema operativo: Windows 10 o posterior; Windows Server 2022, Windows Server 2019 o Windows Server, versión 1803 o posterior
- Antivirus de Microsoft Defender debe instalarse
- Otro producto antivirus o antimalware que no sea de Microsoft debe instalarse y usarse como la solución antivirus principal.
- Los puntos de conexión deben incorporarse a Defender para punto de conexión

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>Cómo afecta Antivirus de Microsoft Defender a la funcionalidad de Defender para punto de conexión

Defender para punto de conexión afecta a si Antivirus de Microsoft Defender se puede ejecutar en modo pasivo. Antivirus de Microsoft Defender también puede afectar a ciertas funcionalidades de Defender para punto de conexión. Por ejemplo, la protección en tiempo real funciona cuando Antivirus de Microsoft Defender está en modo activo o pasivo, pero no cuando Antivirus de Microsoft Defender está deshabilitada o desinstalada.

En la tabla de esta sección se resumen las características y funcionalidades que funcionan activamente o no, según si Antivirus de Microsoft Defender está en modo activo, modo pasivo o deshabilitado o desinstalado.

> [!IMPORTANT]
> La tabla siguiente está diseñada para ser solo informativa. **No desactive las funcionalidades**, como la protección en tiempo real, la protección proporcionada en la nube o el examen periódico limitado si usa Antivirus de Microsoft Defender en modo pasivo, o si usa [EDR en modo de bloque](edr-in-block-mode.md), que funciona en segundo plano para detectar y corregir artefactos malintencionados detectados después de la infracción.

| Protección | Antivirus de Microsoft Defender <br/>(*Modo activo*) | Antivirus de Microsoft Defender <br/>(*modo pasivo*) | Antivirus de Microsoft Defender <br/>(*Deshabilitado o desinstalado*) | [EDR en modo bloqueo](edr-in-block-mode.md) | 
|:---|:---|:---|:---|:---| 
| [Protección en tiempo real](configure-real-time-protection-microsoft-defender-antivirus.md) | Sí | Vea la nota <sup>[[4](#fn4)]</sup> | No | No | 
| [Protección entregada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md) | Sí | No  | No | No | 
| [Protección de red](network-protection.md)  | Sí | No | No | No | 
| [Reglas de la reducción de la superficie expuesta a ataques](attack-surface-reduction.md)  | Sí | No | No  | No | 
| [Disponibilidad limitada del examen periódico](limited-periodic-scanning-microsoft-defender-antivirus.md) | No | No | Sí | No | 
| [Información de detección y detección de archivos](review-scan-results-microsoft-defender-antivirus.md) | Sí | Sí<sup>[[5](#fn5)]</sup> | No | Sí | 
| [Corrección de amenazas](configure-remediation-microsoft-defender-antivirus.md) | Sí | Vea la nota <sup>[[6](#fn6)]</sup> | No | Sí | 
| [Actualizaciones de inteligencia de seguridad](manage-updates-baselines-microsoft-defender-antivirus.md) | Sí | Sí <sup>[[7](#fn7)]</sup> | No | Sí <sup>[[7](#fn7)]</sup> | 
| [Prevención de pérdida de datos](../../compliance/endpoint-dlp-learn-about.md) | Sí | Sí | No | No |
| [Acceso controlado a carpetas](controlled-folders.md) | Sí |No | No | No |
| [Filtrado de contenido web](web-content-filtering.md) | Sí | Vea la nota <sup>[[8](#fn8)]</sup> | No | No |
| [Control de dispositivos](device-control-report.md) | Sí | Sí | No | No |
| [Protección PUA](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | Sí | No | No | No |

(<a id="fn4">4</a>) En general, cuando Antivirus de Microsoft Defender está en modo pasivo, la protección en tiempo real no proporciona ningún bloqueo o aplicación, aunque esté habilitado y en modo pasivo.

(<a id="fn5">5</a>) Cuando Antivirus de Microsoft Defender está en modo pasivo, los exámenes no están programados.

(<a id="fn6">6</a>) Cuando Antivirus de Microsoft Defender está en modo pasivo, no corrige las amenazas. Sin embargo, las amenazas se pueden corregir mediante la [detección y respuesta de puntos de conexión (EDR) en modo de bloque](edr-in-block-mode.md). En este caso, es posible que vea alertas que muestran Antivirus de Microsoft Defender como origen, incluso cuando Antivirus de Microsoft Defender está en modo pasivo.

(<a id="fn7">7</a>) La cadencia de actualización de inteligencia de seguridad solo se controla mediante Windows Update configuración. Los programadores de actualizaciones específicos de Defender (diarios y semanales en un momento específico, basados en intervalos) solo funcionan cuando Antivirus de Microsoft Defender está en modo activo. Se omiten en modo pasivo.

(<a id="fn8">8</a>) Cuando Antivirus de Microsoft Defender está en modo pasivo, el filtrado de contenido web solo funciona con el explorador Microsoft Edge. 

> [!NOTE]
> La protección contra [la pérdida de datos de punto de conexión](/microsoft-365/compliance/endpoint-dlp-learn-about) sigue funcionando normalmente cuando Antivirus de Microsoft Defender está en modo activo o pasivo.

## <a name="important-notes"></a>Notas importantes

- No deshabilite, detenga ni modifique ninguno de los servicios asociados que usan Antivirus de Microsoft Defender, Defender para punto de conexión o la aplicación Seguridad de Windows. Esta recomendación incluye los servicios y *procesos wscsvc*, *SecurityHealthService*, *MsSense*, *Sense*, *WinDefend* o *MsMpEng* . La modificación manual de estos servicios puede provocar una inestabilidad grave en los dispositivos y puede hacer que la red sea vulnerable. Deshabilitar, detener o modificar esos servicios también puede causar problemas al usar soluciones antivirus que no son de Microsoft y cómo se muestra su información en la [aplicación Seguridad de Windows](microsoft-defender-security-center-antivirus.md).

- En Defender para punto de conexión, active EDR en modo de bloque, incluso si Antivirus de Microsoft Defender no es la solución antivirus principal. EDR en modo de bloque detecta y corrige los elementos malintencionados que se encuentran en el dispositivo (después de la infracción). Para obtener más información, consulte [EDR en modo de bloque](edr-in-block-mode.md).

## <a name="how-to-confirm-the-state-of-microsoft-defender-antivirus"></a>Cómo confirmar el estado de Antivirus de Microsoft Defender

Puede usar uno de varios métodos para confirmar el estado de Antivirus de Microsoft Defender, como se describe en la tabla siguiente:

 | Método | Procedure | 
 |:---|:---| 
 | Aplicación Seguridad de Windows |  1. En un dispositivo Windows, abra la aplicación Seguridad de Windows.<br/>2. Seleccione **Virus & protección contra amenazas**.<br/>3. En **Quién me protege?** seleccione **Administrar proveedores**.<br/>4. En la página **Proveedores de seguridad**, en **Antivirus**, debería ver **que Antivirus de Microsoft Defender está activado**. | 
 | Administrador de tareas |  1. En un dispositivo Windows, abra la aplicación Administrador de tareas.<br/>2. Seleccione la pestaña **Detalles** .<br/>3. Busque **MsMpEng.exe** en la lista. | 
 | Windows PowerShell <br/> (Para confirmar que Antivirus de Microsoft Defender se está ejecutando) |  1. En un dispositivo Windows, abra Windows PowerShell. <br/>2. Ejecute el siguiente cmdlet de PowerShell: `Get-Process`.<br/>3. Revise los resultados. Debería ver **MsMpEng.exe** si Antivirus de Microsoft Defender está habilitado. | 
 | Windows PowerShell <br/>(Para confirmar que la protección antivirus está en su lugar) |  Puede usar el [cmdlet De PowerShell Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).<br/>1. En un dispositivo Windows, abra Windows PowerShell.<br/>2. Ejecute el siguiente cmdlet de PowerShell:<br/> \|Get-MpComputerStatus seleccionar AMRunningMode <br/>3. Revise los resultados. Debería ver El **modo de bloque** **normal**, **pasivo** o EDR si Antivirus de Microsoft Defender está habilitado en el punto de conexión.  | 

## <a name="more-details-about-microsoft-defender-antivirus-states"></a>Más detalles sobre los estados de Antivirus de Microsoft Defender

En la tabla de esta sección se describen varios estados que puede ver con Antivirus de Microsoft Defender.

 |  Estado  |  Qué ocurre  | 
 |:---|:---| 
 |  Modo activo  |  En el modo activo, Antivirus de Microsoft Defender se usa como aplicación antivirus en el equipo. Configuración que se configuran mediante Configuration Manager, directiva de grupo, Microsoft Intune u otros productos de administración se aplicarán. Los archivos se examinan, se corrigen las amenazas y se notifica información de detección en la herramienta de configuración (como Configuration Manager o la aplicación de Antivirus de Microsoft Defender en el propio punto de conexión).  | 
 |  Modo pasivo <br/><br/> o bien <br/><br/> modo de bloque de EDR |  En el modo pasivo, Antivirus de Microsoft Defender no se usa como aplicación antivirus y las amenazas *no* se corrigen mediante Antivirus de Microsoft Defender. <br/><br/>Sin embargo, las amenazas se pueden corregir mediante la [detección y respuesta de puntos de conexión (EDR) en modo de bloque](edr-in-block-mode.md) cuando se ejecutan en EDR modo de bloque. <br/><br/> Los archivos se examinan por EDR y se proporcionan informes para las detecciones de amenazas que se comparten con el servicio Defender para punto de conexión. Es posible que vea alertas que muestran Antivirus de Microsoft Defender como origen, incluso cuando Antivirus de Microsoft Defender está en modo pasivo. <br/><br/> Cuando Antivirus de Microsoft Defender está en modo pasivo, todavía puede [administrar las actualizaciones de Antivirus de Microsoft Defender](manage-updates-baselines-microsoft-defender-antivirus.md); sin embargo, no se puede mover Antivirus de Microsoft Defender  en modo activo si los dispositivos tienen un producto antivirus que no es de Microsoft que proporciona protección en tiempo real contra malware. <br/><br/> Para una eficacia óptima de detección y defensa por capas de seguridad, asegúrese de obtener las actualizaciones antivirus y antimalware, incluso si Antivirus de Microsoft Defender se ejecuta en modo pasivo. Consulte [Administración de actualizaciones Antivirus de Microsoft Defender y aplicación de líneas base](manage-updates-baselines-microsoft-defender-antivirus.md). <br/><br/> Tenga en cuenta que el modo pasivo solo se admite en Windows Server 2012 R2 & 2016 cuando la máquina se incorpora mediante la [solución moderna y unificada](/microsoft-365/security/defender-endpoint/configure-server-endpoints).  | 
 |  Deshabilitado <br/><br/> o bien <br/><br/> Desinstalado  |  Cuando se deshabilita o desinstala, Antivirus de Microsoft Defender no se usa como aplicación antivirus. Los archivos no se examinan y las amenazas no se corrigen. <br/><br/> No se recomienda deshabilitar o desinstalar Antivirus de Microsoft Defender en general; si es posible, mantenga Antivirus de Microsoft Defender en modo pasivo si usa una solución antimalware o antivirus que no sea de Microsoft. <br/><br/> En los casos en los que Antivirus de Microsoft Defender se deshabilita automáticamente, se puede volver a habilitar automáticamente si el producto antivirus o antimalware que no es de Microsoft expira o deja de proporcionar protección en tiempo real contra virus, malware u otras amenazas. La habilitación automática de Antivirus de Microsoft Defender ayuda a garantizar que se mantenga la protección antivirus en los puntos de conexión. <br/><br/> También puede usar el [examen periódico limitado](limited-periodic-scanning-microsoft-defender-antivirus.md), que funciona con el motor de Antivirus de Microsoft Defender para comprobar periódicamente si usa una aplicación antivirus que no es de Microsoft.  | 

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

- [Antivirus de Microsoft Defender en clientes Windows](microsoft-defender-antivirus-in-windows-10.md)
- [EDR en modo bloqueo](edr-in-block-mode.md)
- [Obtenga más información sobre la prevención de pérdida de datos en punto de conexión](/microsoft-365/compliance/endpoint-dlp-learn-about)
