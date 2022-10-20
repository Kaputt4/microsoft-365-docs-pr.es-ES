---
title: Cambiar a Microsoft Defender para punto de conexión- Preparar
description: Prepárese para cambiar a Microsoft Defender para punto de conexión. Actualice los dispositivos y configure las conexiones de red.
keywords: migración, Microsoft Defender para punto de conexión, procedimientos recomendados
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-migratetomdatp
- highpri
- tier1
ms.topic: conceptual
ms.custom:
- migrationguides
- admindeeplinkDEFENDER
ms.date: 04/01/2022
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
search.appverid: met150
ms.openlocfilehash: 6b32b56cba5d6e45266c9c9cb28c8331a95ca019
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68625861"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-1-prepare"></a>Cambiar a Microsoft Defender para punto de conexión- Fase 1: Preparación

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| ![Fase 1: Preparación.](images/phase-diagrams/prepare.png#lightbox)<br/>Fase 1: Preparación | [![Fase 2: Configuración](images/phase-diagrams/setup.png#lightbox)](switch-to-mde-phase-2.md)<br/>[Fase 2: Configuración](switch-to-mde-phase-2.md) | [![Fase 3: Incorporación](images/phase-diagrams/onboard.png#lightbox)](switch-to-mde-phase-3.md)<br/>[Fase 3: Incorporación](switch-to-mde-phase-3.md) |
|--|--|--|
|*¡Estás aquí!*| | |

**Bienvenido a la fase de preparación del [cambio a Defender para punto de conexión](switch-to-mde-overview.md#the-migration-process)**.

Esta fase de migración incluye los pasos siguientes:

1. [Obtención e implementación de actualizaciones en los dispositivos de la organización](#get-and-deploy-updates-across-your-organizations-devices)
2. [Obtenga Defender para punto de conexión](#get-microsoft-defender-for-endpoint).
3. [Conceda acceso al portal de Microsoft 365 Defender](#grant-access-to-the-microsoft-365-defender-portal).
4. [Configure los valores de proxy de dispositivo y conectividad a Internet](#configure-device-proxy-and-internet-connectivity-settings).

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>Obtención e implementación de actualizaciones en los dispositivos de la organización

Como procedimiento recomendado, mantenga actualizados los dispositivos y puntos de conexión de la organización. Asegúrese de que la solución antivirus y la protección de puntos de conexión existentes están actualizadas y de que los sistemas operativos y las aplicaciones de su organización también tienen las actualizaciones más recientes. Esto ahora puede ayudar a evitar problemas más adelante al migrar a Defender para punto de conexión y Microsoft Defender Antivirus.

### <a name="make-sure-your-existing-solution-is-up-to-date"></a>Asegúrese de que la solución existente está actualizada

Mantenga actualizada la solución de endpoint protection existente y asegúrese de que los dispositivos de su organización tienen las actualizaciones de seguridad más recientes.

¿Necesita ayuda? Consulte la documentación del proveedor de soluciones.

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>Asegúrese de que los dispositivos de su organización estén actualizados

¿Necesita ayuda para actualizar los dispositivos de su organización? Vea los siguientes recursos:

|SO|Recurso|
|---|---|
|Windows|[Microsoft Update](https://www.update.microsoft.com)|
|macOS|[Actualización del software en el Equipo Mac](https://support.apple.com/HT201541)|
|iOS|[Actualizar el iPhone, iPad o iPod touch](https://support.apple.com/HT204204)|
|Android|[Comprobar & actualizar la versión de Android](https://support.google.com/android/answer/7680439)|
|Linux|[Linux 101: actualización del sistema](https://www.linux.com/training-tutorials/linux-101-updating-your-system)|

## <a name="get-microsoft-defender-for-endpoint"></a>Obtener Microsoft Defender para punto de conexión

Ahora que ha actualizado los dispositivos de su organización, el siguiente paso es obtener Defender para punto de conexión, asignar licencias y asegurarse de que el servicio está aprovisionado.

1. Compre o pruebe Defender para punto de conexión hoy mismo. [Inicie una evaluación gratuita o solicite una oferta](https://aka.ms/mdatp).

2. Compruebe que las licencias están aprovisionadas correctamente. [Compruebe el estado de la licencia](production-deployment.md#check-license-state).

3. Configure la instancia de nube dedicada de Defender para punto de conexión. Consulte [Configuración de Defender para punto de conexión: Configuración del inquilino](production-deployment.md#tenant-configuration).

4. Si los puntos de conexión (como los dispositivos) de su organización usan un proxy para acceder a Internet, consulte [Configuración de Defender para punto de conexión: Configuración de red](production-deployment.md#network-configuration).

En este momento, está listo para conceder acceso a los administradores de seguridad y a los operadores de seguridad que usarán el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>.

> [!NOTE]
> A veces, el portal de Microsoft 365 Defender se conoce como portal de Defender para punto de conexión y se puede acceder a él en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">https://security.microsoft.com</a>. El Centro de seguridad de Microsoft Defender anterior (https://securitycenter.windows.com) pronto se redirigirá al portal de Microsoft 365 Defender. Para obtener más información, consulte [Microsoft 365 Defender introducción al portal](portal-overview.md).

## <a name="grant-access-to-the-microsoft-365-defender-portal"></a>Concesión de acceso al portal de Microsoft 365 Defender

El <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a> es donde se accede y se configuran las características y funcionalidades de Defender para punto de conexión. Para obtener más información, consulte [Información general del portal de Microsoft 365 Defender](use.md).

Los permisos para el portal de Microsoft 365 Defender se pueden conceder mediante permisos básicos o control de acceso basado en rol (RBAC). Se recomienda usar RBAC para que tenga un control más pormenorizado sobre los permisos.

1. Planee los roles y permisos para los administradores de seguridad y los operadores de seguridad. Consulte [Control de acceso basado en rol](prepare-deployment.md#role-based-access-control).

2. Configure y configure RBAC. Se recomienda usar [Intune](/mem/intune/fundamentals/what-is-intune) para configurar RBAC, especialmente si su organización usa una combinación de dispositivos Windows 10, macOS, iOS y Android. Consulte [Configuración de RBAC mediante Intune](/mem/intune/fundamentals/role-based-access-control).

    Si su organización requiere un método distinto de Intune, elija una de las siguientes opciones:

    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)

    - [Administración de directivas de grupo avanzadas](/microsoft-desktop-optimization-pack/agpm)
    
    - [Windows Admin Center](/windows-server/manage/windows-admin-center/overview)

3. Conceda acceso al portal de Microsoft 365 Defender. (¿Necesita ayuda? Consulte [Administración del acceso al portal mediante RBAC](rbac.md).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Configuración del proxy de dispositivo y la conectividad a Internet

Para habilitar la comunicación entre los dispositivos y Defender para punto de conexión, configure los valores de proxy e Internet. En la tabla siguiente se incluyen vínculos a los recursos que puede usar para configurar el proxy y la configuración de Internet para varios sistemas operativos y funcionalidades:

|Capacidades|Sistema operativo|Recursos|
|---|---|---|
|[Detección y respuesta de puntos de conexión](overview-endpoint-detection-response.md) (EDR)|[Windows 10](/windows/release-health/release-information) o posterior<br/><br/>Windows Server 2022 <br/><br/>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/><br/>[Windows Server 1803 o posterior](/windows-server/get-started/whats-new-in-windows-server-1803)<br/><br/>[Windows Server 2016*](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/><br/>[Windows Server 2012 R2*](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)|[Configuración del proxy de máquina y la conectividad a Internet](configure-proxy-internet.md)|
|Edr |[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/><br/>[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/><br/>[Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)|[Configuración de proxy y conectividad a Internet](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings)|
|Edr|macOS (consulte [Requisitos del sistema](microsoft-defender-endpoint-mac.md))|[Defender para punto de conexión en macOS: conexiones de red](microsoft-defender-endpoint-mac.md#network-connections)|
|[Antivirus de Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md)|[Windows 10](/windows/release-health/release-information) <br/><br/> [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/><br/> Windows Server 2022 <br/><br/> [Windows Server 1803 o posterior](/windows-server/get-started/whats-new-in-windows-server-1803) <br/><br/> [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)<br/><br/>[Windows Server 2012 R2*](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)|[Configurar y validar las conexiones de red del Antivirus de Windows Defender](configure-network-connections-microsoft-defender-antivirus.md)|
|Antivirus|macOS (consulte [Requisitos del sistema](microsoft-defender-endpoint-mac.md))|[Defender para punto de conexión en macOS: conexiones de red](microsoft-defender-endpoint-mac.md#network-connections)|
|Antivirus|Linux (consulte [Requisitos del sistema](microsoft-defender-endpoint-linux.md#system-requirements))|[Defender para punto de conexión en Linux: conexiones de red](microsoft-defender-endpoint-linux.md#network-connections)|

*Requiere la instalación de la solución moderna y unificada para Windows Server 2012 R2 y 2016. Para obtener más información, vea [Incorporación de servidores Windows al servicio de Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/configure-server-endpoints).

## <a name="next-step"></a>Paso siguiente

**¡Enhorabuena**! Ha completado la fase **de preparación** del [cambio a Defender para punto de conexión](switch-to-mde-overview.md#the-migration-process).

- [Continúe con la configuración de Defender para punto de conexión](switch-to-mde-phase-2.md).
