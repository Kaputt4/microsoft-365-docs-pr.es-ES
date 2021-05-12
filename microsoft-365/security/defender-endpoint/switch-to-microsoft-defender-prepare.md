---
title: 'Cambiar a Microsoft Defender para el punto de conexión: Preparar'
description: Esta es la fase 1, Preparar, para migrar a Microsoft Defender para endpoint.
keywords: migración, Microsoft Defender para Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
ms.topic: article
ms.custom: migrationguides
ms.date: 05/10/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: cdf73ba8b97db06537785dff6e2b3f017d47023d
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327359"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-1-prepare"></a>Cambiar a Microsoft Defender para endpoint- Fase 1: Preparar

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| ![Fase 1: Preparación](images/phase-diagrams/prepare.png)<br/>Fase 1: Preparación | [![Fase 2: Configuración](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Fase 2: Configuración](switch-to-microsoft-defender-setup.md) | [![Fase 3: Incorporación](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[Fase 3: Incorporación](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
|*¡Estás aquí!*| | |

**Bienvenido a la fase de preparación de [cambiar a Microsoft Defender para endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)**. 

Esta fase de migración incluye los siguientes pasos:
1. [Obtener e implementar actualizaciones en los dispositivos de la organización](#get-and-deploy-updates-across-your-organizations-devices)
2. [Obtener Microsoft Defender para endpoint](#get-microsoft-defender-for-endpoint).
3. [Conceder acceso al Centro de seguridad de Microsoft Defender](#grant-access-to-the-microsoft-defender-security-center).
4. [Configurar el proxy de dispositivo y la configuración de conectividad a Internet.](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>Obtener e implementar actualizaciones en los dispositivos de la organización

Como práctica recomendada, mantenga actualizados los dispositivos y los puntos de conexión de la organización. Asegúrese de que la protección de puntos de conexión y la solución antivirus existentes están actualizadas y de que los sistemas operativos y las aplicaciones de su organización también tienen las actualizaciones más recientes. Hacerlo ahora puede ayudar a evitar problemas más adelante a medida que migras a Microsoft Defender para Endpoint y Antivirus de Microsoft Defender.

### <a name="make-sure-your-existing-solution-is-up-to-date"></a>Asegúrese de que la solución existente esté actualizada

Mantenga actualizada la solución de protección de puntos de conexión existente y asegúrese de que los dispositivos de su organización tienen las actualizaciones de seguridad más recientes. 

¿Necesita ayuda? Consulte la documentación del proveedor de soluciones.

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>Asegúrese de que los dispositivos de su organización estén actualizados

¿Necesita ayuda para actualizar los dispositivos de su organización? Vea los siguientes recursos:

|Sistema operativo | Resource |
|:--|:--|
|Windows |[Microsoft Update](https://www.update.microsoft.com) |
|macOS | [Cómo actualizar el software en tu Mac](https://support.apple.com/HT201541)|
|iOS |[Actualizar el iPhone, iPad o iPod touch](https://support.apple.com/HT204204)|
|Android |[Comprobar & actualizar la versión de Android](https://support.google.com/android/answer/7680439) |
|Linux | [Linux 101: actualizar el sistema](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a>Obtener Microsoft Defender para endpoint

Ahora que ha actualizado los dispositivos de su organización, el siguiente paso es obtener Microsoft Defender para Endpoint, asignar licencias y asegurarse de que el servicio está aprovisionado.

1. Compre o pruebe Microsoft Defender para Endpoint hoy mismo. [Inicie una prueba gratuita o solicite una cotización](https://aka.ms/mdatp). 
2. Compruebe que las licencias están aprovisionadas correctamente. [Compruebe el estado de la licencia](/microsoft-365/security/defender-endpoint/production-deployment#check-license-state).
3. Como administrador global o administrador de seguridad, configura la instancia de nube dedicada de Microsoft Defender para Endpoint. Consulte [Configuración del punto de conexión de Microsoft Defender: Configuración del espacio empresarial](/microsoft-365/security/defender-endpoint/production-deployment#tenant-configuration).
4. Si los puntos de conexión (como dispositivos) de su organización usan un proxy para tener acceso a Internet, consulte Configuración de [Microsoft Defender para extremo: Configuración de red](/microsoft-365/security/defender-endpoint/production-deployment#network-configuration).
 
En este momento, está listo para conceder acceso a los administradores de seguridad y operadores de seguridad que usarán el Centro de seguridad de Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 

> [!NOTE]
> En ocasiones, el Centro de seguridad de Microsoft Defender se conoce como el portal de Microsoft Defender para endpoint y se puede obtener acceso a este en [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) . 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Conceder acceso al Centro de seguridad de Microsoft Defender

El Centro de seguridad de Microsoft Defender ( ) es donde tiene acceso y configura las características y [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) capacidades de Microsoft Defender para endpoint. Para obtener más información, vea [Overview of the Microsoft Defender Security Center](use.md).

Los permisos del Centro de seguridad de Microsoft Defender se pueden conceder mediante permisos básicos o control de acceso basado en roles (RBAC). Se recomienda usar RBAC para que tenga un control más detallado sobre los permisos.

1. Planee los roles y permisos para los administradores de seguridad y los operadores de seguridad. Vea [Control de acceso basado en roles](prepare-deployment.md#role-based-access-control).
2. Configurar y configurar RBAC. Se recomienda usar [Intune para](/mem/intune/fundamentals/what-is-intune) configurar RBAC, especialmente si su organización usa una combinación de dispositivos Windows 10, macOS, iOS y Android. Consulta [configurar RBAC con Intune](/mem/intune/fundamentals/role-based-access-control).
    Si su organización requiere un método distinto de Intune, elija una de las siguientes opciones:
    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [Administración de directivas de grupo avanzadas](/microsoft-desktop-optimization-pack/agpm)
    - [Centro de administración de Windows](/windows-server/manage/windows-admin-center/overview)
3. Conceder acceso al Centro de seguridad de Microsoft Defender. (¿Necesita ayuda? Consulte [Manage portal access using RBAC](rbac.md)).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Configurar el proxy de dispositivo y la configuración de conectividad a Internet

Para habilitar la comunicación entre los dispositivos y Microsoft Defender para endpoint, configure la configuración de proxy e Internet. En la tabla siguiente se incluyen vínculos a los recursos que puede usar para configurar el proxy y la configuración de Internet para varios sistemas operativos y capacidades:

|Capacidades  | Sistema operativo | Recursos |
|--|--|--|
|[Detección y respuesta de extremos](overview-endpoint-detection-response.md) (EDR) |- [Windows 10](/windows/release-health/release-information) <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 o posterior](/windows-server/get-started/whats-new-in-windows-server-1803)  |[Configurar el proxy de máquina y la configuración de conectividad a Internet](configure-proxy-internet.md) |
|EDR |- [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Configuración de proxy y conectividad a Internet](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10.13 (Sierra Alta)  |[Microsoft Defender para endpoint en macOS: conexiones de red](microsoft-defender-endpoint-mac.md#network-connections)  |
|[Antivirus de Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md) |- [Windows 10](/windows/release-health/release-information) <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 o posterior](/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) |[Configurar y validar las conexiones de red del Antivirus de Windows Defender](configure-network-connections-microsoft-defender-antivirus.md)<br/> |
|Antivirus |macOS: <br/>- 11.3.1 (Big Sur)<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) |[Microsoft Defender para endpoint en macOS: conexiones de red](microsoft-defender-endpoint-mac.md#network-connections) |
|Antivirus |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS o LTS superior<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Microsoft Defender para endpoint en Linux: conexiones de red](microsoft-defender-endpoint-linux.md#network-connections) |

## <a name="next-step"></a>Paso siguiente

**¡Enhorabuena!** Ha completado la fase **preparar** el [cambio a Microsoft Defender para endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)!

- [Continúe con la configuración de Microsoft Defender para endpoint](switch-to-microsoft-defender-setup.md).
