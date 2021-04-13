---
title: Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar líneas base
description: Administrar cómo Antivirus de Microsoft Defender recibe actualizaciones de productos y protección.
keywords: actualizaciones, líneas base de seguridad, protección, actualizaciones de programación, actualizaciones de fuerza, actualizaciones móviles, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bf027dd7f5fad032d57d2dd0b686ccd129f568c7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690978"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a>Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar líneas base

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender Antivirus

Hay dos tipos de actualizaciones relacionadas con la actualización del Antivirus de Microsoft Defender:

- Actualizaciones de inteligencia de seguridad
- Actualizaciones de productos

> [!IMPORTANT]
> Mantener el Antivirus de Microsoft Defender actualizado es fundamental para garantizar que los dispositivos tienen la tecnología y las características más recientes necesarias para protegerse contra nuevas técnicas de malware y ataques.  
> Asegúrese de actualizar la protección antivirus incluso si Antivirus de Microsoft Defender se está ejecutando en [modo pasivo](./microsoft-defender-antivirus-compatibility.md).
> 
> Para ver el motor, la plataforma y la fecha de firma más actuales, visite las actualizaciones de inteligencia de seguridad para Antivirus de [Microsoft Defender y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates).

## <a name="security-intelligence-updates"></a>Actualizaciones de inteligencia de seguridad

Antivirus de Microsoft Defender usa [protección](cloud-protection-microsoft-defender-antivirus.md) entregada en la nube (también denominada Servicio de protección avanzada de Microsoft o MAPS) y descarga periódicamente actualizaciones de inteligencia de seguridad para proporcionar protección.

> [!NOTE]
> Las actualizaciones se lanzan con los números KB siguientes:  
> Antivirus de Microsoft Defender: KB2267602  
> System Center Endpoint Protection: KB2461484

La protección entregada en la nube siempre está activada y requiere una conexión activa a Internet para funcionar. Las actualizaciones de inteligencia de seguridad se producen en una cadencia programada (configurable mediante directiva). Para obtener más información, vea [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md). 

Para obtener una lista de actualizaciones de inteligencia de seguridad recientes, vea Actualizaciones de inteligencia de seguridad para Antivirus de [Microsoft Defender y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates).

Las actualizaciones del motor se incluyen con actualizaciones de inteligencia de seguridad y se lanzan en una cadencia mensual.

## <a name="product-updates"></a>Actualizaciones de productos

Microsoft Defender Antivirus requiere actualizaciones [mensuales (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (conocidas como actualizaciones de *plataforma)* y recibirá actualizaciones de características principales junto con las versiones de Windows 10.

Puede administrar la distribución de actualizaciones a través de uno de los siguientes métodos: 

- [Servicio de actualización de Windows Server (WSUS)](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/sum/understand/software-updates-introduction)
- El método habitual que usas para implementar las actualizaciones de Microsoft y Windows en los puntos de conexión de la red.

Para obtener más información, vea [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).

> [!NOTE]
> Las actualizaciones mensuales se liberan en fases, lo que da como resultado varios paquetes visibles en [los Servicios de actualización de Windows Server](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).

## <a name="monthly-platform-and-engine-versions"></a>Versiones mensuales de plataforma y motor

Para obtener información sobre cómo actualizar o instalar la actualización de plataforma, vea [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).

Todas nuestras actualizaciones contienen 
- mejoras en el rendimiento;
- mejoras en la capacidad de servicio; y 
- mejoras de integración (Cloud, Microsoft 365 Defender).
<br/><br/>

<details>
<summary> Marzo-2021 (Plataforma: 4.18.2103.7 | Motor: 1.1.18000.5)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.335.36.0**  
&ensp;Publicado: **1 de abril de 2021**  
&ensp;Plataforma: **4.19.2103.7**  
&ensp;Motor: **1.1.18000.5**  
&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**
    
### <a name="whats-new"></a>Novedades

- Mejora del motor de supervisión del comportamiento 
- Mitigaciones de ataques de fuerza bruta de red expandida 
- Generación de eventos de intento de manipulación con error adicional cuando [la protección contra manipulaciones](prevent-changes-to-security-settings-with-tamper-protection.md) está habilitada

### <a name="known-issues"></a>Problemas conocidos
Sin problemas conocidos  
<br/>
</details><details>
<summary> Febrero-2021 (Plataforma: 4.18.2102.3 | Motor: 1.1.17900.7)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.333.7.0**  
&ensp;Publicado: **9 de marzo de 2021**  
&ensp;Plataforma: **4.19.2102.3**  
&ensp;Motor: **1.1.17900.7**  
&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**
    
### <a name="whats-new"></a>Novedades

- Recuperación del servicio mejorada a través de [la protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md)
- Ampliar el ámbito de protección contra alteraciones

### <a name="known-issues"></a>Problemas conocidos
Sin problemas conocidos  
<br/>
</details><details>
<summary> Enero-2021 (Plataforma: 4.18.2101.9 | Motor: 1.1.17800.5)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.327.1854.0**  
&ensp;Publicado: **2 de febrero de 2021**  
&ensp;Plataforma: **4.18.2101.9**  
&ensp;Motor: **1.1.17800.5**  
&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**
    
### <a name="whats-new"></a>Novedades

- Mejoras en la detección de vulnerabilidades de shellcode
- Mayor visibilidad para intentos de robo de credenciales
- Mejoras en las características de protección contra el entorpecimiento en los servicios antivirus de Microsoft Defender
- Compatibilidad mejorada con la emulación ARM x64
- Corrección: La notificación de bloqueo de EDR permanece en el historial de amenazas después de que la protección en tiempo real realizara la detección inicial

### <a name="known-issues"></a>Problemas conocidos
Sin problemas conocidos  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a>Actualizaciones de versiones anteriores: solo compatibilidad con actualizaciones técnicas

Después de publicar una nueva versión del paquete, la compatibilidad con las dos versiones anteriores se reduce únicamente al soporte técnico. Las versiones anteriores a las que se enumeran en esta sección y solo se proporcionan para soporte técnico de actualización. 
<br/><br/>
<details>
<summary> Noviembre-2020 (Plataforma: 4.18.2011.6 | Motor: 1.1.17700.4)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.327.1854.0**  
&ensp;Publicado: **03 de diciembre de 2020**  
&ensp;Plataforma: **4.18.2011.6**  
&ensp;Motor: **1.1.17700.4**  
&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**
    
### <a name="whats-new"></a>Novedades

- Registro de compatibilidad con el estado de [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) mejorado

### <a name="known-issues"></a>Problemas conocidos
Sin problemas conocidos  
<br/>
</details><details>
<summary> Octubre-2020 (Plataforma: 4.18.2010.7 | Motor: 1.1.17600.5)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.327.7.0**  
&ensp;Publicado: **29 de octubre de 2020**  
&ensp;Plataforma: **4.18.2010.7**  
&ensp;Motor: **1.1.17600.5**  
&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**
    
### <a name="whats-new"></a>Novedades

- Nuevas descripciones para categorías de amenazas especiales
- Capacidades de emulación mejoradas
- Capacidades mejoradas de permitir o bloquear direcciones host
- Nueva opción en CSP de Defender para omitir la combinación de exclusiones de usuarios locales

### <a name="known-issues"></a>Problemas conocidos

Sin problemas conocidos  
<br/>
</details><details>
<summary> Septiembre-2020 (Plataforma: 4.18.2009.7 | Motor: 1.1.17500.4)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.325.10.0**  
&ensp;Publicado: **01 de octubre de 2020**  
&ensp;Plataforma: **4.18.2009.7**  
&ensp;Motor: **1.1.17500.4**  
&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**
    
### <a name="whats-new"></a>Novedades

- Los permisos de administrador son necesarios para restaurar archivos en cuarentena
- Ahora se admiten eventos con formato XML
- Compatibilidad con CSP para omitir las fusiones de exclusión
- Nuevas interfaces de administración para:
   - Inspección UDP
   - Protección de red en server 2019
   - Exclusiones de direcciones IP para protección de red
- Visibilidad mejorada de las medidas del TPM
- Examen mejorado del módulo VBA de Office

### <a name="known-issues"></a>Problemas conocidos

Sin problemas conocidos  
<br/>
</details>
<details>
<summary> Agosto-2020 (Plataforma: 4.18.2008.9 | Motor: 1.1.17400.5)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.323.9.0**  
&ensp;Publicado: **27 de agosto de 2020**  
&ensp;Plataforma: **4.18.2008.9**  
&ensp;Motor: **1.1.17400.5**  
&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**

### <a name="whats-new"></a>Novedades

- Agregar más eventos de telemetría
- Telemetría de eventos de examen mejorada
- Supervisión de comportamiento mejorada para exámenes de memoria
- Análisis mejorado de secuencias de macros
- Se `AMRunningMode` agregó Get-MpComputerStatus cmdlet de PowerShell
- [Se omite DisableAntiSpyware.](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) Antivirus de Microsoft Defender se desactiva automáticamente cuando detecta otro programa antivirus.


### <a name="known-issues"></a>Problemas conocidos
Sin problemas conocidos  
<br/>
</details>

<details>
<summary> Julio-2020 (Plataforma: 4.18.2007.8 | Motor: 1.1.17300.4)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.321.30.0**  
&ensp;Publicado: **28 de julio de 2020**  
&ensp;Plataforma: **4.18.2007.8**  
&ensp;Motor: **1.1.17300.4**  
&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**
    
### <a name="whats-new"></a>Novedades

- Telemetría mejorada para BITS
- Validación mejorada del certificado de firma de código Authenticode

### <a name="known-issues"></a>Problemas conocidos
Sin problemas conocidos  
<br/>
</details>

<details>
<summary> Junio-2020 (Plataforma: 4.18.2006.10 | Motor: 1.1.17200.2)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.319.20.0**  
&ensp;Publicado: **22 de junio de 2020**  
&ensp;Plataforma: **4.18.2006.10**  
&ensp;Motor: **1.1.17200.2**  
&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**
    
### <a name="whats-new"></a>Novedades

- Posibilidad de especificar la [ubicación de los registros de soporte técnico](./collect-diagnostic-data.md)
- Omitir el examen de captura agresivo en modo pasivo.
- Permitir que Defender actualice con conexiones medidas
- Se ha corregido la optimización del rendimiento cuando se deshabilita el almacenamiento en caché 
- Consulta fija del Registro 
- Aleatorización de tiempo de examen fijo en ADMX

### <a name="known-issues"></a>Problemas conocidos
Sin problemas conocidos  
<br/>
</details>

<details>
<summary> Mayo-2020 (Plataforma: 4.18.2005.4 | Motor: 1.1.17100.2)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.317.20.0**  
&ensp;Publicado: **26 de mayo de 2020**  
&ensp;Plataforma: **4.18.2005.4**  
&ensp;Motor: **1.1.17100.2**  
&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**
    
### <a name="whats-new"></a>Novedades

- Registro mejorado para eventos de examen
- Se ha mejorado el control de bloqueos del modo de usuario.
- Se agregó el seguimiento de eventos para la protección contra manipulaciones
- Envío de ejemplo de AMSI fijo
- Se ha corregido el bloqueo de la nube de AMSI
- Registro de instalación de actualización de seguridad fija

### <a name="known-issues"></a>Problemas conocidos
Sin problemas conocidos  
<br/>
</details>

<details>
<summary> Abril-2020 (Plataforma: 4.18.2004.6 | Motor: 1.1.17000.2)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.315.12.0**  
&ensp;Publicado: **30 de abril de 2020**  
&ensp;Plataforma: **4.18.2004.6**  
&ensp;Motor: **1.1.17000.2**  
&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**
    
### <a name="whats-new"></a>Novedades
- Mejoras de WDfilter
- Agregar más datos de eventos que se pueden usar para atacar eventos de detección de reducción de superficie
- Información de versión fija en datos de diagnóstico y WMI
- Se ha corregido una versión incorrecta de la plataforma en la interfaz de usuario después de la actualización de la plataforma
- Intel de dirección URL dinámica para la protección contra amenazas sin archivos
- Funcionalidad de examen UEFI
- Extender el registro para actualizaciones

### <a name="known-issues"></a>Problemas conocidos
Sin problemas conocidos  
<br/>
</details>

<details>
<summary> Marzo-2020 (Plataforma: 4.18.2003.8 | Motor: 1.1.16900.2)</summary>

&ensp;Versión de actualización de inteligencia de seguridad: **1.313.8.0**  
&ensp;Publicado: **24 de marzo de 2020**  
&ensp;Plataforma: **4.18.2003.8**  
&ensp;Motor: **1.1.16900.4**  
&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**
    
### <a name="whats-new"></a>Novedades

- Opción de limitación de CPU agregada a [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)
- Mejorar la funcionalidad de diagnóstico
- reducir el tiempo de espera de inteligencia de seguridad (5 minutos)
- Ampliar la funcionalidad de registro interno del motor AMSI
- Mejorar la notificación para el bloqueo de procesos
   
### <a name="known-issues"></a>Problemas conocidos
[**Fijo**] Antivirus de Microsoft Defender omite archivos al ejecutar un examen.

<br/>
</details>

<details>

<summary> Febrero-2020 (Plataforma: - | Motor: 1.1.16800.2)</summary>
  

&ensp;Versión de actualización de inteligencia de seguridad: **1.311.4.0**   
&ensp;Publicado: **25 de febrero de 2020**  
&ensp;Plataforma/cliente: **-**  
&ensp;Motor: **1.1.16800.2**  
&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**
     
### <a name="whats-new"></a>Novedades

  
### <a name="known-issues"></a>Problemas conocidos
Sin problemas conocidos
<br/>
</details>

<details>
<summary> Enero-2020 (Plataforma: 4.18.2001.10 | Motor: 1.1.16700.2)</summary>
  

Versión de actualización de inteligencia de seguridad: **1.309.32.0**  
Publicado: **30 de enero de 2020**  
Plataforma/cliente: **4.18.2001.10**  
Motor: **1.1.16700.2**  
&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**
     
### <a name="whats-new"></a>Novedades

- BSOD fijo en WS2016 con Exchange
- Actualizaciones de plataforma de soporte técnico cuando TMP se redirige a la ruta de red
- Las versiones de plataforma y motor se agregan a [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates) <!-- The preceding URL must include "/en-us" -->
- extender la actualización de firma de emergencia [al modo pasivo](./microsoft-defender-antivirus-compatibility.md)
- Corrección 4.18.1911.3 hang
   
### <a name="known-issues"></a>Problemas conocidos

[**Fijo**] los dispositivos que utilizan el modo [de](/windows-hardware/design/device-experiences/modern-standby) espera moderno pueden experimentar una suspensión con el controlador de filtro Windows Defender que da como resultado un vacío de protección.  Las máquinas afectadas aparecen al cliente como que no se han actualizado a la plataforma antimalware más reciente.  
<br/>
> [!IMPORTANT]
> Esta actualización es:
> - que necesitan los dispositivos RS1 que ejecutan la versión inferior de la plataforma para admitir SHA2;
> - tiene una marca de reinicio para sistemas que tienen problemas de suspensión;
> - se vuelve a publicar en abril de 2020 y no se reemplazará por actualizaciones más recientes para mantener la disponibilidad futura;  
> - se clasifica como una actualización debido al requisito de reinicio; y
> - solo se ofrece con [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).
<br/>
</details>

<details>
<summary> Noviembre-2019 (Plataforma: 4.18.1911.3 | Motor: 1.1.16600.7)</summary>

Versión de actualización de inteligencia de seguridad: **1.307.13.0**  
Publicado: **7 de diciembre de 2019**  
Plataforma: **4.18.1911.3**  
Motor: **1.1.17000.7**  
Fase de soporte técnico: **sin compatibilidad**  
     
### <a name="whats-new"></a>Novedades

- Nivel de seguimiento de MpCmdRun fijo
- Información de versión de WDFilter fija
- Mejorar las notificaciones (PUA)
- agregar registros de MRT para admitir archivos
   
### <a name="known-issues"></a>Problemas conocidos
Cuando se instala esta actualización, el dispositivo necesita el paquete de salto 4.10.2001.10 para poder actualizar a la versión más reciente de la plataforma.
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a>Compatibilidad con la plataforma antivirus de Microsoft Defender
Las actualizaciones de plataforma y motor se proporcionan en una cadencia mensual. Para ser totalmente compatible, manténgase al día con las actualizaciones más recientes de la plataforma. Nuestra estructura de soporte es dinámica, evolucionando en dos fases en función de la disponibilidad de la versión más reciente de la plataforma:

- **Fase de mantenimiento** de actualizaciones críticas y de seguridad: al ejecutar la versión más reciente de la plataforma, podrá recibir actualizaciones de seguridad y críticas en la plataforma antimalware.
 
- **Fase de soporte** técnico (solo): después de publicar una nueva versión de la plataforma, la compatibilidad con versiones anteriores (N-2) se reducirá únicamente al soporte técnico. Las versiones de plataforma anteriores a N-2 ya no se admiten.*

\* Se seguirá brindando soporte técnico para las actualizaciones de la versión de versión de Windows 10 (consulta Versión de plataforma incluida con versiones de [Windows 10)](#platform-version-included-with-windows-10-releases)a la versión más reciente de la plataforma.

Durante la fase de soporte técnico (solo), los incidentes de soporte comercialmente razonables se proporcionan a través del servicio de soporte técnico de Microsoft & y las ofertas de soporte administrado de Microsoft (como soporte premier). Si un incidente de soporte requiere una escalación al desarrollo para obtener más instrucciones, requiere una actualización que no sea de seguridad o requiere una actualización de seguridad, se pedirá a los clientes que actualicen a la versión más reciente de la plataforma o a una actualización intermedia (*).

### <a name="platform-version-included-with-windows-10-releases"></a>Versión de plataforma incluida con versiones de Windows 10
En la tabla siguiente se proporcionan las versiones del motor y la plataforma antivirus de Microsoft Defender que se suministran con las versiones más recientes de Windows 10:    

|Versión de Windows 10  |Versión de plataforma  |Versión del motor |Fase de soporte técnico |
|:---|:---|:---|:---|
|2004 (20H1/20H2) |4.18.1909.6 |1.1.17000.2 | Soporte técnico de actualización (solo) |
|1909 (19H2) |4.18.1902.5 |1.1.16700.3 | Soporte técnico de actualización (solo) |
|1903 (19H1) |4.18.1902.5 |1.1.15600.4 | Soporte técnico de actualización (solo) |
|1809 (RS5) |4.18.1807.18075 |1.1.15000.2 | Soporte técnico de actualización (solo) |
|1803 (RS4) |4.13.17134.1 |1.1.14600.4 | Soporte técnico de actualización (solo) |
|1709 (RS3) |4.12.16299.15 |1.1.14104.0 | Soporte técnico de actualización (solo) |
|1703 (RS2) |4.11.15603.2 |1.1.13504.0 | Soporte técnico de actualización (solo) |
|1607 (RS1) |4.10.14393.3683 |1.1.12805.0 | Soporte técnico de actualización (solo) |  

Para obtener información sobre la versión de Windows 10, consulta la hoja de hechos del ciclo [de vida de Windows](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a>Actualizaciones para administración y mantenimiento de imágenes de implementación (DISM)

Se recomienda actualizar las imágenes de instalación del sistema operativo Windows 10 (Enterprise, Pro y Home editions), Windows Server 2019 y Windows Server 2016 con las últimas actualizaciones de antivirus y antimalware. Mantener las imágenes de instalación del sistema operativo actualizadas ayuda a evitar un vacío en la protección. 

Para obtener más información, consulta [Actualización de Microsoft Defender para imágenes de instalación del sistema operativo Windows](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).

<details>
<summary>1.1.2104.01</summary>

&ensp;Versión del paquete: **1.1.2104.01**    
&ensp;Versión de plataforma: **4.18.2102.4**   
&ensp;Versión del motor: **1.1.18000.5**  
&ensp;Versión de firma: **1.335.232.0**    
    
### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno  
<br/>
</details><details>
<summary>1.1.2103.01</summary>

&ensp;Versión del paquete: **1.1.2103.01**    
&ensp;Versión de la **plataforma: 4.18.2101.9**   
&ensp;Versión del motor: **1.1.17800.5**  
&ensp;Versión de firma: **1.331.2302.0**    
    
### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno  
<br/>
</details><details>
<summary>1.1.2102.03</summary>

&ensp;Versión del paquete: **1.1.2102.03**    
&ensp;Versión de plataforma: **4.18.2011.6**   
&ensp;Versión del motor: **1.1.17800.5**  
&ensp;Versión de firma: **1.331.174.0**    
    
### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno  
<br/>
</details><details>
<summary>1.1.2101.02</summary>

&ensp;Versión del paquete: **1.1.2101.02**    
&ensp;Versión de plataforma: **4.18.2011.6**   
&ensp;Versión del motor: **1.1.17700.4**  
&ensp;Versión de firma: **1.329.1796.0**    
    
### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno  
<br/>
</details><details>
<summary>1.1.2012.01</summary>

&ensp;Versión del paquete: **1.1.2012.01**    
&ensp;Versión de la **plataforma: 4.18.2010.7**   
&ensp;Versión del motor: **1.1.17600.5**  
&ensp;Versión de firma: **1.327.1991.0**    
    
### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno  
<br/>
</details><details>
<summary>1.1.2011.02</summary>

&ensp;Versión del paquete: **1.1.2011.02**    
&ensp;Versión de la **plataforma: 4.18.2010.7**   
&ensp;Versión del motor: **1.1.17600.5**  
&ensp;Versión de firma: **1.327.658.0**    
    
### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Firmas de Antivirus de Microsoft Defender actualizados  
<br/>
</details><details>
<summary>1.1.2011.01</summary>

&ensp;Versión del paquete: **1.1.2011.01**    
&ensp;Versión de plataforma: **4.18.2009.7**  
&ensp;Versión del motor: **1.1.17600.5**  
&ensp;Versión de firma: **1.327.344.0**    
    
### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Ninguno  
<br/>
</details><details>
<summary>1.1.2009.10</summary>

&ensp;Versión del paquete: **1.1.2011.01**    
&ensp;Versión de plataforma: **4.18.2008.9**   
&ensp;Versión del motor: **1.1.17400.5**  
&ensp;Versión de firma: **1.327.2216.0**    
    
### <a name="fixes"></a>Correcciones
- Ninguno

### <a name="additional-information"></a>Información adicional
- Se agregó compatibilidad con imágenes de instalación del sistema operativo Windows 10 RS1 o versiones posteriores.  
<br/>
</details>

## <a name="additional-resources"></a>Recursos adicionales

| Artículo | Descripción  |
|:---|:---|
|[Actualización de Microsoft Defender para imágenes de instalación del sistema operativo Windows](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | Revisar los paquetes de actualización de antimalware para las imágenes de instalación del sistema operativo (archivos WIM y VHD). Obtén actualizaciones de Antivirus de Microsoft Defender para Windows 10 (ediciones Enterprise, Pro y Home), Windows Server 2019 y Imágenes de instalación de Windows Server 2016.  |
|[Administrar cómo se descargan y aplican las actualizaciones de protección](manage-protection-updates-microsoft-defender-antivirus.md) | Las actualizaciones de protección se pueden entregar a través de muchos orígenes. |
|[Administrar cuándo se deben descargar y aplicar las actualizaciones de protección](manage-protection-update-schedule-microsoft-defender-antivirus.md) | Puede programar cuándo deben descargarse las actualizaciones de protección. |
|[Administrar actualizaciones de puntos de conexión que están des actualizadas](manage-outdated-endpoints-microsoft-defender-antivirus.md) | Si un extremo pierde una actualización o un examen programado, puede forzar una actualización o examinar la próxima vez que un usuario inicia sesión. |
|[Administrar actualizaciones forzadas basadas en eventos](manage-event-based-updates-microsoft-defender-antivirus.md) | Puede configurar las actualizaciones de protección para que se descarguen al inicio o después de determinados eventos de protección entregados en la nube. |
|[Administrar actualizaciones para dispositivos móviles y máquinas virtuales (VM)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| Puede especificar la configuración, como si las actualizaciones deben producirse en la batería, que son especialmente útiles para dispositivos móviles y máquinas virtuales. |
