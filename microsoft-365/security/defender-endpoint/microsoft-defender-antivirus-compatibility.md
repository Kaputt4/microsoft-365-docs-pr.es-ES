---
title: Compatibilidad de Antivirus de Microsoft Defender con otros productos de seguridad
description: Qué esperar de Antivirus de Microsoft Defender con otros productos de seguridad y los sistemas operativos que está usando.
keywords: windows defender, próxima generación, antivirus, compatibilidad, modo pasivo
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 131b9970572b1034ba5c9907a001f0497d450339
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765448"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Compatibilidad con Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

## <a name="overview"></a>Información general

Antivirus de Microsoft Defender se habilita e instala automáticamente en puntos de conexión y dispositivos que ejecutan Windows 10. Pero, ¿qué sucede cuando se usa otra solución antivirus/antimalware? Depende de si usas [Microsoft Defender para Endpoint](microsoft-defender-endpoint.md) junto con la protección antivirus.
- Si los puntos de conexión y los dispositivos de la organización están protegidos con una solución antivirus o antimalware que no sea de Microsoft y no se usa Microsoft Defender para endpoint, Antivirus de Microsoft Defender pasa automáticamente al modo deshabilitado.
- Si su organización usa Microsoft Defender para Endpoint junto con una solución antivirus o antimalware que no sea de Microsoft, Antivirus de Microsoft Defender pasa automáticamente al modo pasivo. (Antivirus de Microsoft Defender no corrige la protección en tiempo real ni las amenazas).
- Si su organización usa Microsoft Defender para Endpoint junto con una solución antivirus o antimalware que no sea de Microsoft y tiene [EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode) en modo de bloqueo habilitado, siempre que se detecte un artefacto malintencionado, Microsoft Defender for Endpoint realiza acciones para bloquear y corregir el artefacto.

## <a name="antivirus-and-microsoft-defender-for-endpoint"></a>Antivirus y Microsoft Defender para endpoint

En la tabla siguiente se resume lo que sucede con Microsoft Defender Antivirus cuando los productos antivirus de terceros se usan juntos o sin Microsoft Defender para endpoint. 


| Versión de Windows   | Protección antimalware  | Inscripción de Microsoft Defender para puntos de conexión | Estado del antivirus de Microsoft Defender     |
|------|------|-------|-------|
| Windows 10  | Un producto de terceros que Microsoft no ofrece ni desarrolla | Sí  | Modo pasivo  |
| Windows 10  | Un producto de terceros que Microsoft no ofrece ni desarrolla | No   | Modo deshabilitado automáticamente     |
| Windows 10  | Microsoft Defender Antivirus | Sí  | Modo activo | 
| Windows 10  | Microsoft Defender Antivirus | No   | Modo activo |
| Windows Server, versión 1803 o posterior, o Windows Server 2019 | Un producto de terceros que Microsoft no ofrece ni desarrolla | Sí  | Debe establecerse en modo pasivo (manualmente) <sup> [[1](#fn1)]<sup>  | 
| Windows Server, versión 1803 o posterior, o Windows Server 2019 | Un producto de terceros que Microsoft no ofrece ni desarrolla | No  | Debe deshabilitarse (manualmente) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server, versión 1803 o posterior, o Windows Server 2019 | Microsoft Defender Antivirus  | Sí |         Modo activo  |
| Windows Server, versión 1803 o posterior, o Windows Server 2019 | Microsoft Defender Antivirus | No  | Modo activo |
| Windows Server 2016 | Microsoft Defender Antivirus | Sí | Modo activo |
| Windows Server 2016 | Microsoft Defender Antivirus | No | Modo activo |
| Windows Server 2016 | Un producto de terceros que Microsoft no ofrece ni desarrolla | Sí | Debe deshabilitarse (manualmente) <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | Un producto de terceros que Microsoft no ofrece ni desarrolla | No | Debe deshabilitarse (manualmente) <sup> [[2](#fn2)]<sup> |

(<a id="fn1">1</a>) En Windows Server, versión 1803 o posterior, o Windows Server 2019, Antivirus de Microsoft Defender no entra en modo pasivo automáticamente al instalar un producto antivirus que no sea de Microsoft. En esos casos, [establece Antivirus de Microsoft Defender](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) en modo pasivo para evitar problemas causados por tener varios productos antivirus instalados en un servidor.

Si usas Windows Server, versión 1803 o posterior, o Windows Server 2019, puedes establecer Antivirus de Microsoft Defender en modo pasivo estableciendo la siguiente clave del Registro:
- Ruta de acceso: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Nombre: `ForcePassiveMode`
- Tipo: `REG_DWORD`
- Valor: `1`

> [!NOTE]
> La `ForcePassiveMode` clave del Registro no es compatible con Windows Server 2016.

(<a id="fn2">2</a>) En Windows Server 2016, Antivirus de Microsoft Defender no entra en modo pasivo automáticamente al instalar un producto antivirus que no sea de Microsoft. Además, antivirus de Microsoft Defender no se admite en modo pasivo. En esos casos, [deshabilite o](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) desinstale Antivirus de Microsoft Defender manualmente para evitar problemas causados por tener varios productos antivirus instalados en un servidor.

Consulta [Antivirus de Microsoft Defender en Windows Server para ver](microsoft-defender-antivirus-on-windows-server.md) las principales diferencias y opciones de administración para las instalaciones de Windows Server.

> [!IMPORTANT]
> Antivirus de Microsoft Defender solo está disponible en dispositivos que ejecutan Windows 10, Windows Server 2016, Windows Server, versión 1803 o posterior y Windows Server 2019.
>
> En Windows 8.1 y Windows Server 2012, la protección antivirus de extremo de nivel empresarial se ofrece como [System Center Endpoint Protection,](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))que se administra a través de Microsoft Endpoint Configuration Manager.
>
> Windows Defender también se ofrece para dispositivos de consumo en [Windows 8.1 y Windows Server 2012,](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)aunque no proporciona administración de nivel empresarial (ni una interfaz en instalaciones de Windows Server 2012 Server Core).

## <a name="functionality-and-features-available-in-each-state"></a>Funcionalidad y características disponibles en cada estado

En la tabla de esta sección se resumen las funciones y características que están disponibles en cada estado. La tabla está diseñada para ser solo informativo. Está diseñado para describir las características & funciones que funcionan activamente o no, según si Antivirus de Microsoft Defender está en modo activo, en modo pasivo o está deshabilitado o desinstalado. 

> [!IMPORTANT]
> No desactive las funcionalidades, como la protección en tiempo real, la protección entregada en la nube o el examen periódico limitado, si usa Antivirus de Microsoft Defender en modo pasivo o está usando EDR en modo de bloqueo. 

|Protection |Modo activo |Modo pasivo |EDR en modo bloqueo |Deshabilitado o desinstalado |
|:---|:---|:---|:---|:---|
| [Protección en tiempo real y](./configure-real-time-protection-microsoft-defender-antivirus.md) protección entregada en la [nube](./enable-cloud-protection-microsoft-defender-antivirus.md) | Sí | No <sup> [[3](#fn3)]<sup> | No | No |
| [Disponibilidad limitada de análisis periódico](./limited-periodic-scanning-microsoft-defender-antivirus.md) | No | No | No | Sí |
| [Información de detección y detección de archivos](./customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | Sí | Sí | Sí | No |
|  [Corrección de amenazas](./configure-remediation-microsoft-defender-antivirus.md) | Sí | Vea la <sup> nota [[4](#fn4)]<sup> | Sí | No |
| [Actualizaciones de inteligencia de seguridad](./manage-updates-baselines-microsoft-defender-antivirus.md) | Sí | Sí | Sí | No |

(<a id="fn3">3</a>) En general, cuando Antivirus de Microsoft Defender está en modo pasivo, la protección en tiempo real no proporciona ningún bloqueo ni aplicación, aunque esté habilitado y en modo pasivo. 

(<a id="fn4">4</a>) Cuando Antivirus de Microsoft Defender está en modo pasivo, las características de corrección de amenazas solo están activas durante los exámenes programados o a petición.

> [!NOTE]
> [Microsoft 365 Endpoint data loss prevention](/microsoft-365/compliance/endpoint-dlp-learn-about) protection continues to operate normally when Microsoft Defender Antivirus is in active or passive mode.

## <a name="keep-the-following-points-in-mind"></a>Tenga en cuenta los siguientes puntos

- En el modo activo, Antivirus de Microsoft Defender se usa como la aplicación antivirus en el equipo. Se aplicará toda la configuración realizada con Configuration Manager, la directiva de grupo, Intune u otros productos de administración. Los archivos se examinan y se corrigen las amenazas, y la información de detección se notifica en la herramienta de configuración (como Configuration Manager o la aplicación Antivirus de Microsoft Defender en el propio equipo).

- En modo pasivo, Antivirus de Microsoft Defender no se usa como la aplicación antivirus y Antivirus de Microsoft Defender no corrige las amenazas. Los archivos se examinan y se proporcionan informes para las detecciones de amenazas que se comparten con el servicio Detección de puntos de conexión de Microsoft Defender. Por lo tanto, es posible que encuentre alertas en la consola del Centro de seguridad con Antivirus de Microsoft Defender como origen, incluso cuando Antivirus de Microsoft Defender está en modo pasivo.

- Cuando [EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode) en modo de bloqueo está activado y Antivirus de Microsoft Defender no es la solución antivirus principal, todavía puede detectar y corregir elementos malintencionados.

- Cuando se deshabilita, antivirus de Microsoft Defender no se usa como la aplicación antivirus. Los archivos no se examinan y las amenazas no se corrigen. No se recomienda deshabilitar o desinstalar Antivirus de Microsoft Defender en general; si es posible, mantenga antivirus de Microsoft Defender en modo pasivo si usa una solución antivirus o antimalware que no sea de Microsoft.

- Si está inscrito en Microsoft Defender para Endpoint y usa un producto antimalware de terceros, el modo pasivo está habilitado. [El servicio requiere el uso compartido de](/microsoft-365/security/defender-endpoint/defender-compatibility) información común del servicio antivirus de Microsoft Defender para supervisar correctamente los dispositivos y la red en busca de intentos de intrusión y ataques.

- Cuando Antivirus de Microsoft Defender se deshabilita automáticamente, se puede volver a habilitar automáticamente si la protección ofrecida por un producto antivirus que no es de Microsoft expira o deja de proporcionar protección en tiempo real contra virus, malware u otras amenazas. La habilitación automática ayuda a garantizar que la protección antivirus se mantenga en los dispositivos. También te permite habilitar el examen periódico [limitado,](limited-periodic-scanning-microsoft-defender-antivirus.md)que usa el motor antivirus de Microsoft Defender para comprobar periódicamente si hay amenazas además de la aplicación antivirus principal.

- Cuando Antivirus de Microsoft Defender está en modo pasivo, todavía puedes administrar [las actualizaciones de Antivirus de Microsoft Defender;](manage-updates-baselines-microsoft-defender-antivirus.md) sin embargo, no puedes mover Antivirus de Microsoft Defender al modo activo si los dispositivos tienen un producto antivirus actualizado y que no es de Microsoft que proporciona protección en tiempo real contra malware. Para obtener una eficacia óptima de defensa y detección por capas de seguridad, asegúrese de actualizar la protección antivirus de [Microsoft Defender (actualización](./manage-updates-baselines-microsoft-defender-antivirus.md) de inteligencia de seguridad, motor y plataforma) incluso si antivirus de Microsoft Defender se ejecuta en modo pasivo.

   Si desinstala el producto antivirus que no es de Microsoft y usa Antivirus de Microsoft Defender para proporcionar protección a sus dispositivos, Antivirus de Microsoft Defender volverá a su modo activo normal automáticamente.

> [!WARNING]
> No deshabilite, detenga ni modifique ninguno de los servicios asociados que usa Antivirus de Microsoft Defender, Microsoft Defender para endpoint o la aplicación seguridad de Windows. Esta recomendación incluye los servicios y procesos *wscsvc*, *SecurityHealthService*, *MsSense*, *Sense*, *WinDefend* o *MsMpEng.* La modificación manual de estos servicios puede provocar una inestabilidad grave en los dispositivos y puede hacer que la red sea vulnerable. Deshabilitar, detener o modificar esos servicios también puede causar problemas al usar soluciones antivirus que no son de Microsoft y cómo se muestra su información en la aplicación [seguridad de Windows](microsoft-defender-security-center-antivirus.md).


## <a name="see-also"></a>Vea también

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Antivirus de Microsoft Defender en Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [EDR en modo bloqueo](edr-in-block-mode.md)
- [Configurar Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [Abordar falsos positivos/negativos en Microsoft Defender para punto de conexión](defender-endpoint-false-positives-negatives.md)
- [Obtenga más información sobre la prevención de pérdida de datos de Microsoft 365 de punto de conexión](/microsoft-365/compliance/endpoint-dlp-learn-about)