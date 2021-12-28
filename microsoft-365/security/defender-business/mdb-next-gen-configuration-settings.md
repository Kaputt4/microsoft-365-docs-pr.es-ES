---
title: Comprender las opciones de configuración de protección de última generación en Microsoft Defender para empresas (versión preliminar)
description: Comprender las opciones de configuración para la protección de próxima generación en Microsoft Defender para empresas (versión preliminar)
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/27/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 0d0c36fafbd3c35613e0efd50f842b80aa30b9cf
ms.sourcegitcommit: f8fbabf1ec7421cd7ad36aa52b8856fb863cf284
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/28/2021
ms.locfileid: "61620413"
---
# <a name="understand-next-generation-configuration-settings-in-microsoft-defender-for-business-preview"></a>Comprender las opciones de configuración de próxima generación en Microsoft Defender para empresas (versión preliminar)

> [!IMPORTANT]
> Microsoft Defender para empresas ya está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán aquí [para](https://aka.ms/mdb-preview) solicitarlo. Incorporaremos un conjunto inicial de clientes y asociados en las próximas semanas y ampliaremos la versión preliminar antes de la disponibilidad general. Ten en cuenta que la vista previa se iniciará con un [conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios)y agregaremos funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

La protección de última generación en Defender para empresas (versión preliminar) incluye una protección antivirus sólida y antimalware. Las directivas predeterminadas están diseñadas para proteger sus dispositivos y usuarios sin obstaculizar la productividad; sin embargo, también puede personalizar las directivas para que se adapten a sus necesidades empresariales. Y, si usas Microsoft Endpoint Manager, puedes usarlo para administrar las directivas y la configuración de seguridad.

**En este artículo se describe**:

- [Opciones y configuraciones de protección de última generación](#next-generation-protection-settings-and-options)
- [Otras configuraciones preconfiguradas en Defender para empresas (versión preliminar)](#other-preconfigured-settings-in-defender-for-business) 
- [Configuración y configuración predeterminadas de Defender para empresas Microsoft Endpoint Manager](#defender-for-business-default-settings-and-microsoft-endpoint-manager)

## <a name="next-generation-protection-settings-and-options"></a>Opciones y configuraciones de protección de última generación

En la tabla siguiente se enumeran las opciones y la configuración:<br/><br/>

| Configuración | Descripción |
|:---|:---|
| **Protección en tiempo real**  |  |
| **Activar la protección en tiempo real** | Habilitada de forma predeterminada, la protección en tiempo real localiza y detiene que el malware se ejecute en dispositivos. *Se recomienda mantener activada la protección en tiempo real.*<br/><br/>Cuando la protección en tiempo real está activada, configura las siguientes opciones:<br/>- La supervisión del comportamiento está activada ([AllowBehaviorMonitoring](/windows/client-management/mdm/policy-csp-defender#defender-allowbehaviormonitoring))<br/>- Se examinan todos los archivos y datos adjuntos descargados ([AllowIOAVProtection](/windows/client-management/mdm/policy-csp-defender#defender-allowioavprotection))<br/>- Los scripts que se usan en exploradores de Microsoft se examinan ([AllowScriptScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowscriptscanning))   |
| **Bloqueo a primera vista** | Habilitado de forma predeterminada, bloquear a primera vista bloquea el malware en segundos después de la detección, aumenta el tiempo (en segundos) permitido para enviar archivos de ejemplo para su análisis y establece el nivel de detección en Alto. *Se recomienda mantener el bloqueo a primera vista activado.*<br/><br/>Cuando el bloque a primera vista está activado, configura las siguientes opciones para Antivirus de Microsoft Defender: <br/>- El bloqueo y el examen de archivos sospechosos se establece en el nivel de bloqueo alto ([CloudBlockLevel](/windows/client-management/mdm/policy-csp-defender#defender-cloudblocklevel))<br/>- El número de segundos para que un archivo se bloquee y se comprueba se establece en 50 segundos ([CloudExtendedTimeout](/windows/client-management/mdm/policy-csp-defender#defender-cloudextendedtimeout)) <br/><br/>**IMPORTANTE:** Si el bloque a primera vista está desactivado, afecta y afecta a `CloudBlockLevel` `CloudExtendedTimeout` Antivirus de Microsoft Defender.  |
| **Habilitar protección de red** | Cuando está activada, la protección de red ayuda a proteger contra estafas de phishing, sitios de hospedaje contra vulnerabilidades de seguridad y contenido malintencionado en Internet. También impide que los usuarios apaguen la protección de red.<br/><br/>La protección de red se puede establecer en uno de los siguientes modos:<br/>- **Modo de bloqueo** (esta configuración es la predeterminada), lo que impide que los usuarios visiten sitios que se consideran no seguros. *Se recomienda mantener la protección de red establecida en Modo de bloqueo.*<br/>- **Modo auditoría**, que permite a los usuarios visitar sitios que podrían no ser seguros y realizar un seguimiento de la actividad de red desde o hacia dichos sitios <br/>- **Modo deshabilitado**, que impide que los usuarios visiten sitios que podrían no ser seguros ni realiza un seguimiento de la actividad de red desde o hacia dichos sitios |
| **Corrección**  |  |
| **Acción que se debe realizar en aplicaciones potencialmente no deseadas (PUA)** | PUA puede incluir software de publicidad, agrupación de software que ofrece instalar otro software sin firma y software de evasión que intenta eludir las características de seguridad. Aunque PUA no es necesariamente un virus, malware u otro tipo de amenazas, la PUA puede afectar al rendimiento del dispositivo.<br/><br/>La protección de LA PUA bloquea los elementos que se detectan como PUA. Puede establecer la protección de PUA en una de las siguientes opciones: <br/>- **Habilitado** (esta configuración es la predeterminada), que bloquea los elementos detectados como PUA en dispositivos. *Se recomienda mantener habilitada la protección de LA PUA.*<br/>- **Modo auditoría**, que no realiza ninguna acción en los elementos detectados como PUA <br/>- **Disabled**, que no detecta ni realiza acciones en elementos que podrían ser PUA |
| **Escanear**   |  |
| **Tipo de examen programado** | Considera la posibilidad de ejecutar un examen de antivirus semanal en tus dispositivos. Puede elegir entre las siguientes opciones de tipo de examen: <br/>- **El análisis rápido** comprueba las ubicaciones, como las claves del Registro y las carpetas de inicio, donde se podría registrar malware para empezar con un dispositivo. *Se recomienda usar la opción de exploración rápida.* <br/>- **Fullscan** comprueba todos los archivos y carpetas de un dispositivo <br/>- **Deshabilitado** significa que no se realizarán exámenes programados. Los usuarios aún pueden ejecutar exámenes en sus propios dispositivos. (En general, no se recomienda deshabilitar los exámenes programados). <br/><br/> [Obtenga más información sobre los tipos de examen](../defender-endpoint/schedule-antivirus-scans.md). |
| **Día de la semana para ejecutar un examen programado** | Seleccione un día para que se ejecuten los exámenes de antivirus semanales normales. |
| **Hora del día para ejecutar un examen programado** | Seleccione una hora para ejecutar los exámenes de antivirus programados periódicamente para que se ejecuten. |
| **Usar bajo rendimiento** | Esta configuración está desactivada de forma predeterminada. *Se recomienda mantener esta configuración desactivada.* Sin embargo, puedes activar esta configuración para limitar la memoria del dispositivo y los recursos que se usan durante los exámenes programados. <br/><br/>**IMPORTANTE** Si activa **Usar bajo rendimiento,** configura las siguientes opciones para Antivirus de Microsoft Defender: <br/>- Los archivos de archivo no se examinan ([AllowArchiveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowarchivescanning))<br/>- Los exámenes tienen asignada una prioridad de CPU baja ([EnableLowCPUPriority](/windows/client-management/mdm/policy-csp-defender#defender-enablelowcpupriority)) <br/>- Si se pierde un examen antivirus completo, no se ejecutará ningún examen de ponerse al día ([DisableCatchupFullScan](/windows/client-management/mdm/policy-csp-defender#defender-disablecatchupfullscan)) <br/>- Si se pierde un examen rápido del antivirus, no se ejecutará ningún examen de recuperación ([DisableCatchupQuickScan](/windows/client-management/mdm/policy-csp-defender#defender-disablecatchupquickscan)) <br/>- Reduce el factor de carga de CPU promedio durante un examen antivirus del 50 % al 20 % ([AvgCPULoadFactor](/windows/client-management/mdm/policy-csp-defender#defender-avgcpuloadfactor)) |
| **Experiencia del usuario**   |  |
| **Permitir que los usuarios accedan a la Seguridad de Windows aplicación** | Activa esta configuración para permitir a los usuarios abrir la aplicación Seguridad de Windows en sus dispositivos. Los usuarios no podrán invalidar la configuración que configures en Microsoft Defender para empresas (versión preliminar), pero podrán ejecutar un examen rápido si es necesario o ver las amenazas detectadas. |
| **Exclusiones de antivirus** | Las exclusiones son procesos, archivos o carpetas que se omiten Antivirus de Microsoft Defender exámenes. *En general, no es necesario definir exclusiones.* Antivirus de Microsoft Defender incluye muchas exclusiones automáticas basadas en comportamientos conocidos del sistema operativo y archivos de administración típicos.<br/><br/>[Más información sobre las exclusiones](../defender-endpoint/configure-exclusions-microsoft-defender-antivirus.md) |
| **Exclusiones de procesos** | Las exclusiones de procesos impiden que los archivos abiertos por procesos específicos sean examinados por Antivirus de Microsoft Defender. <br/><br/>[Más información sobre las exclusiones de procesos](../defender-endpoint/configure-process-opened-file-exclusions-microsoft-defender-antivirus.md) |
| **Exclusiones de extensión de archivo** | Las exclusiones de extensión de archivo impiden que los archivos con extensiones específicas sean examinados por Antivirus de Microsoft Defender.<br/><br/>[Más información sobre las exclusiones de extensiones de archivo](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md) |
| **Exclusiones de archivos y carpetas** | Las exclusiones de archivos y carpetas impiden que los archivos que están en carpetas específicas sean examinados por Antivirus de Microsoft Defender. <br/><br/>[Más información sobre las exclusiones de archivos y carpetas](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md) |

## <a name="other-preconfigured-settings-in-defender-for-business"></a>Otras configuraciones preconfiguradas en Defender para empresas

La siguiente configuración de seguridad está preconfigurada en Defender para empresas (versión preliminar):

- El examen de unidades extraíbles está activado ([AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning))
- Los exámenes rápidos diarios no tienen un tiempo preestablecido ([ScheduleQuickScanTime](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime))
- Las actualizaciones de inteligencia de seguridad se comprueban antes de que se ejecute un examen antivirus ([CheckForSignaturesBeforeRunningScan](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan))
- Las comprobaciones de inteligencia de seguridad se producen cada cuatro horas ([SignatureUpdateInterval](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval))

## <a name="defender-for-business-default-settings-and-microsoft-endpoint-manager"></a>Configuración y configuración predeterminadas de Defender para empresas Microsoft Endpoint Manager

En la tabla siguiente se describen las opciones preconfiguradas para Defender para empresas (versión preliminar) y cómo dicha configuración se corresponde con lo que puede ver en Microsoft Endpoint Manager (o Microsoft Intune). Si usa el proceso de configuración simplificado [en Defender para empresas](mdb-simplified-configuration.md) (versión preliminar), no es necesario editar esta configuración.
<br/><br/>

| Configuración  | Descripción  |
|---------|---------|
| [Protección en la nube](/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection)     | A veces denominada protección entregada en la nube o Servicio de protección avanzada de Microsoft (MAPS), la protección en la nube funciona con Antivirus de Microsoft Defender y la nube de Microsoft para identificar nuevas amenazas, a veces incluso antes de que un único dispositivo se ve afectado. De forma predeterminada, [AllowCloudProtection](/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection) está activado. <br/><br/>[Obtenga más información sobre la protección en la nube](../defender-endpoint/cloud-protection-microsoft-defender-antivirus.md).         |
| [Supervisión de archivos entrantes y salientes](/windows/client-management/mdm/policy-csp-defender#defender-realtimescandirection)     | Para supervisar los archivos entrantes y salientes, [RealTimeScanDirection](/windows/client-management/mdm/policy-csp-defender#defender-realtimescandirection) está configurado para supervisar todos los archivos.         |
| [Examinar archivos de red](/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) | De forma predeterminada, [AllowScanningNetworkFiles](/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) no está habilitado y los archivos de red no se examinan. |
| [Examinar mensajes de correo electrónico](/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) | De forma predeterminada, [AllowEmailScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) no está habilitado y los mensajes de correo electrónico no se examinan. |
| [Número de días (0-90) para mantener malware en cuarentena](/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) | De forma predeterminada, [DaysToRetainCleanedMalware](/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) esta configuración se establece en cero (0) días. Artifacts que en cuarentena no se quitan automáticamente.  |
| [Enviar muestras de consentimiento](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) | De forma predeterminada, [SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) es et para enviar muestras seguras automáticamente. Algunos ejemplos de ejemplos seguros `.bat` incluyen , , y archivos que no contienen información de identificación personal `.scr` `.dll` `.exe` (PII). Si un archivo contiene PII, el usuario recibe una solicitud para permitir que el envío de ejemplo continúe.<br/><br/>[Más información sobre la protección en la nube y el envío de muestras](../defender-endpoint/cloud-protection-microsoft-antivirus-sample-submission.md) |
| [Examinar unidades extraíbles](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) | De forma predeterminada, [AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) está configurado para examinar unidades extraíbles, como unidades usb en dispositivos.<br/><br/>[Más información sobre la configuración de directivas de antimalware](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#list-of-antimalware-policy-settings)   |
| [Ejecutar el tiempo de examen rápido diario](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) | De forma predeterminada, [ScheduleQuickScanTime](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) se establece en 2:00 AM.<br/><br/>[Obtenga más información sobre la configuración del examen](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings).   |
| [Comprobar si hay actualizaciones de firmas antes de ejecutar el examen](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan) | De forma predeterminada, [CheckForSignaturesBeforeRunningScan](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan) está configurado para buscar actualizaciones de inteligencia de seguridad antes de ejecutar exámenes antivirus/antimalware.<br/><br/>[Obtenga más información sobre la configuración del examen y](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) las actualizaciones de inteligencia de [seguridad.](../defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus.md#security-intelligence-updates)   |
| [Con qué frecuencia (de 0 a 24 horas) para comprobar si hay actualizaciones de inteligencia de seguridad](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) | De forma predeterminada, [SignatureUpdateInterval](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) está configurado para comprobar si hay actualizaciones de inteligencia de seguridad cada cuatro horas.<br/><br/>[Obtenga más información sobre la configuración del examen y](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) las actualizaciones de inteligencia de [seguridad.](../defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus.md#security-intelligence-updates) |


## <a name="next-steps"></a>Pasos siguientes

- [Ver y administrar incidentes en Microsoft Defender para empresas (versión preliminar)](mdb-view-manage-incidents.md)

- [Responder y mitigar amenazas en Microsoft Defender para empresas (versión preliminar)](mdb-respond-mitigate-threats.md)

- [Revisar acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)


## <a name="see-also"></a>Consulte también

- [Visite el portal Microsoft 365 Defender web](mdb-get-started.md)

- [Administrar la configuración del firewall en Microsoft Defender para empresas (versión preliminar)](mdb-custom-rules-firewall.md)

- [CSP de directivas: Defender](/windows/client-management/mdm/policy-csp-defender)
