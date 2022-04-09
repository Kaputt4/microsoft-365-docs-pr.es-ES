---
title: Administración de actualizaciones Antivirus de Microsoft Defender y aplicación de líneas base
description: Administre cómo Antivirus de Microsoft Defender recibe actualizaciones de productos y protección.
keywords: actualizaciones, líneas base de seguridad, protección, actualizaciones de programación, actualizaciones forzadas, actualizaciones móviles, wsus
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr, mkaminska
manager: dansimp
ms.technology: mde
ms.date: 04/07/2022
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: 346f806129afc30ec5543c99bce3709af60cee73
ms.sourcegitcommit: dd7e5b67ff4ae4e7f74490e437c1795933c74cc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2022
ms.locfileid: "64730648"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a>Administración de actualizaciones Antivirus de Microsoft Defender y aplicación de líneas base

**Se aplica a:**
- [planes de Microsoft Defender para punto de conexión 1 y 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

Mantener Antivirus de Microsoft Defender actualizado es fundamental para garantizar que los dispositivos tengan la tecnología y las características más recientes necesarias para protegerse frente a nuevas técnicas de malware y ataques. Asegúrese de actualizar la protección antivirus, incluso si Antivirus de Microsoft Defender se ejecuta en [modo pasivo](microsoft-defender-antivirus-compatibility.md). Hay dos tipos de actualizaciones relacionadas con mantener Antivirus de Microsoft Defender actualizados:

- Actualizaciones de inteligencia de seguridad
- Actualizaciones de productos

> [!TIP]
> Para ver el motor, la plataforma y la fecha de firma más actuales, visite [las actualizaciones de inteligencia de seguridad para Antivirus de Microsoft Defender y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates).

## <a name="security-intelligence-updates"></a>Actualizaciones de inteligencia de seguridad

Antivirus de Microsoft Defender usa [la protección proporcionada en la nube](cloud-protection-microsoft-defender-antivirus.md) (también denominada Servicio de protección avanzada de Microsoft o MAPS) y descarga periódicamente actualizaciones dinámicas de inteligencia de seguridad para proporcionar protección adicional. Estas actualizaciones dinámicas no toman el lugar de las actualizaciones periódicas de inteligencia de seguridad a través de la actualización de inteligencia de seguridad KB2267602.

> [!NOTE]
> Las actualizaciones se publican en los siguientes KB:
> - Antivirus de Microsoft Defender: KB2267602
> - System Center Endpoint Protection: KB2461484

La protección entregada en la nube siempre está activada y requiere una conexión activa a Internet para funcionar. Las actualizaciones de inteligencia de seguridad se producen en una cadencia programada (configurable a través de la directiva). Para obtener más información, consulte [Uso de la protección proporcionada por la nube de Microsoft en Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md).

Para obtener una lista de las actualizaciones recientes de inteligencia de seguridad, consulte [Actualizaciones de inteligencia de seguridad para Antivirus de Microsoft Defender y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates).

Las actualizaciones del motor se incluyen con actualizaciones de inteligencia de seguridad y se publican con una cadencia mensual.

## <a name="product-updates"></a>Actualizaciones de productos

Antivirus de Microsoft Defender requiere [actualizaciones mensuales (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) conocidas como *actualizaciones de plataforma*.

Puede administrar la distribución de actualizaciones mediante uno de los métodos siguientes:

- [Windows Server Update Service (WSUS)](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/sum/understand/software-updates-introduction)
- Método habitual que se usa para implementar Microsoft y Windows actualizaciones en los puntos de conexión de la red.

Para obtener más información, vea [Administrar los orígenes para Antivirus de Microsoft Defender actualizaciones de protección](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).

> [!NOTE]
> - Las actualizaciones mensuales se publican en fases, lo que da como resultado varios paquetes visibles en [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).
> - En este artículo se enumeran los cambios que se incluyen en el amplio canal de versión. [Consulte la versión más reciente del canal amplio aquí](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info).
> - Para más información sobre el proceso de implementación gradual y para ver más información sobre la próxima versión, consulte [Administración del proceso de implementación gradual para las actualizaciones de Microsoft Defender](manage-gradual-rollout.md).
> - Para obtener más información sobre las actualizaciones de inteligencia de seguridad, consulte [Actualizaciones de inteligencia de seguridad para Antivirus de Microsoft Defender y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates).
> - Si busca una lista de procesos de Microsoft Defender, **[descargue el libro mde-urls](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)** y, a continuación, seleccione la hoja **de cálculo Procesos de Microsoft Defender** . El libro mde-urls también enumera los servicios y sus direcciones URL asociadas a las que la red debe poder conectarse, como se describe en [Habilitar el acceso a direcciones URL de servicio Microsoft Defender para punto de conexión en el servidor proxy](configure-proxy-internet.md).

## <a name="monthly-platform-and-engine-versions"></a>Versiones mensuales de la plataforma y del motor

Para obtener información sobre cómo actualizar o instalar la actualización de la plataforma, consulte [Actualización para Windows Defender plataforma antimalware](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).

Todas nuestras actualizaciones contienen

- Mejoras en el rendimiento
- Mejoras en la facilidad de servicio
- Mejoras de integración (nube, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender))
<br/><br/>
<details>
<summary>Marzo de 2022 (Plataforma: 4.18.2203.5 | Motor: 1.1.19100.5)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.361.1449.0**<br/>
&ensp;Fecha de publicación: **7 de marzo de 2022**<br/>
&ensp;Plataforma: **4.18.2203.5**<br/>
&ensp;Motor: **1.1.19100.5**<br/>
&ensp;Fase de soporte técnico: **Actualizaciones críticas y de seguridad**<br/>

Versión del motor: 1.1.19100.5 <br/>
Versión de actualización de inteligencia de seguridad: 1.361.1449.0<br/>

### <a name="whats-new"></a>Novedades

- Se ha agregado una corrección para una [regla de reducción de superficie expuesta a ataques](attack-surface-reduction.md) que bloqueó un complemento de Outlook 
- Se ha agregado una corrección para el problema de rendimiento de [la supervisión del comportamiento](configure-protection-features-microsoft-defender-antivirus.md) relacionado con los procesos en directo cortos 
- Corrección agregada para la exclusión de [AMSI](/windows/win32/amsi/antimalware-scan-interface-portal) 
- Funcionalidades mejoradas [de protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md) 
- Se ha agregado una corrección para que la [protección en tiempo real](configure-protection-features-microsoft-defender-antivirus.md) se deshabilite en algunos casos al usar `SharedSignaturesPath` la configuración (para obtener más información sobre el `SharedSignaturesPath` parámetro, vea [Set-MpPreference](/powershell/module/defender/set-mppreference))

### <a name="known-issues"></a>Problemas conocidos

No hay problemas conocidos

<br/><br/>
</details><details>
<summary>Febrero de 2022 (Plataforma: 4.18.2202.4 | Motor: 1.1.19000.8)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.361.14.0**<br/>
&ensp;Fecha de publicación: **14 de marzo de 2022**<br/>
&ensp;Plataforma: **4.18.2202.4**<br/>
&ensp;Motor: **1.1.19000.8**<br/>
&ensp;Fase de soporte técnico: **Actualizaciones críticas y de seguridad**<br/>

Versión del motor: 1.1.19000.8 <br/>
Versión de actualización de inteligencia de seguridad: 1.361.14.0 <br/>

### <a name="whats-new"></a>Novedades

- Mejoras en la lógica de detección y supervisión del comportamiento
- Se han corregido las detecciones de reducción de superficie expuesta a ataques desencadenantes falsos positivos
- Corrección agregada que da como resultado una mejor fidelidad de EDR y alertas de detección de búsqueda avanzada
- Defender ya no admite notificaciones personalizadas en elementos emergentes del sistema. Gpo/Intune/SCCM modificado y documentos para reflejar este cambio.
- Mejoras para capturar tanto la información como la copia de los archivos escritos en el almacenamiento extraíble. Para obtener más información, consulte [Microsoft Defender para punto de conexión dispositivo control extraíble Storage Access Control, medios de almacenamiento extraíbles](device-control-removable-storage-access-control.md).
- Salida de tráfico mejorada cuando no se puede acceder al servicio SmartScreen 
- Mejoras de conectividad para los clientes que usan servidores proxy con requisitos de autenticación
- Se ha corregido un error de actualización del dispositivo VDI para fileshares de red 
- EDR en modo de bloque ahora admite la segmentación pormenorizada de dispositivos con nuevos CSP. Consulte [Detección y respuesta de puntos de conexión (EDR) en modo de bloque](edr-in-block-mode.md).

### <a name="known-issues"></a>Problemas conocidos

No hay problemas conocidos

<br/><br/>
</details><details>
<summary>Enero-2022 (Plataforma: 4.18.2201.10 | Motor: 1.1.18900.2)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.357.8.0**<br/>
&ensp;Fecha de publicación: **9 de febrero de 2022**<br/>
&ensp;Plataforma: **4.18.2201.10**<br/>
&ensp;Motor: **1.1.18900.2**<br/>
&ensp;Fase de soporte técnico: **Actualizaciones críticas y de seguridad**<br/>

Versión del motor: 1.1.18900.2 <br/>
Versión de actualización de inteligencia de seguridad: 1.357.8.0 <br/>

### <a name="whats-new"></a>Novedades

- Mejoras en la supervisión del comportamiento en el rendimiento de filtrado
- Protección de TrustedInstaller
- Mejoras en la protección contra alteraciones
- Se ha reemplazado por `ScanScheduleTime` un nuevo `ScanScheduleOffest` cmdlet en [Set-MpPreference](/powershell/module/defender/set-mppreference). Esta directiva configura el número de minutos después de medianoche para realizar un examen programado.
- Se agregó la `-ServiceHealthReportInterval` configuración a [Set-MpPreference](/powershell/module/defender/set-mppreference). Esta directiva configura el intervalo de tiempo (en minutos) para realizar un examen programado.
- Se agregó la `AllowSwitchToAsyncInspection` configuración a [Set-MpPreference](/powershell/module/defender/set-mppreference). Esta directiva permite una optimización del rendimiento, que permite que los flujos de red inspeccionados sincrónicamente cambien a la inspección asincrónica una vez que se hayan comprobado y validado.
- Analizador de rendimiento actualizaciones v2: se ha agregado compatibilidad remota con PowerShell y PowerShell 7.x. Consulte [Analizador de rendimiento para Antivirus de Microsoft Defender](tune-performance-defender-antivirus.md).
- Se ha corregido un posible error de paquete duplicado en Antivirus de Microsoft Defender controlador del sistema de inspección de red.

### <a name="known-issues"></a>Problemas conocidos

No hay problemas conocidos

<br/><br/>
</details>


### <a name="previous-version-updates-technical-upgrade-support-only"></a>Actualizaciones de versiones anteriores: solo soporte técnico de actualización

Una vez publicada una nueva versión del paquete, la compatibilidad con las dos versiones anteriores se reduce solo a soporte técnico. Las versiones anteriores a las que aparecen en esta sección y se proporcionan solo para soporte técnico de actualización.<br/><br/>

<details>
<summary>Noviembre de 2021 (Plataforma: 4.18.2111.5 | Motor: 1.1.18800.4)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.355.2.0**<br/>
&ensp;Fecha de publicación: **9 de diciembre de 2021**<br/>
&ensp;Plataforma: **4.18.2111.5**<br/>
&ensp;Motor: **1.1.18800.4**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

Versión del motor: 1.1.18800.4 Versión de actualización de inteligencia de seguridad: 1.355.2.0

### <a name="whats-new"></a>Novedades

- Eficiencia mejorada del uso de CPU de determinados escenarios intensivos en servidores Exchange
- Se agregaron nuevos campos de estado de control de dispositivo en Get-MpComputerStatus en el módulo de PowerShell de Defender. Para obtener más información, consulte [Microsoft Defender para punto de conexión Storage Access Control extraíbles de Device Control](device-control-removable-storage-access-control.md).
- Se ha corregido un error en el que `SharedSignatureRoot` no se podía quitar el valor cuando se establece con PowerShell
- Se ha corregido un error en el que no se pudo habilitar la [protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md), aunque Microsoft Defender para punto de conexión indicaba que la protección contra alteraciones estaba activada.
- Se han agregado correcciones de errores y compatibilidad al analizador de rendimiento para Antivirus de Microsoft Defender herramienta. Para obtener más información, consulte [Analizador de rendimiento para Antivirus de Microsoft Defender](tune-performance-defender-antivirus.md).   
   - Se ha agregado compatibilidad con PowerShell ISE para `New-MpPerformanceRecording`
   - Se han corregido los errores de `Get-MpPerformanceReport -TopFilesPerProcess`
   - Se ha corregido la pérdida de sesión de grabación de rendimiento al usar `New-MpPerformanceRecording` en PowerShell 7.x, sesiones remotas e ISE de PowerShell


### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Octubre de 2021 (Plataforma: 4.18.2110.6 | Motor: 1.1.18700.4)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.353.3.0**<br/>
&ensp;Fecha de publicación: **28 de octubre de 2021**<br/>
&ensp;Plataforma: **4.18.2110.6**<br/>
&ensp;Motor: **1.1.18700.4**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

Versión del motor: 1.1.18700.4 Versión de actualización de inteligencia de seguridad: 1.353.3.0

### <a name="whats-new"></a>Novedades

- Mejoras en la cobertura del tráfico de red del protocolo de transferencia de archivos (FTP)
- Corrección para reducir el uso de CPU de Microsoft Defender en Exchange Server que se ejecutan en Windows Server 2016
- Corrección de interrupciones del examen
- Corrección de alertas sobre intentos de manipulación bloqueados que no aparecen en Security Center
- Mejoras en la resistencia de alteraciones en el servicio Microsoft Defender

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Septiembre de 2021 (Plataforma: 4.18.2109.6 | Motor: 1.1.18600.4)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.351.7.0**<br/>
&ensp;Fecha de publicación: **7 de octubre de 2021**<br/>
&ensp;Plataforma: **4.18.2109.6**<br/>
&ensp;Motor: **1.1.18600.4**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

Versión del motor: 1.1.18600.4 Versión de actualización de inteligencia de seguridad: 1.351.7.0

### <a name="whats-new"></a>Novedades
- Nuevo anillo de retraso para Antivirus de Microsoft Defender motor y actualizaciones de plataforma. Los dispositivos que opten por este anillo recibirán actualizaciones con un retraso de 48 horas. El nuevo anillo de retraso se sugiere solo para entornos críticos. Consulte [Administración del proceso de implementación gradual para las actualizaciones de Microsoft Defender](manage-gradual-rollout.md).
- Mejoras en el proceso de implementación gradual de actualizaciones de Microsoft Defender

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Agosto de 2021 (Plataforma: 4.18.2108.7 | Motor: 1.1.18500.10)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.349.22.0**<br/>
&ensp;Fecha de publicación: **2 de septiembre de 2021**<br/>
&ensp;Plataforma: **4.18.2108.7**<br/>
&ensp;Motor: **1.1.18500.10**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

### <a name="whats-new"></a>Novedades
- Mejoras en el motor de supervisión del comportamiento
- Lanzamiento del nuevo [analizador de rendimiento para Antivirus de Microsoft Defender](tune-performance-defender-antivirus.md)
- Antivirus de Microsoft Defender protegido contra la carga de archivos DLL malintencionados
- Antivirus de Microsoft Defender protegido contra la omisión TrustedInstaller
- Ampliación de las notificaciones de cambio de archivo para incluir más datos para Human-Operated ransomware (HumOR)

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Julio-2021 (Plataforma: 4.18.2107.4 | Motor: 1.1.18400.4)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.345.13.0**<br/>
&ensp;Fecha de lanzamiento: **5 de agosto de 2021**<br/>
&ensp;Plataforma: **4.18.2107.4**<br/>
&ensp;Motor: **1.1.18400.4**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

### <a name="whats-new"></a>Novedades
- Compatibilidad con el control de dispositivos agregada para dispositivos portátiles Windows
- La protección de aplicaciones potencialmente no deseadas (PUA) está activada de forma predeterminada para los consumidores (vea [Aplicaciones potencialmente no deseadas bloqueadas de forma predeterminada](https://support.microsoft.com/windows/potentially-unwanted-apps-will-be-blocked-by-default-b9f53cb9-7f1e-40bb-8c6b-a17e0ab6289e)).
- Los exámenes programados para directiva de grupo sistemas administrados por objetos se ajustarán al tiempo de examen configurado por el usuario
- Mejoras en el motor de supervisión del comportamiento

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos

<br/>
</details><details>
<summary> Junio de 2021 (Plataforma: 4.18.2106.5 | Motor: 1.1.18300.4)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.343.17.0**<br/>
&ensp;Fecha de lanzamiento: **28 de junio de 2021**<br/>
&ensp;Plataforma: **4.18.2106.5**<br/>
&ensp;Motor: **1.1.18300.4**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

### <a name="whats-new"></a>Novedades
- Nuevos controles para administrar el proceso de implementación gradual de las actualizaciones de Microsoft Defender. Consulte [Administración del proceso de implementación gradual para las actualizaciones de Microsoft Defender](manage-gradual-rollout.md).
- Mejora del motor de supervisión del comportamiento
- Mejoras en la implementación de definiciones de antimalware
- Inspecciones de eventos de red perimetral extendida

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Mayo de 2021 (Plataforma: 4.18.2105.4 | Motor: 1.1.18200.4)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.341.8.0**<br/>
&ensp;Fecha de lanzamiento: **3 de junio de 2021**<br/>
&ensp;Plataforma: **4.18.2105.4**<br/>
&ensp;Motor: **1.1.18200.4**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

### <a name="whats-new"></a>Novedades
- Mejoras en la [supervisión del comportamiento](client-behavioral-blocking.md)
- Característica de filtrado de notificaciones de [protección de red](network-protection.md) fija

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Abril de 2021 (Plataforma: 4.18.2104.14 | Motor: 1.1.18100.5)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.337.2.0**<br/>
&ensp;Publicado: **26 de abril de 2021**  (Motor: 1.1.18100.6 publicado el 5 de mayo de 2021)<br/>
&ensp;Plataforma: **4.18.2104.14**<br/>
&ensp;Motor: **1.1.18100.5**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

### <a name="whats-new"></a>Novedades
- Más lógica de supervisión del comportamiento
- Detección mejorada del registrador de claves en modo kernel
- Se han agregado nuevos controles para administrar el proceso de implementación gradual para [las actualizaciones de Microsoft Defender](manage-gradual-rollout.md).


### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Marzo de 2021 (Plataforma: 4.18.2103.7 | Motor: 1.1.18000.5)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.335.36.0**<br/>
&ensp;Fecha de publicación: **2 de abril de 2021**<br/>
&ensp;Plataforma: **4.18.2103.7**<br/>
&ensp;Motor: **1.1.18000.5**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

### <a name="whats-new"></a>Novedades

- Mejora del motor de supervisión del comportamiento
- Mitigaciones de ataques por fuerza bruta de red expandida
- Generación de eventos de intento de manipulación con más errores cuando la [protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md) está habilitada

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Febrero de 2021 (Plataforma: 4.18.2102.3 | Motor: 1.1.17900.7)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.333.7.0**<br/>
&ensp;Fecha de publicación: **9 de marzo de 2021**<br/>
&ensp;Plataforma: **4.18.2102.3**<br/>
&ensp;Motor: **1.1.17900.7**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

### <a name="whats-new"></a>Novedades

- Mejora de la recuperación del servicio mediante [la protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md)
- Extensión del ámbito de protección contra alteraciones

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Enero de 2021 (Plataforma: 4.18.2101.9 | Motor: 1.1.17800.5)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.327.1854.0**<br/>
&ensp;Fecha de publicación: **2 de febrero de 2021**<br/>
&ensp;Plataforma: **4.18.2101.9**<br/>
&ensp;Motor: **1.1.17800.5**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

### <a name="whats-new"></a>Novedades

- Mejoras en la detección de vulnerabilidades de seguridad del código de shell
- Mayor visibilidad de los intentos de robo de credenciales
- Mejoras en las características de antiampering en los servicios de Antivirus de Microsoft Defender
- Compatibilidad mejorada con la emulación arm x64
- Corrección: EDR notificación de bloqueo permanece en el historial de amenazas después de que la protección en tiempo real haya realizado la detección inicial

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Noviembre de 2020 (Plataforma: 4.18.2011.6 | Motor: 1.1.17700.4)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.327.1854.0**<br/>
&ensp;Fecha de publicación: **03 de diciembre de 2020**<br/>
&ensp;Plataforma: **4.18.2011.6**<br/>
&ensp;Motor: **1.1.17700.4**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

### <a name="whats-new"></a>Novedades

- Registro mejorado de compatibilidad con el estado [de SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Octubre de 2020 (Plataforma: 4.18.2010.7 | Motor: 1.1.17600.5)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.327.7.0**<br/>
&ensp;Fecha de publicación: **29 de octubre de 2020**<br/>
&ensp;Plataforma: **4.18.2010.7**<br/>
&ensp;Motor: **1.1.17600.5**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

### <a name="whats-new"></a>Novedades

- Nuevas descripciones para categorías de amenazas especiales
- Funcionalidades de emulación mejoradas
- Funcionalidades mejoradas de permitir o bloquear direcciones de host
- Nueva opción en CSP de Defender para omitir la combinación de exclusiones de usuarios locales

### <a name="known-issues"></a>Problemas conocidos

No hay problemas conocidos
<br/>
</details><details>
<summary> Septiembre de 2020 (Plataforma: 4.18.2009.7 | Motor: 1.1.17500.4)</summary>

&ensp;Versión de actualización de Inteligencia de seguridad: **1.325.10.0**<br/>
&ensp;Fecha de publicación: **01 de octubre de 2020**<br/>
&ensp;Plataforma: **4.18.2009.7**<br/>
&ensp;Motor: **1.1.17500.4**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

### <a name="whats-new"></a>Novedades

- Se requieren permisos de administrador para restaurar archivos en cuarentena
- Ahora se admiten eventos con formato XML
- Compatibilidad con CSP para omitir las combinaciones de exclusión
- Nuevas interfaces de administración para:
   - Inspección de UDP
   - Protección de red en Server 2019
   - Exclusiones de direcciones IP para la protección de red
- Visibilidad mejorada de las medidas de TPM
- Examen mejorado de Office módulo VBA

### <a name="known-issues"></a>Problemas conocidos

No hay problemas conocidos
<br/>
</details>
<details>
<summary> Agosto de 2020 (Plataforma: 4.18.2008.9 | Motor: 1.1.17400.5)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.323.9.0**<br/>
&ensp;Fecha de lanzamiento: **27 de agosto de 2020**<br/>
&ensp;Plataforma: **4.18.2008.9**<br/>
&ensp;Motor: **1.1.17400.5**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

### <a name="whats-new"></a>Novedades

- Agregar más eventos de telemetría
- Telemetría de eventos de examen mejorada
- Supervisión mejorada del comportamiento de los exámenes de memoria
- Examen mejorado de flujos de macros
- Se ha agregado `AMRunningMode` a Get-MpComputerStatus cmdlet de PowerShell
- [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) se omite. Antivirus de Microsoft Defender se desactiva automáticamente cuando detecta otro programa antivirus.


### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details>

<details>
<summary> Julio-2020 (Plataforma: 4.18.2007.8 | Motor: 1.1.17300.4)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.321.30.0**<br/>
&ensp;Fecha de lanzamiento: **28 de julio de 2020**<br/>
&ensp;Plataforma: **4.18.2007.8**<br/>
&ensp;Motor: **1.1.17300.4**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

### <a name="whats-new"></a>Novedades

- Telemetría mejorada para BITS
- Validación mejorada del certificado de firma de código authenticode

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details>

<details>
<summary> Junio de 2020 (Plataforma: 4.18.2006.10 | Motor: 1.1.17200.2)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.319.20.0**<br/>
&ensp;Fecha de lanzamiento: **22 de junio de 2020**<br/>
&ensp;Plataforma: **4.18.2006.10**<br/>
&ensp;Motor: **1.1.17200.2**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

### <a name="whats-new"></a>Novedades

- Posibilidad de especificar la [ubicación de los registros de soporte técnico](./collect-diagnostic-data.md)
- Omitir el examen de captura agresivo en modo pasivo.
- Permitir que Defender actualice en conexiones de uso medido
- Se ha corregido el ajuste del rendimiento al deshabilitar el almacenamiento en caché
- Se ha corregido la consulta del Registro.
- Se ha corregido la aleatoriedad del tiempo de examen en ADMX

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details>

<details>
<summary> Mayo de 2020 (Plataforma: 4.18.2005.4 | Motor: 1.1.17100.2)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.317.20.0**<br/>
&ensp;Fecha de lanzamiento: **26 de mayo de 2020**<br/>
&ensp;Plataforma: **4.18.2005.4**<br/>
&ensp;Motor: **1.1.17100.2**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

### <a name="whats-new"></a>Novedades

- Registro mejorado para eventos de examen
- Control de bloqueos del modo de usuario mejorado.
- Se ha agregado el seguimiento de eventos para la protección contra alteraciones
- Se ha corregido el envío de ejemplo de AMSI
- Se ha corregido el bloqueo en la nube de AMSI
- Se ha corregido el registro de instalación de actualizaciones de seguridad

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details>

<details>
<summary> Abril de 2020 (Plataforma: 4.18.2004.6 | Motor: 1.1.17000.2)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.315.12.0**<br/>
&ensp;Fecha de publicación: **30 de abril de 2020**<br/>
&ensp;Plataforma: **4.18.2004.6**<br/>
&ensp;Motor: **1.1.17000.2**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

### <a name="whats-new"></a>Novedades
- Mejoras de WDfilter
- Agregar más datos de eventos accionables a eventos de detección de reducción de superficie expuesta a ataques
- Se ha corregido la información de versión en datos de diagnóstico y WMI
- Se ha corregido una versión incorrecta de la plataforma en la interfaz de usuario después de la actualización de la plataforma
- Información sobre direcciones URL dinámicas para la protección contra amenazas sin archivos
- Funcionalidad de examen de UEFI
- Ampliación del registro para las actualizaciones

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details>

<details>
<summary> Marzo de 2020 (Plataforma: 4.18.2003.8 | Motor: 1.1.16900.2)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.313.8.0**<br/>
&ensp;Fecha de publicación: **24 de marzo de 2020**<br/>
&ensp;Plataforma: **4.18.2003.8**<br/>
&ensp;Motor: **1.1.16900.4**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

### <a name="whats-new"></a>Novedades

- Opción de limitación de CPU agregada a [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)
- Mejora de la funcionalidad de diagnóstico
- reducir el tiempo de espera de inteligencia de seguridad (5 minutos)
- Ampliación de la funcionalidad de registro interno del motor de AMSI
- Mejora de la notificación para el bloqueo de procesos

### <a name="known-issues"></a>Problemas conocidos
[**Corregido**] Antivirus de Microsoft Defender omite archivos al ejecutar un examen.

<br/>
</details>

<details>

<summary> Febrero de 2020 (Plataforma: - | Motor: 1.1.16800.2)</summary>


&ensp;Versión de actualización de inteligencia de seguridad: **1.311.4.0**<br/>
&ensp;Fecha de publicación: **25 de febrero de 2020**<br/>
&ensp;Plataforma o cliente: **-**<br/>
&ensp;Motor: **1.1.16800.2**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

### <a name="whats-new"></a>Novedades


### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details>

<details>
<summary> Enero-2020 (Plataforma: 4.18.2001.10 | Motor: 1.1.16700.2)</summary>


Versión de actualización de Inteligencia de seguridad: **1.309.32.0**<br/>
Fecha de lanzamiento: **30 de enero de 2020**<br/>
Plataforma o cliente: **4.18.2001.10**<br/>
Motor: **1.1.16700.2**<br/>
&ensp;Fase de soporte **técnico: soporte técnico de actualización (solo)**<br/>

### <a name="whats-new"></a>Novedades

- Se ha corregido el BSOD en WS2016 con Exchange
- Compatibilidad con actualizaciones de plataforma cuando se redirige TMP a la ruta de acceso de red
- Las versiones de la plataforma y del motor se agregan a [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates) <!-- The preceding URL must include "/en-us" -->
- Ampliar la actualización de firma de emergencia al [modo pasivo](./microsoft-defender-antivirus-compatibility.md)
- Corrección de bloqueo de 4.18.1911.3

### <a name="known-issues"></a>Problemas conocidos

[**Corregido] Los** dispositivos que usan el [modo de espera moderno](/windows-hardware/design/device-experiences/modern-standby) pueden experimentar un bloqueo con el controlador de filtro Windows Defender que da lugar a una brecha de protección.  Las máquinas afectadas parecen que el cliente no se ha actualizado a la plataforma antimalware más reciente.
<br/>
> [!IMPORTANT]
> Esta actualización es:
> - que necesitan los dispositivos RS1 que ejecutan la versión más baja de la plataforma para admitir SHA2;
> - tiene una marca de reinicio para los sistemas que tienen problemas de suspensión;
> - se vuelve a publicar en abril de 2020 y no se reemplazará por actualizaciones más recientes para mantener la disponibilidad futura;
> - se clasifica como una actualización debido al requisito de reinicio; Y
> - solo se ofrece con [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).
<br/>
</details>

<details>
<summary> Noviembre de 2019 (Plataforma: 4.18.1911.3 | Motor: 1.1.16600.7)</summary>

Versión de actualización de inteligencia de seguridad: **1.307.13.0**<br/>
Fecha de publicación: **7 de diciembre de 2019**<br/>
Plataforma: **4.18.1911.3**<br/>
Motor: **1.1.17000.7**<br/>
Fase de soporte técnico: **sin soporte técnico**<br/>

### <a name="whats-new"></a>Novedades

- Se ha corregido el nivel de seguimiento MpCmdRun
- Se ha corregido la información de la versión de WDFilter.
- Mejora de las notificaciones (PUA)
- agregar registros mrt para admitir archivos

### <a name="known-issues"></a>Problemas conocidos
Cuando se instala esta actualización, el dispositivo necesita el paquete de salto 4.18.2001.10 para poder actualizar a la versión más reciente de la plataforma.
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a>compatibilidad con la plataforma Antivirus de Microsoft Defender

Las actualizaciones de la plataforma y del motor se proporcionan con una cadencia mensual. Para ser totalmente compatible, manténgase al día con las últimas actualizaciones de la plataforma. Nuestra estructura de soporte técnico es dinámica, evolucionando en dos fases en función de la disponibilidad de la última versión de la plataforma:

- **Fase de mantenimiento de actualizaciones críticas y de seguridad** : al ejecutar la versión más reciente de la plataforma, podrá recibir actualizaciones de seguridad y críticas en la plataforma antimalware.

- **Fase de soporte técnico (solo):** una vez publicada una nueva versión de la plataforma, la compatibilidad con versiones anteriores (N-2) solo se reducirá al soporte técnico. Ya no se admitirán versiones de plataforma anteriores a N-2.*

\*El soporte técnico seguirá proporcionándose para las actualizaciones de la versión de Windows 10 versión (consulte Versión de la [plataforma incluida con las versiones de Windows 10](#platform-version-included-with-windows-10-releases)) a la versión más reciente de la plataforma.

Durante la fase de soporte técnico (solo), los incidentes de soporte técnico comercialmente razonables se proporcionarán a través del servicio de atención al cliente de Microsoft & soporte técnico y las ofertas de soporte técnico administrado de Microsoft (por ejemplo, soporte técnico Premier). Si un incidente de soporte técnico requiere una ampliación al desarrollo para obtener más instrucciones, requiere una actualización que no sea de seguridad o requiere una actualización de seguridad, se pedirá a los clientes que actualicen a la versión más reciente de la plataforma o una actualización intermedia (*).

> [!NOTE]
> Si va a implementar manualmente Antivirus de Microsoft Defender Platform Update o si usa un script o un producto de administración que no es de Microsoft para implementar Antivirus de Microsoft Defender Platform Update, asegúrese de que la versión `4.18.2001.10` está instalada desde el [catálogo de Microsoft Update](https://www.catalog.update.microsoft.com/Search.aspx?q=4.18.2001.10).  antes de instalar la versión más reciente de Platform Update (N-2).

### <a name="platform-version-included-with-windows-10-releases"></a>Versión de la plataforma incluida con versiones de Windows 10

En la tabla siguiente se proporcionan las versiones de motor y plataforma de Antivirus de Microsoft Defender que se incluyen con las versiones de Windows 10 más recientes:<br/><br/>

|Windows 10 versión  |Versión de la plataforma  |Versión del motor |Fase de soporte técnico |
|:---|:---|:---|:---|
|2004 (20H1/20H2) |4.18.1909.6 |1.1.17000.2 | Soporte técnico de actualización (solo) |
|1909 (19H2) |4.18.1902.5 |1.1.16700.3 | Soporte técnico de actualización (solo) |
|1903 (19H1) |4.18.1902.5 |1.1.15600.4 | Soporte técnico de actualización (solo) |
|1809 (RS5) |4.18.1807.18075 |1.1.15000.2 | Soporte técnico de actualización (solo) |
|1803 (RS4) |4.13.17134.1 |1.1.14600.4 | Soporte técnico de actualización (solo) |
|1709 (RS3) |4.12.16299.15 |1.1.14104.0 | Soporte técnico de actualización (solo) |
|1703 (RS2) |4.11.15603.2 |1.1.13504.0 | Soporte técnico de actualización (solo) |
|1607 (RS1) |4.10.14393.3683 |1.1.12805.0 | Soporte técnico de actualización (solo) |

Para obtener Windows 10 información de versión, consulte la [hoja de hechos del ciclo de vida de Windows](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a>Actualizaciones para el mantenimiento y la administración de imágenes de implementación (DISM)

Se recomienda actualizar los Windows 10 (ediciones Enterprise, Pro y Home), Windows Server 2019, Windows Server 2022 e imágenes de instalación del sistema operativo Windows Server 2016 con las actualizaciones antivirus y antimalware más recientes. Mantener actualizadas las imágenes de instalación del sistema operativo ayuda a evitar una brecha en la protección.

Para obtener más información, consulte [Actualización de Microsoft Defender para Windows imágenes de instalación del sistema operativo](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).

<details>
<summary>20220321.1</summary>

&ensp;Versión del paquete: **2020321.1**<br/>
&ensp;Versión de la plataforma: **4.18.2202.4**<br/>
&ensp;Versión del motor: **1.1.19000.8**<br/>
&ensp;Versión de firma: **1.351.337.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno

<br/>
</details><details>
<summary>20220305.1</summary>

&ensp;Versión del paquete: **20220305.1**<br/>
&ensp;Versión de la plataforma: **4.18.2201.10**<br/>
&ensp;Versión del motor: **1.1.18900.3**<br/>
&ensp;Versión de firma: **1.359.1405.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno

<br/>
</details><details>
<summary>20220203.1</summary>

&ensp;Versión del paquete: **2020203.1**<br/>
&ensp;Versión de la plataforma: **4.18.2111.5**<br/>
&ensp;Versión del motor: **1.1.18900.2**<br/>
&ensp;Versión de firma: **1.357.32.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno
<br/>
</details><details>
<summary>20220105.1</summary>

&ensp;Versión del paquete: **20220105.1**<br/>
&ensp;Versión de la plataforma: **4.18.2111.5**<br/>
&ensp;Versión del motor: **1.1.18800.4**<br/>
&ensp;Versión de firma: **1.355.1482.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno
<br/>
</details><details>
<summary>1.1.2112.01</summary>

&ensp;Versión del paquete: **1.1.2112.01**<br/>
&ensp;Versión de la plataforma: **4.18.2110.6**<br/>
&ensp;Versión del motor: **1.1.18700.4**<br/>
&ensp;Versión de firma: **1.353.2283.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno
<br/>
</details><details>
<summary>1.1.2111.02</summary>

&ensp;Versión del paquete: **1.1.2111.02**<br/>
&ensp;Versión de la plataforma: **4.18.2110.6**<br/>
&ensp;Versión del motor: **1.1.18700.4**<br/>
&ensp;Versión de firma: **1.353.613.0**<br/>

### <a name="fixes"></a>Correcciones
- Se ha corregido un problema relacionado con los archivos de localización

### <a name="additional-information"></a>Información adicional
- Ninguno
<br/>
</details><details>
<summary>1.1.2110.01</summary>

&ensp;Versión del paquete: **1.1.2110.01**<br/>
&ensp;Versión de la plataforma: **4.18.2109.6**<br/>
&ensp;Versión del motor: **1.1.18500.10**<br/>
&ensp;Versión de firma: **1.349.2103.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno
<br/>
</details><details>
<summary>1.1.2109.01</summary>

&ensp;Versión del paquete: **1.1.2109.01**<br/>
&ensp;Versión de la plataforma: **4.18.2107.4**<br/>
&ensp;Versión del motor: **1.1.18400.5**<br/>
&ensp;Versión de firma: **1.347.891.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno
<br/>
</details><details>
<summary>1.1.2108.01</summary>

&ensp;Versión del paquete: **1.1.2108.01**<br/>
&ensp;Versión de la plataforma: **4.18.2107.4**<br/>
&ensp;Versión del motor: **1.1.18300.4**<br/>
&ensp;Versión de firma: **1.343.2244.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno
<br/>
</details><details>
<summary>1.1.2107.02</summary>

&ensp;Versión del paquete: **1.1.2107.02**<br/>
&ensp;Versión de la plataforma: **4.18.2105.5**<br/>
&ensp;Versión del motor: **1.1.18300.4**<br/>
&ensp;Versión de firma: **1.343.658.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno
<br/>
</details><details>
<summary>1.1.2106.01</summary>

&ensp;Versión del paquete: **1.1.2106.01**<br/>
&ensp;Versión de la plataforma: **4.18.2104.14**<br/>
&ensp;Versión del motor: **1.1.18100.6**<br/>
&ensp;Versión de firma: **1.339.1923.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno
<br/>
</details><details>
<summary>1.1.2105.01</summary>

&ensp;Versión del paquete: **1.1.2105.01**<br/>
&ensp;Versión de la plataforma: **4.18.2103.7**<br/>
&ensp;Versión del motor: **1.1.18100.6**<br/>
&ensp;Versión de firma: **1.339.42.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno
<br/>
</details><details>
<summary>1.1.2104.01</summary>

&ensp;Versión del paquete: **1.1.2104.01**<br/>
&ensp;Versión de la plataforma: **4.18.2102.4**<br/>
&ensp;Versión del motor: **1.1.18000.5**<br/>
&ensp;Versión de firma: **1.335.232.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno
<br/>
</details><details>
<summary>1.1.2103.01</summary>

&ensp;Versión del paquete: **1.1.2103.01**<br/>
&ensp;Versión de la plataforma: **4.18.2101.9**<br/>
&ensp;Versión del motor: **1.1.17800.5**<br/>
&ensp;Versión de firma: **1.331.2302.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno
<br/>
</details><details>
<summary>1.1.2102.03</summary>

&ensp;Versión del paquete: **1.1.2102.03**<br/>
&ensp;Versión de la plataforma: **4.18.2011.6**<br/>
&ensp;Versión del motor: **1.1.17800.5**<br/>
&ensp;Versión de firma: **1.331.174.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno
<br/>
</details><details>
<summary>1.1.2101.02</summary>

&ensp;Versión del paquete: **1.1.2101.02**<br/>
&ensp;Versión de la plataforma: **4.18.2011.6**<br/>
&ensp;Versión del motor: **1.1.17700.4**<br/>
&ensp;Versión de firma: **1.329.1796.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno
<br/>
</details><details>
<summary>1.1.2012.01</summary>

&ensp;Versión del paquete: **1.1.2012.01**<br/>
&ensp;Versión de la plataforma: **4.18.2010.7**<br/>
&ensp;Versión del motor: **1.1.17600.5**<br/>
&ensp;Versión de firma: **1.327.1991.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno
<br/>
</details><details>
<summary>1.1.2011.02</summary>

&ensp;Versión del paquete: **1.1.2011.02**<br/>
&ensp;Versión de la plataforma: **4.18.2010.7**<br/>
&ensp;Versión del motor: **1.1.17600.5**<br/>
&ensp;Versión de firma: **1.327.658.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Firmas de Antivirus de Microsoft Defender actualizadas
<br/>
</details><details>
<summary>1.1.2011.01</summary>

&ensp;Versión del paquete: **1.1.2011.01**<br/>
&ensp;Versión de la plataforma: **4.18.2009.7**<br/>
&ensp;Versión del motor: **1.1.17600.5**<br/>
&ensp;Versión de firma: **1.327.344.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno
<br/>
</details><details>
<summary>1.1.2009.10</summary>

&ensp;Versión del paquete: **1.1.2011.01**<br/>
&ensp;Versión de la plataforma: **4.18.2008.9**<br/>
&ensp;Versión del motor: **1.1.17400.5**<br/>
&ensp;Versión de firma: **1.327.2216.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Se ha agregado compatibilidad con Windows 10 imágenes de instalación del sistema operativo RS1 o posterior.
<br/>
</details>

## <a name="more-resources"></a>Más recursos

| Artículo | Descripción  |
|:---|:---|
|[Actualización de Microsoft Defender para Windows imágenes de instalación del sistema operativo](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | Revise los paquetes de actualización antimalware para las imágenes de instalación del sistema operativo (archivos WIM y VHD). Obtener actualizaciones de Antivirus de Microsoft Defender para Windows 10 (ediciones Enterprise, Pro y Home), Windows Server 2019, Windows Server 2022 e instalación de Windows Server 2016 Imágenes.  |
|[Administrar cómo se descargan y aplican las actualizaciones de protección](manage-protection-updates-microsoft-defender-antivirus.md) | Las actualizaciones de protección se pueden entregar a través de muchos orígenes. |
|[Administrar cuándo se deben descargar y aplicar las actualizaciones de protección](manage-protection-update-schedule-microsoft-defender-antivirus.md) | Puede programar cuándo se deben descargar las actualizaciones de protección. |
|[Administrar las actualizaciones de los puntos de conexión que están obsoletos](manage-outdated-endpoints-microsoft-defender-antivirus.md) | Si un punto de conexión no realiza una actualización o un examen programado, puede forzar una actualización o examinarla la próxima vez que un usuario inicie sesión. |
|[Administrar las actualizaciones forzadas basadas en eventos](manage-event-based-updates-microsoft-defender-antivirus.md) | Puede establecer que las actualizaciones de protección se descarguen al iniciar o después de determinados eventos de protección entregados en la nube. |
|[Administrar las actualizaciones de dispositivos móviles y máquinas virtuales](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| Puede especificar la configuración, como si se deben producir actualizaciones en la batería, que son especialmente útiles para dispositivos móviles y máquinas virtuales. |
| [actualización de Microsoft Defender para punto de conexión para EDR Sensor](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac) | Puede actualizar el sensor de EDR (MsSense.exe) que se incluye en el nuevo paquete de solución unificada Microsoft Defender para punto de conexión publicado en 2021.   |
