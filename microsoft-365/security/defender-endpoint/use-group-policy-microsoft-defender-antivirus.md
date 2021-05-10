---
title: Configurar Antivirus de Microsoft Defender con directiva de grupo
description: Obtenga información sobre cómo usar una directiva de grupo para configurar y administrar Antivirus de Microsoft Defender en los puntos de conexión en Microsoft Defender para endpoint.
keywords: directiva de grupo, GPO, configuración, configuración, configuración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/08/2021
ms.reviewer: ksarens, jtoole, pahuijbr
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 74f58959c22313806ebc95aef14e8ccb2d75326b
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302105"
---
# <a name="use-group-policy-settings-to-configure-and-manage-microsoft-defender-antivirus"></a>Usar la configuración de directiva de grupo para configurar y administrar Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Puede usar la [directiva de grupo](/windows/win32/srvnodes/group-policy) para configurar y administrar Antivirus de Microsoft Defender en los puntos de conexión.

## <a name="configure-microsoft-defender-antivirus-using-group-policy"></a>Configurar Antivirus de Microsoft Defender con la directiva de grupo

En general, puede usar el siguiente procedimiento para configurar o cambiar la configuración Antivirus de Microsoft Defender de directiva de grupo:

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.

2. Con el **Editor de administración de directivas de grupo,** vaya a Configuración del **equipo**.

3. Haga clic **en Plantillas administrativas**.

4. Expanda el árbol para **Windows componentes**  >  **Antivirus de Microsoft Defender**.

5. Expanda la sección (denominada  Ubicación en la tabla de este tema) que contiene la configuración que desea configurar, haga doble clic en la configuración para abrirlo y realice cambios en la configuración.

6. [Implemente el GPO actualizado como lo hace normalmente](/windows/win32/srvnodes/group-policy). 

## <a name="group-policy-settings-and-resources"></a>Configuración y recursos de directiva de grupo

En la tabla siguiente de este tema se enumeran las opciones de configuración de directiva de grupo disponibles en Windows 10, versión 1703, y se proporcionan vínculos al tema correspondiente en esta biblioteca de documentación (cuando corresponda). 

> [!TIP]
> Descargue la hoja de cálculo de referencia Configuración directiva de grupo [para Windows 10 de mayo de 2020 (2004).](https://www.microsoft.com/download/101451) Esta hoja de cálculo enumera la configuración de directiva para las configuraciones de equipo y usuario que se incluyen en los archivos de plantilla administrativa entregados para la actualización de mayo de 2020 (2004) para Windows 10 mayo de 2020. Puede configurar hacer referencia a la hoja de cálculo al editar objetos de directiva de grupo.

| Ubicación | Configuración | Artículo |
|:---|:---|:---|
| Interfaz de cliente | Habilitar el modo de interfaz de usuario sin cabeza | [Impedir que los usuarios vean o interactúen con la interfaz Antivirus de Microsoft Defender usuario](prevent-end-user-interaction-microsoft-defender-antivirus.md) |
| Interfaz de cliente | Mostrar texto adicional a los clientes cuando necesitan realizar una acción | [Configurar las notificaciones que aparecen en los puntos de conexión](configure-notifications-microsoft-defender-antivirus.md) |
| Interfaz de cliente | Suprimir todas las notificaciones | [Configurar las notificaciones que aparecen en los puntos de conexión](configure-notifications-microsoft-defender-antivirus.md) |
| Interfaz de cliente | Suprime las notificaciones de reinicio | [Configurar las notificaciones que aparecen en los puntos de conexión](configure-notifications-microsoft-defender-antivirus.md) |
| Exclusiones | Exclusiones de extensión | [Configurar y validar exclusiones en Antivirus de Microsoft Defender exámenes](configure-exclusions-microsoft-defender-antivirus.md) |
| Exclusiones | Exclusiones de ruta de acceso | [Configurar y validar exclusiones en Antivirus de Microsoft Defender exámenes](configure-exclusions-microsoft-defender-antivirus.md) |
| Exclusiones | Exclusiones de procesos | [Configurar y validar exclusiones en Antivirus de Microsoft Defender exámenes](configure-exclusions-microsoft-defender-antivirus.md) | 
| Exclusiones | Desactivar exclusiones automáticas | [Configurar y validar exclusiones en Antivirus de Microsoft Defender exámenes](configure-exclusions-microsoft-defender-antivirus.md) |
| MAPAS | Configurar la característica "Bloquear a primera vista" | [Habilitar bloque a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md) |
| MAPAS | Unirse a Microsoft MAPS | [Habilitar la protección proporcionada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md) |
| MAPAS | Enviar ejemplos de archivos cuando sea necesario realizar análisis adicionales | [Habilitar la protección proporcionada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md) |
| MAPAS | Configurar la invalidación de configuración local para los informes en Microsoft MAPS | [Impedir o permitir que los usuarios modifiquen localmente la configuración de directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| MpEngine | Configurar la comprobación de nube extendida | [Configurar el período de espera de bloqueo en la nube](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) |
| MpEngine | Seleccionar nivel de protección en la nube | [Especificar el nivel de protección proporcionado en la nube](specify-cloud-protection-level-microsoft-defender-antivirus.md) |
| Sistema de inspección de red | Especificar conjuntos de definiciones adicionales para la inspección del tráfico de red | [Especificar conjuntos de definiciones adicionales para la inspección del tráfico de red](specify-additional-definitions-network-traffic-inspection-mdav.md) |
| Sistema de inspección de red | Activar la retirada de definiciones | [Configurar la retirada de definiciones](turn-on-definition-retirement.md)  |
| Sistema de inspección de red | Activar el reconocimiento de protocolos | [Activar el reconocimiento de protocolos](turn-on-protocol-recognition.md)  |
| Cuarentena | Configurar la invalidación de configuración local para la eliminación de elementos de la carpeta cuarentena | [Impedir o permitir que los usuarios modifiquen localmente la configuración de directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Cuarentena | Configurar la eliminación de elementos de la carpeta cuarentena | [Configurar la corrección para Antivirus de Microsoft Defender exámenes](configure-remediation-microsoft-defender-antivirus.md) |
| Protección en tiempo real | Configurar la invalidación de configuración local para la actividad del programa y el archivo de supervisión en el equipo | [Impedir o permitir que los usuarios modifiquen localmente la configuración de directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Protección en tiempo real | Configurar la invalidación de configuración local para la supervisión de la actividad de archivos entrantes y salientes | [Impedir o permitir que los usuarios modifiquen localmente la configuración de directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Protección en tiempo real | Configurar la invalidación de configuración local para examinar todos los archivos y datos adjuntos descargados | [Impedir o permitir que los usuarios modifiquen localmente la configuración de directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Protección en tiempo real | Configurar la invalidación de configuración local para activar la supervisión del comportamiento | [Impedir o permitir que los usuarios modifiquen localmente la configuración de directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Protección en tiempo real | Configurar la invalidación de configuración local para activar la protección en tiempo real | [Impedir o permitir que los usuarios modifiquen localmente la configuración de directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Protección en tiempo real | Definir el tamaño máximo de los archivos y datos adjuntos descargados que se examinarán | [Habilitar y configurar la Antivirus de Microsoft Defender y la supervisión siempre activas](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protección en tiempo real | Supervisar la actividad de archivos y programas en el equipo | [Habilitar y configurar la Antivirus de Microsoft Defender y la supervisión siempre activas](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protección en tiempo real | Examinar todos los archivos y datos adjuntos descargados | [Habilitar y configurar la Antivirus de Microsoft Defender y la supervisión siempre activas](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protección en tiempo real | Desactivar la protección en tiempo real | [Habilitar y configurar la Antivirus de Microsoft Defender y la supervisión siempre activas](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protección en tiempo real | Activar la supervisión del comportamiento | [Habilitar y configurar la Antivirus de Microsoft Defender y la supervisión siempre activas](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protección en tiempo real | Activar el examen de procesos siempre que esté habilitada la protección en tiempo real | [Habilitar y configurar la Antivirus de Microsoft Defender y la supervisión siempre activas](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protección en tiempo real | Activar las notificaciones de escritura por volumen sin procesar | [Habilitar y configurar la Antivirus de Microsoft Defender y la supervisión siempre activas](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protección en tiempo real | Configurar la supervisión para la actividad del programa y los archivos entrantes y salientes | [Habilitar y configurar la Antivirus de Microsoft Defender y la supervisión siempre activas](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Corrección | Configurar la invalidación de configuración local para la hora del día para ejecutar un examen completo programado para completar la corrección | [Impedir o permitir que los usuarios modifiquen localmente la configuración de directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Corrección | Especificar el día de la semana para ejecutar un examen completo programado para completar la corrección | [Configurar exámenes Antivirus de Microsoft Defender programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Corrección | Especificar la hora del día para ejecutar un examen completo programado para completar la corrección | [Configurar exámenes Antivirus de Microsoft Defender programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Generación de informes | Desactivar las notificaciones mejoradas | [Configurar las notificaciones que aparecen en los puntos de conexión](configure-notifications-microsoft-defender-antivirus.md)
| Raíz | Desactivar Antivirus de Microsoft Defender | No se usa (esta configuración debe establecerse en **No configurar para** garantizar que las aplicaciones antivirus de terceros instaladas funcionen correctamente)
| Raíz | Definir direcciones para omitir el servidor proxy | No se usa |
| Raíz | Definir proxy autoconfig (.pac) para conectarse a la red | No se usa |
| Raíz | Definir servidor proxy para conectarse a la red | No se usa |
| Raíz | Configurar el comportamiento de combinación de administradores locales para listas | [Impedir o permitir que los usuarios modifiquen localmente la configuración de directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Raíz | Permitir que el servicio antimalware se inicie con prioridad normal | [Configurar la corrección para Antivirus de Microsoft Defender exámenes](configure-remediation-microsoft-defender-antivirus.md) |
| Raíz | Permitir que el servicio antimalware siga ejecutándose siempre | [Configurar la corrección para Antivirus de Microsoft Defender exámenes](configure-remediation-microsoft-defender-antivirus.md) |
| Raíz | Desactivar la corrección rutinaria | [Configurar la corrección para Antivirus de Microsoft Defender exámenes](configure-remediation-microsoft-defender-antivirus.md) |
| Raíz | Randomize scheduled task times | [Configurar exámenes programados para Antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar | Permitir a los usuarios pausar el examen | [Impedir que los usuarios vean o interactúen con la interfaz Antivirus de Microsoft Defender usuario](prevent-end-user-interaction-microsoft-defender-antivirus.md) (no se admite en Windows 10) |
| Examinar | Compruebe las definiciones de virus y spyware más recientes antes de ejecutar un examen programado | [Administrar las actualizaciones forzadas basadas en eventos](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Examinar | Definir el número de días después de los cuales se fuerza un examen de ponerse al día | [Administrar actualizaciones de puntos de conexión que están des actualizadas](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Examinar | Activar el examen completo de ponerse al día | [Administrar actualizaciones de puntos de conexión que están des actualizadas](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Examinar | Activar el examen rápido de ponerse al día | [Administrar actualizaciones de puntos de conexión que están des actualizadas](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Examinar | Configurar la invalidación de configuración local para el porcentaje máximo de uso de LA CPU | [Impedir o permitir que los usuarios modifiquen localmente la configuración de directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Examinar | Configurar la invalidación de configuración local para el día de examen de programación | [Impedir o permitir que los usuarios modifiquen localmente la configuración de directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Examinar | Configurar la invalidación de configuración local para el tiempo de examen rápido programado | [Impedir o permitir que los usuarios modifiquen localmente la configuración de directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Examinar | Configurar la invalidación de configuración local para el tiempo de examen programado | [Impedir o permitir que los usuarios modifiquen localmente la configuración de directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Examinar | Configurar la invalidación de configuración local para el tipo de examen que se usará para un examen programado | [Impedir o permitir que los usuarios modifiquen localmente la configuración de directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Examinar | Crear un punto de restauración del sistema | [Configurar la corrección para Antivirus de Microsoft Defender exámenes](configure-remediation-microsoft-defender-antivirus.md) |
| Examinar | Activar la eliminación de elementos de la carpeta historial de examen | [Configurar la corrección para Antivirus de Microsoft Defender exámenes](configure-remediation-microsoft-defender-antivirus.md) |
| Examinar | Activar heurística | [Habilitar y configurar la Antivirus de Microsoft Defender y la supervisión siempre activas](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Examinar | Activar el examen de correo electrónico | [Configurar opciones de examen en Antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Activar el examen de puntos de repetición | [Configurar opciones de examen en Antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Ejecutar examen completo en unidades de red asignadas | [Configurar opciones de examen en Antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Examinar archivos de archivo | [Configurar opciones de examen en Antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Examinar archivos de red | [Configurar opciones de examen en Antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Examinar archivos ejecutables empaquetados | [Configurar opciones de examen en Antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Examinar unidades extraíbles | [Configurar opciones de examen en Antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Especificar la profundidad máxima para examinar archivos de archivo | [Configurar opciones de examen en Antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Especificar el porcentaje máximo de uso de CPU durante un examen | [Configurar opciones de examen en Antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Especificar el tamaño máximo de los archivos de archivo que se examinarán | [Configurar opciones de examen en Antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Especificar el día de la semana para ejecutar un examen programado | [Configurar exámenes programados para Antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar | Especificar el intervalo para ejecutar exámenes rápidos por día | [Configurar exámenes programados para Antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar | Especificar el tipo de examen que se usará para un examen programado | [Configurar exámenes programados para Antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar | Especificar la hora de un examen rápido diario | [Configurar exámenes programados para Antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar | Especificar la hora del día para ejecutar un examen programado | [Configurar exámenes programados para Antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar | Iniciar el examen programado solo cuando el equipo está en uso pero no está en uso | [Configurar exámenes programados para Antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Actualizaciones de inteligencia de seguridad | Permitir actualizaciones de inteligencia de seguridad de Microsoft Update | [Administrar las actualizaciones de dispositivos móviles y máquinas virtuales](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| Actualizaciones de inteligencia de seguridad | Permitir actualizaciones de inteligencia de seguridad al ejecutarse con batería | [Administrar las actualizaciones de dispositivos móviles y máquinas virtuales](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| Actualizaciones de inteligencia de seguridad | Permitir que las notificaciones deshabilite informes basados en definiciones en Microsoft MAPS | [Administrar las actualizaciones forzadas basadas en eventos](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Actualizaciones de inteligencia de seguridad | Permitir actualizaciones de inteligencia de seguridad en tiempo real basadas en informes de Microsoft MAPS | [Administrar las actualizaciones forzadas basadas en eventos](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Actualizaciones de inteligencia de seguridad | Buscar las definiciones más recientes de virus y spyware al inicio | [Administrar las actualizaciones forzadas basadas en eventos](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Actualizaciones de inteligencia de seguridad | Definir recursos compartidos de archivos para descargar actualizaciones de inteligencia de seguridad | [Administrar Antivirus de Microsoft Defender de protección e inteligencia de seguridad](manage-protection-updates-microsoft-defender-antivirus.md) |
| Actualizaciones de inteligencia de seguridad | Definir el número de días después de los cuales se requiere una actualización de inteligencia de seguridad de ponerse al día | [Administrar actualizaciones de puntos de conexión que están des actualizadas](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Actualizaciones de inteligencia de seguridad | Definir el número de días antes de que las definiciones de spyware se consideren des actualizadas | [Administrar actualizaciones de puntos de conexión que están des actualizadas](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Actualizaciones de inteligencia de seguridad | Definir el número de días antes de que las definiciones de virus se consideren des actualizadas | [Administrar actualizaciones de puntos de conexión que están des actualizadas](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Actualizaciones de inteligencia de seguridad | Definir el orden de los orígenes para descargar actualizaciones de inteligencia de seguridad | [Administrar Antivirus de Microsoft Defender de protección e inteligencia de seguridad](manage-protection-updates-microsoft-defender-antivirus.md) |
| Actualizaciones de inteligencia de seguridad | Iniciar actualización de inteligencia de seguridad al inicio | [Administrar las actualizaciones forzadas basadas en eventos](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Actualizaciones de inteligencia de seguridad | Especificar el día de la semana para comprobar si hay actualizaciones de inteligencia de seguridad | [Administrar cuándo se deben descargar y aplicar las actualizaciones de protección](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Actualizaciones de inteligencia de seguridad | Especificar el intervalo para comprobar si hay actualizaciones de inteligencia de seguridad | [Administrar cuándo se deben descargar y aplicar las actualizaciones de protección](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Actualizaciones de inteligencia de seguridad | Especificar la hora para comprobar si hay actualizaciones de inteligencia de seguridad | [Administrar cuándo se deben descargar y aplicar las actualizaciones de protección](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Actualizaciones de inteligencia de seguridad | Activar el examen después de la actualización de inteligencia de seguridad | [Configurar exámenes programados para Antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Amenazas | Especificar niveles de alerta de amenazas en los que no se debe realizar ninguna acción predeterminada cuando se detecte | [Configurar la corrección para Antivirus de Microsoft Defender exámenes](configure-remediation-microsoft-defender-antivirus.md) |
| Amenazas | Especificar amenazas en las que no se debe realizar una acción predeterminada cuando se detecte | [Configurar la corrección para Antivirus de Microsoft Defender exámenes](configure-remediation-microsoft-defender-antivirus.md) |

## <a name="see-also"></a>Vea también

- [Temas de referencia para herramientas de administración y configuración](configuration-management-reference-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
