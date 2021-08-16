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
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.topic: article
ms.custom: migrationguides
ms.date: 08/11/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: a9202cf5da326bd573e85459591f408b04ddad03
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "58257735"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-1-prepare"></a>Cambiar a Microsoft Defender para endpoint- Fase 1: Preparar

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| ![Fase 1: Preparación](images/phase-diagrams/prepare.png)<br/>Fase 1: Preparación | [![Fase 2: Configuración](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Fase 2: Configuración](switch-to-microsoft-defender-setup.md) | [![Fase 3: Incorporación](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[Fase 3: Incorporación](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
|*¡Estás aquí!*| | |

**Bienvenido a la fase Preparar de [cambiar a Defender para endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)**. 

Esta fase de migración incluye los siguientes pasos:

1. [Obtener e implementar actualizaciones en los dispositivos de la organización](#get-and-deploy-updates-across-your-organizations-devices)
2. [Obtener Defender para endpoint](#get-microsoft-defender-for-endpoint).
3. [Conceder acceso al portal de Microsoft 365 Defender](#grant-access-to-the-microsoft-365-defender-portal).
4. [Configurar el proxy de dispositivo y la configuración de conectividad a Internet.](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>Obtener e implementar actualizaciones en los dispositivos de la organización

Como práctica recomendada, mantenga actualizados los dispositivos y los puntos de conexión de la organización. Asegúrese de que la protección de puntos de conexión y la solución antivirus existentes están actualizadas y de que los sistemas operativos y las aplicaciones de su organización también tienen las actualizaciones más recientes. Hacer esto ahora puede ayudar a evitar problemas más adelante a medida que migra a Defender para endpoint y Antivirus de Microsoft Defender.

### <a name="make-sure-your-existing-solution-is-up-to-date"></a>Asegúrese de que la solución existente esté actualizada

Mantenga actualizada la solución de protección de puntos de conexión existente y asegúrese de que los dispositivos de su organización tienen las actualizaciones de seguridad más recientes. 

¿Necesita ayuda? Consulte la documentación del proveedor de soluciones.

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>Asegúrese de que los dispositivos de su organización estén actualizados

¿Necesita ayuda para actualizar los dispositivos de su organización? Vea los siguientes recursos:

|SO | Recurso |
|:--|:--|
|Windows |[Microsoft Update](https://www.update.microsoft.com) |
|macOS | [Cómo actualizar el software en tu Mac](https://support.apple.com/HT201541)|
|iOS |[Actualizar el iPhone, iPad o iPod touch](https://support.apple.com/HT204204)|
|Android |[Comprobar & actualizar la versión de Android](https://support.google.com/android/answer/7680439) |
|Linux | [Linux 101: actualizar el sistema](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a>Obtener Microsoft Defender para endpoint

Ahora que ha actualizado los dispositivos de su organización, el siguiente paso es obtener Defender for Endpoint, asignar licencias y asegurarse de que el servicio está aprovisionado.

1. Compre o pruebe Defender for Endpoint hoy mismo. [Inicie una prueba gratuita o solicite una cotización](https://aka.ms/mdatp). 

2. Compruebe que las licencias están aprovisionadas correctamente. [Compruebe el estado de la licencia](production-deployment.md#check-license-state).

3. Configura la instancia de nube dedicada de Defender para Endpoint. Vea [Defender for Endpoint setup: Tenant configuration](production-deployment.md#tenant-configuration).

4. Si los puntos de conexión (como dispositivos) de su organización usan un proxy para tener acceso a Internet, vea Configuración de defender para puntos de [conexión: Configuración de red](production-deployment.md#network-configuration).
 
En este punto, está listo para conceder acceso a los administradores de seguridad y operadores de seguridad que usarán el portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ). 

> [!NOTE]
> El Microsoft 365 Defender se conoce a veces como el portal de Defender para endpoint y se puede obtener acceso a este en [https://security.microsoft.com](https://security.microsoft.com) . The former Centro de seguridad de Microsoft Defender ( https://securitycenter.windows.com) will soon redirect to the Microsoft 365 Defender portal. Para obtener más información, [vea Microsoft 365 Defender información general del portal](portal-overview.md).

## <a name="grant-access-to-the-microsoft-365-defender-portal"></a>Conceder acceso al portal de Microsoft 365 Defender web

El Microsoft 365 Defender web ( ) es donde se accede y se configuran las características y capacidades [https://security.microsoft.com](https://security.microsoft.com) de Defender para endpoint. Para obtener más información, vea [Overview of the Microsoft 365 Defender portal](use.md).

Los permisos del portal Microsoft 365 Defender pueden concederse mediante permisos básicos o control de acceso basado en roles (RBAC). Se recomienda usar RBAC para que tenga un control más detallado sobre los permisos.

1. Planee los roles y permisos para los administradores de seguridad y los operadores de seguridad. Vea [Control de acceso basado en roles](prepare-deployment.md#role-based-access-control).

2. Configurar y configurar RBAC. Se recomienda usar [Intune para](/mem/intune/fundamentals/what-is-intune) configurar RBAC, especialmente si su organización usa una combinación de dispositivos Windows 10, macOS, iOS y Android. Consulta [configurar RBAC con Intune](/mem/intune/fundamentals/role-based-access-control).

    Si su organización requiere un método distinto de Intune, elija una de las siguientes opciones:

    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [Administración de directivas de grupo avanzadas](/microsoft-desktop-optimization-pack/agpm)
    - [Windows Centro de administración](/windows-server/manage/windows-admin-center/overview)

3. Conceda acceso al portal de Microsoft 365 Defender web. (¿Necesita ayuda? Consulte [Manage portal access using RBAC](rbac.md)).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Configurar el proxy de dispositivo y la configuración de conectividad a Internet

Para habilitar la comunicación entre los dispositivos y Defender para endpoint, configure la configuración de proxy e Internet. En la tabla siguiente se incluyen vínculos a los recursos que puede usar para configurar el proxy y la configuración de Internet para varios sistemas operativos y capacidades:

| Capacidades  | Sistema operativo | Recursos |
|:--|:--|:--|
| [Detección y respuesta de extremos](overview-endpoint-detection-response.md) (EDR) | [Windows 10](/windows/release-health/release-information) <br/>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>[Windows Server 1803 o posterior](/windows-server/get-started/whats-new-in-windows-server-1803)  | [Configurar el proxy de máquina y la configuración de conectividad a Internet](configure-proxy-internet.md) |
| EDR | [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>[Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Configuración de proxy y conectividad a Internet](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
| EDR  | macOS: 11.3.1 (Big Sur); 10.15 (Catalina); 10.14 (Mojave)   | [Defender para endpoint en macOS: conexiones de red](microsoft-defender-endpoint-mac.md#network-connections)  |
| [Antivirus de Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md) | [Windows 10](/windows/release-health/release-information) <br/>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>[Windows Server 1803 o posterior](/windows-server/get-started/whats-new-in-windows-server-1803) <br/>[Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) | [Configurar y validar las conexiones de red del Antivirus de Windows Defender](configure-network-connections-microsoft-defender-antivirus.md) |
| Antivirus | macOS: 11.3.1 (Big Sur); 10.15 (Catalina); 10.14 (Mojave) | [Defender para endpoint en macOS: conexiones de red](microsoft-defender-endpoint-mac.md#network-connections) |
| Antivirus | Linux: RHEL 7.2+; CentOS Linux 7.2+; Ubuntu 16 LTS o LTS superior; SLES 12+; Debian 9+; Oracle Linux 7.2 | [Defender para endpoint en Linux: conexiones de red](microsoft-defender-endpoint-linux.md#network-connections) |

## <a name="next-step"></a>Paso siguiente

**¡Enhorabuena!** Ha completado la fase **de preparación** de cambiar a Defender [para endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)!

- [Continúe con la configuración de Defender para Endpoint](switch-to-microsoft-defender-setup.md).
