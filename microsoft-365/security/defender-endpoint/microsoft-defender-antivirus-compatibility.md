---
title: Antivirus de Microsoft Defender compatibilidad con otros productos de seguridad
description: Obtenga información Antivirus de Microsoft Defender con otros productos de seguridad y los sistemas operativos.
keywords: windows Defender, defender para el punto de conexión, la próxima generación, antivirus, compatibilidad, modo pasivo
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: mkaminska, pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 08/11/2021
ms.openlocfilehash: be816488ebe930da2f757ed192a12d81c0a222ef
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213607"
---
# <a name="microsoft-defender-antivirus-compatibility-with-other-security-products"></a>Antivirus de Microsoft Defender compatibilidad con otros productos de seguridad

**Se aplica a:**

- Antivirus de Microsoft Defender
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)


Antivirus de Microsoft Defender se instala automáticamente en puntos de conexión que ejecutan las siguientes versiones de Windows:

- Windows 10 o posterior
- Windows Server 2016
- Windows Servidor, versión 1803 o posterior
- Windows Server 2019

¿Qué sucede cuando se usa otra solución antivirus o antimalware que no sea de Microsoft? ¿Puede ejecutar Antivirus de Microsoft Defender junto con otro producto antivirus? Las respuestas dependen de varios factores, como el sistema operativo y si usa [Microsoft Defender para](microsoft-defender-endpoint.md) Endpoint (Defender para endpoint) junto con la protección antivirus.

En este artículo se describe lo que sucede con Antivirus de Microsoft Defender y una solución antivirus o antimalware que no es de Microsoft, con o sin Defender for Endpoint.

## <a name="antivirus-protection-without-defender-for-endpoint"></a>Protección antivirus sin Defender para endpoint

En esta sección se describe lo que sucede con Antivirus de Microsoft Defender antivirus o antimalware de Microsoft en los puntos de conexión que no están incorporados a Defender for Endpoint. En la tabla siguiente se resume lo que se debe esperar:

<br>

****

|Versión de Windows|Solución antivirus/antimalware principal|Antivirus de Microsoft Defender estado|
|---|---|---|---|
|Windows 10|Antivirus de Microsoft Defender|Modo activo|
|Windows 10|Una solución antivirus o antimalware que no es de Microsoft|Modo deshabilitado (sucede automáticamente)|
|Windows Server 2016 <p> Windows Servidor, versión 1803 o posterior <p> Windows Server 2019|Antivirus de Microsoft Defender|Modo activo|
|Windows Server 2016 <p> Windows Servidor, versión 1803 o posterior <p> Windows Server 2019|Una solución antivirus o antimalware que no es de Microsoft|Deshabilitado (establecido manualmente) <sup> [[1](#fn1)]<sup></sup>|

(<a id="fn1">1</a>) En Windows Server, si está ejecutando un producto antivirus que no es de Microsoft, puede deshabilitar Antivirus de Microsoft Defender mediante la directiva de grupo para desactivar Antivirus de Microsoft Defender o mediante la clave del Registro [DisableAntiSpyware.](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) Para usar la clave del Registro, vaya `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` a y establezca o cree una entrada DWORD denominada `DisableAntiSpyware` . Establezca su valor en (que establece el valor de la clave del Registro `1` en *true)* y seleccione **Hexadecimal** para su base.

> [!TIP]
> Consulte [Antivirus de Microsoft Defender en Windows Server](microsoft-defender-antivirus-on-windows-server.md) para obtener información sobre las principales diferencias y opciones de administración para Windows server. En Windows Server 2016, es posible que *vea* Antivirus de Windows Defender en lugar de *Antivirus de Microsoft Defender*.

## <a name="antivirus-protection-with-defender-for-endpoint"></a>Protección antivirus con Defender para endpoint

Si su organización usa una solución antivirus o antimalware que no sea de Microsoft junto con Defender for Endpoint, Antivirus de Microsoft Defender puede, según el sistema operativo, ejecutarse en modo pasivo.

<br>

****

|Versión de Windows|Solución antivirus/antimalware principal|Antivirus de Microsoft Defender estado|
|---|---|---|---|
|Windows 10 o posterior|Antivirus de Microsoft Defender|Modo activo|
|Windows 10 o posterior|Una solución antivirus o antimalware que no es de Microsoft|Modo pasivo (sucede automáticamente)|
|Windows Server 2016 <p> Windows Servidor, versión 1803 o posterior <p> Windows Server 2019|Antivirus de Microsoft Defender|Modo activo|
|Windows Servidor, versión 1803 o posterior <p> Windows Server 2019|Una solución antivirus o antimalware que no es de Microsoft|Modo pasivo (configurado manualmente) <sup> [[2](#fn2)]<sup></sup>|
|Windows Server 2016|Una solución antivirus o antimalware que no es de Microsoft|Deshabilitado (establecido manualmente) <sup> [[3](#fn3)]<sup>|

(<a id="fn2">2</a>) En Windows Server, versión 1803 o posterior, o Windows Server 2019, cuando instale un producto antivirus que no sea de Microsoft, establezca Antivirus de Microsoft Defender en modo pasivo manualmente. Puede usar la clave del Registro **ForceDefenderPassiveMode** para realizar esta tarea. Para usar la clave del Registro, vaya `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` a y establezca o cree una entrada DWORD denominada `ForceDefenderPassiveMode` . Establezca su valor en (que establece el valor de la clave del Registro `1` en *true)* y seleccione **Hexadecimal** para su base. Para obtener más información, vea [Passive mode and Windows Server](microsoft-defender-antivirus-on-windows-server.md#passive-mode-and-windows-server).

(<a id="fn3">3</a>) En Windows Server 2016, puede deshabilitar Antivirus de Microsoft Defender mediante la directiva de grupo para desactivar Antivirus de Windows Defender o mediante la clave del Registro [DisableAntiSpyware.](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) Para usar la clave del Registro, vaya `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` a y establezca o cree una entrada DWORD denominada `DisableAntiSpyware` . Establezca su valor en (que establece el valor de la clave del Registro `1` en *true)* y seleccione **Hexadecimal** para su base.

> [!TIP]
> Consulte [Antivirus de Microsoft Defender en Windows Server](microsoft-defender-antivirus-on-windows-server.md) para obtener información sobre las principales diferencias y opciones de administración para Windows server. En Windows Server 2016, es posible que *vea* Antivirus de Windows Defender en lugar de *Antivirus de Microsoft Defender*.

### <a name="why-run-microsoft-defender-antivirus-in-passive-mode"></a>¿Por qué Antivirus de Microsoft Defender en modo pasivo?

Defender for Endpoint incluye funcionalidades que amplían aún más la protección antivirus que está instalada en el punto de conexión. Puede beneficiarse de la ejecución de Antivirus de Microsoft Defender junto con otra solución antivirus.

Por ejemplo, la detección y respuesta de puntos de conexión [(EDR)](edr-in-block-mode.md) en modo de bloqueo proporciona protección adicional contra artefactos malintencionados incluso si Antivirus de Microsoft Defender no es el producto antivirus principal. Estas funcionalidades Antivirus de Microsoft Defender que se instalen y se ejecuten en modo pasivo o en modo activo.

### <a name="requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode"></a>Requisitos para Antivirus de Microsoft Defender ejecutar en modo pasivo

Para que Antivirus de Microsoft Defender en modo pasivo, los extremos deben cumplir los siguientes requisitos:

- Sistema operativo: Windows 10 o posterior; Windows Servidor, versión 1803 o posterior; o Windows Server 2019
- Antivirus de Microsoft Defender debe instalarse
- Otro producto antivirus o antimalware que no sea de Microsoft debe instalarse y usarse como solución antivirus principal
- Los puntos de conexión deben incorporarse a Defender for Endpoint

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>Cómo Antivirus de Microsoft Defender afecta a la funcionalidad de Defender for Endpoint

Defender for Endpoint afecta a si Antivirus de Microsoft Defender puede ejecutarse en modo pasivo. Antivirus de Microsoft Defender puede afectar a ciertas funcionalidades en Defender para endpoint, también. Por ejemplo, la protección en tiempo real funciona cuando Antivirus de Microsoft Defender está en modo activo o pasivo, pero no cuando Antivirus de Microsoft Defender deshabilita o desinstala.

En la tabla de esta sección se resumen las características y capacidades que funcionan activamente o no, según si Antivirus de Microsoft Defender está en modo activo, en modo pasivo o deshabilitado o desinstalado.

> [!IMPORTANT]
> La tabla siguiente está diseñada para ser solo informativo. No desactive las funcionalidades, como la protección en tiempo real, la protección entregada en la nube o el examen periódico limitado si usa Antivirus de Microsoft Defender en modo pasivo, o si usa [EDR](edr-in-block-mode.md)en modo de bloqueo, que funciona en segundo plano para detectar y corregir artefactos malintencionados que se detectaron después de la infracción.

<br>

****

|Protection|Antivirus de Microsoft Defender <p> Modo activo|Antivirus de Microsoft Defender <p> Modo pasivo|Antivirus de Microsoft Defender <p> Deshabilitado o desinstalado|[EDR en modo bloqueo](edr-in-block-mode.md)|
|---|---|---|---|---|
|[Protección en tiempo real y](configure-real-time-protection-microsoft-defender-antivirus.md) protección entregada en la [nube](enable-cloud-protection-microsoft-defender-antivirus.md)|Sí|No <sup> [[5](#fn5)]<sup>|No|No|
|[Disponibilidad limitada de análisis periódico](limited-periodic-scanning-microsoft-defender-antivirus.md)|No|No|Sí|No|
|[Información de detección y detección de archivos](review-scan-results-microsoft-defender-antivirus.md)|Sí|Sí|No|Sí|
|[Corrección de amenazas](configure-remediation-microsoft-defender-antivirus.md)|Sí|Vea la <sup> nota [[6](#fn6)]<sup>|No|Sí|
|[Actualizaciones de inteligencia de seguridad](manage-updates-baselines-microsoft-defender-antivirus.md)|Sí|Sí|No|Sí|
||||||

(<a id="fn5">5</a>) En general, cuando Antivirus de Microsoft Defender está en modo pasivo, la protección en tiempo real no proporciona ningún bloqueo ni aplicación, aunque esté habilitada y en modo pasivo.

(<a id="fn6">6</a>) Cuando Antivirus de Microsoft Defender está en modo pasivo, las características de corrección de amenazas solo están activas durante los exámenes programados o a petición.

> [!NOTE]
> [Microsoft 365 protección de](/microsoft-365/compliance/endpoint-dlp-learn-about) prevención de pérdida de datos del punto de conexión sigue funcionando con normalidad cuando Antivirus de Microsoft Defender está en modo activo o pasivo.

## <a name="important-notes"></a>Notas importantes

- No deshabilite, detenga ni modifique ninguno de los servicios asociados que usan Antivirus de Microsoft Defender, Defender para endpoint o la aplicación Seguridad de Windows usuario. Esta recomendación incluye los servicios y procesos *wscsvc*, *SecurityHealthService*, *MsSense*, *Sense*, *WinDefend* o *MsMpEng.* La modificación manual de estos servicios puede provocar una inestabilidad grave en los dispositivos y puede hacer que la red sea vulnerable. Deshabilitar, detener o modificar esos servicios también puede causar problemas al usar soluciones antivirus que no son de Microsoft y cómo se muestra su información en la [Seguridad de Windows aplicación](microsoft-defender-security-center-antivirus.md).

- En Defender para endpoint, activa EDR en modo de bloqueo, incluso si Antivirus de Microsoft Defender no es la solución antivirus principal. EDR en modo de bloqueo detecta y corrige elementos malintencionados que se encuentran en el dispositivo (después de la infracción). Para obtener más información, [vea EDR en modo de bloque](edr-in-block-mode.md).

## <a name="how-to-confirm-the-state-of-microsoft-defender-antivirus"></a>Cómo confirmar el estado de Antivirus de Microsoft Defender

Puede usar uno de varios métodos para confirmar el estado de Antivirus de Microsoft Defender, tal como se describe en la tabla siguiente:

<br>

****

|Método|Procedure|
|---|---|
|Seguridad de Windows app|<ol><li>En un Windows, abre la aplicación Seguridad de Windows usuario.</li><li>Seleccione **Protección antivirus y contra amenazas**.</li><li>En **Quién's protecting me?** select **Manage providers**.</li><li>En la **página Proveedores de** seguridad, en **Antivirus,** debería ver Antivirus de Microsoft Defender **está activado**.</li></ol>|
|Administrador de tareas|<ol><li>En un Windows, abre la aplicación Administrador de tareas.</li><li>Seleccione la **pestaña** Detalles.</li><li>Busque **MsMpEng.exe** en la lista.</li></ol>|
|Windows PowerShell <p> (Para confirmar que Antivirus de Microsoft Defender se está ejecutando)|<ol><li>En un dispositivo Windows, abra Windows PowerShell</li><li>Ejecute el siguiente cmdlet de PowerShell: `Get-Process` .</li><li>Revisar los resultados. Debería ver **MsMpEng.exe** si Antivirus de Microsoft Defender está habilitado.</li></ol>|
|Windows PowerShell <p> (Para confirmar que la protección antivirus está en su lugar)|Puede usar el [cmdlet de PowerShell Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus). <ol><li>En un dispositivo Windows, abra Windows PowerShell.</li><li>Ejecute el siguiente cmdlet de PowerShell: `Get-MpComputerStatus|select AMRunningMode` .</li><li>Revisar los resultados. Debería ver **Normal** o **Pasivo** si Antivirus de Microsoft Defender está habilitado en el punto de conexión.</li></ol>|
|Símbolo del sistema|<ol><li>En un dispositivo Windows, abra símbolo del sistema.</li><li>Escriba `sc query windefend` y, a continuación, presione ENTRAR.</li><li>Revise los resultados para confirmar que Antivirus de Microsoft Defender se está ejecutando en modo pasivo.</li></ol>|
|||

## <a name="more-details-about-microsoft-defender-antivirus-states"></a>Más detalles sobre Antivirus de Microsoft Defender estados

En la tabla de esta sección se describen varios estados que puede ver con Antivirus de Microsoft Defender.

<br>

****

|Antivirus de Microsoft Defender estado|Qué ocurre|
|---|---|
|Modo activo|En modo activo, Antivirus de Microsoft Defender se usa como la aplicación antivirus en el equipo. Configuración que se configuran mediante Configuration Manager, directiva de grupo, Microsoft Intune u otros productos de administración se aplicarán. Los archivos se examinan, las amenazas se corrigen y la información de detección se notifica en la herramienta de configuración (como Configuration Manager o la aplicación Antivirus de Microsoft Defender en el propio punto de conexión).|
|Modo pasivo|En modo pasivo, Antivirus de Microsoft Defender no se usa como la  aplicación antivirus y las amenazas no se corrigen Antivirus de Microsoft Defender. Sin embargo, la detección y respuesta de puntos de conexión [(EDR)](edr-in-block-mode.md)pueden corregir las amenazas en modo de bloqueo. <p> Los archivos se examinan y se proporcionan informes para las detecciones de amenazas que se comparten con el servicio Defender for Endpoint. Es posible que vea alertas en [el](microsoft-defender-security-center.md) centro de seguridad Antivirus de Microsoft Defender como origen, incluso cuando Antivirus de Microsoft Defender está en modo pasivo. <p> Cuando Antivirus de Microsoft Defender está en modo pasivo, todavía puede [administrar actualizaciones](manage-updates-baselines-microsoft-defender-antivirus.md)para Antivirus de Microsoft Defender ; sin embargo, no puedes mover Antivirus de Microsoft Defender al modo activo si tus dispositivos tienen un producto antivirus que no es de Microsoft que proporciona protección en tiempo real contra malware. <p> Para obtener una eficacia óptima de defensa y detección en capas de seguridad, asegúrese de obtener las actualizaciones de antivirus y antimwalware, incluso si Antivirus de Microsoft Defender se está ejecutando en modo pasivo. Consulte [Manage Antivirus de Microsoft Defender updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md). <p> **NOTA:** El modo pasivo no se admite en Windows Server 2016.|
|Deshabilitado <p> o <p> Desinstalado|Cuando se deshabilita o desinstala, Antivirus de Microsoft Defender no se usa como la aplicación antivirus. Los archivos no se examinan y las amenazas no se corrigen. <p> No se recomienda deshabilitar o desinstalar Antivirus de Microsoft Defender en general; si es posible, Antivirus de Microsoft Defender en modo pasivo si usa una solución antivirus o antimalware que no sea de Microsoft. <p> En los casos en que Antivirus de Microsoft Defender se deshabilita automáticamente, se puede volver a habilitar automáticamente si el producto antivirus o antimalware que no es de Microsoft expira o deja de proporcionar protección en tiempo real contra virus, malware u otras amenazas. La habilitación automática de Antivirus de Microsoft Defender ayuda a garantizar que la protección antivirus se mantenga en los puntos de conexión. <p> También puedes usar [el](limited-periodic-scanning-microsoft-defender-antivirus.md)examen periódico limitado, que funciona con el motor de Antivirus de Microsoft Defender para comprobar periódicamente si hay amenazas si usas una aplicación antivirus que no sea de Microsoft.|
|||

## <a name="see-also"></a>Vea también

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Antivirus de Microsoft Defender en Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [EDR en modo bloqueo](edr-in-block-mode.md)
- [Obtenga más información sobre la prevención de pérdida de datos de Microsoft 365 de punto de conexión](/microsoft-365/compliance/endpoint-dlp-learn-about)
