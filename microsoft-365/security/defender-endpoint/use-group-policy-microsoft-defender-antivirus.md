---
title: Configuración del Antivirus de Microsoft Defender con directiva de grupo
description: Obtenga información sobre cómo usar una directiva de grupo para configurar y administrar antivirus de Microsoft Defender en los puntos de conexión de Microsoft Defender para punto de conexión.
keywords: directiva de grupo, GPO, configuración, configuración
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/04/2022
ms.reviewer: ksarens, jtoole, pahuijbr
manager: dansimp
ms.subservice: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: 3ee7fa60e50d2b6ad606044b03eac4074443bd8a
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67575719"
---
# <a name="use-group-policy-settings-to-configure-and-manage-microsoft-defender-antivirus"></a>Uso de directiva de grupo configuración para configurar y administrar antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Puede usar [directiva de grupo](/windows/win32/srvnodes/group-policy) para configurar y administrar antivirus de Microsoft Defender en los puntos de conexión.

## <a name="configure-microsoft-defender-antivirus-using-group-policy"></a>Configuración del Antivirus de Microsoft Defender mediante directiva de grupo

En general, puede usar el procedimiento siguiente para configurar o cambiar la configuración de directiva de grupo del Antivirus de Microsoft Defender:

1. En la máquina de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón derecho en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.

2. Con el **Editor de administración de directiva de grupo** vaya a **Configuración del equipo**.

3. Haga clic en **Plantillas administrativas**.

4. Expanda el árbol a **componentes** \> de Windows **Antivirus de Microsoft Defender**.

5. Expanda la sección (denominada **Ubicación** en la tabla de este tema) que contiene la configuración que desea configurar, haga doble clic en la configuración para abrirla y realice cambios en la configuración.

6. [Implemente el GPO actualizado como lo hace normalmente](/windows/win32/srvnodes/group-policy).

## <a name="group-policy-settings-and-resources"></a>directiva de grupo configuración y recursos

En la tabla siguiente se enumeran las opciones de configuración de directiva de grupo que se usan habitualmente y que están disponibles en Windows 10.

> [!TIP]
> Descargue la hoja de cálculo de referencia de directiva de grupo, que muestra la configuración de directiva para las configuraciones de equipo y usuario que se incluyen en los archivos de plantilla administrativa entregados con para Windows. Puede configurar la referencia a la hoja de cálculo al editar directiva de grupo Objetos. <br/><br/> Estas son las versiones más recientes:
> - [Hoja de cálculo de referencia de configuración de directiva de grupo para Windows 10 actualización de mayo de 2020 (2004)](https://www.microsoft.com/download/details.aspx?id=101451)
> - [Hoja de cálculo de referencia de configuración de directiva de grupo para Windows 11 actualización de octubre de 2021 (21H2)](https://www.microsoft.com/download/details.aspx?id=103506)

<br/><br/>

|Ubicación|Setting|Artículo|
|---|---|---|
|Interfaz de cliente|Habilitación del modo de interfaz de usuario sin cabeza|[Impedir que los usuarios vean o interactúen con la interfaz de usuario del Antivirus de Microsoft Defender](prevent-end-user-interaction-microsoft-defender-antivirus.md)|
|Interfaz de cliente|Mostrar texto adicional a los clientes cuando necesiten realizar una acción|[Configurar las notificaciones que aparecen en los puntos de conexión](configure-notifications-microsoft-defender-antivirus.md)|
|Interfaz de cliente|Suprimir todas las notificaciones|[Configurar las notificaciones que aparecen en los puntos de conexión](configure-notifications-microsoft-defender-antivirus.md)|
|Interfaz de cliente|Suprime las notificaciones de reinicio|[Configurar las notificaciones que aparecen en los puntos de conexión](configure-notifications-microsoft-defender-antivirus.md)|
|Exclusiones|Exclusiones de extensiones|[Configuración y validación de exclusiones en exámenes del Antivirus de Microsoft Defender](configure-exclusions-microsoft-defender-antivirus.md)|
|Exclusiones|Exclusiones de ruta de acceso|[Configuración y validación de exclusiones en exámenes del Antivirus de Microsoft Defender](configure-exclusions-microsoft-defender-antivirus.md)|
|Exclusiones|Exclusiones de procesos|[Configuración y validación de exclusiones en exámenes del Antivirus de Microsoft Defender](configure-exclusions-microsoft-defender-antivirus.md)|
|Exclusiones|Desactivar exclusiones automáticas|[Configuración y validación de exclusiones en exámenes del Antivirus de Microsoft Defender](configure-exclusions-microsoft-defender-antivirus.md)|
|MAPAS|Configuración de la característica "Bloquear a primera vista"|[Habilitación del bloque a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md)|
|MAPAS|Unirse a Microsoft MAPS|[Habilitar la protección proporcionada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md)|
|MAPAS|Envío de ejemplos de archivos cuando se requiera un análisis adicional|[Habilitar la protección proporcionada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md)|
|MAPAS|Configuración de la invalidación de configuración local para informar a Microsoft MAPS|[Impedir o permitir que los usuarios modifiquen localmente la configuración de la directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|MpEngine|Configuración de la comprobación de nube extendida|[Configurar el período de espera de bloqueo en la nube](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)|
|MpEngine|Selección del nivel de protección en la nube|[Especificar el nivel de protección proporcionado en la nube](specify-cloud-protection-level-microsoft-defender-antivirus.md)|
|Sistema de inspección de red|Especificar conjuntos de definiciones adicionales para la inspección del tráfico de red| No usado (en desuso) |
|Sistema de inspección de red|Activar la retirada de definiciones| No usado (en desuso)|
|Sistema de inspección de red|Activar el reconocimiento de protocolos| No usado (en desuso)|
|Quarantine|Configuración de la invalidación de configuración local para la eliminación de elementos de la carpeta Cuarentena|[Impedir o permitir que los usuarios modifiquen localmente la configuración de la directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|Quarantine|Configuración de la eliminación de elementos de la carpeta Cuarentena|[Configuración de la corrección para exámenes del Antivirus de Microsoft Defender](configure-remediation-microsoft-defender-antivirus.md)|
|Protección en tiempo real|Configuración de la invalidación de configuración local para supervisar la actividad de archivos y programas en el equipo|[Impedir o permitir que los usuarios modifiquen localmente la configuración de la directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|Protección en tiempo real|Configuración de la invalidación de configuración local para la supervisión de la actividad de archivo entrante y saliente|[Impedir o permitir que los usuarios modifiquen localmente la configuración de la directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|Protección en tiempo real|Configuración de la invalidación de configuración local para examinar todos los archivos y datos adjuntos descargados|[Impedir o permitir que los usuarios modifiquen localmente la configuración de la directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|Protección en tiempo real|Configuración de la invalidación de configuración local para activar la supervisión del comportamiento|[Impedir o permitir que los usuarios modifiquen localmente la configuración de la directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|Protección en tiempo real|Configuración de la invalidación de configuración local para activar la protección en tiempo real|[Impedir o permitir que los usuarios modifiquen localmente la configuración de la directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|Protección en tiempo real|Definir el tamaño máximo de los archivos descargados y los datos adjuntos que se van a examinar|[Habilitación y configuración de la protección y supervisión always-on del Antivirus de Microsoft Defender](configure-real-time-protection-microsoft-defender-antivirus.md)|
|Protección en tiempo real|Supervisión de la actividad de archivos y programas en el equipo|[Habilitación y configuración de la protección y supervisión always-on del Antivirus de Microsoft Defender](configure-real-time-protection-microsoft-defender-antivirus.md)|
|Protección en tiempo real|Examinar todos los archivos y datos adjuntos descargados|[Habilitación y configuración de la protección y supervisión always-on del Antivirus de Microsoft Defender](configure-real-time-protection-microsoft-defender-antivirus.md)|
|Protección en tiempo real|Desactivar la protección en tiempo real|[Habilitación y configuración de la protección y supervisión always-on del Antivirus de Microsoft Defender](configure-real-time-protection-microsoft-defender-antivirus.md)|
|Protección en tiempo real|Activar la supervisión del comportamiento|[Habilitación y configuración de la protección y supervisión always-on del Antivirus de Microsoft Defender](configure-real-time-protection-microsoft-defender-antivirus.md)|
|Protección en tiempo real|Activar el examen de procesos siempre que se habilite la protección en tiempo real|[Habilitación y configuración de la protección y supervisión always-on del Antivirus de Microsoft Defender](configure-real-time-protection-microsoft-defender-antivirus.md)|
|Protección en tiempo real|Activar notificaciones de escritura de volumen sin procesar|[Habilitación y configuración de la protección y supervisión always-on del Antivirus de Microsoft Defender](configure-real-time-protection-microsoft-defender-antivirus.md)|
|Protección en tiempo real|Configuración de la supervisión de la actividad de archivos y programas entrantes y salientes|[Habilitación y configuración de la protección y supervisión always-on del Antivirus de Microsoft Defender](configure-real-time-protection-microsoft-defender-antivirus.md)|
|Remediación|Configuración de la invalidación de configuración local para la hora del día para ejecutar un examen completo programado para completar la corrección|[Impedir o permitir que los usuarios modifiquen localmente la configuración de la directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|Remediación|Especificar el día de la semana para ejecutar un examen completo programado para completar la corrección|[Configuración de exámenes programados del Antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|Remediación|Especificar la hora del día para ejecutar un examen completo programado para completar la corrección|[Configuración de exámenes programados del Antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|Reporting|Desactivar notificaciones mejoradas|[Configurar las notificaciones que aparecen en los puntos de conexión](configure-notifications-microsoft-defender-antivirus.md)
|Raíz|Desactivar antivirus de Microsoft Defender|No se usa. Si usa o planea usar un producto antivirus que no sea de Microsoft, consulte Compatibilidad del [Antivirus de Microsoft Defender con otros productos de seguridad](microsoft-defender-antivirus-compatibility.md).|
|Raíz|Definición de direcciones para omitir el servidor proxy|[Configurar las opciones de proxy de dispositivo y de conectividad a Internet](configure-proxy-internet.md#configure-a-static-proxy-for-microsoft-defender-antivirus)|
|Raíz|Definición de la configuración automática de proxy (.pac) para conectarse a la red|[Configurar las opciones de proxy de dispositivo y de conectividad a Internet](configure-proxy-internet.md#configure-a-static-proxy-for-microsoft-defender-antivirus)|
|Raíz|Definición del servidor proxy para conectarse a la red|[Configurar las opciones de proxy de dispositivo y de conectividad a Internet](configure-proxy-internet.md#configure-a-static-proxy-for-microsoft-defender-antivirus)|
|Raíz|Configuración del comportamiento de combinación de administrador local para listas|[Impedir o permitir que los usuarios modifiquen localmente la configuración de la directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|Raíz|Permitir que el servicio antimalware se inicie con prioridad normal|[Configuración de la corrección para exámenes del Antivirus de Microsoft Defender](configure-remediation-microsoft-defender-antivirus.md)|
|Raíz|Permitir que el servicio antimalware siga ejecutándose siempre|[Configuración de la corrección para exámenes del Antivirus de Microsoft Defender](configure-remediation-microsoft-defender-antivirus.md)|
|Raíz|Desactivar la corrección rutinaria|[Configuración de la corrección para exámenes del Antivirus de Microsoft Defender](configure-remediation-microsoft-defender-antivirus.md)|
|Raíz|Aleatorizar los tiempos de las tareas programadas|[Configuración de exámenes programados para antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|Examinar|Permitir a los usuarios pausar el examen|[Impedir que los usuarios vean o interactúen con la interfaz de usuario del Antivirus de Microsoft Defender](prevent-end-user-interaction-microsoft-defender-antivirus.md) (no se admite en Windows 10).|
|Examinar|Compruebe las definiciones de virus y spyware más recientes antes de ejecutar un examen programado.|[Administrar las actualizaciones forzadas basadas en eventos](manage-event-based-updates-microsoft-defender-antivirus.md)|
|Examinar|Definir el número de días después de los cuales se fuerza un examen de puesta al día|[Administrar actualizaciones para puntos finales que están desactualizados](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|Examinar|Activar el examen completo para ponerse al día|[Administrar actualizaciones para puntos finales que están desactualizados](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|Examinar|Activar el examen rápido para ponerse al día|[Administrar actualizaciones para puntos finales que están desactualizados](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|Examinar|Configuración de la invalidación de configuración local para el porcentaje máximo de uso de CPU|[Impedir o permitir que los usuarios modifiquen localmente la configuración de la directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|Examinar|Configuración de la invalidación de configuración local para el día del examen de programación|[Impedir o permitir que los usuarios modifiquen localmente la configuración de la directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|Examinar|Configuración de la invalidación de configuración local para el tiempo de examen rápido programado|[Impedir o permitir que los usuarios modifiquen localmente la configuración de la directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|Examinar|Configuración de la invalidación de configuración local para el tiempo de examen programado|[Impedir o permitir que los usuarios modifiquen localmente la configuración de la directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|Examinar|Configuración de la invalidación de configuración local para el tipo de examen que se usará para un examen programado|[Impedir o permitir que los usuarios modifiquen localmente la configuración de la directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|Examinar|Creación de un punto de restauración del sistema|[Configuración de la corrección para exámenes del Antivirus de Microsoft Defender](configure-remediation-microsoft-defender-antivirus.md)|
|Examinar|Activar la eliminación de elementos de la carpeta del historial de exámenes|[Configuración de la corrección para exámenes del Antivirus de Microsoft Defender](configure-remediation-microsoft-defender-antivirus.md)|
|Examinar|Activar la heurística|[Habilitación y configuración de la protección y supervisión always-on del Antivirus de Microsoft Defender](configure-real-time-protection-microsoft-defender-antivirus.md)|
|Examinar|Activar el examen de correo electrónico|[Configuración de opciones de examen en antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|Examinar|Activar el examen del punto de reanálisis|[Configuración de opciones de examen en antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|Examinar|Ejecución del examen completo en unidades de red asignadas|[Configuración de opciones de examen en antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|Examinar|Examen de archivos de archivo|[Configuración de opciones de examen en antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|Examinar|Examen de archivos de red|[Configuración de opciones de examen en antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|Examinar|Examen de archivos ejecutables empaquetados|[Configuración de opciones de examen en antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
| Examinar | Examen de scripts | [Configuración de opciones de examen en antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) <p>Consulte también [Defender/AllowScriptScanning](/windows/client-management/mdm/policy-csp-defender).|
|Examinar|Examen de unidades extraíbles|[Configuración de opciones de examen en antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|Examinar|Especificar la profundidad máxima para examinar archivos de archivo|[Configuración de opciones de examen en antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|Examinar|Especificar el porcentaje máximo de uso de CPU durante un examen|[Configuración de opciones de examen en antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|Examinar|Especificar el tamaño máximo de los archivos de archivo que se van a examinar|[Configuración de opciones de examen en antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|Examinar|Especificar el día de la semana para ejecutar un examen programado|[Configuración de exámenes programados para antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|Examinar|Especificar el intervalo para ejecutar exámenes rápidos al día|[Configuración de exámenes programados para antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|Examinar|Especificar el tipo de examen que se va a usar para un examen programado|[Configuración de exámenes programados para antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|Examinar|Especificar la hora de un examen rápido diario|[Configuración de exámenes programados para antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|Examinar|Especificar la hora del día para ejecutar un examen programado|[Configuración de exámenes programados para antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|Examinar|Iniciar el examen programado solo cuando el equipo está encendido, pero no en uso|[Configuración de exámenes programados para antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|Actualizaciones de inteligencia de seguridad|Permitir actualizaciones de inteligencia de seguridad de Microsoft Update|[Administrar las actualizaciones de dispositivos móviles y máquinas virtuales](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)|
|Actualizaciones de inteligencia de seguridad|Permitir actualizaciones de inteligencia de seguridad al ejecutarse con batería|[Administrar las actualizaciones de dispositivos móviles y máquinas virtuales](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)|
|Actualizaciones de inteligencia de seguridad|Permitir que las notificaciones deshabiliten informes basados en definiciones en Microsoft MAPS|[Administrar las actualizaciones forzadas basadas en eventos](manage-event-based-updates-microsoft-defender-antivirus.md)|
|Actualizaciones de inteligencia de seguridad|Permitir actualizaciones de inteligencia de seguridad en tiempo real basadas en informes de Microsoft MAPS|[Administrar las actualizaciones forzadas basadas en eventos](manage-event-based-updates-microsoft-defender-antivirus.md)|
|Actualizaciones de inteligencia de seguridad|Comprobación de las definiciones de virus y spyware más recientes en el inicio|[Administrar las actualizaciones forzadas basadas en eventos](manage-event-based-updates-microsoft-defender-antivirus.md)|
|Actualizaciones de inteligencia de seguridad|Definición de recursos compartidos de archivos para descargar actualizaciones de inteligencia de seguridad|[Administración de actualizaciones de inteligencia de seguridad y protección antivirus de Microsoft Defender](manage-protection-updates-microsoft-defender-antivirus.md)|
|Actualizaciones de inteligencia de seguridad|Definir el número de días después de los cuales se requiere una actualización de inteligencia de seguridad|[Administrar actualizaciones para puntos finales que están desactualizados](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|Actualizaciones de inteligencia de seguridad|Definir el número de días antes de que las definiciones de spyware se consideren obsoletas|[Administrar actualizaciones para puntos finales que están desactualizados](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|Actualizaciones de inteligencia de seguridad|Definir el número de días antes de que las definiciones de virus se consideren obsoletas|[Administrar actualizaciones para puntos finales que están desactualizados](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|Actualizaciones de inteligencia de seguridad|Definir el orden de los orígenes para descargar las actualizaciones de inteligencia de seguridad|[Administración de actualizaciones de inteligencia de seguridad y protección antivirus de Microsoft Defender](manage-protection-updates-microsoft-defender-antivirus.md)|
|Actualizaciones de inteligencia de seguridad|Inicio de la actualización de inteligencia de seguridad|[Administrar las actualizaciones forzadas basadas en eventos](manage-event-based-updates-microsoft-defender-antivirus.md)|
|Actualizaciones de inteligencia de seguridad|Especificar el día de la semana para comprobar si hay actualizaciones de inteligencia de seguridad|[Administre cuándo deben descargarse y aplicarse las actualizaciones de protección](manage-protection-update-schedule-microsoft-defender-antivirus.md)|
|Actualizaciones de inteligencia de seguridad|Especificar el intervalo para comprobar si hay actualizaciones de inteligencia de seguridad|[Administre cuándo deben descargarse y aplicarse las actualizaciones de protección](manage-protection-update-schedule-microsoft-defender-antivirus.md)|
|Actualizaciones de inteligencia de seguridad|Especificar el tiempo para comprobar si hay actualizaciones de inteligencia de seguridad|[Administre cuándo deben descargarse y aplicarse las actualizaciones de protección](manage-protection-update-schedule-microsoft-defender-antivirus.md)|
|Actualizaciones de inteligencia de seguridad|Activar el examen después de la actualización de Inteligencia de seguridad|[Configuración de exámenes programados para antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|Amenazas|Especificar los niveles de alerta de amenaza en los que no se debe realizar una acción predeterminada cuando se detecte|[Configuración de la corrección para exámenes del Antivirus de Microsoft Defender](configure-remediation-microsoft-defender-antivirus.md)|
|Amenazas|Especificar amenazas en las que no se debe realizar una acción predeterminada cuando se detecte|[Configuración de la corrección para exámenes del Antivirus de Microsoft Defender](configure-remediation-microsoft-defender-antivirus.md)|

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características iOS](ios-configure-features.md)

## <a name="see-also"></a>Vea también

- [Temas de referencia para herramientas de administración y configuración](configuration-management-reference-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
