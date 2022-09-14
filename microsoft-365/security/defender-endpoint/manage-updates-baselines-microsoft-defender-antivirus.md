---
title: Para obtener más información, consulte Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar bases de referencia.
description: Administrar cómo Antivirus de Microsoft Defender recibe actualizaciones de productos y protección.
keywords: actualizaciones, líneas base de seguridad, protección, programar actualizaciones, forzar actualizaciones, actualizaciones móviles, wsus
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: high
ms.date: 09/13/2022
audience: ITPro
ms.topic: reference
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr, mkaminska, v-vutrieu
manager: dansimp
ms.subservice: mde
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: 24b5d6be3e4b0a226617623b68c49d2043475045
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67672235"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a>Para obtener más información, consulte Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar bases de referencia.

**Se aplica a:**
- [Microsoft Defender para punto de conexión, planes 1 y 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Mantener Antivirus de Microsoft Defender actualizados es fundamental para garantizar que los dispositivos tengan la tecnología y las características más recientes necesarias para protegerse frente a nuevas técnicas de ataque y malware. Asegúrese de actualizar la protección antivirus, incluso si Antivirus de Microsoft Defender se ejecuta en [ modo pasivo](microsoft-defender-antivirus-compatibility.md). Existen dos tipos de actualizaciones vinculadas a mantener el Antivirus de Microsoft Defender al día:

- [Actualizaciones de inteligencia de seguridad](#security-intelligence-updates)
- [Actualizaciones de productos](#product-updates)

> [!TIP]
> Para ver el motor, la plataforma y la fecha de la firma más recientes, visite las [Actualizaciones de inteligencia de seguridad para Antivirus de Microsoft Defender y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates) 

## <a name="security-intelligence-updates"></a>Actualizaciones de inteligencia de seguridad

El Antivirus de Microsoft Defender utiliza la [protección suministrada por la nube](cloud-protection-microsoft-defender-antivirus.md) (también llamada Servicio de Protección Avanzada de Microsoft o MAPS) y descarga de forma periódica las actualizaciones dinámicas de inteligencia de seguridad para proporcionar más protección. Estas actualizaciones dinámicas no reemplazan las actualizaciones regulares de inteligencia de seguridad realizadas a través de la actualización de inteligencia de seguridad KB2267602.

> [!NOTE]
> Las actualizaciones se publican en los siguientes KB:
> - Antivirus de Microsoft Defender: KB2267602
> - System Center Endpoint Protection: KB2461484

La protección de entrega en la nube siempre está activada y requiere una conexión activa a Internet para funcionar. Las actualizaciones de inteligencia de seguridad se producen en una cadencia programada (configurable a través de la directiva). Para obtener más información, consulte [Usar la protección proporcionada por la nube de Microsoft en Antivirus de Microsoft Defender ](cloud-protection-microsoft-defender-antivirus.md).

Para obtener una lista de las actualizaciones recientes de inteligencia de seguridad, consulte [Las actualizaciones de inteligencia de seguridad para Antivirus de Microsoft Defender y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates).

Las actualizaciones del motor están incluidas en las actualizaciones de inteligencia de seguridad y son publicadas mensualmente.

## <a name="product-updates"></a>Actualizaciones de productos

Antivirus de Microsoft Defender requiere [actualizaciones mensuales (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) conocidas como *actualizaciones de plataforma*.

Puede administrar la distribución de actualizaciones a través de uno de los métodos siguientes:

- [Servicio de actualización de Windows Server (WSUS)](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/sum/understand/software-updates-introduction)
- El método habitual que se usa para implementar actualizaciones de Microsoft y Windows en los puntos de conexión de la red.

Para obtener más información, consulte [Administrar los orígenes de las actualizaciones de protección Antivirus de Microsoft Defender](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).

> [!NOTE]
> - Las actualizaciones mensuales se publican en fases, lo que da como resultado varios paquetes visibles en el [Servicios de actualización de Window Server](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).
> - En este artículo se enumeran los cambios que se incluyen en el canal de lanzamiento general. [Vea la última versión general del canal aquí](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info).
> - Para obtener más información sobre el proceso de lanzamiento gradual y ver más información sobre la próxima versión, consulte [Administrar el proceso de lanzamiento gradual de las actualizaciones de Microsoft Defender](manage-gradual-rollout.md).
> - Para obtener más información sobre las actualizaciones de inteligencia de seguridad, consulte [Actualizaciones de inteligencia de seguridad para Antivirus de Microsoft Defender y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates).
> - Si busca una lista de procesos de Microsoft Defender, **[descargue el libro mde-urls](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)** y a continuación seleccione la hoja de cálculo **Procesos de Microsoft Defender**. El libro mde-urls también enumera los servicios y sus direcciones URL asociadas a las que la red debe poder conectarse, como se describe en [Habilitar el acceso a las direcciones URL del servicio Microsoft Defender para punto de conexión en el servidor proxy](configure-proxy-internet.md).

## <a name="monthly-platform-and-engine-versions"></a>Versiones mensuales de plataforma y motor

Para obtener información sobre cómo actualizar o instalar la actualización de la plataforma, consulte [Actualizar para Windows Defender plataforma antimalware](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).

Todas nuestras actualizaciones contienen

- Mejoras en el rendimiento
- Mejoras en la capacidad de servicio
- Mejoras de integración (nube, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender))
<br/><br/>
<details>
<summary>Agosto de 2022 (Plataforma: 4.18.2207.7 | Motor: 1.1.19600.3)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.373.1647.0**<br/>
&ensp;Fecha de lanzamiento: **6 de septiembre de 2022**<br/>
&ensp;Plataforma: **4.18.2207.7**<br/>
&ensp;Motor: **1.1.19600.3**<br/>
&ensp;Fase de soporte técnico: **Actualizaciones críticas y de seguridad**<br/>

Versión del motor: 1.1.19600.3<br/>
Versión de actualización de inteligencia de seguridad: 1.373.1647.0 <br/>

### <a name="whats-new"></a>Novedades

- Se han corregido problemas del instalador del agente unificado en el servidor WS2012R2 y Windows Server 2016
- Se ha corregido un problema de corrección para la detección personalizada.
- Condición de carrera fija relacionada con la supervisión del comportamiento
- Se han resuelto varios escenarios de interbloqueo en archivos dll de Defender
- Frecuencia mejorada de notificación del sistema de Windows para las reglas de ASR

### <a name="known-issues"></a>Problemas conocidos

- Ninguno

<br/><br/>
</details><details>
<summary>Julio-2022 (Plataforma: 4.18.2207.5 | Motor: 1.1.19500.2)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.373.219.0**<br/>
&ensp;Fecha de lanzamiento: **15 de agosto de 2022**<br/>
&ensp;Plataforma: **4.18.2207.5**<br/>
&ensp;Motor: **1.1.19500.2**<br/>
&ensp;Fase de soporte técnico: **Actualizaciones críticas y de seguridad**<br/>

Versión del motor: 1.1.19300.2<br/>
Versión de actualización de inteligencia de seguridad: 1.373.219.0 <br/>

### <a name="whats-new"></a>Novedades

- Mejora del rendimiento del retraso de [suspensión híbrida](/windows-hardware/customize/power-settings/sleep-settings-hybrid-sleep) cuando el Antivirus de Microsoft Defender está activo 
- Se ha corregido el comportamiento de detección de clientes relacionado con [indicadores de riesgo de bloqueo de certificados personalizados](indicator-certificates.md) 
- Mejora del rendimiento del almacenamiento en caché de la [interfaz de examen de antimalware (AMSI)](/windows/win32/amsi/antimalware-scan-interface-portal) 
- Detección y corrección mejoradas para macros relacionadas con [Microsoft Visual Basic para Aplicaciones](/office/vba/language/concepts/getting-started/64-bit-visual-basic-for-applications-overview) (VBA) 
- Procesamiento mejorado de exclusiones de AMSI 
- Se ha corregido la detección de interbloqueos en el procesamiento de reglas del Sistema de prevención de intrusiones de host (HIPS). (Para obtener información adicional sobre HIPS y Defender para punto de conexión, vea [Migrar de un HIPS de terceros a reglas de ASR](migrating-asr-rules.md)). 
- Se ha corregido una fuga de memoria en la que `MsMpEng.exe` consumía bytes privados. (Si el uso elevado de CPU también es un problema, consulte [Uso elevado de CPU debido al Antivirus de Microsoft Defender](troubleshooting-mode-scenarios.md)). 
- Se ha corregido el interbloqueo con la [supervisión del comportamiento](configure-real-time-protection-microsoft-defender-antivirus.md) 
- Validación de confianza mejorada 
- Se ha corregido un problema de bloqueo del motor en plataformas operativas heredadas 
- Actualizaciones del analizador de rendimiento, versión 3: se ha agregado compatibilidad con la ruta de acceso principal, información de omisión de exámenes y compatibilidad con el examen bajo demanda. Consulte [Analizador de rendimiento para Antivirus de Microsoft Defender](tune-performance-defender-antivirus.md). 
- Mejoras en el rendimiento de Defender durante las operaciones de copia de archivos
- Mejoras agregadas para el [modo de solución de problemas](enable-troubleshooting-mode.md)  
- Se ha agregado una corrección para los canales WINEVT de Defender en las actualizaciones o reinicios. (Consulte [Registro de eventos de Windows](/windows/win32/api/_wes/) para obtener más información sobre WINEVT).
- Se ha agregado una corrección para el error [de administración de WMI de Defender](use-wmi-microsoft-defender-antivirus.md) durante el inicio o las actualizaciones. 
- Se ha agregado una corrección para la versión 2010/2011 duplicada en los [eventos operativos de Windows Visor de eventos](troubleshoot-microsoft-defender-antivirus.md) 
- Se ha agregado compatibilidad con la protección de tokens de procesos de pila de [Defender para punto de conexión](microsoft-defender-endpoint.md) . 


### <a name="known-issues"></a>Problemas conocidos

- Los clientes que implementan la actualización de plataforma 4.18.2207.5 pueden experimentar retrasos en el rendimiento de red que podrían afectar a las aplicaciones.

<br/><br/>
</details><details>
<summary>Mayo de 2022 (Plataforma: 4.18.2205.7 | Motor: 1.1.19300.2)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.369.88.0**<br/>
&ensp;Publicación:**22 de junio de 2022**<br/>
&ensp;Plataforma: **4.18.2205.7**<br/>
&ensp;Motor: **1.1.19300.2**<br/>
&ensp;Fase de soporte técnico: **Actualizaciones críticas y de seguridad**<br/>

Versión del motor: 1.1.19300.2<br/>
Versión de actualización de inteligencia de seguridad: 1.369.88.0<br/>

### <a name="whats-new"></a>Novedades

- Se ha agregado una corrección para la configuración del canal ETW para las actualizaciones. 
- Se ha agregado compatibilidad con exclusiones contextuales que permiten una segmentación de exclusión más específica. 
- Tamaño máximo de contexto fijo
- Se ha agregado una corrección para la [detección de ASR LSASS](attack-surface-reduction-rules-reference.md)
- Se ha agregado una corrección a SHSetKnownFolder para la lógica de exclusión de reglas.
- Se han agregado límites de uso de disco de AMSI para el almacén de historial
- Se ha agregado una corrección para que el servicio Defender rechace aceptar actualizaciones de firma

### <a name="known-issues"></a>Problemas conocidos

No hay problemas conocidos

<br/><br/>
</details>


### <a name="previous-version-updates-technical-upgrade-support-only"></a>Actualizaciones de la versión anterior: solo soporte técnico para actualizaciones técnicas

Una vez publicada la nueva versión del paquete, la compatibilidad con las dos versiones anteriores se reduce solo al soporte técnico. Las versiones anteriores a ésta se enumeran en esta sección, y solo se proporcionan para el apoyo técnico de actualización.<br/><br/>

<details>
<summary>Marzo 2022 *ACTUALIZACIÓN* (plataforma: 4.18.2203.5 | Motor: 1.1.19200.5)</summary>

*Los clientes que aplicaron la actualización del motor de Microsoft Defender de marzo de 2022 (**1.1.19100.5**) podrían haber encontrado un uso elevado de recursos (CPU o memoria). Microsoft ha publicado una actualización (**1.1.19200.5**) que resuelve los errores introducidos en la versión anterior. Se recomienda a los clientes actualizar al menos a esta nueva compilación de motor de Antivirus Engine (**1.1.19200.5**). Para asegurarse de que los problemas de rendimiento están totalmente corregidos, se recomienda reiniciar los equipos después de aplicar la actualización.*

&ensp;Versión de actualización de inteligencia de seguridad: **1.363.817.0**<br/>
&ensp;Publicación:**22 de abril de 2022**<br/>
&ensp;Plataforma: **4.18.2203.5**<br/>
&ensp;Motor: **1.1.19200.5**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

Versión del motor: 1.1.19200.5 <br/>
Versión de actualización de inteligencia de seguridad: 1.363.817.0<br/>

### <a name="whats-new"></a>Novedades

- Resuelve problemas con un uso elevado de recursos (CPU o memoria) relacionados con la actualización anterior del motor de Microsoft Defender de marzo de 2022 (1.1.19100.5)

### <a name="known-issues"></a>Problemas conocidos

No hay problemas conocidos

<br/><br/>
</details><details>
<summary>Marzo-2022 (plataforma: 4.18.2203.5 | Motor: 1.1.19100.5)</summary>

&ensp;Versión de actualización de inteligencia de seguridad de: **1.361.1449.0**<br/>
&ensp;Publicación:**7 de abril de 2022**<br/>
&ensp;Plataforma: **4.18.2203.5**<br/>
&ensp;Motor: **1.1.19100.5**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

Versión del motor: 1.1.19100.5 <br/>
Versión de actualización de inteligencia de seguridad: 1.361.1449.0<br/>

### <a name="whats-new"></a>Novedades

- Se ha agregado una corrección para una [regla de reducción de la superficie expuesta a ataques](attack-surface-reduction.md) que bloqueaba un complemento de Outlook. 
- Se ha agregado una corrección para la [supervisión de comportamiento](configure-protection-features-microsoft-defender-antivirus.md) del problema de rendimiento relacionado con procesos activos cortos. 
- Se ha agregado una corrección para la exclusión de [AMSI](/windows/win32/amsi/antimalware-scan-interface-portal) 
- Capacidades mejoradas de [protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md) 
- Se ha agregado una corrección para la[protección en tiempo real](configure-protection-features-microsoft-defender-antivirus.md) donde en algunos casos se deshabilite al usar la configuración `SharedSignaturesPath`. Para obtener más información sobre el parámetro `SharedSignaturesPath`, consulte [set-MpPreference](/powershell/module/defender/set-mppreference).

### <a name="known-issues"></a>Problemas conocidos

- Potencial para un uso elevado de recursos (CPU y/o memoria). Consulte la actualización plataforma 4.18.2203.5 y motor 1.1.19200.5 para marzo de 2022.

<br/><br/>
</details><details>
<summary>Febrero de 2022 (plataforma: 4.18.2202.4 | Motor: 1.1.19000.8)</summary>

&ensp;Versión actualizada de la inteligencia de seguridad: **1.361.14.0**<br/>
&ensp;Publicado: **14 de marzo de 2022**<br/>
&ensp;Plataforma: **4.18.2202.4**<br/>
&ensp;Motor: **1.1.19000.8**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

Versión del motor: 1.1.19000.8 <br/>
Versión de actualización de inteligencia de seguridad: 1.361.14.0 <br/>

### <a name="whats-new"></a>Novedades

- Mejoras en la lógica de detección y supervisión del comportamiento
- Se han corregidos falsos positivos que desencadenan detecciones de reducción de superficie expuesta a ataques
- Se ha agregado una corrección que da como resultado una mayor fidelidad de las alertas de detección de búsqueda avanzada y EDR
- Defender ha dejado de admitir notificaciones personalizadas en los elementos emergentes de notificaciones del sistema. Se han modificado GPO/Intune/SCCM y documentos para reflejar este cambio.
- Mejoras para capturar tanto la información como la copia de los archivos escritos en un almacenamiento extraíble. Para obtener más información, consulte [Control de acceso de almacenamiento extraíble de Control de dispositivos de Microsoft Defender para punto de conexión, medios de almacenamiento extraíbles](device-control-removable-storage-access-control.md).  
- Salida de tráfico mejorada cuando no se puede acceder al servicio SmartScreen 
- Mejoras de conectividad para los clientes que usan servidores proxy con requisitos de autenticación
- Se ha corregido un error de actualización del dispositivo VDI para FileShares de red. 
- EDR en modo de bloque ahora admite la selección de destino de dispositivos pormenorizada con nuevos CSP. Consulte [Detección y respuesta de puntos de conexión (EDR) en modo de bloqueo](edr-in-block-mode.md).

### <a name="known-issues"></a>Problemas conocidos

No hay problemas conocidos

<br/><br/>
</details><details>
<summary>Enero-2022 (plataforma: 4.18.2201.10 | Motor: 1.1.18900.2)</summary>

&ensp;Versión actualizada de inteligencia de seguridad: **1.357.8.0**<br/>
&ensp;Publicado:**9 de febrero de 2022**<br/>
&ensp;Plataforma :**4.18.2201.10**<br/>
&ensp;Motor: **1.1.18900.2**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

Versión del motor: 1.1.18900.2 <br/>
Versión de actualización de inteligencia de seguridad: 1.357.8.0 <br/>

### <a name="whats-new"></a>Novedades

- Mejoras en la supervisión del comportamiento en el rendimiento del filtrado
- Protección de TrustedInstaller
- Mejoras en la protección contra alteraciones
- Se ha reemplazado `ScanScheduleTime` con un nuevo `ScanScheduleOffest`cmdlet en [Set-MpPreference](/powershell/module/defender/set-mppreference). Esta directiva configura el número de minutos después de la medianoche para hacer un escaneo digitalizado.
- Se ha agregado la configuración de `-ServiceHealthReportInterval` a [Set-MpPreference](/powershell/module/defender/set-mppreference). Esta instrucción configura el intervalo de tiempo (en minutos) para realizar un análisis programado. 
- Se ha agregado la configuración de `AllowSwitchToAsyncInspection` a [Set-MpPreference](/powershell/module/defender/set-mppreference). Esta directiva permite una optimización del rendimiento, que permite que los flujos de red inspeccionados sincrónicamente, cambien a la inspección asincrónica una vez que se han comprobado y validado.
- Actualizaciones del analizador de rendimiento v2: se ha agregado compatibilidad con PowerShell remoto y PowerShell 7.x. Consulte [Analizador de rendimiento para Antivirus de Microsoft Defender](tune-performance-defender-antivirus.md).
- Se ha corregido un posible error de duplicación de paquetes en el controlador del sistema de inspección de red de Antivirus de Microsoft Defender.

### <a name="known-issues"></a>Problemas conocidos

No hay problemas conocidos

<br/><br/>
</details><details>
<summary>Noviembre de 2021 (plataforma: 4.18.2111.5 | Motor: 1.1.18800.4)</summary>

&ensp; Versión de actualización de inteligencia de seguridad: **1.355.2.0**<br/>
&ensp;Publicado: **9 de diciembre de 2021**<br/>
&ensp;Plataforma: **4.18.2111.5**<br/>
&ensp;Motor: **1.1.18800.4**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

Versión del motor: 1.1.18800.4 Versión de actualización de inteligencia de seguridad: 1.355.2.0

### <a name="whats-new"></a>Novedades

- Mejora de la eficiencia del uso de CPU en determinados escenarios intensivos en servidores de Exchange
- Se agregaron nuevos campos de estado de control de dispositivo en Get-MpComputerStatus en el módulo de PowerShell de Defender. Para obtener más información, consulte [Control de acceso de almacenamiento extraíble de Control de dispositivos de Microsoft Defender para punto de conexión, medios de almacenamiento extraíbles](device-control-removable-storage-access-control.md).
- Se ha corregido un error en el que no se podía quitar el valor `SharedSignatureRoot` cuando se establecía con PowerShell.
- Se ha corregido un error en el que [protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md) no se habilitaba, aunque Microsoft Defender para punto de conexión indicaba que la protección contra alteraciones estaba activada
- Se ha agregado compatibilidad y corrección de errores al analizador de rendimiento de la herramienta de Antivirus de Microsoft Defender. Para obtener más información, consulte [Analizador de rendimiento para el Antivirus de Microsoft Defender](tune-performance-defender-antivirus.md).   
   - Se ha agregado soporte con PowerShell ISE para `New-MpPerformanceRecording`
   - Se han corregido errores de error para `Get-MpPerformanceReport -TopFilesPerProcess`
   - Se ha corregido la pérdida de sesión de grabación de rendimiento al usar `New-MpPerformanceRecording` en PowerShell 7.x, sesiones remotas e ISE de PowerShell


### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Octubre de 2021 (plataforma: 4.18.2110.6 | Motor: 1.1.18700.4)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.353.3.0**<br/>
&ensp;Publicado:**28 de octubre de 2021**<br/>
&ensp;Plataforma: **4.18.2110.6**<br/>
&ensp;Motor: **1.1.18700.4**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

Versión del motor: 1.1.18700.4 Versión de actualización de inteligencia de seguridad: 1.353.3.0

### <a name="whats-new"></a>Novedades

- Mejoras en la cobertura de tráfico de red del protocolo de transferencia de archivos (FTP)
- Corrección para reducir el uso de CPU de Microsoft Defender en Exchange Server que se ejecuta en Windows Server 2016
- Corrección de interrupciones del análisis
- Corrección de alertas sobre intentos de manipulación bloqueados que no aparecen en Security Center
- Mejoras en la resistencia a alteraciones en el servicio Microsoft Defender

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Septiembre de 2021 (plataforma: 4.18.2109.6 | Motor: 1.1.18600.4)</summary>

&ensp;Versión de actualización de inteligencia de seguridad:: **1.351.7.0**<br/>
&ensp;Publicado:**7 de octubre de 2021**<br/>
&ensp;Plataforma: **4.18.2109.6**<br/>
&ensp;Motor: **1.1.18600.4**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

Versión del motor: 1.1.18600.4 Versión de actualización de inteligencia de seguridad: 1.351.7.0

### <a name="whats-new"></a>Novedades
- Nuevo anillo de retraso para el motor Antivirus de Microsoft Defender y las actualizaciones de la plataforma. Los dispositivos que opten por este anillo recibirán actualizaciones con un retraso de 48 horas. El nuevo anillo de retraso solo se sugiere para entornos críticos. Para más información [gestionar el proceso de despliegue gradual de las actualizaciones del Antivirus de Microsoft Defender.](manage-gradual-rollout.md).
- Mejoras en el proceso de implementación gradual de actualizaciones de Microsoft Defender

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Agosto de 2021 (plataforma: 4.18.2108.7 | Motor: 1.1.18500.10)</summary>

&ensp; Versión de actualización de inteligencia de seguridad: **1.349.22.0**<br/>
&ensp;Publicado:**2 de septiembre de 2021**<br/>
&ensp;Plataforma: **4.18.2108.7**<br/>
&ensp;Motor: **1.1.18500.10**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

### <a name="whats-new"></a>Novedades
- Mejoras en el motor de supervisión de comportamiento
- Se publicó un nuevo [analizador de rendimiento para Antivirus de Microsoft Defender](tune-performance-defender-antivirus.md)
- Antivirus de Microsoft Defender protegido contra la carga de archivos DLL maliciosos
- Antivirus de Microsoft Defender protegido contra la omisión de TrustedInstaller
- Ampliación de las notificaciones de cambio de archivo para incluir más datos para Ransomware operado por humanos (HumOR)

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Julio de 2021 (plataforma: 4.18.2107.4 | Motor: 1.1.18400.4)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.345.13.0**<br/>
&ensp;Publicación:**5 de abril de 2021**<br/>
&ensp;Plataforma: **4.18.2107.4**<br/>
&ensp;Motor: **1.1.18400.4**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

### <a name="whats-new"></a>Novedades
- Se ha añadido soporte de control de dispositivos para los dispositivos portátiles de Windows
- La protección de aplicaciones potencialmente no deseadas (PUA) está activada de forma predeterminada para los consumidores (consulte [Bloquear aplicaciones potencialmente no deseadas con Antivirus de Microsoft Defender](/microsoft-365/security/defender-endpoint/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)).
- Los análisis programados para los sistemas gestionados por objetos de política de grupo se ajustarán a la hora de análisis configurada por el usuario
- Mejoras en el motor de supervisión de comportamiento

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos

<br/>
</details><details>
<summary> Junio de 2021 (plataforma: 4.18.2106.5 | Motor: 1.1.18300.4)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.343.17.0**<br/>
&ensp;Publicación:**28 de junio de 2021**<br/>
&ensp;Plataforma: **4.18.2106.5**<br/>
&ensp;Motor: **1.1.18300.4**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

### <a name="whats-new"></a>Novedades
- Nuevos controles para administrar el proceso de implementación gradual de las actualizaciones de Microsoft Defender. Para más información [gestionar el proceso de despliegue gradual de las actualizaciones del Antivirus de Microsoft Defender.](manage-gradual-rollout.md).
- Mejora del motor de supervisión de comportamiento
- Mejoras en la implementación de definiciones de antimalware
- Inspecciones de eventos de la red Extended Edge

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Mayo de 2021 (plataforma: 4.18.2105.4 | Motor: 1.1.18200.4)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.341.8.0**<br/>
&ensp;Publicación:**3 de junio de 2021**<br/>
&ensp;Plataforma: **4.18.2105.4**<br/>
&ensp;Motor: **1.1.18200.4**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

### <a name="whats-new"></a>Novedades
- Mejoras en la [supervisión del comportamiento](client-behavioral-blocking.md)
- Se ha corregido [característica de filtrado de notificaciones de](network-protection.md) protección de red

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Abril de 2021 (plataforma: 4.18.2104.14 | Motor: 1.1.18100.5)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.337.2.0**<br/>
&ensp;Publicado: **26 de abril de 2021**  (Motor: 1.1.18100.6 publicado el 5 de mayo de 2021)<br/>
&ensp;Plataforma: **4.18.2104.14**<br/>
&ensp;Motor: **1.1.18100.5**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

### <a name="whats-new"></a>Novedades
- Más lógica de supervisión de comportamiento
- Detección mejorada del registrador de claves en modo kernel
- Se han añadido nuevos controles para gestionar el proceso de despliegue gradual de [ las actualizaciones Antivirus Microsoft Defender](manage-gradual-rollout.md)


### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Marzo de 2021 (plataforma: 4.18.2103.7 | Motor: 1.1.18000.5)</summary>

&ensp;Versión de actualización de inteligencia de seguridad:: **1.335.36.0**<br/>
&ensp;Publicación:**2 de abril de 2021**<br/>
&ensp;Plataforma: **4.18.2103.7**<br/>
&ensp;Motor: **1.1.18000.5**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

### <a name="whats-new"></a>Novedades

- Mejora en el motor de supervisión de comportamiento
- Mitigaciones de ataque por fuerza bruta de red expandida
- Más generación de eventos de intento fallido de manipulación cuando la protección [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) está habilitada

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Febrero de 2021 (plataforma: 4.18.2102.3 | Motor: 1.1.17900.7)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.333.7.0**<br/>
&ensp;Fecha de lanzamiento:**9 de marzo de 2021**<br/>
&ensp;Plataforma: **4.18.2102.3**<br/>
&ensp;Motor: **1.1.17900.7**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

### <a name="whats-new"></a>Novedades

- Recuperación de servicio mejorada mediante [protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md)
- Extender ámbito de protección contra alteraciones

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Enero de 2021 (plataforma: 4.18.2101.9 | Motor: 1.1.17800.5)</summary>

&ensp; Versión de actualización de inteligencia de seguridad: **1.327.1854.0**<br/>
&ensp;Publicado:**2 de febrero de 2021**<br/>
&ensp;Plataforma: **4.18.2101.9**<br/>
&ensp;Motor: **1.1.17800.5**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

### <a name="whats-new"></a>Novedades

- Mejoras en la detección de vulnerabilidades de seguridad de Shellcode
- Mayor visibilidad de los intentos de robo de credenciales
- Mejoras en las características de protección en los servicios de Antivirus de Microsoft Defender
- Compatibilidad mejorada con la emulación ARM x64
- Corrección: la notificación de bloqueo de EDR permanece en el historial de amenazas después de que la protección en tiempo real haya realizado la detección inicial

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Noviembre de 2020 (plataforma: 4.18.2011.6 | Motor: 1.1.17700.4)</summary>

&ensp; Versión de actualización de inteligencia de seguridad: **1.327.1854.0**<br/>
&ensp;Publicación: **03 de diciembre de 2020**<br/>
&ensp;Plataforma: **4.18.2011.6**<br/>
&ensp;Motor: **1.1.17700.4**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

### <a name="whats-new"></a>Novedades

- Se ha mejorado [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) del registro de soporte de estado 

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details><details>
<summary> Octubre de 2020 (plataforma: 4.18.2010.7 | Motor: 1.1.17600.5)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.327.7.0**<br/>
&ensp;Publicado:**29 de octubre de 2020**<br/>
&ensp;Plataforma: **4.18.2010.7**<br/>
&ensp;Motor: **1.1.17600.5**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

### <a name="whats-new"></a>Novedades

- Nuevas descripciones para categorías de amenazas especiales
- Funcionalidades de emulación mejoradas
- Capacidades de permiso o bloqueo de direcciones de host mejoradas
- Nueva opción de CSP de Defender para omitir la combinación de exclusiones de usuario local

### <a name="known-issues"></a>Problemas conocidos

No hay problemas conocidos
<br/>
</details><details>
<summary> Septiembre de 2020 (plataforma: 4.18.2009.7 | Motor: 1.1.17500.4)</summary>

&ensp; Versión de actualización de inteligencia de seguridad: **1.325.10.0**<br/>
&ensp;Publicado:**01 de octubre de 2020**<br/>
&ensp;Plataforma: **4.18.2009.7**<br/>
&ensp;Motor: **1.1.17500.4**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

### <a name="whats-new"></a>Novedades

- Se requieren permisos de administrador para restaurar archivos en cuarentena
- Ahora se admiten eventos con formato XML
- Compatibilidad de CSP para omitir combinaciones de exclusión
- Nuevas interfaces de administración para:
   - Inspección de UDP
   - Protección de red en Server 2019
   - Exclusiones de direcciones IP para Protección de red
- Visibilidad mejorada de las medidas de TPM
- Escaneo mejorado del módulo Office VBA

### <a name="known-issues"></a>Problemas conocidos

No hay problemas conocidos
<br/>
</details>
<details>
<summary> Agosto de 2020 (plataforma: 4.18.2008.9 | Motor: 1.1.17400.5)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.323.9.0**<br/>
&ensp;Publicación:**27 de agosto de 2020**<br/>
&ensp;Plataforma: **4.18.2008.9**<br/>
&ensp;Motor: **1.1.17400.5**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

### <a name="whats-new"></a>Novedades

- Agregar más eventos de telemetría
- Mejora de la telemetría de eventos de exploración
- Supervisión de comportamiento mejorada para exploración de memoria
- Análisis mejorado de secuencias de macros
- Se agregó `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet
- [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) se ignora. El antivirus de Microsoft Defender se desactiva automáticamente cuando detecta otro programa antivirus.


### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details>

<details>
<summary> Julio de 2020 (plataforma: 4.18.2007.8 | Motor: 1.1.17300.4)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.321.30.0**<br/>
&ensp;Publicación:**28 de julio de 2020**<br/>
&ensp;Plataforma: **4.18.2007.8**<br/>
&ensp;Motor: **1.1.17300.4**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

### <a name="whats-new"></a>Novedades

- Telemetría mejorada para BITS
- Validación mejorada del certificado de firma de código Authenticode

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details>

<details>
<summary> Junio de 2020 (plataforma: 4.18.2006.10 | Motor: 1.1.17200.2)</summary>

&ensp;Versión de actualización de la inteligencia de seguridad:: **1.319.20.0**<br/>
&ensp;Publicación:**June 22, 2020**<br/>
&ensp;Plataforma: **4.18.2006.10**<br/>
&ensp;Motor: **1.1.17200.2**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

### <a name="whats-new"></a>Novedades

- Posibilidad de especificar la [ubicación de los registros de soporte técnico](./collect-diagnostic-data.md)
- Omitir el escaneo agresivo de recuperación en modo pasivo.
- Permitir que Defender se actualice en conexiones de uso medido
- Se ha corregido el ajuste del rendimiento al deshabilitar el almacenamiento en caché
- Se ha corregido la consulta del registro
- Se ha corregido la aleatorización del tiempo de escaneo en ADMX

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details>

<details>
<summary> Mayo de 2020 (plataforma: 4.18.2005.4 | Motor: 1.1.17100.2)</summary>

&ensp; Versión de actualización de inteligencia de seguridad:: **1.317.20.0**<br/>
&ensp;Publicado: **26 de mayo de 2020** <br/>
&ensp;Plataforma: **4.18.2005.4**<br/>
&ensp;Motor: **1.1.17100.2**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

### <a name="whats-new"></a>Novedades

- Registro mejorado para eventos de escaneo
- Se ha mejorado la gestión de los fallos en el modo de usuario.
- Se ha agregado el seguimiento de eventos para la protección contra manipulaciones
- Se ha corregido el envío de ejemplo de AMSI
- Se ha corregido el bloqueo en la nube de AMSI
- Se ha corregido el registro de instalación de actualizaciones de seguridad

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details>

<details>
<summary> Abril de 2020 (plataforma: 4.18.2004.6 | Motor: 1.1.17000.2)</summary>

&ensp; Versión de actualización de inteligencia de seguridad: **1.315.12.0**<br/>
&ensp;Publicación: **30 de abril de 2020**<br/>
&ensp;Plataforma: **4.18.2004.6**<br/>
&ensp;Motor: **1.1.17000.2**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

### <a name="whats-new"></a>Novedades
- Mejoras en el WDfilter
- Agregar más datos de eventos accionables a los eventos de detección de reducción de la superficie expuesta a ataques
- Se ha corregido la información de versión en los datos de diagnóstico y en WMI
- Se ha corregido la versión incorrecta de la plataforma en la interfaz de usuario tras la actualización de la misma.
- Información de dirección URL dinámica para la protección contra amenazas sin archivos
- Funcionalidad de detección de UEFI
- Ampliar el registro de actualizaciones

### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details>

<details>
<summary> Marzo de 2020 (plataforma: 4.18.2003.8 | Motor: 1.1.16900.2)</summary>

&ensp; Versión de actualización de inteligencia de seguridad: **1.313.8.0**<br/>
&ensp;Publicado: **24 de marzo de 2020**<br/>
&ensp;Plataforma: **4.18.2003.8**<br/>
&ensp;Motor: **1.1.16900.4**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

### <a name="whats-new"></a>Novedades

- Opción de limitación de CPU agregada a [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)
- Mejorar la funcionalidad de diagnóstico
- reducir el tiempo de espera de inteligencia de seguridad (5 minutos)
- Ampliar la capacidad de registro interno del motor AMSI
- Mejora de la notificación para el bloqueo de procesos

### <a name="known-issues"></a>Problemas conocidos
[**Solucionado**] Antivirus de Microsoft Defender omite los archivos al ejecutar un análisis.

<br/>
</details>

<details>

<summary> Febrero-2020 (plataforma: - | Motor: 1.1.16800.2)</summary>


&ensp;Versión de actualización de inteligencia de seguridad:: **1.311.4.0**<br/>
&ensp;Publicado: **25 de febrero de 2020**<br/>
Plataforma o Cliente de: &ensp;**-**<br/>
&ensp;Motor: **1.1.16800.2**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

### <a name="whats-new"></a>Novedades


### <a name="known-issues"></a>Problemas conocidos
No hay problemas conocidos
<br/>
</details>

<details>
<summary> Enero-2020 (plataforma: 4.18.2001.10 | Motor: 1.1.16700.2)</summary>


Versión de actualización de inteligencia de seguridad: **1.309.32.0**<br/>
Publicado: **30 de enero de 2020**<br/>
Plataforma o Cliente de: **4.18.2001.10**<br/>
Motor: **1.1.16700.2**<br/>
&ensp;Fase de soporte técnico: **soporte técnico de actualización (únicamente)**<br/>

### <a name="whats-new"></a>Novedades

- BSOD corregido en WS2016 con Exchange
- Compatibilidad con las actualizaciones de la plataforma cuando TMP se redirige a la ruta de acceso de red
- Las versiones de plataforma y motor se agregan a [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates) <!-- The preceding URL must include "/en-us" -->
- extender la actualización de firma de emergencia a [modo pasivo](./microsoft-defender-antivirus-compatibility.md)
- Corrección de bloqueo 4.18.1911.3

### <a name="known-issues"></a>Problemas conocidos

[**Fijo**] dispositivos que usan [modo de espera moderno](/windows-hardware/design/device-experiences/modern-standby) pueden experimentar un bloqueo con el controlador de filtro de Windows Defender queda lugar a una brecha de protección.  Parece que las máquinas afectadas no se han actualizado a la plataforma antimalware más reciente para el cliente.
<br/>
> [!IMPORTANT]
> Esta actualización es:
> - los dispositivos RS1 que ejecutan una versión inferior de la plataforma para admitir SHA2;
> - tiene una marca de reinicio para los sistemas que tienen problemas de bloqueo;
> - se vuelve a publicar en abril de 2020 y no se sustituirá por actualizaciones más recientes para mantener la disponibilidad futura;
> - se clasifica como una actualización debido al requisito de reinicio; Y
> - solo se ofrece con [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).
<br/>
</details>

<details>
<summary> Noviembre de 2019 (plataforma: 4.18.1911.3 | Motor: 1.1.16600.7)</summary>

Versión de actualización de inteligencia de seguridad:**1.307.13.0**<br/>
Publicación: **7 de diciembre de 2019**<br/>
Plataforma: **4.18.1911.3**<br/>
Motor: **1.1.17000.7**<br/>
Fase de soporte técnico:: **Sin soporte**<br/>

### <a name="whats-new"></a>Novedades

- Se ha corregido el nivel de seguimiento de MpCmdRun
- Se ha corregido la información de la versión de WDFilter
- Mejorar las notificaciones (PUA)
- agregar registros de MRT a los archivos de soporte

### <a name="known-issues"></a>Problemas conocidos
Cuando se instala esta actualización, el dispositivo necesita el paquete de salto 4.18.2001.10 para poder actualizar a la versión más reciente de la plataforma.
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a>Compatibilidad con la plataforma Antivirus de Microsoft Defender

Las actualizaciones de la plataforma y del motor se proporcionan cada mes. Para ser totalmente compatible, manténgase al día con las últimas actualizaciones de la plataforma. Nuestra estructura de soporte técnico es dinámica y evoluciona en dos fases en función de la disponibilidad de la versión más reciente de la plataforma:

- **Fase de mantenimiento de actualizaciones críticas y de seguridad** : al ejecutar la versión más reciente de la plataforma, podrá recibir actualizaciones críticas y de seguridad para la plataforma antimalware.

- **Fase de soporte técnico (únicamente)**: Después de publicar una nueva versión de la plataforma, el soporte técnico para versiones anteriores (N-2) se reducirá solo al soporte técnico. Ya no se admitirán las versiones de plataforma anteriores a N-2.*

\* Se seguirá ofreciendo soporte técnico para las actualizaciones desde la versión de lanzamiento de Windows 10 (consulte a [Versión de la plataforma incluida en las versiones de Windows 10](#platform-version-included-with-windows-10-releases)) a la versión más reciente de la plataforma.

Durante la fase de soporte técnico (únicamente), los incidentes de soporte técnico comercialmente razonables se proporcionarán a través del servicio de atención al cliente de Microsoft y Soporte técnico y ofertas de soporte técnico administrado de Microsoft (como soporte técnico Premier).   Si un incidente de soporte requiere escalar a desarrollo para obtener más orientación, requiere una actualización que no sea de seguridad o requiere una actualización de seguridad, se les pedirá a los clientes que actualicen a la última versión de la plataforma o una actualización intermedia (*).

> [!NOTE]
> Si va a implementar manualmente el Antivirus de Microsoft Defender Platform Update, o si usa un script o un producto de administración que no es de Microsoft para implementar Antivirus Microsoft Defender Platform Update, asegúrese de que la versión `4.18.2001.10` está instalada desde el [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/Search.aspx?q=4.18.2001.10) antes de instalar la versión más reciente de la actualización de plataforma (N-2).

### <a name="platform-version-included-with-windows-10-releases"></a>Versión de la plataforma incluida con las versiones de Windows 10

En la tabla siguiente se proporcionan las versiones de plataforma y motor Antivirus de Microsoft Defender que se incluyen con las versiones de Windows 10 más recientes:<br/><br/>

|Versión de Windows 10  |Versión de la plataforma  |Versión del motor |Fase de soporte técnico |
|:---|:---|:---|:---|
|2004 (20H1/20H2) |4.18.1909.6. |1.1.17000.2 | Soporte técnico de actualización (únicamente) |
|1909 (19H2) |4.18.1902.5 |1.1.16700.3 | Soporte técnico de actualización (únicamente) |
|1903  (19H1) |4.18.1902.5 |1.1.15600.4 | Soporte técnico de actualización (únicamente) |
|1809 (RS5) |4.18.1807.18075. |1.1.15000.2 | Soporte técnico de actualización (únicamente) |
|1803  (RS4) |4.13.17134.1 |1.1.14600.4 | Soporte técnico de actualización (únicamente) |
|1709  (RS3) |4.12.16299.15 |1.1.14104.0 | Soporte técnico de actualización (únicamente) |
|1703  (RS2) |4.11.15603.2 |1.1.13504.0. | Soporte técnico de actualización (únicamente) |
|1607 (RS1) |4.10.14393.3683 |1.1.12805.0 | Soporte técnico de actualización (únicamente) |

Para obtener información sobre la versión de Windows 10 [consulte la hoja informativa sobre el ciclo de vida de Windows](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a>Actualizaciones para el Servicio y Gestión de Imágenes de Despliegue (DISM)

Se recomienda actualizar las imágenes de instalación del sistema operativo Windows 10 (ediciones Enterprise, Pro y Home), Windows Server 2019, Windows Server 2022 y Windows Server 2016 con las actualizaciones antivirus y antimalware más recientes. Mantener actualizadas las imágenes de instalación del sistema operativo ayuda a evitar una brecha en la protección.

Para obtener más información, vea [las imágenes de instalación de Microsoft Defender para el sistema operativo Windows](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).

<details>
<summary>20220901.4</summary>

&ensp;Versión del paquete: **20220901.4**<br/>
&ensp;Versión de la plataforma: **4.18.2205.7**<br/>
&ensp;Versión del motor: **1.1.19500.2**<br/>
&ensp;Versión de firma: **1.373.1371.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno

<br/>
</details><details>
<summary>20220802.1</summary>

&ensp;Versión del paquete: **20220802.1**<br/>
&ensp;Versión de la plataforma: **4.18.2205.7**<br/>
&ensp;Versión del motor: **1.1.19400.3**<br/>
&ensp;Versión de firma: **1.371.1205.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno

<br/>
</details><details>
<summary>20220629.5</summary>

&ensp;Versión del paquete: **20220629.5**<br/>
&ensp;Versión de la plataforma: **4.18.2205.7**<br/>
&ensp;Versión del motor: **1.1.19300.2**<br/>
&ensp;Versión de firma: **1.369.220.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno

<br/>
</details><details>
<summary>20220603.3</summary>

&ensp;Versión del paquete: **20220603.3**<br/>
&ensp;Versión de la plataforma: **4.18.2203.5**<br/>
&ensp;Versión del motor: **1.1.19200.6**<br/>
&ensp;Versión de firma: **1.367.1009.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno

<br/>
</details><details>
<summary>20220506.6.</summary>

&ensp;Versión del paquete: **20220506.6**<br/>
&ensp;Versión de la plataforma: **4.18.2203.5**<br/>
&ensp;Versión del motor: **1.1.19200.5**<br/>
&ensp;Versión de firma: **1.363.1436.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno

<br/>
</details><details>
<summary>20220321.1.</summary>

&ensp;Versión del paquete: **20220321.1**<br/>
&ensp;Versión de la plataforma: **4.18.2202.4**<br/>
&ensp;Versión del motor: **1.1.19000.8**<br/>
&ensp;Versión de firma: **1.351.337.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno

<br/>
</details><details>
<summary>20220305.1.</summary>

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

&ensp;Versión del paquete: **20220203.1**<br/>
&ensp;Versión de la plataforma: **4.18.2111.5**<br/>
&ensp;Versión del motor: **1.1.18900.2**<br/>
&ensp;Versión de firma: **1.357.32.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno
<br/>
</details><details>
<summary>20220105.1.</summary>

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
<summary>1.1.2111.02.</summary>

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
<summary>1.1.2110.01.</summary>

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
<summary>1.1.2109.01.</summary>

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
<summary>1.1.2011.02.</summary>

&ensp;Versión del paquete: **1.1.2011.02**<br/>
&ensp;Versión de la plataforma: **4.18.2010.7**<br/>
&ensp;Versión del motor: **1.1.17600.5**<br/>
&ensp;Versión de firma: **1.327.658.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Firmas del Antivirus de Microsoft Defender actualizadas
<br/>
</details><details>
<summary>1.1.2011.01.</summary>

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
&ensp;Versión de firma de: **1.327.2216.0**<br/>

### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Se ha agregado compatibilidad para Windows 10 imágenes de instalación del sistema operativo RS1 o posterior.
<br/>
</details>

## <a name="more-resources"></a>Más recursos

| Artículo | Descripción  |
|:---|:---|
|[Imágenes de instalación de Microsoft Defender para el sistema operativo Windows](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | Revise los paquetes de actualización antimalware de las imágenes de instalación del sistema operativo (archivos WIM y VHD).  Obtenga las actualizaciones del antivirus Microsoft Defender para las imágenes de instalación de Windows 10 (ediciones Enterprise, Pro y Home), Windows Server 2019, Windows Server 2022 y Windows Server 2016.  |
|[Administre cómo se descargan y aplican las actualizaciones de protección](manage-protection-updates-microsoft-defender-antivirus.md) | Las actualizaciones de protección se pueden entregar a través de muchos orígenes. |
|[Administre cuándo deben descargarse y aplicarse las actualizaciones de protección](manage-protection-update-schedule-microsoft-defender-antivirus.md) | Puede programar cuándo deben descargarse las actualizaciones de protección. |
|[Administrar actualizaciones para puntos finales que están desactualizados](manage-outdated-endpoints-microsoft-defender-antivirus.md) | Si un punto final pierde una actualización o un análisis programado, puede forzar una actualización o un análisis la próxima vez que un usuario inicie sesión. |
|[Administrar las actualizaciones forzadas basadas en eventos](manage-event-based-updates-microsoft-defender-antivirus.md) | Puede establecer que las actualizaciones de protección se descarguen al inicio o después de ciertos eventos de protección entregados en la nube. |
|[Administrar las actualizaciones de dispositivos móviles y máquinas virtuales](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| Puede especificar opciones de configuración, como si las actualizaciones deben producirse con energía de la batería, que son especialmente útiles para dispositivos móviles y máquinas virtuales. |
| [Actualización de Microsoft Defender para punto de conexión para el sensor EDR](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac) | Puede actualizar el sensor EDR (MsSense.exe) que se incluye en el nuevo paquete de solución unificada de Microsoft Defender para punto de conexión publicado en 2021.     |

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)
