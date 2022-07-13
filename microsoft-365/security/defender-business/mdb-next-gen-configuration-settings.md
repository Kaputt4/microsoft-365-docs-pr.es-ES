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
ms.openlocfilehash: 69eea26df1f96b72ef66e53e46d679f40f0294b7
ms.sourcegitcommit: fa90763559239c4c46c5e848939126763879d8e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2022
ms.locfileid: "66772485"
---
# <a name="understand-next-generation-configuration-settings-in-microsoft-defender-for-business"></a>Descripción de la configuración de próxima generación en Microsoft Defender para Empresas

La protección de última generación en Defender for Business incluye antivirus sólidos y protección antimalware. Las directivas predeterminadas están diseñadas para proteger los dispositivos y los usuarios sin obstaculizar la productividad. También puede personalizar las directivas para satisfacer sus necesidades empresariales. Además, si usa Microsoft Intune, puede usar el Centro de administración de Microsoft Endpoint Manager para administrar las directivas de seguridad.

**En este artículo se describe**:

- [Configuración y opciones de protección de última generación](#next-generation-protection-settings-and-options)
- [Otras configuraciones preconfiguradas en Defender para empresas](#other-preconfigured-settings-in-defender-for-business) 
- [Configuración predeterminada de Defender for Business y Microsoft Intune](#defender-for-business-default-settings-and-microsoft-intune)

## <a name="next-generation-protection-settings-and-options"></a>Configuración y opciones de protección de última generación

En la tabla siguiente se enumeran la configuración y las opciones.

| Valor | Descripción |
|:---|:---|
| **Protección en tiempo real**  |  |
| **Activar la protección en tiempo real** | Habilitada de forma predeterminada, la protección en tiempo real busca y evita que el malware se ejecute en los dispositivos. *Se recomienda mantener activada la protección en tiempo real.*<p>Cuando se activa la protección en tiempo real, configura los siguientes valores:<ul><li>La supervisión del comportamiento está activada ([AllowBehaviorMonitoring](/windows/client-management/mdm/policy-csp-defender#defender-allowbehaviormonitoring)).</li><li>Se examinan todos los archivos y datos adjuntos descargados ([AllowIOAVProtection](/windows/client-management/mdm/policy-csp-defender#defender-allowioavprotection)).</li><li>Los scripts que se usan en exploradores de Microsoft se [examinan (AllowScriptScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowscriptscanning)).</li></ul>   |
| **Bloqueo a primera vista** | Habilitado de forma predeterminada, bloquear a primera vista bloquea el malware en segundos después de la detección, aumenta el tiempo (en segundos) permitido para enviar archivos de ejemplo para su análisis y establece el nivel de detección en Alto. *Se recomienda mantener activado el bloqueo a primera vista.*<p>Cuando el bloqueo a primera vista está activado, configura los siguientes valores para el Antivirus de Microsoft Defender:<ul><li>El bloqueo y el examen de archivos sospechosos se establecen en el nivel de bloqueo alto ([CloudBlockLevel](/windows/client-management/mdm/policy-csp-defender#defender-cloudblocklevel)).</li><li>El número de segundos para que un archivo se bloquee y compruebe se establece en 50 segundos ([CloudExtendedTimeout](/windows/client-management/mdm/policy-csp-defender#defender-cloudextendedtimeout)).</li></ul> <p>**Importante** Si el bloqueo a primera vista está desactivado, afecta a `CloudBlockLevel` y `CloudExtendedTimeout` para el Antivirus de Microsoft Defender.  |
| **Habilitar protección de red** | Cuando está activada, la protección de red ayuda a protegerse frente a estafas de suplantación de identidad (phishing), sitios de hospedaje de vulnerabilidades de seguridad y contenido malintencionado en Internet. También impide que los usuarios desactiven la protección de red.<p>La protección de red se puede establecer en los modos siguientes:<ul><li>**El modo de bloque** es la configuración predeterminada. Impide que los usuarios visiten sitios que se consideran no seguros. *Se recomienda mantener la protección de red establecida en modo de bloqueo.*</li><li>**El modo auditoría** permite a los usuarios visitar sitios que podrían no ser seguros y realizar un seguimiento de la actividad de red hacia y desde dichos sitios.</li><li>**El modo deshabilitado** no impide que los usuarios visiten sitios que podrían no ser seguros ni realiza un seguimiento de la actividad de red hacia o desde dichos sitios.</li></ul> |
| **Remediación**  |  |
| **Acción para realizar aplicaciones potencialmente no deseadas (PUA)** | PUA puede incluir software de publicidad; agrupación de software que ofrece para instalar otro software sin firmar; y el software de evasión que intenta eludir las características de seguridad. Aunque PUA no es necesariamente un virus, malware u otro tipo de amenaza, puede afectar al rendimiento del dispositivo.<p>La protección pua bloquea los elementos que se detectan como PUA. Puede establecer la protección pua en lo siguiente:<ul><li>**Habilitado** es la configuración predeterminada. Bloquea los elementos detectados como PUA en los dispositivos. *Se recomienda mantener habilitada la protección de PUA.*</li><li>**El modo auditoría** no realiza ninguna acción en los elementos detectados como PUA.</li><li>**Deshabilitado** no detecta ni realiza acciones en elementos que podrían ser PUA.</li></ul> |
| **Escanear**   |  |
| **Tipo de examen programado** | Considere la posibilidad de ejecutar un examen antivirus semanal en los dispositivos. Puede elegir entre las siguientes opciones de tipo de examen:<ul><li>**Quickscan** comprueba las ubicaciones, como las claves del Registro y las carpetas de inicio, donde se podría registrar malware para iniciarse junto con un dispositivo. *Se recomienda usar la opción quickscan.*</li><li>**Fullscan** comprueba todos los archivos y carpetas de un dispositivo.</li><li>**Deshabilitado** significa que no se realizará ningún examen programado. Los usuarios todavía pueden ejecutar exámenes en sus propios dispositivos. (En general, no se recomienda deshabilitar los exámenes programados).</li></ul><p> [Obtenga más información sobre los tipos de examen](../defender-endpoint/schedule-antivirus-scans.md). |
| **Día de la semana para ejecutar un examen programado** | Seleccione un día para que se ejecuten los exámenes antivirus normales y semanales. |
| **Hora del día para ejecutar un examen programado** | Seleccione una hora para ejecutar los exámenes antivirus programados periódicamente para ejecutarse. |
| **Uso de bajo rendimiento** | Esta configuración está desactivada de forma predeterminada. *Se recomienda mantener esta configuración desactivada.* Sin embargo, puede activar esta configuración para limitar la memoria del dispositivo y los recursos que se usan durante los exámenes programados. <p>**Importante** Si activa **Usar bajo rendimiento**, configura los siguientes valores para el Antivirus de Microsoft Defender:<ul><li>Los archivos de archivo no se [examinan (AllowArchiveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowarchivescanning)).</li><li>A los exámenes se les asigna una prioridad de CPU baja ([EnableLowCPUPriority](/windows/client-management/mdm/policy-csp-defender#defender-enablelowcpupriority)).</li><li>Si se pierde un examen antivirus completo, no se ejecutará ningún examen de puesta al día ([DisableCatchupFullScan](/windows/client-management/mdm/policy-csp-defender#defender-disablecatchupfullscan)).</li><li>Si se pierde un examen rápido del antivirus, no se ejecutará ningún examen de puesta al día ([DisableCatchupQuickScan](/windows/client-management/mdm/policy-csp-defender#defender-disablecatchupquickscan)).</li><li>Reduce el promedio de factor de carga de CPU durante un examen antivirus del 50 al 20 por ciento ([AvgCPULoadFactor](/windows/client-management/mdm/policy-csp-defender#defender-avgcpuloadfactor)).</li></ul> |
| **Experiencia del usuario**   |  |
| **Permitir que los usuarios accedan a la aplicación Seguridad de Windows** | Active esta configuración para permitir que los usuarios abran la aplicación Seguridad de Windows en sus dispositivos. Los usuarios no podrán invalidar la configuración que configure en Defender for Business, pero podrán ejecutar un examen rápido o ver las amenazas detectadas. |
| **Exclusiones de antivirus** | Las exclusiones son procesos, archivos o carpetas omitidos por los exámenes del Antivirus de Microsoft Defender. *En general, no es necesario definir exclusiones.* Antivirus de Microsoft Defender incluye muchas exclusiones automáticas basadas en el comportamiento conocido del sistema operativo y los archivos de administración típicos.<p>[Obtenga más información sobre las exclusiones](../defender-endpoint/configure-exclusions-microsoft-defender-antivirus.md). |
| **Exclusiones de procesos** | Las exclusiones de procesos impiden que antivirus de Microsoft Defender analice los archivos abiertos por procesos específicos. <p>[Obtenga más información sobre las exclusiones de procesos](../defender-endpoint/configure-process-opened-file-exclusions-microsoft-defender-antivirus.md). |
| **Exclusiones de extensiones de archivo** | Las exclusiones de extensiones de archivo impiden que antivirus de Microsoft Defender analice los archivos con extensiones específicas.<p>[Obtenga más información sobre las exclusiones de extensiones de archivo](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md). |
| **Exclusiones de archivos y carpetas** | Las exclusiones de archivos y carpetas impiden que antivirus de Microsoft Defender analice los archivos que se encuentran en carpetas específicas. <p>[Obtenga más información sobre las exclusiones de archivos y carpetas](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md). |

## <a name="other-preconfigured-settings-in-defender-for-business"></a>Otras configuraciones preconfiguradas en Defender para empresas

La siguiente configuración de seguridad está preconfigurada en Defender para empresas:

- El examen de unidades extraíbles está activado ([AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning)).
- Los exámenes rápidos diarios no tienen una hora preestablecida ([ScheduleQuickScanTime](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime)).
- Las actualizaciones de inteligencia de seguridad se comprueban antes de que se ejecute un examen antivirus ([CheckForSignaturesBeforeRunningScan](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan)).
- Las comprobaciones de inteligencia de seguridad se producen cada cuatro horas ([SignatureUpdateInterval](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval)).

## <a name="defender-for-business-default-settings-and-microsoft-intune"></a>Configuración predeterminada de Defender for Business y Microsoft Intune

En la tabla siguiente se describen los valores preconfigurados para Defender para empresas y cómo se corresponden con lo que puede ver en Intune (administrado en el Centro de administración de Microsoft Endpoint Manager). Si usa el [proceso de configuración simplificado en Defender for Business](mdb-simplified-configuration.md), no es necesario editar esta configuración.

| Valor  | Descripción  |
|---------|---------|
| [Protección en la nube](/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection)     | A veces denominada protección entregada en la nube o Servicio de protección avanzada de Microsoft (MAPS), la protección en la nube funciona con el Antivirus de Microsoft Defender y la nube de Microsoft para identificar nuevas amenazas, a veces incluso antes de que un solo dispositivo se vea afectado. De forma predeterminada, [AllowCloudProtection](/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection) está activado. <p>[Más información sobre la protección en la nube](../defender-endpoint/cloud-protection-microsoft-defender-antivirus.md).         |
| [Supervisión de archivos entrantes y salientes](/windows/client-management/mdm/policy-csp-defender#defender-realtimescandirection)     | Para supervisar los archivos entrantes y salientes, [RealTimeScanDirection](/windows/client-management/mdm/policy-csp-defender#defender-realtimescandirection) está establecido para supervisar todos los archivos.         |
| [Examen de archivos de red](/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) | De forma predeterminada, [AllowScanningNetworkFiles](/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) no está habilitado y los archivos de red no se examinan. |
| [Examen de mensajes de correo electrónico](/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) | De forma predeterminada, [AllowEmailScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) no está habilitado y los mensajes de correo electrónico no se examinan. |
| [Número de días (0-90) para mantener el malware en cuarentena](/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) | De forma predeterminada, la configuración [DaysToRetainCleanedMalware](/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) se establece en cero (0) días. Los artefactos que están en cuarentena no se quitan automáticamente.  |
| [Enviar el consentimiento de ejemplos](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) | De forma predeterminada, [SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) está establecido para enviar muestras seguras automáticamente. Algunos ejemplos de ejemplos seguros son `.bat`, `.scr`, `.dll`y `.exe` archivos que no contienen información de identificación personal (PII). Si un archivo contiene PII, el usuario recibe una solicitud para permitir que continúe el envío de ejemplo.<p>[Obtenga más información sobre la protección en la nube y el envío de ejemplos](../defender-endpoint/cloud-protection-microsoft-antivirus-sample-submission.md). |
| [Examen de unidades extraíbles](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) | De forma predeterminada, [AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) está configurado para examinar unidades extraíbles, como unidades usb en dispositivos.<p>[Obtenga más información sobre la configuración de directivas antimalware](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#list-of-antimalware-policy-settings).   |
| [Ejecución del tiempo de examen rápido diario](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) | De forma predeterminada, [ScheduleQuickScanTime](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) se establece en 2:00 AM.<p>[Obtenga más información sobre la configuración del examen](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings).   |
| [Comprobación de actualizaciones de firmas antes de ejecutar el examen](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan) | De forma predeterminada, [CheckForSignaturesBeforeRunningScan](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan) está configurado para comprobar si hay actualizaciones de inteligencia de seguridad antes de ejecutar exámenes antivirus o antimalware.<p>[Obtenga más información sobre la configuración de examen](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) y [las actualizaciones de inteligencia de seguridad](../defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus.md#security-intelligence-updates).   |
| [Frecuencia (0-24 horas) para comprobar si hay actualizaciones de inteligencia de seguridad](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) | De forma predeterminada, [SignatureUpdateInterval](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) está configurado para comprobar si hay actualizaciones de inteligencia de seguridad cada cuatro horas.<p>[Obtenga más información sobre la configuración de examen](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) y [las actualizaciones de inteligencia de seguridad](../defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus.md#security-intelligence-updates). |


## <a name="next-steps"></a>Pasos siguientes

- [Visualización y administración de incidentes en Defender para empresas](mdb-view-manage-incidents.md)
- [Respuesta y mitigación de amenazas en Defender para empresas](mdb-respond-mitigate-threats.md)
- [Revisión de las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)


## <a name="see-also"></a>Vea también

- [Visitar el portal de Microsoft 365 Defender](mdb-get-started.md)
- [Administración de la configuración del firewall en Defender para empresas](mdb-custom-rules-firewall.md)
- [CSP de directiva: Defender](/windows/client-management/mdm/policy-csp-defender)
