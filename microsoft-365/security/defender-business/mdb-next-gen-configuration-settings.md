---
title: Comprender las opciones de configuración de protección de última generación en Microsoft Defender para empresas (versión preliminar)
description: Comprender las opciones de configuración para la protección de próxima generación en Microsoft Defender para empresas (versión preliminar)
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/13/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: ab2d82c3b5db6b114b8172e0f4bf4aa3658eb28a
ms.sourcegitcommit: 74f79aacb4ffcc6cb0e315239b1493324eabb449
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2021
ms.locfileid: "61507247"
---
# <a name="understand-next-generation-configuration-settings-in-microsoft-defender-for-business-preview"></a>Comprender las opciones de configuración de próxima generación en Microsoft Defender para empresas (versión preliminar)

> [!IMPORTANT]
> Microsoft Defender para empresas ya está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán aquí [para](https://aka.ms/mdb-preview) solicitarlo. Incorporaremos un conjunto inicial de clientes y asociados en las próximas semanas y ampliaremos la versión preliminar antes de la disponibilidad general. Ten en cuenta que la vista previa se iniciará con un [conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios)y agregaremos funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

La protección de última generación en Microsoft Defender para empresas (versión preliminar) incluye protección antivirus y antimalware sólida. Las directivas predeterminadas están diseñadas para proteger sus dispositivos y usuarios sin obstaculizar la productividad; sin embargo, también puede personalizar las directivas para que se adapten a sus necesidades empresariales. 

**En este artículo se describe**:

- [Opciones y configuraciones de protección de última generación](#next-generation-protection-settings-and-options)
- [Configuración preconfigurada adicional](#additional-preconfigured-settings) 

## <a name="next-generation-protection-settings-and-options"></a>Opciones y configuraciones de protección de última generación

En la tabla siguiente se enumeran las opciones y la configuración:<br/><br/>

| Configuración | Descripción |
|:---|:---|
| **Protección en tiempo real**  |  |
| **Activar la protección en tiempo real** | Habilitada de forma predeterminada, la protección en tiempo real localiza y detiene que el malware se ejecute en dispositivos. *Se recomienda mantener activada la protección en tiempo real.*<br/><br/>Cuando la protección en tiempo real está activada, configura las siguientes opciones:<br/>- La supervisión del comportamiento está activada ([AllowBehaviorMonitoring](/windows/client-management/mdm/policy-csp-defender))<br/>- Se examinan todos los archivos y datos adjuntos descargados ([AllowIOAVProtection](/windows/client-management/mdm/policy-csp-defender))<br/>- Los scripts que se usan en exploradores de Microsoft se examinan ([AllowScriptScanning](/windows/client-management/mdm/policy-csp-defender))   |
| **Bloqueo a primera vista** | Habilitado de forma predeterminada, bloquear a primera vista bloquea el malware en segundos después de la detección, aumenta el tiempo (en segundos) permitido para enviar archivos de ejemplo para su análisis y establece el nivel de detección en Alto. *Se recomienda mantener el bloqueo a primera vista activado.*<br/><br/>Cuando el bloque a primera vista está activado, configura las siguientes opciones para Antivirus de Microsoft Defender: <br/>- El bloqueo y el examen de archivos sospechosos se establece en el nivel de bloqueo alto ([CloudBlockLevel](/windows/client-management/mdm/policy-csp-defender))<br/>- El número de segundos para que un archivo se bloquee y se comprueba se establece en 50 segundos ([CloudExtendedTimeout](/windows/client-management/mdm/policy-csp-defender)) <br/><br/>**IMPORTANTE:** Si el bloque a primera vista está desactivado, afecta y afecta a `CloudBlockLevel` `CloudExtendedTimeout` Antivirus de Microsoft Defender.  |
| **Habilitar protección de red** | Cuando está activada, la protección de red ayuda a proteger contra estafas de phishing, sitios de hospedaje contra vulnerabilidades de seguridad y contenido malintencionado en Internet. También impide que los usuarios apaguen la protección de red.<br/><br/>La protección de red se puede establecer en uno de los siguientes modos:<br/>- **Modo de bloqueo** (esta configuración es la predeterminada), lo que impide que los usuarios visiten sitios que se consideran no seguros. *Se recomienda mantener la protección de red establecida en Modo de bloqueo.*<br/>- **Modo auditoría**, que permite a los usuarios visitar sitios que podrían no ser seguros y realizar un seguimiento de la actividad de red desde o hacia dichos sitios <br/>- **Modo deshabilitado**, que impide que los usuarios visiten sitios que podrían no ser seguros ni realiza un seguimiento de la actividad de red desde o hacia dichos sitios |
| **Corrección**  |  |
| **Acción que se debe realizar en aplicaciones potencialmente no deseadas (PUA)** | PUA puede incluir software de publicidad, agrupación de software que ofrece instalar otro software sin firma y software de evasión que intenta eludir las características de seguridad. Aunque PUA no es necesariamente un virus, malware u otro tipo de amenazas, la PUA puede afectar al rendimiento del dispositivo.<br/><br/>La protección de LA PUA bloquea los elementos que se detectan como PUA. Puede establecer la protección de PUA en una de las siguientes opciones: <br/>- **Habilitado** (esta configuración es la predeterminada), que bloquea los elementos detectados como PUA en dispositivos. *Se recomienda mantener habilitada la protección de LA PUA.*<br/>- **Modo auditoría**, que no realiza ninguna acción en los elementos detectados como PUA <br/>- **Disabled**, que no detecta ni realiza acciones en elementos que podrían ser PUA |
| **Escanear**   |  |
| **Tipo de examen programado** | Considera la posibilidad de ejecutar un examen de antivirus semanal en tus dispositivos. Puede elegir entre las siguientes opciones de tipo de examen: <br/>- **El análisis rápido** comprueba las ubicaciones, como las claves del Registro y las carpetas de inicio, donde se podría registrar malware para empezar con un dispositivo. *Se recomienda usar la opción de exploración rápida.* <br/>- **Fullscan** comprueba todos los archivos y carpetas de un dispositivo <br/>- **Deshabilitado** significa que no se realizarán exámenes programados. Los usuarios aún pueden ejecutar exámenes en sus propios dispositivos. (En general, no se recomienda deshabilitar los exámenes programados). <br/><br/> [Obtenga más información sobre los tipos de examen](../defender-endpoint/schedule-antivirus-scans.md). |
| **Día de la semana para ejecutar un examen programado** | Seleccione un día para que se ejecuten los exámenes de antivirus semanales normales. |
| **Hora del día para ejecutar un examen programado** | Seleccione una hora para ejecutar los exámenes de antivirus programados periódicamente para que se ejecuten. |
| **Usar bajo rendimiento** | Esta configuración está desactivada de forma predeterminada. *Se recomienda mantener esta configuración desactivada.* Sin embargo, puedes activar esta configuración para limitar la memoria del dispositivo y los recursos que se usan durante los exámenes programados. <br/><br/>**IMPORTANTE** Si activa **Usar bajo rendimiento,** configura las siguientes opciones para Antivirus de Microsoft Defender: <br/>- Los archivos de archivo no se examinan ([AllowArchiveScanning](/windows/client-management/mdm/policy-csp-defender))<br/>- Los exámenes tienen asignada una prioridad de CPU baja ([EnableLowCPUPriority](/windows/client-management/mdm/policy-csp-defender)) <br/>- Si se pierde un examen antivirus completo, no se ejecutará ningún examen de ponerse al día ([DisableCatchupFullScan](/windows/client-management/mdm/policy-csp-defender)) <br/>- Si se pierde un examen rápido del antivirus, no se ejecutará ningún examen de recuperación ([DisableCatchupQuickScan](/windows/client-management/mdm/policy-csp-defender)) <br/>- Reduce el factor de carga de CPU promedio durante un examen antivirus del 50 % al 20 % ([AvgCPULoadFactor](/windows/client-management/mdm/policy-csp-defender)) |
| **Experiencia del usuario**   |  |
| **Permitir que los usuarios accedan a la Seguridad de Windows aplicación** | Activa esta configuración para permitir a los usuarios abrir la aplicación Seguridad de Windows en sus dispositivos. Los usuarios no podrán invalidar la configuración que configures en Microsoft Defender para empresas (versión preliminar), pero podrán ejecutar un examen rápido si es necesario o ver las amenazas detectadas. |
| **Exclusiones de antivirus** | Las exclusiones son procesos, archivos o carpetas que se omiten Antivirus de Microsoft Defender exámenes. *En general, no es necesario definir exclusiones.* Antivirus de Microsoft Defender incluye muchas exclusiones automáticas basadas en comportamientos conocidos del sistema operativo y archivos de administración típicos.<br/><br/>[Más información sobre las exclusiones](../defender-endpoint/configure-exclusions-microsoft-defender-antivirus.md) |
| **Exclusiones de procesos** | Las exclusiones de procesos impiden que los archivos abiertos por procesos específicos sean examinados por Antivirus de Microsoft Defender. <br/><br/>[Más información sobre las exclusiones de procesos](../defender-endpoint/configure-process-opened-file-exclusions-microsoft-defender-antivirus.md) |
| **Exclusiones de extensión de archivo** | Las exclusiones de extensión de archivo impiden que los archivos con extensiones específicas sean examinados por Antivirus de Microsoft Defender.<br/><br/>[Más información sobre las exclusiones de extensiones de archivo](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md) |
| **Exclusiones de archivos y carpetas** | Las exclusiones de archivos y carpetas impiden que los archivos que están en carpetas específicas sean examinados por Antivirus de Microsoft Defender. <br/><br/>[Más información sobre las exclusiones de archivos y carpetas](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md) |

## <a name="additional-preconfigured-settings"></a>Configuración preconfigurada adicional

La siguiente configuración adicional está preconfigurada para la protección de próxima generación en Defender para empresas (versión preliminar):

- El examen de unidades extraíbles está activado ([AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender))
- Los exámenes rápidos diarios no tienen un tiempo preestablecido ([ScheduleQuickScanTime](/windows/client-management/mdm/policy-csp-defender))
- Las actualizaciones de inteligencia de seguridad se comprueban antes de que se ejecute un examen antivirus ([CheckForSignaturesBeforeRunningScan](/windows/client-management/mdm/policy-csp-defender))
- Las comprobaciones de inteligencia de seguridad se producen cada cuatro horas ([SignatureUpdateInterval](/windows/client-management/mdm/policy-csp-defender))

## <a name="next-steps"></a>Pasos siguientes

- [Ver y administrar incidentes en Microsoft Defender para empresas (versión preliminar)](mdb-view-manage-incidents.md)

- [Responder y mitigar amenazas en Microsoft Defender para empresas (versión preliminar)](mdb-respond-mitigate-threats.md)

- [Revisar acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)


## <a name="see-also"></a>Vea también

- [Visite el portal Microsoft 365 Defender web](mdb-get-started.md)

- [Administrar la configuración del firewall en Microsoft Defender para empresas (versión preliminar)](mdb-custom-rules-firewall.md)

- [CSP de directivas: Defender](/windows/client-management/mdm/policy-csp-defender)