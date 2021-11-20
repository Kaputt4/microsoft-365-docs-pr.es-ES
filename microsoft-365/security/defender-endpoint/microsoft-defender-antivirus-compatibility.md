---
title: Antivirus de Microsoft Defender compatibilidad con otros productos de seguridad
description: Obtenga información Antivirus de Microsoft Defender con otros productos de seguridad y los sistemas operativos.
keywords: windows Defender, defender para el punto de conexión, la próxima generación, antivirus, compatibilidad, modo pasivo
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
ms.date: 10/26/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: 1624d30eb7e8112e2e8739c6d7cbfdb208f8816e
ms.sourcegitcommit: 07405a81513d1c63071a128b9d5070d3a3bfe1cd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2021
ms.locfileid: "61122590"
---
# <a name="microsoft-defender-antivirus-compatibility-with-other-security-products"></a>Antivirus de Microsoft Defender compatibilidad con otros productos de seguridad

**Se aplica a:**

- Antivirus de Microsoft Defender
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

Antivirus de Microsoft Defender se instala automáticamente en puntos de conexión que ejecutan las siguientes versiones de Windows:

- Windows 10 o posterior
- Windows Server 2022
- Windows Server 2019
- Windows server, versión 1803 o posterior
- Windows Server 2016

¿Qué sucede cuando se usa otra solución antivirus o antimalware que no sea de Microsoft? ¿Puede ejecutar Antivirus de Microsoft Defender junto con otro producto antivirus? Las respuestas dependen de varios factores, como el sistema operativo y si usa [Microsoft Defender para](microsoft-defender-endpoint.md) Endpoint (Defender para endpoint) junto con la protección antivirus.

En este artículo se describe lo que sucede con Antivirus de Microsoft Defender y una solución antivirus o antimalware que no es de Microsoft, con o sin Defender for Endpoint.

> [!IMPORTANT]
> Antivirus de Microsoft Defender solo está disponible en dispositivos que ejecutan Windows 10 y 11, Windows Server 2022, Windows Server 2019, Windows Server, versión 1803 o posterior, Windows Server 2016 y Windows Server 2012 R2.
>
> En Windows 8.1, la protección antivirus de extremo de nivel de empresa se [ofrece System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10)), que se administra a través de Microsoft Endpoint Configuration Manager.
>
> Windows Defender también se ofrece para dispositivos de consumidores en [Windows 8.1](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender), aunque Windows Defender no proporciona administración de nivel de empresa.

## <a name="antivirus-protection-without-defender-for-endpoint"></a>Protección antivirus sin Defender para endpoint

En esta sección se describe lo que sucede con Antivirus de Microsoft Defender antivirus o antimalware de Microsoft en los puntos de conexión que no están incorporados a Defender for Endpoint. En la tabla siguiente se resume lo que se debe esperar:

<br/><br/>

|Versión de Windows|Solución antivirus/antimalware principal|Antivirus de Microsoft Defender estado|
|---|---|---|
|Windows 10 <p> Windows 11|Antivirus de Microsoft Defender|Modo activo|
|Windows 10 <p> Windows 11|Una solución antivirus o antimalware que no es de Microsoft|Modo deshabilitado (sucede automáticamente)|
|Windows Server 2022 <p> Windows Server 2019<p> Windows server, versión 1803 o posterior <p> Windows Server 2016 |Antivirus de Microsoft Defender|Modo activo|
|Windows Server 2022<p>Windows Server 2019<p>Windows server, versión 1803 o posterior <p> Windows Server 2016 <p>  |Una solución antivirus o antimalware que no es de Microsoft|Deshabilitado (establecido manualmente) <sup>[[1](#fn1)]</sup>|

(<a id="fn1">1</a>) En Windows Server, si está ejecutando un producto antivirus que no es de Microsoft, puede deshabilitar Antivirus de Microsoft Defender mediante la directiva de grupo para desactivar Antivirus de Microsoft Defender o mediante la clave del Registro [DisableAntiSpyware.](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) Para usar la clave del Registro, vaya `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` a y establezca o cree una entrada DWORD denominada `DisableAntiSpyware` . Establezca su valor en (que establece el valor de la clave del Registro `1` en *true)* y seleccione **Hexadecimal** para su base.

> [!TIP]
> En Windows Server 2016, es posible que *vea* Antivirus de Windows Defender en lugar de *Antivirus de Microsoft Defender*.

## <a name="microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions"></a>Antivirus de Microsoft Defender antivirus y soluciones antimalware que no son de Microsoft

En la tabla siguiente se resume lo que sucede con Antivirus de Microsoft Defender soluciones antivirus o antimalware que no son de Microsoft se usan juntas o sin Microsoft Defender para endpoint. 

| Versión de Windows   | Solución antivirus/antimalware  | Incorporado a <br/> ¿Defender para endpoint? | Antivirus de Microsoft Defender estado     |
|------|------|-------|-------|
| Windows 10 <p> Windows 11| Antivirus de Microsoft Defender | Sí  | Modo activo | 
| Windows 10 <p> Windows 11 | Antivirus de Microsoft Defender | No   | Modo activo |
| Windows 10 <p> Windows 11  | Una solución antivirus o antimalware que no es de Microsoft | Sí  | Modo pasivo (automáticamente) |
| Windows 10 <p> Windows 11  | Una solución antivirus o antimalware que no es de Microsoft | No   | Modo deshabilitado (automáticamente)    |
| Windows Server 2019 <p>Windows server, versión 1803 o posterior  | Antivirus de Microsoft Defender  | Sí |         Modo activo  |
| Windows Server 2019 <p> Windows server, versión 1803 o posterior   | Antivirus de Microsoft Defender | No  | Modo activo |
| Windows Server 2019 <p> Windows server, versión 1803 o posterior  | Una solución antivirus o antimalware que no es de Microsoft | Sí  | Antivirus de Microsoft Defender debe establecerse en modo pasivo (manualmente) <sup> [[2](#fn2)]<sup>  | 
| Windows Server 2019 <p> Windows server, versión 1803 o posterior  | Una solución antivirus o antimalware que no es de Microsoft | No  | Antivirus de Microsoft Defender debe deshabilitarse (manualmente) <sup> [[3](#fn3)]<sup></sup>  |
| Windows Server 2016 <br><br> Windows Server 2012 R2   | Antivirus de Microsoft Defender | Sí | Modo activo |
|Windows Server 2016 <br><br> Windows Server 2012 R2  | Antivirus de Microsoft Defender | No | Modo activo |
| Windows Server 2016 <br><br> Windows Server 2012 R2  | Una solución antivirus o antimalware que no es de Microsoft | Sí | Antivirus de Microsoft Defender debe establecerse en modo pasivo (manualmente) <sup> [[2](#fn2)]<sup> |
|Windows Server 2016 <br><br> Windows Server 2012 R2  | Una solución antivirus o antimalware que no es de Microsoft | No | Antivirus de Microsoft Defender debe deshabilitarse (manualmente) <sup> [[3](#fn3)]<sup> |

(<a id="fn2">2</a>) En Windows Server 2019, Windows Server, versión 1803 o posterior, Windows Server 2016 o Windows Server 2012 R2, Antivirus de Microsoft Defender no entra en modo pasivo automáticamente al instalar un producto antivirus que no es de Microsoft. En esos casos, establezca Antivirus de Microsoft Defender en modo pasivo para evitar problemas causados por tener varios productos antivirus instalados en un servidor. Puede establecer el Antivirus de Microsoft Defender en modo pasivo mediante PowerShell, directiva de grupo o una clave del Registro. 

  Puede establecer el Antivirus de Microsoft Defender en modo pasivo estableciendo la siguiente clave del Registro:
- Ruta de acceso: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Nombre: `ForceDefenderPassiveMode`
- Tipo: `REG_DWORD`
- Valor: `1`

 > [!NOTE]
 > Para que el modo pasivo funcione en puntos de conexión que ejecutan Windows Server 2016 y Windows Server 2012 R2, estos extremos deben incorporarse con las instrucciones de [Onboard Windows servers](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016). 

(<a id="fn3">3</a>) En Windows Server 2016 o Windows Server 2012 R2, si usa un producto antivirus que no es de Microsoft y ese extremo no está incorporado a Microsoft Defender para endpoint, deshabilite o desinstale Antivirus de Microsoft Defender  manualmente para evitar problemas causados por tener varios productos antivirus instalados en un servidor.

> [!TIP]
> En Windows Server 2016, es posible que *vea* Antivirus de Windows Defender en lugar de *Antivirus de Microsoft Defender*.

> [!IMPORTANT]
> Antivirus de Microsoft Defender solo está disponible en dispositivos que ejecutan Windows 10 y 11, Windows Server 2022, Windows Server 2019, Windows Server, versión 1803 o posterior, Windows Server 2016 y Windows Server 2012 R2.
>
> En Windows 8.1, la protección antivirus de extremo de nivel de empresa se [ofrece System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10)), que se administra a través de Microsoft Endpoint Configuration Manager.
>
> Windows Defender también se ofrece para dispositivos de consumidores en [Windows 8.1](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender), aunque Windows Defender no proporciona administración de nivel de empresa.

Defender for Endpoint incluye funcionalidades que amplían aún más la protección antivirus que está instalada en el punto de conexión. Puede beneficiarse de la ejecución de Antivirus de Microsoft Defender junto con otra solución antivirus.

Por ejemplo, la detección y respuesta de puntos de conexión [(EDR)](edr-in-block-mode.md) en modo de bloqueo proporciona protección adicional contra artefactos malintencionados incluso si Antivirus de Microsoft Defender no es el producto antivirus principal. Estas funcionalidades Antivirus de Microsoft Defender que se instalen y se ejecuten en modo pasivo o en modo activo.

### <a name="requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode"></a>Requisitos para Antivirus de Microsoft Defender ejecutar en modo pasivo

Para que Antivirus de Microsoft Defender en modo pasivo, los extremos deben cumplir los siguientes requisitos:

- Sistema operativo: Windows 10 o posterior; Windows Server 2022, Windows Server 2019 o Windows Server, versión 1803 o posterior
- Antivirus de Microsoft Defender debe instalarse
- Otro producto antivirus o antimalware que no sea de Microsoft debe instalarse y usarse como solución antivirus principal
- Los puntos de conexión deben incorporarse a Defender for Endpoint

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>Cómo Antivirus de Microsoft Defender afecta a la funcionalidad de Defender for Endpoint

Defender for Endpoint afecta a si Antivirus de Microsoft Defender puede ejecutarse en modo pasivo. Antivirus de Microsoft Defender puede afectar a ciertas funcionalidades en Defender para endpoint, también. Por ejemplo, la protección en tiempo real funciona cuando Antivirus de Microsoft Defender está en modo activo o pasivo, pero no cuando Antivirus de Microsoft Defender deshabilita o desinstala.

En la tabla de esta sección se resumen las características y capacidades que funcionan activamente o no, según si Antivirus de Microsoft Defender está en modo activo, en modo pasivo o deshabilitado o desinstalado.

> [!IMPORTANT]
> La tabla siguiente está diseñada para ser solo informativo. No desactive las funcionalidades, como la protección en tiempo real, la protección entregada en la nube o el examen periódico limitado si usa Antivirus de Microsoft Defender en modo pasivo, o si usa [EDR](edr-in-block-mode.md)en modo de bloqueo, que funciona en segundo plano para detectar y corregir artefactos malintencionados que se detectaron después de la infracción.

<br/><br/>

 | Protección | Antivirus de Microsoft Defender <br/>(*Modo activo*) | Antivirus de Microsoft Defender <br/>(*Modo pasivo*) | Antivirus de Microsoft Defender <br/>(*Deshabilitado o desinstalado*) | [EDR en modo bloqueo](edr-in-block-mode.md) | 
 |---|---|---|---|---| 
 | [Protección en tiempo real](configure-real-time-protection-microsoft-defender-antivirus.md) | Sí | No <sup>[[4](#fn4)]</sup> | No | No | 
 | [Protección entregada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md) | Sí | No  | No | No | 
 | [Protección de red](network-protection.md)  | Sí | No | No | No | 
 | [Reglas de la reducción de la superficie expuesta a ataques](attack-surface-reduction.md)  | Sí | No | No  | No | 
 | [Disponibilidad limitada de análisis periódico](limited-periodic-scanning-microsoft-defender-antivirus.md) | No | No | Sí | No | 
 | [Información de detección y detección de archivos](review-scan-results-microsoft-defender-antivirus.md) | Sí | Sí | No | Sí | 
 | [Corrección de amenazas](configure-remediation-microsoft-defender-antivirus.md) | Sí | Vea la <sup>nota [[5](#fn5)]</sup> | No | Sí | 
 | [Actualizaciones de inteligencia de seguridad](manage-updates-baselines-microsoft-defender-antivirus.md) | Sí | Sí | No | Sí | 

(<a id="fn4">4</a>) En general, cuando Antivirus de Microsoft Defender está en modo pasivo, la protección en tiempo real no proporciona ningún bloqueo ni aplicación, aunque esté habilitada y en modo pasivo.

(<a id="fn5">5</a>) Cuando Antivirus de Microsoft Defender está en modo pasivo, las características de corrección de amenazas solo están activas durante los exámenes programados o a petición.

> [!NOTE]
> [Microsoft 365 protección de](/microsoft-365/compliance/endpoint-dlp-learn-about) prevención de pérdida de datos del punto de conexión sigue funcionando con normalidad cuando Antivirus de Microsoft Defender está en modo activo o pasivo.

## <a name="important-notes"></a>Notas importantes

- No deshabilite, detenga ni modifique ninguno de los servicios asociados que usan Antivirus de Microsoft Defender, Defender para endpoint o la aplicación Seguridad de Windows usuario. Esta recomendación incluye los servicios y procesos *wscsvc*, *SecurityHealthService*, *MsSense*, *Sense*, *WinDefend* o *MsMpEng.* La modificación manual de estos servicios puede provocar una inestabilidad grave en los dispositivos y puede hacer que la red sea vulnerable. Deshabilitar, detener o modificar esos servicios también puede causar problemas al usar soluciones antivirus que no son de Microsoft y cómo se muestra su información en la [Seguridad de Windows aplicación](microsoft-defender-security-center-antivirus.md).

- En Defender para endpoint, activa EDR en modo de bloqueo, incluso si Antivirus de Microsoft Defender no es la solución antivirus principal. EDR en modo de bloqueo detecta y corrige elementos malintencionados que se encuentran en el dispositivo (después de la infracción). Para obtener más información, [vea EDR en modo de bloque](edr-in-block-mode.md).

## <a name="how-to-confirm-the-state-of-microsoft-defender-antivirus"></a>Cómo confirmar el estado de Antivirus de Microsoft Defender

Puede usar uno de varios métodos para confirmar el estado de Antivirus de Microsoft Defender, tal como se describe en la tabla siguiente:

<br/><br/>

 | Método | Procedure | 
 |---|---| 
 | Seguridad de Windows app |  1. En un Windows, abra la aplicación Seguridad de Windows usuario.<br/>2. Seleccione **Virus & protección contra amenazas**.<br/>3. **¿Quién está protegiendo?** seleccione **Administrar proveedores**.<br/>4. En la página **Proveedores de** seguridad, en **Antivirus,** debería ver Antivirus de Microsoft Defender **está activado**. | 
 | Administrador de tareas |  1. En un dispositivo Windows, abra la aplicación Administrador de tareas.<br/>2. Seleccione la **pestaña** Detalles.<br/>3. Busque **MsMpEng.exe** en la lista. | 
 | Windows PowerShell <br/><br/> (Para confirmar que Antivirus de Microsoft Defender se está ejecutando) |  1. En un dispositivo Windows, abra Windows PowerShell. <br/>2. Ejecute el siguiente cmdlet de PowerShell: `Get-Process` .<br/>3. Revise los resultados. Debería ver **MsMpEng.exe** si Antivirus de Microsoft Defender está habilitado. | 
 | Windows PowerShell <br/><br/> (Para confirmar que la protección antivirus está en su lugar) |  Puede usar el [cmdlet de PowerShell Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus). <br/><br/>1. En un dispositivo Windows, abra Windows PowerShell.<br/>2. Ejecute el siguiente cmdlet de PowerShell: `Get-MpComputerStatus | select AMRunningMode` .<br/>3. Revise los resultados. Debería ver **Normal** o **Pasivo** si Antivirus de Microsoft Defender está habilitado en el punto de conexión.  | 
 | Símbolo del sistema |  1. En un dispositivo Windows, abra el símbolo del sistema.<br/>2. Escriba `sc query windefend` y, a continuación, presione ENTRAR.<br/>3. Revise los resultados para confirmar que Antivirus de Microsoft Defender se está ejecutando en modo pasivo.  | 

## <a name="more-details-about-microsoft-defender-antivirus-states"></a>Más detalles sobre Antivirus de Microsoft Defender estados

En la tabla de esta sección se describen varios estados que puede ver con Antivirus de Microsoft Defender.

<br/><br/>

 |  Estado  |  Qué ocurre  | 
 |---|---| 
 |  Modo activo  |  En modo activo, Antivirus de Microsoft Defender se usa como la aplicación antivirus en el equipo. Configuración que se configuran mediante Configuration Manager, directiva de grupo, Microsoft Intune u otros productos de administración se aplicarán. Los archivos se examinan, las amenazas se corrigen y la información de detección se notifica en la herramienta de configuración (como Configuration Manager o la aplicación Antivirus de Microsoft Defender en el propio punto de conexión).  | 
 |  Modo pasivo  |  En modo pasivo, Antivirus de Microsoft Defender no se usa como la  aplicación antivirus y las amenazas no se corrigen Antivirus de Microsoft Defender. Sin embargo, la detección y respuesta de puntos de conexión [(EDR)](edr-in-block-mode.md)pueden corregir las amenazas en modo de bloqueo. <br/><br/> Los archivos se examinan y se proporcionan informes para las detecciones de amenazas que se comparten con el servicio Defender for Endpoint. Es posible que veas alertas en [defender para](microsoft-defender-security-center.md) la nube mostrando Antivirus de Microsoft Defender como origen, incluso cuando Antivirus de Microsoft Defender está en modo pasivo. <br/><br/> Cuando Antivirus de Microsoft Defender está en modo pasivo, todavía puede administrar actualizaciones para [Antivirus de Microsoft Defender;](manage-updates-baselines-microsoft-defender-antivirus.md)sin embargo, no puede mover Antivirus de Microsoft Defender  en modo activo si los dispositivos tienen un producto antivirus que no es De Microsoft que proporciona protección en tiempo real contra malware. <br/><br/> Para obtener una eficacia óptima de defensa y detección en capas de seguridad, asegúrese de obtener las actualizaciones de antivirus y antimwalware, incluso si Antivirus de Microsoft Defender se está ejecutando en modo pasivo. Consulte [Manage Antivirus de Microsoft Defender updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md). <br/><br/> **NOTA:** El modo pasivo no se admite en Windows Server 2016.  | 
 |  Deshabilitado <br/><br/> o <br/><br/> Desinstalado  |  Cuando se deshabilita o desinstala, Antivirus de Microsoft Defender no se usa como la aplicación antivirus. Los archivos no se examinan y las amenazas no se corrigen. <br/><br/> No se recomienda deshabilitar o desinstalar Antivirus de Microsoft Defender en general; si es posible, mantenga Antivirus de Microsoft Defender en modo pasivo si usa una solución antivirus o antimalware que no sea de Microsoft. <br/><br/> En los casos en que Antivirus de Microsoft Defender se deshabilita automáticamente, se puede volver a habilitar automáticamente si el producto antivirus o antimalware que no es de Microsoft expira o deja de proporcionar protección en tiempo real contra virus, malware u otras amenazas. La habilitación automática de Antivirus de Microsoft Defender ayuda a garantizar que la protección antivirus se mantenga en los puntos de conexión. <br/><br/> También puedes usar [el](limited-periodic-scanning-microsoft-defender-antivirus.md)examen periódico limitado, que funciona con el motor de Antivirus de Microsoft Defender para comprobar periódicamente si hay amenazas si usas una aplicación antivirus que no sea de Microsoft.  | 


## <a name="see-also"></a>Vea también

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [EDR en modo bloqueo](edr-in-block-mode.md)
- [Obtenga más información sobre la prevención de pérdida de datos de Microsoft 365 de punto de conexión](/microsoft-365/compliance/endpoint-dlp-learn-about)
