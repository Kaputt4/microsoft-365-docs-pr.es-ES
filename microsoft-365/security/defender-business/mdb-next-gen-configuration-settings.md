---
title: Descripción de las opciones de configuración de protección de próxima generación en Microsoft Defender para Empresas
description: Descripción de la configuración de protección antivirus y de próxima generación en Defender para empresas, seguridad de puntos de conexión para pequeñas y medianas empresas.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 34cbd422cafe5c171f47e8e6470c4b12f9e1700d
ms.sourcegitcommit: f30616b90b382409f53a056b7a6c8be078e6866f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "65174469"
---
# <a name="understand-next-generation-configuration-settings-in-microsoft-defender-for-business"></a>Descripción de la configuración de próxima generación en Microsoft Defender para Empresas

La protección de última generación en Defender for Business incluye antivirus sólidos y protección antimalware. Las directivas predeterminadas están diseñadas para proteger los dispositivos y los usuarios sin obstaculizar la productividad; sin embargo, también puede personalizar las directivas para satisfacer sus necesidades empresariales. Además, si usa Microsoft Intune, puede usar el centro de administración de Microsoft Endpoint Manager para administrar las directivas de seguridad.

**En este artículo se describe**:

- [Configuración y opciones de protección de última generación](#next-generation-protection-settings-and-options)
- [Otras configuraciones preconfiguradas en Defender para empresas](#other-preconfigured-settings-in-defender-for-business) 
- [Configuración predeterminada de Defender for Business y Microsoft Intune](#defender-for-business-default-settings-and-microsoft-intune)

## <a name="next-generation-protection-settings-and-options"></a>Configuración y opciones de protección de última generación

En la tabla siguiente se enumeran la configuración y las opciones:

| Configuración | Descripción |
|:---|:---|
| **Protección en tiempo real**  |  |
| **Activar la protección en tiempo real** | Habilitada de forma predeterminada, la protección en tiempo real busca y evita que el malware se ejecute en los dispositivos. *Se recomienda mantener activada la protección en tiempo real.*<br/><br/>Cuando se activa la protección en tiempo real, configura los siguientes valores:<br/>- La supervisión del comportamiento está activada ([AllowBehaviorMonitoring](/windows/client-management/mdm/policy-csp-defender#defender-allowbehaviormonitoring))<br/>- Se examinan todos los archivos y datos adjuntos descargados ([AllowIOAVProtection](/windows/client-management/mdm/policy-csp-defender#defender-allowioavprotection))<br/>- Los scripts que se usan en exploradores de Microsoft se [examinan (AllowScriptScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowscriptscanning))   |
| **Bloqueo a primera vista** | Habilitado de forma predeterminada, bloquear a primera vista bloquea el malware en segundos después de la detección, aumenta el tiempo (en segundos) permitido para enviar archivos de ejemplo para su análisis y establece el nivel de detección en Alto. *Se recomienda mantener activado el bloqueo a primera vista.*<br/><br/>Cuando el bloqueo a primera vista está activado, configura los siguientes valores para Antivirus de Microsoft Defender: <br/>- El bloqueo y el examen de archivos sospechosos se establece en el nivel de bloqueo alto ([CloudBlockLevel](/windows/client-management/mdm/policy-csp-defender#defender-cloudblocklevel))<br/>- El número de segundos para que un archivo se bloquee y compruebe se establece en 50 segundos ([CloudExtendedTimeout](/windows/client-management/mdm/policy-csp-defender#defender-cloudextendedtimeout)) <br/><br/>**IMPORTANTE**: Si el bloqueo a primera vista está desactivado, afecta a `CloudBlockLevel` y `CloudExtendedTimeout` para Antivirus de Microsoft Defender.  |
| **Habilitar protección de red** | Cuando está activada, la protección de red ayuda a protegerse frente a estafas de suplantación de identidad (phishing), sitios de hospedaje de vulnerabilidades de seguridad y contenido malintencionado en Internet. También impide que los usuarios desactiven la protección de red.<br/><br/>La protección de red se puede establecer en uno de los modos siguientes:<br/>- **Modo de bloque** (esta configuración es la predeterminada), lo que impide que los usuarios visiten sitios que se consideran no seguros. *Se recomienda mantener la protección de red establecida en modo de bloqueo.*<br/>- **Modo de auditoría**, que permite a los usuarios visitar sitios que podrían no ser seguros y realizar un seguimiento de la actividad de red hacia y desde dichos sitios <br/>- **Modo deshabilitado**, que impide a los usuarios visitar sitios que podrían no ser seguros ni realizar un seguimiento de la actividad de red hacia y desde dichos sitios |
| **Remediación**  |  |
| **Acción para realizar aplicaciones potencialmente no deseadas (PUA)** | PUA puede incluir software de publicidad, software de agrupación que ofrece para instalar otro software sin firmar y software de evasión que intenta eludir las características de seguridad. Aunque PUA no es necesariamente un virus, malware u otro tipo de amenazas, PUA puede afectar al rendimiento del dispositivo.<br/><br/>La protección pua bloquea los elementos que se detectan como PUA. Puede establecer la protección pua en una de las siguientes opciones: <br/>- **Habilitado** (esta configuración es la predeterminada), que bloquea los elementos detectados como PUA en los dispositivos. *Se recomienda mantener habilitada la protección de PUA.*<br/>- **Modo de auditoría**, que no realiza ninguna acción en los elementos detectados como PUA <br/>- **Deshabilitado**, que no detecta ni toma medidas en elementos que podrían ser PUA |
| **Escanear**   |  |
| **Tipo de examen programado** | Considere la posibilidad de ejecutar un examen antivirus semanal en los dispositivos. Puede elegir entre las siguientes opciones de tipo de examen: <br/>- **Quickscan** comprueba las ubicaciones, como las claves del Registro y las carpetas de inicio, donde se podría registrar malware para empezar con un dispositivo. *Se recomienda usar la opción quickscan.* <br/>- **Fullscan** comprueba todos los archivos y carpetas de un dispositivo <br/>- **Deshabilitado** significa que no se realizará ningún examen programado. Los usuarios todavía pueden ejecutar exámenes en sus propios dispositivos. (En general, no se recomienda deshabilitar los exámenes programados). <br/><br/> [Obtenga más información sobre los tipos de examen](../defender-endpoint/schedule-antivirus-scans.md). |
| **Día de la semana para ejecutar un examen programado** | Seleccione un día para que se ejecuten los exámenes antivirus normales y semanales. |
| **Hora del día para ejecutar un examen programado** | Seleccione una hora para ejecutar los exámenes antivirus programados periódicamente para ejecutarse. |
| **Uso de bajo rendimiento** | Esta configuración está desactivada de forma predeterminada. *Se recomienda mantener esta configuración desactivada.* Sin embargo, puede activar esta configuración para limitar la memoria del dispositivo y los recursos que se usan durante los exámenes programados. <br/><br/>**IMPORTANTE** Si activa **Usar bajo rendimiento**, configura los siguientes valores para Antivirus de Microsoft Defender: <br/>- No se examinan los archivos de archivo ([AllowArchiveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowarchivescanning))<br/>- A los exámenes se les asigna una prioridad de CPU baja ([EnableLowCPUPriority](/windows/client-management/mdm/policy-csp-defender#defender-enablelowcpupriority)) <br/>- Si se pierde un examen antivirus completo, no se ejecutará ningún examen de puesta al día ([DisableCatchupFullScan](/windows/client-management/mdm/policy-csp-defender#defender-disablecatchupfullscan)) <br/>- Si se pierde un examen rápido del antivirus, no se ejecutará ningún examen de puesta al día ([DisableCatchupQuickScan](/windows/client-management/mdm/policy-csp-defender#defender-disablecatchupquickscan)) <br/>- Reduce el factor de carga promedio de CPU durante un examen antivirus del 50 % al 20 % ([AvgCPULoadFactor](/windows/client-management/mdm/policy-csp-defender#defender-avgcpuloadfactor)) |
| **Experiencia del usuario**   |  |
| **Permitir que los usuarios accedan a la aplicación Seguridad de Windows** | Active esta opción para permitir que los usuarios abran la aplicación Seguridad de Windows en sus dispositivos. Los usuarios no podrán invalidar la configuración que configure en Microsoft Defender para Empresas, pero podrán ejecutar un examen rápido si es necesario o ver las amenazas detectadas. |
| **Exclusiones de antivirus** | Las exclusiones son procesos, archivos o carpetas omitidos por Antivirus de Microsoft Defender exámenes. *En general, no es necesario definir exclusiones.* Antivirus de Microsoft Defender incluye muchas exclusiones automáticas basadas en comportamientos conocidos del sistema operativo y archivos de administración típicos.<br/><br/>[Más información sobre las exclusiones](../defender-endpoint/configure-exclusions-microsoft-defender-antivirus.md) |
| **Exclusiones de procesos** | Las exclusiones de procesos impiden que Antivirus de Microsoft Defender analicen los archivos abiertos por procesos específicos. <br/><br/>[Más información sobre las exclusiones de procesos](../defender-endpoint/configure-process-opened-file-exclusions-microsoft-defender-antivirus.md) |
| **Exclusiones de extensiones de archivo** | Las exclusiones de extensiones de archivo impiden que Antivirus de Microsoft Defender analicen los archivos con extensiones específicas.<br/><br/>[Más información sobre las exclusiones de extensiones de archivo](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md) |
| **Exclusiones de archivos y carpetas** | Las exclusiones de archivos y carpetas impiden que Antivirus de Microsoft Defender analicen los archivos que se encuentran en carpetas específicas. <br/><br/>[Más información sobre las exclusiones de archivos y carpetas](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md) |

## <a name="other-preconfigured-settings-in-defender-for-business"></a>Otras configuraciones preconfiguradas en Defender para empresas

La siguiente configuración de seguridad está preconfigurada en Defender para empresas:

- El examen de unidades extraíbles está activado ([AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning))
- Los exámenes rápidos diarios no tienen una hora preestablecida ([ScheduleQuickScanTime](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime))
- Las actualizaciones de inteligencia de seguridad se comprueban antes de que se ejecute un examen antivirus ([CheckForSignaturesBeforeRunningScan](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan))
- Las comprobaciones de inteligencia de seguridad se producen cada cuatro horas ([SignatureUpdateInterval](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval))

## <a name="defender-for-business-default-settings-and-microsoft-intune"></a>Configuración predeterminada de Defender for Business y Microsoft Intune

En la tabla siguiente se describen los valores preconfigurados para Defender para empresas y cómo se corresponden con lo que puede ver en Intune (administrado en el centro de administración de Microsoft Endpoint Manager). Si usa el [proceso de configuración simplificado en Defender for Business](mdb-simplified-configuration.md), no es necesario editar esta configuración.

| Configuración  | Descripción  |
|---------|---------|
| [Protección en la nube](/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection)     | A veces denominada protección entregada en la nube o Servicio de protección avanzada de Microsoft (MAPS), la protección en la nube funciona con Antivirus de Microsoft Defender y la nube de Microsoft para identificar nuevas amenazas, a veces incluso antes de que un solo dispositivo se vea afectado. De forma predeterminada, [AllowCloudProtection](/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection) está activado. <br/><br/>[Más información sobre la protección en la nube](../defender-endpoint/cloud-protection-microsoft-defender-antivirus.md).         |
| [Supervisión de archivos entrantes y salientes](/windows/client-management/mdm/policy-csp-defender#defender-realtimescandirection)     | Para supervisar los archivos entrantes y salientes, [RealTimeScanDirection](/windows/client-management/mdm/policy-csp-defender#defender-realtimescandirection) está establecido para supervisar todos los archivos.         |
| [Examen de archivos de red](/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) | De forma predeterminada, [AllowScanningNetworkFiles](/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) no está habilitado y los archivos de red no se examinan. |
| [Examen de mensajes de correo electrónico](/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) | De forma predeterminada, [AllowEmailScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) no está habilitado y los mensajes de correo electrónico no se examinan. |
| [Número de días (0-90) para mantener el malware en cuarentena](/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) | De forma predeterminada, [DaysToRetainCleanedMalware](/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) esta configuración se establece en cero (0) días. Artifacts que en cuarentena no se quitan automáticamente.  |
| [Enviar el consentimiento de ejemplos](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) | De forma predeterminada, [SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) está establecido para enviar muestras seguras automáticamente. Algunos ejemplos de ejemplos seguros son `.bat`, `.scr`, `.dll`y `.exe` archivos que no contienen información de identificación personal (PII). Si un archivo contiene PII, el usuario recibe una solicitud para permitir que continúe el envío de ejemplo.<br/><br/>[Más información sobre la protección en la nube y el envío de ejemplos](../defender-endpoint/cloud-protection-microsoft-antivirus-sample-submission.md) |
| [Examen de unidades extraíbles](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) | De forma predeterminada, [AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) está configurado para examinar unidades extraíbles, como unidades usb en dispositivos.<br/><br/>[Más información sobre la configuración de directivas antimalware](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#list-of-antimalware-policy-settings)   |
| [Ejecución del tiempo de examen rápido diario](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) | De forma predeterminada, [ScheduleQuickScanTime](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) se establece en 2:00 AM.<br/><br/>[Obtenga más información sobre la configuración del examen](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings).   |
| [Comprobación de actualizaciones de firmas antes de ejecutar el examen](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan) | De forma predeterminada, [CheckForSignaturesBeforeRunningScan](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan) está configurado para comprobar si hay actualizaciones de inteligencia de seguridad antes de ejecutar exámenes antivirus o antimalware.<br/><br/>[Obtenga más información sobre la configuración de examen](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) y [las actualizaciones de inteligencia de seguridad](../defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus.md#security-intelligence-updates).   |
| [Frecuencia (0-24 horas) para comprobar si hay actualizaciones de inteligencia de seguridad](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) | De forma predeterminada, [SignatureUpdateInterval](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) está configurado para comprobar si hay actualizaciones de inteligencia de seguridad cada cuatro horas.<br/><br/>[Obtenga más información sobre la configuración de examen](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) y [las actualizaciones de inteligencia de seguridad](../defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus.md#security-intelligence-updates). |


## <a name="next-steps"></a>Siguientes pasos

- [Visualización y administración de incidentes en Microsoft Defender para Empresas](mdb-view-manage-incidents.md)
- [Respuesta y mitigación de amenazas en Microsoft Defender para Empresas](mdb-respond-mitigate-threats.md)
- [Revisión de las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)


## <a name="see-also"></a>Consulte también

- [Visitar el portal de Microsoft 365 Defender](mdb-get-started.md)
- [Administración de la configuración del firewall en Microsoft Defender para Empresas](mdb-custom-rules-firewall.md)
- [CSP de directiva: Defender](/windows/client-management/mdm/policy-csp-defender)
