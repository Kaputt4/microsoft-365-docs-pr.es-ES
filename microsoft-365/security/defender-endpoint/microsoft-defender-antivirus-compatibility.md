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
ms.reviewer: tewchen, pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 05/08/2021
ms.openlocfilehash: f03fab3f296f98b448693c6a5d0886f409201703
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288484"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Antivirus de Microsoft Defender compatibilidad

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

## <a name="summary"></a>Resumen

Antivirus de Microsoft Defender se habilita e instala automáticamente en puntos de conexión y dispositivos que se ejecutan Windows 10. Pero, ¿qué sucede cuando se usa otra solución antivirus o antimalware (que no es Microsoft) Depende de si usas [Microsoft Defender para Endpoint](microsoft-defender-endpoint.md) junto con la protección antivirus. En este artículo se describe lo que sucede con las soluciones antivirus/antimalware cuando los puntos de conexión están incorporados a Microsoft Defender para endpoint.

## <a name="keep-the-following-points-in-mind"></a>Tenga en cuenta los siguientes puntos

- En modo activo, Antivirus de Microsoft Defender se usa como la aplicación antivirus en el equipo. Se aplicará toda la configuración realizada con Configuration Manager, la directiva de grupo, Intune u otros productos de administración. Los archivos se examinan y se corrigen las amenazas, y la información de detección se notifica en la herramienta de configuración (como Configuration Manager o la aplicación Antivirus de Microsoft Defender en el propio equipo).

- En modo pasivo, Antivirus de Microsoft Defender no se usa como la aplicación antivirus y las amenazas no se corrigen Antivirus de Microsoft Defender. Los archivos se examinan y se proporcionan informes para las detecciones de amenazas que se comparten con el servicio Detección de puntos de conexión de Microsoft Defender. Es posible que vea alertas en [el](microsoft-defender-security-center.md) centro de seguridad Antivirus de Microsoft Defender como origen, incluso cuando Antivirus de Microsoft Defender está en modo pasivo.

- Cuando [EDR en modo](edr-in-block-mode.md) de bloqueo está activado y Antivirus de Microsoft Defender no es la solución antivirus principal, detectará y corregirá elementos malintencionados. EDR en modo de bloque requiere Antivirus de Microsoft Defender habilitarse en modo activo o en modo pasivo.

- Cuando se deshabilita, Antivirus de Microsoft Defender no se usa como la aplicación antivirus. Los archivos no se examinan y las amenazas no se corrigen. No se recomienda deshabilitar o desinstalar Antivirus de Microsoft Defender en general; si es posible, Antivirus de Microsoft Defender en modo pasivo si usa una solución antivirus o antimalware que no sea de Microsoft.

- Si está inscrito en Microsoft Defender para Endpoint y usa un producto antimalware de terceros, el modo pasivo está habilitado. El servicio requiere el uso compartido de información común Antivirus de Microsoft Defender servicio para supervisar correctamente los dispositivos y la red en busca de intentos de intrusión y ataques. Para obtener más información, [vea Antivirus de Microsoft Defender compatibilidad con Microsoft Defender para Endpoint](defender-compatibility.md). 

- Cuando Antivirus de Microsoft Defender está en modo pasivo, todavía puede [administrar actualizaciones](manage-updates-baselines-microsoft-defender-antivirus.md)para Antivirus de Microsoft Defender ; sin embargo, no puedes mover Antivirus de Microsoft Defender al modo activo si los dispositivos tienen un producto antivirus actualizado y que no es de Microsoft que proporciona protección en tiempo real contra malware. Para obtener una eficacia óptima de defensa y detección en capas de seguridad, asegúrese de actualizar la protección [de Antivirus de Microsoft Defender (actualización](manage-updates-baselines-microsoft-defender-antivirus.md) de inteligencia de seguridad, motor y plataforma) incluso si Antivirus de Microsoft Defender se está ejecutando en modo pasivo.

- Cuando Antivirus de Microsoft Defender se deshabilita automáticamente, se puede volver a habilitar automáticamente si la protección ofrecida por un producto antivirus que no es de Microsoft expira o deja de proporcionar protección en tiempo real contra virus, malware u otras amenazas. La habilitación automática ayuda a garantizar que la protección antivirus se mantenga en los dispositivos. También te permite habilitar el examen periódico [limitado,](limited-periodic-scanning-microsoft-defender-antivirus.md)que usa el motor de Antivirus de Microsoft Defender para comprobar periódicamente si hay amenazas además de la aplicación antivirus principal.

## <a name="microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions"></a>Antivirus de Microsoft Defender antivirus y soluciones antimalware que no son de Microsoft

En la tabla siguiente se resume lo que sucede con Antivirus de Microsoft Defender soluciones antivirus o antimalware que no son de Microsoft se usan juntas o sin Microsoft Defender para endpoint. 

| Versión de Windows   | Solución antivirus/antimalware  | Incorporado a <br/> ¿Defender para endpoint? | Antivirus de Microsoft Defender estado     |
|------|------|-------|-------|
| Windows 10  | Antivirus de Microsoft Defender | Sí  | Modo activo | 
| Windows 10  | Antivirus de Microsoft Defender | No   | Modo activo |
| Windows 10  | Una solución antivirus o antimalware que no es de Microsoft | Sí  | Modo pasivo (automáticamente) |
| Windows 10  | Una solución antivirus o antimalware que no es de Microsoft | No   | Modo deshabilitado (automáticamente)    |
| Windows Servidor, versión 1803 o posterior <p> Windows Server 2019 | Antivirus de Microsoft Defender  | Sí |         Modo activo  |
| Windows Servidor, versión 1803 o posterior <p> Windows Server 2019 | Antivirus de Microsoft Defender | No  | Modo activo |
| Windows Servidor, versión 1803 o posterior <p> Windows Server 2019 | Una solución antivirus o antimalware que no es de Microsoft | Sí  | Antivirus de Microsoft Defender debe establecerse en modo pasivo (manualmente) <sup> [[1](#fn1)]<sup>  | 
| Windows Servidor, versión 1803 o posterior <p> Windows Server 2019 | Una solución antivirus o antimalware que no es de Microsoft | No  | Antivirus de Microsoft Defender debe deshabilitarse (manualmente) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server 2016 | Antivirus de Microsoft Defender | Sí | Modo activo |
| Windows Server 2016 | Antivirus de Microsoft Defender | No | Modo activo |
| Windows Server 2016 | Una solución antivirus o antimalware que no es de Microsoft | Sí | Antivirus de Microsoft Defender debe deshabilitarse (manualmente) <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | Una solución antivirus o antimalware que no es de Microsoft | No | Antivirus de Microsoft Defender debe deshabilitarse (manualmente) <sup> [[2](#fn2)]<sup> |

(<a id="fn1">1</a>) En Windows Server, versión 1803 o posterior, o Windows Server 2019, Antivirus de Microsoft Defender no entra en modo pasivo automáticamente al instalar un producto antivirus que no sea de Microsoft. En esos casos, [establezca Antivirus de Microsoft Defender en modo pasivo](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) para evitar problemas causados por tener varios productos antivirus instalados en un servidor. Puede establecer el Antivirus de Microsoft Defender en modo pasivo mediante PowerShell, directiva de grupo o una clave del Registro.

Si usa Windows Server, versión 1803 o posterior, o Windows Server 2019, puede establecer Antivirus de Microsoft Defender en modo pasivo estableciendo la siguiente clave del Registro:
- Ruta de acceso: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Nombre: `ForceDefenderPassiveMode`
- Tipo: `REG_DWORD`
- Valor: `1`

> [!NOTE]
> El modo pasivo no se admite en Windows Server 2016. La clave del Registro se puede usar en Windows Server, versión 1803 o posterior, o Windows `ForceDefenderPassiveMode` Server 2019, pero no Windows Server 2016. 

(<a id="fn2">2</a>) En Windows Server 2016, si usa un producto antivirus que no es de Microsoft, no puede ejecutar Antivirus de Microsoft Defender en modo pasivo o en modo activo. En tales casos, [deshabilitar o desinstalar Antivirus de Microsoft Defender manualmente](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) para evitar problemas causados por tener varios productos antivirus instalados en un servidor.

Consulte [Antivirus de Microsoft Defender en Windows Server](microsoft-defender-antivirus-on-windows-server.md) para obtener información sobre las principales diferencias y opciones de administración para Windows server.

> [!IMPORTANT]
> Antivirus de Microsoft Defender solo está disponible en dispositivos que ejecutan Windows 10, Windows Server 2016, Windows Server, versión 1803 o posterior y Windows Server 2019.
>
> En Windows 8.1 y Windows Server 2012, la protección antivirus de extremo de nivel empresarial se ofrece como System Center Endpoint Protection [,](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))que se administra a través de Microsoft Endpoint Configuration Manager.
>
> Windows Defender también se ofrece para dispositivos de consumidores en Windows 8.1 y [Windows Server 2012](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender), aunque no proporciona administración de nivel de empresa (o una interfaz en instalaciones de server core de Windows Server 2012).

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>Cómo Antivirus de Microsoft Defender afecta a la funcionalidad de Defender for Endpoint

En la tabla de esta sección se resumen las funciones y características que están disponibles en cada estado. La tabla está diseñada para ser solo informativo. Está pensado para describir las características & funciones que funcionan activamente o no, según si Antivirus de Microsoft Defender está en modo activo, en modo pasivo o está deshabilitado o desinstalado. 

> [!IMPORTANT]
> No desactive las funcionalidades, como la protección en tiempo real, la protección entregada en la nube o el examen periódico limitado, si usa Antivirus de Microsoft Defender en modo pasivo o está usando EDR en modo de bloqueo. 

|Protection |Modo activo |Modo pasivo |EDR en modo bloqueo |Deshabilitado o desinstalado |
|:---|:---|:---|:---|:---|
| [Protección en tiempo real y](configure-real-time-protection-microsoft-defender-antivirus.md) protección entregada en la [nube](enable-cloud-protection-microsoft-defender-antivirus.md) | Sí | No <sup> [[3](#fn3)]<sup> | No | No |
| [Disponibilidad limitada de análisis periódico](limited-periodic-scanning-microsoft-defender-antivirus.md) | No | No | No | Sí |
| [Información de detección y detección de archivos](customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | Sí | Sí | Sí | No |
|  [Corrección de amenazas](configure-remediation-microsoft-defender-antivirus.md) | Sí | Vea la <sup> nota [[4](#fn4)]<sup> | Sí | No |
| [Actualizaciones de inteligencia de seguridad](manage-updates-baselines-microsoft-defender-antivirus.md) | Sí | Sí | Sí | No |

(<a id="fn3">3</a>) En general, cuando Antivirus de Microsoft Defender está en modo pasivo, la protección en tiempo real no proporciona ningún bloqueo ni aplicación, aunque esté habilitada y en modo pasivo. 

(<a id="fn4">4</a>) Cuando Antivirus de Microsoft Defender está en modo pasivo, las características de corrección de amenazas solo están activas durante los exámenes programados o a petición.

> [!NOTE]
> [Microsoft 365 protección de prevención de pérdida de](/microsoft-365/compliance/endpoint-dlp-learn-about) datos de punto de conexión sigue funcionando con normalidad cuando Antivirus de Microsoft Defender está en modo activo o pasivo.

## <a name="why-defender-for-endpoint-matters"></a>Por qué defender para endpoints es importante

Considera la posibilidad de incorporar los puntos de conexión a Defender for Endpoint, incluso si usas una solución antivirus o antimalware que no sea de Microsoft. En la mayoría de los casos, cuando incorpores los dispositivos a Defender for Endpoint, puedes usar Antivirus de Microsoft Defender junto con la solución antivirus que no sea microsoft para mayor protección. Por ejemplo, puede usar [EDR](edr-in-block-mode.md)en modo de bloque , que bloquea y corrige artefactos malintencionados que la solución antivirus principal podría haber perdido. 

Aquí se muestra cómo funciona:

- Si los dispositivos cliente de su organización están protegidos por una solución antivirus o antimwalware que no sea de Microsoft, cuando estos dispositivos se incorporen a Defender for Endpoint, Antivirus de Microsoft Defender pasa al modo pasivo automáticamente. En este caso, se producen detecciones de amenazas, pero la protección en tiempo real y las amenazas no se corrigen Antivirus de Microsoft Defender. **NOTA:** Este escenario en particular no se aplica a los puntos de conexión que ejecutan Windows Server.

- Si los dispositivos cliente de la organización están protegidos por una solución antivirus o antimalware que no sea de Microsoft y esos dispositivos no están incorporados a Microsoft Defender para Endpoint, Antivirus de Microsoft Defender pasa al modo deshabilitado automáticamente. En este caso, las amenazas no se detectan ni se corrigen Antivirus de Microsoft Defender. **NOTA:** Este escenario en particular no se aplica a los puntos de conexión que ejecutan Windows Server.

- Si los puntos de conexión de la organización ejecutan Windows Server y esos puntos de conexión están protegidos por una solución antivirus o antimalware que no sea de Microsoft, cuando estos extremos se incorporen a Defender for Endpoint, Antivirus de Microsoft Defender no entra en modo pasivo ni en modo deshabilitado automáticamente. En este escenario en particular, debe configurar sus Windows de servidor de forma adecuada. 

   - En Windows Server, versión 1803 o posterior y Windows Server 2019, puede configurar Antivirus de Microsoft Defender para que se ejecute en modo pasivo. 
   - En Windows Server 2016, Antivirus de Microsoft Defender se debe deshabilitar (el modo pasivo no se admite en Windows Server 2016).

- Si los puntos de conexión de la organización están protegidos por una solución antivirus o antimalware que no sea de Microsoft, cuando estos dispositivos se incorporen a Defender for Endpoint con [EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode) en modo de bloqueo habilitado, Defender for Endpoint bloquea y corrige artefactos malintencionados. **NOTA:** Este escenario en particular no se aplica a Windows Server 2016. EDR en modo de bloque requiere Antivirus de Microsoft Defender habilitarse en modo activo o en modo pasivo.


> [!WARNING]
> No deshabilite, detenga ni modifique ninguno de los servicios asociados que usan Antivirus de Microsoft Defender, Microsoft Defender para endpoint o la aplicación Seguridad de Windows usuario. Esta recomendación incluye los servicios y procesos *wscsvc*, *SecurityHealthService*, *MsSense*, *Sense*, *WinDefend* o *MsMpEng.* La modificación manual de estos servicios puede provocar una inestabilidad grave en los dispositivos y puede hacer que la red sea vulnerable. Deshabilitar, detener o modificar esos servicios también puede causar problemas al usar soluciones antivirus que no son de Microsoft y cómo se muestra su información en la [Seguridad de Windows aplicación](microsoft-defender-security-center-antivirus.md).


## <a name="see-also"></a>Vea también

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Antivirus de Microsoft Defender en Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [EDR en modo bloqueo](edr-in-block-mode.md)
- [Configurar Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [Abordar falsos positivos/negativos en Microsoft Defender para punto de conexión](defender-endpoint-false-positives-negatives.md)
- [Obtenga más información sobre la prevención de pérdida de datos de Microsoft 365 de punto de conexión](/microsoft-365/compliance/endpoint-dlp-learn-about)
